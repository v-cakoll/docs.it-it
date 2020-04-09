---
title: 'Eventi del dominio: progettazione e implementazione'
description: Architettura di Microservizi .NET per applicazioni .NET in contenitori | Ottenere un quadro dettagliato degli eventi di dominio, un concetto chiave per stabilire la comunicazione tra le aggregazioni.
ms.date: 10/08/2018
ms.openlocfilehash: e03abba66945a6434f6a81eaa9f50d53998f346c
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988716"
---
# <a name="domain-events-design-and-implementation"></a>Eventi del dominio: progettazione e implementazione

Usare gli eventi del dominio per implementare in modo esplicito gli effetti collaterali delle modifiche all'interno del dominio. In altre parole, e con riferimento alla terminologia DDD, usare gli eventi del dominio per implementare in modo esplicito gli effetti collaterali tra più aggregazioni. Facoltativamente per migliorare la scalabilità e ridurre l'impatto sui blocchi di database, usare la coerenza finale tra le aggregazioni all'interno dello stesso dominio.

## <a name="what-is-a-domain-event"></a>Che cos'è un evento del dominio?

Un evento è qualcosa che si è verificato in passato. Un evento di dominio è qualcosa che si verifica nel dominio e che deve essere notificato ad altri elementi dello stesso dominio (in-process). In genere tali elementi reagiscono in qualche modo all'evento.

Un vantaggio importante degli eventi di dominio è che gli effetti collaterali possono essere espressi in modo esplicito.

Ad esempio, se si sta usando Entity Framework e deve esistere una reazione a un evento, probabilmente si scriverà codice per tutto ciò che è necessario per attivare l'evento. In questo modo la regola viene accoppiata implicitamente al codice e sarà necessario verificare nel codice che la regola venga implementata.

D'altra parte, l'uso degli eventi di dominio rende il concetto esplicito perché sono presenti un elemento `DomainEvent` e almeno un elemento `DomainEventHandler`.

Ad esempio, quando viene creato un ordine nell'applicazione eShopOnContainer, l'utente diventa un acquirente, quindi viene generato un evento `OrderStartedDomainEvent` che viene gestito in `ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler`, di conseguenza il concetto sottostante è evidente.

In sostanza, gli eventi di dominio consentono di esprimere esplicitamente le regole di dominio, in base al linguaggio comune offerto dagli esperti del dominio. Gli eventi di dominio consentono anche una migliore separazione delle problematiche tra le classi all'interno dello stesso dominio.

È importante garantire che, proprio come in una transazione di database, vengano completate correttamente tutte le operazioni correlate a un evento di dominio oppure nessuna di esse.

Gli eventi di dominio sono simili agli eventi di tipo messaggistica, con una differenza importante. Con la messaggistica reale, l'accodamento di messaggi, i broker di messaggi o un bus di servizio che usa il protocollo AMQP, un messaggio viene sempre inviato in modo asincrono e trasferito tra processi e computer. Questo approccio è utile per l'integrazione di più contesti delimitati, microservizi o persino applicazioni differenti. Tuttavia, con gli eventi del dominio si vuole generare un evento dall'operazione di dominio attualmente in esecuzione, facendo in modo che tutti gli effetti collaterali si verifichino all'interno dello stesso dominio.

Gli eventi del dominio e i relativi effetti collaterali, ossia le azioni attivate dopo l'elaborazione da parte dei gestori di eventi, devono verificarsi quasi immediatamente, in genere durante il processo, e all'interno dello stesso dominio. Gli eventi del dominio possono quindi essere sincroni o asincroni. Gli eventi di integrazione, invece, devono essere sempre asincroni.

## <a name="domain-events-versus-integration-events"></a>Confronto tra eventi del dominio ed eventi di integrazione

Da un punto di vista semantico gli eventi del dominio e quelli di integrazione si equivalgono, ovvero sono notifiche di un evento che si è appena verificato. Tuttavia, la relativa implementazione deve essere diversa. Gli eventi del dominio non sono altro che messaggi inviati al dispatcher di eventi del dominio, eventualmente implementabile come mediatore in memoria in base a un contenitore IoC o a qualsiasi altro metodo.

Al contrario, lo scopo degli eventi di integrazione è propagare le transazioni e gli aggiornamenti di cui è stato eseguito il commit in altri sottosistemi, indipendentemente se si tratti di altri microservizi, contesti delimitati o persino di applicazioni esterne. Tali eventi devono quindi verificarsi solo se l'entità è stata salvata in modo permanente. In caso contrario, è come se tutta l'operazione non fosse mai stata eseguita.

Come indicato in precedenza, gli eventi di integrazione devono essere basati sulla comunicazione asincrona tra più microservizi (altri contesti delimitati) o persino applicazioni/sistemi esterni.

Di conseguenza, l'interfaccia del bus di eventi richiede un'infrastruttura che consenta la comunicazione tra processi distribuita tra servizi potenzialmente remoti. Può essere basata su un bus di servizio commerciale, sulle code, su un database condiviso usato come cassetta postale o qualsiasi altro sistema di messaggistica distribuito e preferibilmente di tipo push.

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a>Eventi del dominio come modalità consigliata per attivare effetti collaterali tra più aggregazioni all'interno dello stesso dominio

Se l'esecuzione di un comando correlato a un'istanza di aggregazione richiede l'esecuzione di regole di dominio aggiuntive su una o più aggregazioni aggiuntive, è necessario progettare e implementare questi effetti collaterali in modo che vengano attivati dagli eventi del dominio. Come illustrato nella figura 7-14 e, in base a uno dei principali casi d'uso, un evento di dominio deve essere usato per propagare le modifiche dello stato tra più aggregazioni all'interno dello stesso modello di dominio.

![Diagramma che mostra un evento di dominio che controlla i dati in un'aggregazione Buyer.Diagram showing a domain event controlling data to a Buyer aggregate.](./media/domain-events-design-implementation/domain-model-ordering-microservice.png)

**Figura 7-14**. Eventi del dominio per garantire la coerenza tra più aggregazioni all'interno dello stesso dominio

Nella figura 7-14 viene illustrato come la coerenza tra le aggregazioni viene ottenuta dagli eventi di dominio. Quando l'utente avvia un ordine, `OrderStarted` Order Aggregate invia un evento di dominio. L'evento di dominio OrderStarted viene gestito dall'aggregazione acquirente per creare un oggetto Buyer nel microservizio di ordinazione, in base alle informazioni utente originali del microservizio di identità (con le informazioni fornite nel comando CreateOrder).

In alternativa, la radice di aggregazione può avere una sottoscrizione per gli eventi generati dai membri delle relative aggregazioni (entità figlio). Ad esempio, ogni entità figlio OrderItem può generare un evento quando il prezzo dell'articolo è superiore a un importo specifico o quando la quantità di articoli di prodotto è troppo elevata. La radice di aggregazione può quindi ricevere questi eventi ed eseguire un'aggregazione o un calcolo globale.

È importante comprendere che questa comunicazione basata su eventi non viene implementata direttamente all'interno delle aggregazioni, ma è necessario implementare i gestori di eventi del dominio.

La gestione degli eventi del dominio avviene a livello di applicazione. Il livello del modello di dominio deve essere incentrato solo sulla logica di dominio, un aspetto noto agli esperti di dominio, non sull'infrastruttura dell'applicazione, come i gestori e le azioni di persistenza degli effetti collaterali che usano i repository. Pertanto, il livello dell'applicazione è quello in cui i gestori di eventi del dominio attivano azioni quando viene generato un evento di dominio.

Gli eventi del dominio possono essere usati anche per attivare un numero qualsiasi di azioni di applicazioni e, ancor più importante, devono essere aperti ad aumentarle in futuro in modo disgiunto. Ad esempio, quando l'ordine viene avviato è possibile pubblicare un evento del dominio per propagare queste informazioni ad altre aggregazioni o per generare azioni di applicazioni, come le notifiche.

Il punto chiave è il numero aperto di azioni da eseguire al verificarsi di un evento del dominio. Con il tempo le azioni e le regole nel dominio e nell'applicazione aumenteranno. La complessità o il numero di azioni di effetto collaterale quando accade qualcosa aumenterà, ma se `new`il codice è stato accoppiato con "colla" (vale a dire, la creazione di oggetti specifici con ), quindi ogni volta che è necessario aggiungere una nuova azione sarebbe anche necessario modificare il codice di lavoro e testato.

Questa modifica può generare nuovi bug e tale approccio non è conforme al [principio aperto/chiuso](https://en.wikipedia.org/wiki/Open/closed_principle) di [SOLID](https://en.wikipedia.org/wiki/SOLID). Come se non bastasse, la classe originale che orchestra le operazioni aumenterebbe sempre di più, contrariamente al [principio di singola responsabilità (Single Responsibility Principle, SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).

Se invece si usano gli eventi del dominio, è possibile creare un'implementazione con granularità fine disgiunta separando le responsabilità tramite questo approccio:

1. Inviare un comando, ad esempio CreateOrder.
2. Ricevere il comando in un gestore di comandi.
   - Eseguire una singola transazione di aggregazione.
   - (Facoltativo) Generare eventi del dominio per gli effetti collaterali, ad esempio OrderStartedDomainEvent.
3. Gestire gli eventi del dominio (all'interno del processo corrente) che eseguiranno un numero aperto di effetti collaterali in più aggregazioni o azioni di applicazioni. Ad esempio:
   - Verificare o creare l'acquirente e la modalità di pagamento.
   - Creare e inviare un evento di integrazione correlato al bus di eventi per propagare gli stati tra i microservizi o attivare azioni esterne, come l'invio di un messaggio di posta elettronica all'acquirente.
   - Gestire gli altri effetti collaterali.

Come illustrato nella figura 7-15, a partire dallo stesso evento di dominio è possibile gestire più azioni relative ad altre aggregazioni nel dominio o azioni di applicazioni aggiuntive che è necessario eseguire tra i microservizi che si connettono con gli eventi di integrazione e il bus di eventi.

![Diagramma che mostra un evento di dominio che passa dati a diversi gestori eventi.](./media/domain-events-design-implementation/aggregate-domain-event-handlers.png)

**Figura 7-15**. Gestione di più azioni per ogni dominio

Per lo stesso evento possono essere presenti diversi gestori nel livello dell'applicazione, un gestore può risolvere la coerenza tra aggregazioni, un altro può pubblicare un evento di integrazione in modo che possa essere usato da altri microservizi. I gestori eventi sono in genere nel livello dell'applicazione, perché si useranno oggetti dell'infrastruttura come repository o un'API dell'applicazione per il comportamento del microservizio. In questo senso, i gestori di eventi sono simili ai gestori di comandi poiché entrambi fanno parte del livello dell'applicazione. La differenza importante è che un comando deve essere elaborato una sola volta. Un evento del dominio può essere elaborato zero o *n* volte perché può essere ricevuto da più ricevitori o gestori dell'evento con uno scopo diverso per ogni gestore.

La presenza di un numero aperto di gestori per evento di dominio consente di aggiungere tutte le regole di dominio necessarie, senza influire sul codice corrente. Ad esempio, implementare la regola di business seguente può essere facile come aggiungere alcuni gestori di eventi o anche uno solo:

> Quando la quantità totale acquistata da un cliente nello store, con qualsiasi numero di ordini, supera $ 6.000, applicare uno sconto del 10% per ogni nuovo ordine e notificare al cliente questo sconto per gli ordini futuri con un messaggio di posta elettronica.

## <a name="implement-domain-events"></a>Implementare eventi di dominio

In C# un evento del dominio è semplicemente una classe o una struttura di dati, come un DTO (Data Transfer Object), con tutte le informazioni correlate all'evento che si è appena verificato nel dominio, come illustrato nell'esempio seguente:

```csharp
public class OrderStartedDomainEvent : INotification
{
    public string UserId { get; }
    public int CardTypeId { get; }
    public string CardNumber { get; }
    public string CardSecurityNumber { get; }
    public string CardHolderName { get; }
    public DateTime CardExpiration { get; }
    public Order Order { get; }

    public OrderStartedDomainEvent(Order order,
                                   int cardTypeId, string cardNumber,
                                   string cardSecurityNumber, string cardHolderName,
                                   DateTime cardExpiration)
    {
        Order = order;
        CardTypeId = cardTypeId;
        CardNumber = cardNumber;
        CardSecurityNumber = cardSecurityNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
    }
}
```

Si tratta essenzialmente di una classe che contiene tutti i dati relativi all'evento OrderStarted.

Nel linguaggio comune del dominio, poiché un evento è qualcosa che si è verificato in passato, il nome della classe dell'evento deve essere rappresentato con un verbo al passato, ad esempio OrderStartedDomainEvent oppure OrderShippedDomainEvent. Questa è la modalità di implementazione dell'evento di dominio nel microservizio per gli ordini in eShopOnContainers.

Come notato in precedenza, una caratteristica importante degli eventi è che, poiché un evento è qualcosa che si è verificato in passato, non deve variare. Di conseguenza la classe deve essere non modificabile. Nel codice precedente le proprietà sono di sola lettura. Non c'è alcun modo di aggiornare l'oggetto, è possibile solo impostarne i valori durante la creazione.

È importante sottolineare qui che se gli eventi di dominio dovessero essere gestiti in modo asincrono, utilizzando una coda che richiedeva la serializzazione e la deserializzazione degli oggetti evento, le proprietà dovrebbero essere "private set" anziché di sola lettura, in modo che il deserializzatore sarebbe in grado di assegnare i valori al momento della dequequequesing. Ciò non è un problema nel microservizio degli ordini, dal momento che la pubblicazione/sottoscrizione dell'evento di dominio viene implementata in modo sincrono tramite MediatR.

### <a name="raise-domain-events"></a>Generare eventi di dominio

La domanda successiva è come generare un evento del dominio in modo che venga ricevuto dai gestori di eventi correlati. Sono disponibili più approcci.

In origine Udi Dahan ha proposto, ad esempio in diversi post correlati come [Domain Events – Take 2](http://udidahan.com/2008/08/25/domain-events-take-2/) (Eventi del dominio - Parte 2), di usare una classe statica per la gestione e la generazione di eventi. Potrebbe trattarsi di una classe statica denominata DomainEvents che genera immediatamente eventi di dominio al momento della chiamata, usando una sintassi come `DomainEvents.Raise(Event myEvent)`. Jimmy Bogard ha scritto un post di blog, [Strengthening your domain: Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/) (Rafforzamento del dominio: eventi del dominio), in cui consiglia un approccio simile.

Tuttavia, quando la classe di eventi del dominio è statica, esegue anche immediatamente l'invio ai gestori. I test e il debug risultano quindi più difficili perché i gestori di eventi con la logica degli effetti collaterali vengono eseguiti immediatamente dopo la generazione dell'evento. Quando si eseguono i test e il debug, è possibile concentrarsi solo su ciò che accade nelle classi di aggregazione correnti e non essere reindirizzati improvvisamente ad altri gestori di eventi per gli effetti collaterali correlati ad altre aggregazioni o alla logica dell'applicazione. Per questo motivo sono stati sviluppati altri approcci, come illustrato nella sezione successiva.

#### <a name="the-deferred-approach-to-raise-and-dispatch-events"></a>Approccio posticipato per la generazione e l'invio di eventi

Anziché eseguire immediatamente l'invio a un gestore di eventi del dominio, un approccio migliore consiste nell'aggiungere gli eventi del dominio a una raccolta e inviare questi eventi *immediatamente prima* o *immediatamente* *dopo* il commit della transazione, come con SaveChanges in Entity Framework. Questo approccio è stato descritto da Jimmy Bogard in questo post [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/) (Un pattern migliore per gli eventi del dominio)

È importante decidere se inviare gli eventi del dominio immediatamente prima o dopo il commit della transazione perché questa scelta determina se gli effetti collaterali verranno inclusi nella stessa transazione o in transazioni diverse. Nel secondo caso è necessario gestire la coerenza finale tra più aggregazioni. Questo argomento verrà illustrato nella sezione successiva.

L'approccio posticipato è quello usato nell'applicazione eShopOnContainers. Prima si aggiungono gli eventi che si verificano nelle entità in una raccolta o in un elenco di eventi per ogni entità. Questo elenco deve far parte dell'oggetto entità o, ancor meglio, della classe base dell'entità, come illustrato nell'esempio seguente della classe base Entity:

```csharp
public abstract class Entity
{
     //...
     private List<INotification> _domainEvents;
     public List<INotification> DomainEvents => _domainEvents;

     public void AddDomainEvent(INotification eventItem)
     {
         _domainEvents = _domainEvents ?? new List<INotification>();
         _domainEvents.Add(eventItem);
     }

     public void RemoveDomainEvent(INotification eventItem)
     {
         _domainEvents?.Remove(eventItem);
     }
     //... Additional code
}
```

Per generare un evento, è sufficiente aggiungerlo alla raccolta di eventi dal codice in qualsiasi metodo dell'entità aggregate-root.

Nel codice seguente, parte di [Order aggregate-root in eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) (Ordinare aggregate-root in eShopOnContainers), viene illustrato un esempio:

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
                                                          cardTypeId, cardNumber,
                                                          cardSecurityNumber,
                                                          cardHolderName,
                                                          cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

Si noti che l'unica operazione che il metodo AddDomainEvent sta eseguendo è l'aggiunta di un evento all'elenco. Non viene inviato alcun evento e non viene richiamato nessun gestore dell'evento.

In effetti si vuole inviare gli eventi in un secondo momento, al momento del commit della transazione nel database. Se si usa Entity Framework Core, ciò significa nel metodo SaveChanges dell'oggetto DbContext di Entity Framework, come illustrato nel codice seguente:

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<bool> SaveEntitiesAsync(CancellationToken cancellationToken = default(CancellationToken))
    {
        // Dispatch Domain Events collection.
        // Choices:
        // A) Right BEFORE committing data (EF SaveChanges) into the DB. This makes
        // a single transaction including side effects from the domain event
        // handlers that are using the same DbContext with Scope lifetime
        // B) Right AFTER committing data (EF SaveChanges) into the DB. This makes
        // multiple transactions. You will need to handle eventual consistency and
        // compensatory actions in case of failures.
        await _mediator.DispatchDomainEventsAsync(this);

        // After this line runs, all the changes (from the Command Handler and Domain
        // event handlers) performed through the DbContext will be committed
        var result = await base.SaveChangesAsync();
    }
}
```

Con questo codice si inviano gli eventi dell'entità ai rispettivi gestori di eventi.

Il risultato complessivo è la separazione tra la generazione di un evento del dominio (una semplice aggiunta in un elenco in memoria) e l'invio a un gestore dell'evento. Inoltre, a seconda del tipo di dispatcher in uso, si possono inviare gli eventi in modo sincrono o asincrono.

Tenere presente che in questo contesto i limiti transazionali hanno un ruolo importante. Questo approccio può funzionare bene se l'unità di lavoro e la transazione possono estendersi su più aggregazioni, come quando si usa Entity Framework Core e un database relazionale. Se tuttavia la transazione non può estendersi sulle aggregazioni, ad esempio quando si usa un database NoSQL come Azure CosmosDB, è necessario implementare passaggi aggiuntivi per ottenere la coerenza. Questo è un altro motivo per cui il mancato riconoscimento della persistenza non è universale, ma dipende dal sistema di archiviazione in uso.

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a>Confronto tra singola transazione tra le aggregazioni e coerenza finale tra le aggregazioni

Una questione controversa è se eseguire una singola transazione tra le aggregazioni o usare la coerenza finale tra queste aggregazioni. Molti autori di documenti sul modello DDD, come Eric Evans e Vaughn Vernon, sostengono la regola che una transazione corrisponde a un'aggregazione e pertanto sostengono la coerenza finale tra le aggregazioni. Ad esempio, nel libro *Domain-Driven Design*, Eric Evans afferma il concetto seguente:

> Non è previsto che una regola che si estende sulle aggregazioni venga aggiornata in ogni momento. Tramite l'elaborazione degli eventi, l'elaborazione batch o altri meccanismi di aggiornamento, è possibile risolvere le altre dipendenze in un determinato periodo di tempo. (pagina 128)

Vaughn Vernon dice quanto segue in [Effective Aggregate Design. Parte II: Rendere gli aggregati insieme](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):

> Pertanto, se l'esecuzione di un comando in un'istanza di aggregazione richiede \[l'esecuzione di regole di business aggiuntive su una o più aggregazioni, utilizzare la coerenza finale... \] Esiste un modo pratico per supportare la coerenza finale in un modello DDD. Un metodo di aggregazione pubblica un evento del dominio che viene recapitato in tempo a uno o più sottoscrittori asincroni.

Questa spiegazione logica si basa sull'adozione di transazioni con granularità fine anziché su transazioni che si estendono su molte aggregazioni o entità. L'idea è che, nel secondo caso, il numero di blocchi di database sarà notevole nelle applicazioni su larga scala con esigenze di scalabilità. Accettare il fatto che le applicazioni con scalabilità elevata non necessitano di una coerenza transazionale immediata tra più aggregazioni consente di accettare il concetto di coerenza finale. Le modifiche atomiche spesso non sono necessarie per l'azienda e, in ogni caso, è responsabilità degli esperti di dominio indicare se operazioni specifiche necessitano di transazioni atomiche. Se un'operazione richiede sempre una transazione atomica tra più aggregazioni, ci si potrebbe chiedere se l'aggregazione deve essere di dimensione maggiore o non è stata progettata correttamente.

Tuttavia, altri sviluppatori e progettisti come Jimmy Bogard concordano sull'estensione di una singola transazione tra diverse aggregazioni, ma solo quando queste aggregazioni aggiuntive sono correlate agli effetti collaterali per lo stesso comando originale. Ad esempio, in [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/) (Un pattern migliore per gli eventi del dominio) Bogard afferma il concetto seguente:

> In genere, si desidera che gli effetti collaterali di un evento di dominio si verifichino \[all'interno della stessa transazione logica, ma non necessariamente nello stesso ambito di generazione dell'evento di dominio ... \] Appena prima di eseguire il commit della transazione, inviamo i nostri eventi ai rispettivi gestori.

Se si inviano gli eventi del dominio immediatamente *prima* del commit della transazione originale, si vuole che gli effetti collaterali di questi eventi vengano inclusi nella stessa transazione. Ad esempio, se il metodo SaveChanges dell'oggetto DbContext di Entity Framework presenta un errore, la transazione eseguirà il rollback di tutte le modifiche, incluso il risultato di tutte le operazioni degli effetti collaterali implementate dai rispettivi gestori di eventi del dominio. Ciò avviene perché l'ambito della vita dell'oggetto DbContext viene definito come "con ambito" per impostazione predefinita. Pertanto, l'oggetto DbContext viene condiviso tra più oggetti del repository di cui viene creata un'istanza all'interno della stesso grafo di oggetto o ambito. Questo coincide con l'ambito HttpRequest quando si sviluppano app MVC o API Web.

Effettivamente entrambi gli approcci, la singola transazione atomica e la coerenza finale, possono essere corretti. Dipende molto dai requisiti aziendali e del dominio e dalle indicazioni degli esperti del dominio. Dipende anche dalla scalabilità necessaria per il servizio perché le transazioni più granulari hanno un impatto minore sui blocchi di database. Dipende anche dall'investimento sul codice che si è disposti a fare perché la coerenza finale richiede codice più complesso per rilevare possibili incoerenze tra le aggregazioni e la necessità di implementare azioni di compensazione. Tenere in considerazione che se si esegue il commit delle modifiche nell'aggregazione originale e, successivamente, quando gli eventi vengono inviati, si verifica un problema e i gestori di eventi non possono eseguire il commit dei relativi effetti collaterali, si verificheranno incoerenze tra le aggregazioni.

Un modo per consentire azioni di compensazione consiste nell'archiviare gli eventi del dominio in tabelle di database aggiuntive in modo che possano far parte della transazione originale. Successivamente è possibile usare un processo batch che rilevi le incoerenze ed esegua azioni di compensazione confrontando l'elenco di eventi con lo stato corrente delle aggregazioni. Le azioni di compensazione rientrano in un argomento complesso che richiederà un'analisi approfondita in prima persona e una discussione con l'utente del business e gli esperti di dominio.

In ogni caso è possibile scegliere l'approccio necessario. L'approccio posticipato iniziale, che genera gli eventi prima del commit per usare una singola transazione, è l'approccio più semplice quando si usa Entity Framework Core e un database relazionale. È più facile da implementare e valido in molti casi aziendali. È anche l'approccio adottato nel microservizio per gli ordini in eShopOnContainers.

Come si inviano effettivamente gli eventi ai rispettivi gestori di eventi? Che cos'è l'oggetto `_mediator` illustrato nell'esempio precedente? Ha a che fare con le tecniche e gli artefatti che si usano per eseguire il mapping tra gli eventi e i rispettivi gestori di eventi.

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a>Il dispatcher di eventi del dominio: mapping dagli eventi ai gestori di eventi

Una volta che si è in grado di inviare o pubblicare gli eventi, è necessario un tipo di elemento che pubblicherà l'evento in modo che ogni gestore correlato possa ricevere ed elaborare gli effetti collaterali in base a questo evento.

Un approccio è un sistema di messaggistica reale o anche un bus di eventi, possibilmente basato su un bus di servizio anziché sugli eventi in memoria. Tuttavia, nel primo caso, la messaggistica reale sarebbe eccessiva per l'elaborazione di eventi del dominio perché è sufficiente elaborare gli eventi all'interno dello stesso processo, ovvero all'interno dello stesso dominio e livello di applicazione.

Un altro modo per eseguire il mapping degli eventi a più gestori di eventi consiste nell'usare la registrazione di tipi in un contenitore IoC in modo che sia possibile dedurre in modo dinamico dove inviare gli eventi. In altre parole, è necessario sapere quali gestori di eventi devono ricevere un evento specifico. Nella figura 7-16 viene illustrato un approccio semplificato specifico.

![Diagramma che mostra un dispatcher di eventi di dominio che invia eventi ai gestori appropriati.](./media/domain-events-design-implementation/domain-event-dispatcher.png)

**Figura 7-16**. Dispatcher di eventi del dominio usando IoC

È possibile compilare autonomamente tutto il codice complesso e gli elementi per implementare questo approccio. Tuttavia è possibile anche usare le librerie disponibili come [MediatR](https://github.com/jbogard/MediatR), che usa il contenitore IoC in background. È quindi possibile utilizzare direttamente le interfacce predefinite e i metodi di pubblicazione/spedizione dell'oggetto mediatore.

Nel codice è necessario prima registrare i tipi di gestori di eventi nel contenitore IoC, come illustrato nell'esempio seguente nel [microservizio per gli ordini eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/MediatorModule.cs):

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement IAsyncNotificationHandler<>)
        // in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
                                       .GetTypeInfo().Assembly)
                                         .AsClosedTypesOf(typeof(IAsyncNotificationHandler<>));
        // Other registrations ...
    }
}
```

Il codice prima identifica l'assembly contenente i gestori di eventi del dominio, individuando l'assembly contenente i gestori, usando typeof(ValidateOrAddBuyerAggregateWhenXxxx), ma si potrebbe scegliere qualsiasi altro gestore di eventi per individuare l'assembly. Poiché tutti i gestori di eventi implementano l'interfaccia IAsyncNotificationHandler, il codice cerca solo questi tipi e registra tutti i gestori di eventi.

### <a name="how-to-subscribe-to-domain-events"></a>Creazione di sottoscrizioni per gli eventi del dominio

Quando si usa MediatR, ogni gestore di eventi deve usare un tipo di evento fornito nel parametro generico dell'interfaccia INotificationHandler, come illustrato nel codice seguente:

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

In base alla relazione tra l'evento e il gestore dell'evento, che può essere considerato la sottoscrizione, l'artefatto MediatR può individuare e attivare tutti i gestori di eventi per ogni evento.

### <a name="how-to-handle-domain-events"></a>Come gestire gli eventi del dominio

Infine, il gestore di eventi implementa in genere il codice al livello dell'applicazione che usa i repository dell'infrastruttura per ottenere le aggregazioni aggiuntive necessarie e per eseguire la logica del dominio per gli effetti collaterali. Nel seguente [codice del gestore dell'evento del dominio in eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/DomainEventHandlers/OrderStartedEvent/ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler.cs) viene illustrato un esempio di implementazione.

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
                   : INotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;

    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // ...Parameter validations...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ? orderStartedEvent.CardTypeId : 1;
        var userGuid = _identityService.GetUserIdentity();
        var buyer = await _buyerRepository.FindAsync(userGuid);
        bool buyerOriginallyExisted = (buyer == null) ? false : true;

        if (!buyerOriginallyExisted)
        {
            buyer = new Buyer(userGuid);
        }

        buyer.VerifyOrAddPaymentMethod(cardTypeId,
                                       $"Payment Method on {DateTime.UtcNow}",
                                       orderStartedEvent.CardNumber,
                                       orderStartedEvent.CardSecurityNumber,
                                       orderStartedEvent.CardHolderName,
                                       orderStartedEvent.CardExpiration,
                                       orderStartedEvent.Order.Id);

        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer)
                                                                      : _buyerRepository.Add(buyer);

        await _buyerRepository.UnitOfWork
                .SaveEntitiesAsync();

        // Logging code using buyerUpdated info, etc.
    }
}
```

Il codice del gestore dell'evento del dominio precedente viene considerato codice a livello dell'applicazione perché usa i repository di infrastruttura, come spiegato nella sezione successiva sul livello di persistenza dell'infrastruttura. I gestori di eventi possono anche usare altri componenti dell'infrastruttura.

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a>Gli eventi del dominio possono generare eventi di integrazione da pubblicare al di fuori dei limiti del microservizio

Infine, è importante ricordare che a volte è possibile propagare eventi tra più microservizi. La propagazione è un evento di integrazione e potrebbe essere pubblicata tramite un bus di eventi da un qualsiasi gestore dell'evento di dominio specifico.

## <a name="conclusions-on-domain-events"></a>Conclusioni sugli eventi del dominio

Come illustrato, usare gli eventi del dominio per implementare in modo esplicito gli effetti collaterali delle modifiche all'interno del dominio. Per usare la terminologia DDD, usare gli eventi del dominio per implementare in modo esplicito gli effetti collaterali tra una o più aggregazioni. Inoltre, per migliorare la scalabilità e ridurre l'impatto sui blocchi di database, facoltativamente usare la coerenza finale tra le aggregazioni all'interno dello stesso dominio.

L'app di riferimento usa [MediatR](https://github.com/jbogard/MediatR) per propagare gli eventi di dominio in modo sincrono tra le aggregazioni, all'interno di una singola transazione. Tuttavia, è anche possibile usare alcune implementazioni AMQP come [RabbitMQ](https://www.rabbitmq.com/) o [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) per propagare gli eventi di dominio in modo asincrono, usando la coerenza finale ma, come accennato in precedenza, è necessario considerare la necessità di azioni compensative in caso di errori.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Greg Young. Che cos'è un evento di dominio?** \
  <https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf#page=25>

- **Jan Stenberg. Eventi di dominio e coerenza finale** \
  <https://www.infoq.com/news/2015/09/domain-events-consistency>

- **Jimmy Bogard. Un modello di eventi di dominio migliore** \
  <https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/>

- **Vaughn Vernon. Efficace progettazione aggregata Parte II: Rendere gli aggregati insieme** \
  [https://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

- **Jimmy Bogard. Rafforzamento del dominio: Eventi di dominio** \
  <https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>

- **Tony Truong. Esempio di modello di eventi di dominioDomain Events Pattern Example** \
  <https://www.tonytruong.net/domain-events-pattern-example/>

- **Udi Dahan. Come creare modelli di dominio completamente incapsulatiHow to create fully encapsulated Domain Models** \
  <http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/>

- **Udi Dahan. Eventi di dominio – Take 2** \
  <http://udidahan.com/2008/08/25/domain-events-take-2/>

- **Udi Dahan. Eventi di dominio – Salvezza** \
  <http://udidahan.com/2009/06/14/domain-events-salvation/>

- **Jan Kronquist. Non pubblicare eventi di dominio, restituiscli!** \
  <https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/>

- **Cesar de la Torre. Eventi di dominio e eventi di integrazione nelle architetture DDD e microserviziDomain Events vs.** \
  <https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/>

>[!div class="step-by-step"]
>[Successivo](client-side-validation.md)
>[precedente](infrastructure-persistence-layer-design.md)
