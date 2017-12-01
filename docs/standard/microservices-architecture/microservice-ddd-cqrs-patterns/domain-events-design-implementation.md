---
title: Eventi del dominio. Progettazione e implementazione
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione, progettazione e gli eventi di dominio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2d98b302be4ee72d8225526944fc3e41cbadcb5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="domain-events-design-and-implementation"></a>Eventi del dominio: progettazione e implementazione

Utilizzare gli eventi di dominio per implementare in modo esplicito gli effetti collaterali delle modifiche all'interno del dominio. In altre parole e utilizzando la terminologia DDD, utilizzare gli eventi di dominio per implementare in modo esplicito gli effetti collaterali tra più funzioni di aggregazione. Facoltativamente, per una migliore scalabilità e minore impatto in blocchi di database, utilizzare la coerenza eventuale tra funzioni di aggregazione all'interno dello stesso dominio.

## <a name="what-is-a-domain-event"></a>Che cos'è un evento di dominio?

Un evento è un elemento che si è verificato in precedenza. Dominio sia un evento, in modo logico, un elemento che si sono verificati in un particolare dominio, e un elemento si desidera altre parti del dominio stesso (in-process) da tenere in considerazione e potenzialmente reagire di conseguenza.

Un importante vantaggio di eventi di dominio è che gli effetti collaterali dopo è verificato un problema in un dominio possono essere espressi in modo esplicito anziché in modo implicito. Tali lato effetti devono essere coerenti in modo verificarsi entrambi tutte le operazioni correlate all'attività di business, o nessuno di essi. Inoltre, gli eventi di dominio consentono una migliore separazione delle problematiche tra le classi all'interno dello stesso dominio.

Ad esempio, se si utilizza soltanto solo Entity Framework e le entità o anche le aggregazioni, se essere causate da un caso d'uso di effetti collaterali, quelli verrà implementati come un concetto implicito nel codice a dopo che è verificato un problema. Tuttavia, se è possibile visualizzare solo il codice, si potrebbe sapere se tale codice (l'effetto collaterale) fa parte dell'operazione principale o se è effettivamente un effetto collaterale. D'altra parte, l'uso di eventi del dominio rende il concetto esplicite e una parte del linguaggio universale. Ad esempio, nell'applicazione eShopOnContainers, si crea un ordine non è quasi nell'ordine. Aggiorna o si crea un acquirente di aggregazione in base all'utente originale, in quanto l'utente non è un acquirente fino a quando non è disponibile un ordine. Se si utilizzano gli eventi di dominio, è possibile esprimere in modo esplicito tale regola di dominio basato su nel linguaggio universale fornito da esperti del settore.

Gli eventi di dominio sono simili agli eventi di messaggistica in stile, con una differenza importante. Con la messaggistica reale, Accodamento messaggi, gestori di messaggi o un bus di servizio mediante AMPQ, un messaggio viene sempre inviato in modo asincrono e comunicato tra i processi e le macchine. Ciò è utile per l'integrazione di più contesti delimitata, microservizi o addirittura nelle diverse applicazioni. Tuttavia, con gli eventi di dominio, che si desidera generare un evento dall'operazione di dominio che è in esecuzione, ma si desidera che tutti gli effetti collaterali si verifichi all'interno dello stesso dominio.

Gli eventi di dominio e i relativi effetti collaterali (le azioni attivate in seguito che sono gestite da gestori di eventi) deve verificarsi quasi immediatamente, in genere in-process e all'interno dello stesso dominio. Pertanto, gli eventi di dominio potrebbe essere sincrono o asincrono. Eventi di integrazione, tuttavia, devono essere sempre asincroni.

## <a name="domain-events-versus-integration-events"></a>Eventi del dominio e gli eventi di integrazione

Semanticamente, dominio e l'integrazione di eventi sono la stessa cosa: notifiche solo si è verificato qualcosa. Tuttavia, l'implementazione deve essere diversa. Gli eventi di dominio sono solo i messaggi inviati al dispatcher eventi dominio, che potrebbe essere implementato come un mediatore in memoria in base a un contenitore IoC o qualsiasi altro metodo.

D'altra parte, lo scopo di eventi di integrazione è per propagare il commit delle transazioni e gli aggiornamenti per altri sottosistemi, siano essi altri microservizi, delimitata contesti o applicazioni anche esterne. Di conseguenza, dovranno essere eseguite solo se l'entità è stata resa persistente, poiché in molti scenari in caso di errore, l'intera operazione non si è verificato.

Inoltre e come indicato, integrazione con gli eventi devono essere basati sulla comunicazione asincrona tra più microservizi (altri contesti delimitata) o sistemi esterne o le applicazioni. Di conseguenza, l'interfaccia del bus di eventi deve parte dell'infrastruttura che consente di inter-process e distribuito la comunicazione tra servizi potenzialmente remoto. Può basarsi su un bus di servizio esterno, code, un database condiviso utilizzato come una cassetta postale o qualsiasi altro distribuiti e idealmente push sistema di messaggistica basato su.

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a>Eventi come un modo migliore per attivare gli effetti collaterali tra più aggregazioni all'interno dello stesso dominio del dominio

Se eseguire un comando relative a una istanza di aggregazione richiede regole di dominio aggiuntivi per l'esecuzione su una o più aggregazioni aggiuntive, è necessario progettare e implementare tali effetti collaterali verrà attivata da eventi del dominio. Come illustrato nella figura 9-14 e come uno dei principali casi d'uso, l'evento di un dominio deve essere usato per propagare le modifiche dello stato tra più aggregazioni all'interno del modello di dominio stesso.

![](./media/image15.png)

**Figura 9-14**. Eventi per garantire la coerenza tra più aggregazioni all'interno dello stesso dominio del dominio

Nella figura, quando l'utente avvia un ordine, l'evento di dominio OrderStarted genera la creazione di un oggetto Buyer in microservizio l'ordinamento, in base (le informazioni fornite nel comando CreateOrder) le informazioni utente originale da microservizio l'identità. Quando viene creato in primo luogo, dall'aggregazione ordine viene generato l'evento di dominio.

In alternativa, è possibile avere la radice di aggregazione sottoscritta gli eventi generati dai membri del relativo aggregazioni (entità figlio). Ad esempio, ogni entità figlio OrderItem può generare un evento quando il prezzo dell'articolo è superiore a una quantità specifica o quando la quantità di elementi di prodotto è troppo elevata. La radice di aggregazione può ricevere tali eventi ed eseguire un calcolo globale o l'aggregazione.

È importante comprendere che questa comunicazione basata su eventi non è implementata direttamente all'interno di funzioni di aggregazione; è necessario implementare i gestori di eventi di dominio. Gestione degli eventi di dominio è un problema dell'applicazione. Il livello del modello di dominio deve solo concentrarsi sulla logica di dominio, operazioni che si potrebbe considerare un esperto di dominio, non infrastruttura dell'applicazione come gestori eventi e azioni di persistenza effetto collaterale utilizzando repository. Pertanto, al livello applicazione è in cui si hanno i gestori di eventi di dominio attivano azioni quando viene generato un evento di dominio.

Eventi del dominio possono anche essere utilizzati per avviare qualsiasi numero di azioni di applicazione, e ciò che è più importante, deve essere aperta per aumentare il numero in futuro in modo separato. Ad esempio, quando l'ordine viene avviato, potrebbe essere da pubblicare un evento di dominio per propagare tali informazioni da altre funzioni di aggregazione o anche per generare le azioni di applicazioni quali le notifiche.

Il punto chiave è il numero di azioni da eseguire quando si verifica un evento di dominio aprire. Infine, aumentano le azioni e le regole del dominio e l'applicazione. La complessità o il numero di azioni di effetto collaterale, quando si verifica un evento aumenteranno, ma se il codice sono stato combinato con "glue" (ovvero solo istanze di oggetti con la parola chiave new in C\#), quindi ogni volta che è necessario aggiungere una nuova azione è necessario modificare il codice originale. Ciò potrebbe causare nuovi bug, poiché con ogni nuovo requisito è necessario modificare il flusso di codice originale. Questo va contro il [principio aperto o chiuso](https://en.wikipedia.org/wiki/Open/closed_principle) da [a tinta unita](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)). Non solo, la classe originale che è stato orchestrazione le operazioni di aumento delle dimensioni e aumento delle dimensioni, che va contro il [singolo responsabilità principio (criteri di restrizione software)](https://en.wikipedia.org/wiki/Single_responsibility_principle).

D'altra parte, se si utilizzano gli eventi di dominio, è possibile creare un'implementazione con granularità fine e disaccoppiata adeguatamente responsabilità utilizzando questo approccio:

1.  Inviare un comando (ad esempio, CreateOrder).
2.  Il comando di ricezione in un gestore del comando.
    -   Eseguire la transazione della funzione di aggregazione singolo.
    -   (Facoltativo) Generare eventi di dominio per gli effetti collaterali (ad esempio, OrderStartedDomainDvent).
1.  Handle dominio eventi (all'interno del processo corrente) thast verrà eseguito un numero di aprire gli effetti collaterali in più funzioni di aggregazione o azioni di applicazione. Ad esempio:
    -   Verificare o create (metodo di pagamento e l'acquirente).
    -   Creare e inviare un evento correlato di integrazione per il bus di eventi per gli stati si propagano tra microservizi o trigger azioni esterne quali l'invio di un messaggio di posta elettronica all'acquirente.
    -   Gestire altri effetti collaterali.

Come illustrato nella figura 9-15, a partire dall'evento stesso dominio, è possibile gestire più azioni relative a altre funzioni di aggregazione nel dominio o azioni di applicazione aggiuntiva che è necessario eseguire tra microservizi connessione con il bus di eventi ed eventi di integrazione.

![](./media/image16.png)

**Figura 9-15**. La gestione di più azioni per ogni dominio

I gestori di eventi sono in genere nel livello dell'applicazione, poiché si utilizzeranno gli oggetti di infrastruttura come repository o un'API di applicazione per il comportamento del microservizio. In tal senso, i gestori di eventi sono simili ai gestori di comando, in modo che entrambi siano parte del livello di applicazione. La differenza importante è che un comando deve essere elaborato una sola volta. Un evento di dominio può essere elaborato da zero o  *n*  volte, poiché se possono essere ricevuti da più ricevitori o gestori di eventi con uno scopo diverso per ogni gestore.

La possibilità di un numero di gestori per l'evento di dominio aprire consente di aggiungere molte altre regole di dominio senza conseguenze per il codice corrente. Implementa la seguente regola di business che deve essere eseguita a destra dopo un evento, ad esempio, potrebbe essere facile come aggiungere alcuni gestori di eventi (o anche solo una):

Quando la quantità totale acquistata da un cliente nell'archivio, in qualsiasi numero di ordini, supera $6.000, applicare un sconto del 10% per ogni nuovo ordine e una notifica al cliente con un messaggio di posta elettronica su tale sconto per gli ordini futuri.

## <a name="implementing-domain-events"></a>Implementazione di eventi di dominio

In c#, l'evento di un dominio è semplicemente una struttura di dati azienda o classe, come un DTO, con tutte le informazioni correlate a cosa è successo solo nel dominio, come illustrato nell'esempio seguente:

```csharp
public class OrderStartedDomainEvent : IAsyncNotification
{
    public int CardTypeId { get; private set; }
    public string CardNumber { get; private set; }
    public string CardSecurityNumber { get; private set; }
    public string CardHolderName { get; private set; }
    public DateTime CardExpiration { get; private set; }
    public Order Order { get; private set; }

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

In termini di linguaggio universale di dominio, poiché un evento è un elemento che si sono verificati in passato, il nome della classe dell'evento deve essere rappresentato come un verbo passato, ad esempio OrderStartedDomainEvent o OrderShippedDomainEvent. Che è l'implementazione di eventi di dominio l'ordinamento microservizio in eShopOnContainers.

Come notato in precedenza, una caratteristica importante degli eventi è che poiché un evento è un elemento che si sono verificati in passato, consiglia di non modificare. Di conseguenza deve essere una classe non modificabile. È possibile visualizzare nel codice precedente che le proprietà sono di sola lettura all'esterno dell'oggetto. L'unico modo per aggiornare l'oggetto è tramite il costruttore quando si crea l'oggetto evento.

### <a name="raising-domain-events"></a>Generazione di eventi di dominio

Domanda successiva viene illustrato come generare un evento di dominio in modo da raggiungere relativi gestori di eventi correlati. È possibile utilizzare diversi approcci disponibili.

udi Dahan proposto in origine (ad esempio, in diversi correlata post, ad esempio [dominio eventi e richiedere 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) utilizzando una classe statica per la gestione e generazione degli eventi. Potrebbe trattarsi di una classe statica denominata DomainEvents che determina la generazione di eventi di dominio immediatamente quando viene chiamato, utilizzando una sintassi analoga DomainEvents.Raise (evento myEvent). Jimmy Bogard ha scritto un post di blog ([rafforzare il dominio: eventi del dominio](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) che si consiglia un approccio simile.

Tuttavia, quando la classe di eventi di dominio è statica, anche invia ai gestori immediatamente. Questo test e debug più difficile, perché i gestori di eventi con la logica di effetti collaterali vengono eseguiti immediatamente dopo l'evento viene generato. Quando si eseguono test e debug, si desidera lo stato attivo su solo ciò che accade nelle classi aggregazione corrente; non si desidera improvvisamente reindirizzati ad altri gestori di eventi per gli effetti collaterali correlati ad altre funzioni di aggregazione o la logica dell'applicazione. Ecco perché altri approcci sono stati ulteriormente sviluppati, come illustrato nella sezione successiva.

#### <a name="the-deferred-approach-for-raising-and-dispatching-events"></a>L'approccio posticipata per la generazione e invio di eventi

Invece di invio immediatamente a un gestore di dominio, un approccio migliore consiste nell'aggiungere gli eventi di dominio a una raccolta e quindi per inviare gli eventi di dominio *immediatamente prima di* o *destra*  *Dopo aver* il commit della transazione (come con SaveChanges in Entity Framework). (Questo approccio descritto da Jimmy Bogard in questo post di [un modello di eventi di dominio migliorato](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)

Decidere se inviare gli eventi di dominio immediatamente prima o a destra dopo il commit della transazione è importante, poiché determina se gli effetti collaterali verranno incluse come parte della stessa transazione o in transazioni diverse. Nel secondo caso, è necessario affrontare la coerenza eventuale tra più funzioni di aggregazione. In questo argomento viene illustrato nella sezione successiva.

L'approccio posticipata è quali eShopOnContainers utilizza. È innanzitutto necessario aggiungere gli eventi in corso nelle entità in una raccolta o un elenco di eventi per l'entità. Tale elenco deve essere fanno parte dell'oggetto entità, o, ancora meglio, la classe di entità di base, come illustrato nell'esempio seguente:

```csharp
public abstract class Entity
{
    private List<IAsyncNotification> _domainEvents;

    public List<IAsyncNotification> DomainEvents => _domainEvents;

    public void AddDomainEvent(IAsyncNotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<IAsyncNotification>();
        _domainEvents.Add(eventItem);
    }

    public void RemoveDomainEvent(IAsyncNotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }
    // ...
}
```

Quando si desidera generare un evento, viene semplicemente aggiunto alla raccolta di eventi per essere inserito all'interno di un metodo di aggregazione di entità, come illustrato nel codice seguente:

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
    cardTypeId,
    cardNumber,
    cardSecurityNumber,
    cardHolderName,
    cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

Si noti che l'unico elemento che esegue il metodo AddDomainEvent viene aggiunta di un evento all'elenco. Viene generato alcun evento ancora, e nessun gestore dell'evento viene richiamato ancora.

In realtà si desidera inviare gli eventi in un secondo momento quando si esegue il commit della transazione nel database. Se si utilizza Entity Framework Core, significa che nel metodo SaveChanges DbContext l'Entity Framework, come illustrato nel codice seguente:

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<int> SaveEntitiesAsync()
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
        // event handlers) performed through the DbContext will be commited
        var result = await base.SaveChangesAsync();
    }
}
```

Con questo codice, inviare gli eventi di entità per i rispettivi gestori eventi.

Il risultato complessivo è è avere separata la generazione di un evento di dominio (aggiunta di un semplice in un elenco in memoria) da distribuirlo a un gestore eventi. Inoltre, a seconda di quale tipo di dispatcher in uso, si potrebbero inviare gli eventi in modo sincrono o asincrono.

Tenere presente che limiti transazionali diventi significativi riprodurre qui. Se l'unità di lavoro e delle transazioni può estendersi su più di una funzione di aggregazione (come avviene quando si utilizza Entity Framework Core e un database relazionale), questo può funzionare bene. Tuttavia, se la transazione non può estendersi aggregati, ad esempio quando si utilizza un database NoSQL come Azure DocumentDB, è necessario implementare i passaggi aggiuntivi per ottenere la coerenza. Si tratta di un altro motivo mancato riconoscimento della persistenza non universale; a seconda del sistema di archiviazione in uso.

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a>Singola transazione tra funzioni di aggregazione e la coerenza eventuale tra funzioni di aggregazione

Se si desidera eseguire una singola transazione tra funzioni di aggregazione e basarsi su coerenza finale tra tali aggregazioni alla domanda è controversi. Molti autori DDD come Eric Evans e Vaughn Vernon sostenere la regola che una transazione = un'aggregazione e pertanto sostenere per la coerenza finale in funzioni di aggregazione. Ad esempio, nel suo libro *la progettazione*, Eric Evans afferma:

Una regola che si estende su aggregazioni non previsto per essere aggiornate in qualsiasi momento. Tramite l'elaborazione degli eventi, l'elaborazione batch o altri meccanismi di aggiornamento, altre dipendenze possono essere risolti all'interno di tempo specifico. (pagina. 128)

Vaughn Vernon il messaggio seguente in [progettazione di aggregazione efficace. Parte II: Apportato aggrega lavoro insieme](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):

Di conseguenza, se l'esecuzione di un comando in una istanza di aggregazione richiede che le regole di business aggiuntive eseguire su una o più aggregazioni, utilizzare la coerenza eventuale \[...\] È un modo pratico per supportare la coerenza eventuale in un modello DDD. Un metodo di aggregazione pubblica un evento di dominio che è nel tempo recapitato a uno o più sottoscrittori asincroni.

Questa spiegazione logica si basa su adottando granulari per le transazioni anziché le transazioni che si estende su molte funzioni di aggregazione o entità. L'idea è che nel secondo caso, il numero di blocchi di database sarà significativo nelle applicazioni su larga scala con esigenze di scalabilità. L'adozione del fatto che le applicazioni con scalabilità elevata, deve necessariamente contenere immediata coerenza transazionale tra più aggregazioni consente di accettare il concetto di coerenza finale. Le modifiche spesso non sono necessari per l'azienda ed è in ogni caso la responsabilità di esperti del settore per pronunciare le necessitano operazioni particolari transazioni atomiche o non è atomico. Se una transazione atomica tra più funzioni di aggregazione è sempre un'operazione, è possibile chiedere se la funzione di aggregazione deve essere maggiore o non è stato progettato in modo corretto.

Tuttavia, altri sviluppatori e progettisti come Jimmy Bogard desidera che si estende su una singola transazione tra diverse funzioni di aggregazione, ma solo quando le aggregazioni aggiuntive sono correlate gli effetti collaterali per lo stesso comando originale. Ad esempio, in [un modello di eventi di dominio migliorato](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard afferma:

In genere, desidero che gli effetti collaterali di un evento di dominio di cui si verificano all'interno della stessa transazione logica, ma non necessariamente nello stesso ambito di generazione dell'evento di dominio \[...\] Prima che si esegue il commit della transazione, si invia gli eventi per i rispettivi gestori.

Se si dispatch destra eventi dominio *prima* eseguito il commit della transazione originale, è perché si vuole che gli effetti collaterali di tali eventi da includere nella stessa transazione. Ad esempio, se il metodo DbContext SaveChanges EF non riesce, la transazione verrà rollback tutte le modifiche, tra cui il risultato di tutte le operazioni di effetto collaterale implementato per i gestori di eventi del dominio correlate. Questo è poiché l'ambito della vita DbContext per impostazione predefinita, definito come "con ambito." Pertanto, l'oggetto DbContext è condiviso da più oggetti di repository viene creata un'istanza all'interno della stesso ambito o di un oggetto grafico. Che coincide con l'ambito di HttpRequest quando si sviluppano applicazioni API Web o di MVC.

In realtà, entrambi gli approcci (singola transazione atomica e la coerenza eventuale) possono essere corretti. Questo dipende i dominio o dei requisiti aziendali e cosa esperti del settore indicano. Dipende inoltre come scalabile è necessario il servizio sia (più granulare transazioni hanno un impatto minore in relazione a blocchi di database). E dipende quanto investimento che si desidera apportare al codice, poiché la coerenza eventuale codice più complesso è necessario per rilevare possibili incoerenze tra funzioni di aggregazione e la necessità di implementare le azioni di compensazione. Prendere in considerazione che se si esegue il commit delle modifiche per l'aggregazione originale e, successivamente, quando gli eventi inviati, si verifica un problema e i gestori eventi non è possibile eseguire il commit i relativi effetti collaterali, sarà necessario incoerenze tra funzioni di aggregazione.

Un modo per consentire le azioni di compensazione, è possibile archiviare gli eventi di dominio nelle tabelle di database aggiuntivi in modo che possono far parte della transazione originale. Successivamente, è possibile usare un processo batch che rileva le incoerenze ed esegue le azioni di compensazione, confrontando l'elenco di eventi con lo stato corrente delle aggregazioni. Le azioni di compensazione fanno parte di un argomento di tipo complesso che richiederà l'analisi approfondita del lato, che include la discussione con l'utente di business e gli esperti di dominio.

In ogni caso, è possibile scegliere l'approccio che è necessario. Ma iniziale posticipata approccio-generazione degli eventi prima di eseguire il commit, in modo da utilizzare una singola transazione, è l'approccio più semplice quando si utilizza Entity Framework Core e un database relazionale. È più facile da implementare e in molti casi è valido. È anche l'approccio adottato nell'ordinamento microservizio in eShopOnContainers.

Ma, come effettivamente inviare gli eventi ai relativi gestori eventi rispettivi? Che cos'è il \_oggetto mediatore che viene visualizzato nell'esempio precedente? Che deve eseguire con le tecniche e gli elementi che è possibile utilizzare per eseguire il mapping tra gli eventi e i relativi gestori eventi.

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a>Il dispatcher di eventi di dominio: mapping dagli eventi ai gestori di eventi

Quando si sarà in grado di inviare o pubblicare gli eventi, è necessario un tipo di elemento per la pubblicazione dell'evento in modo che ogni gestore correlati può accedervi e gli effetti collaterali di processo in base a tale evento.

Un approccio è un sistema di messaggistica reale o anche un bus di eventi, eventualmente in base a un bus di servizio anziché gli eventi in memoria. Tuttavia, nel primo caso, messaggistica reale sarebbe eccessivi per l'elaborazione di eventi del dominio, poiché è sufficiente elaborare gli eventi all'interno dello stesso processo (ovvero, all'interno del livello di applicazione e del dominio stesso).

Un altro modo per eseguire il mapping a più gestori eventi è tramite la registrazione di tipi in un contenitore di inversione di controllo in modo che è in grado di dedurre in modo dinamico dove inviare gli eventi. In altre parole, è necessario conoscere i requisiti di gestori eventi per ottenere un evento specifico. Nella figura 9-16 viene illustrato un approccio semplificato per tale.

![](./media/image17.png)

**Nella figura 9-16**. Dispatcher di eventi di dominio usando IoC

È possibile compilare tutti i plumbing e gli elementi per implementare tale approccio personalmente. Tuttavia, è inoltre possibile utilizzare le librerie disponibili come [MediatR](https://github.com/jbogard/MediatR), che nel sistema l'Usa il contenitore di IoT. È possibile pertanto è utilizzare direttamente le interfacce predefinite e i metodi di pubblicazione/distribuzione dell'oggetto mediatore.

Nel codice, è innanzitutto necessario registrare i tipi di gestore di evento nel contenitore di inversione di controllo, come illustrato nell'esempio seguente:

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement
        // IAsyncNotificationHandler<>) in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(
            typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
            .GetTypeInfo().Assembly)
            .Where(t => t.IsClosedTypeOf(typeof(IAsyncNotificationHandler<>)))
            .AsImplementedInterfaces();
        // Other registrations ...
    }
}
```

Il codice innanzitutto identifica l'assembly contenente i gestori di eventi di dominio, individuazione dell'assembly contenente i gestori (Usa typeof(ValidateOrAddBuyerAggregateWhenXxxx), ma è stato scelto un altro gestore eventi per individuare l'assembly). Poiché tutti i gestori di eventi implementano l'interfaccia IAsyncNotificationHandler, il codice quindi cerca solo i tipi e registra tutti i gestori eventi.

### <a name="how-to-subscribe-to-domain-events"></a>Come sottoscrivere gli eventi di dominio

Quando si utilizza MediatR, ogni gestore eventi deve utilizzare un tipo di evento che viene fornito nel parametro generico dell'interfaccia IAsyncNotificationHandler, come si può notare nel codice seguente:

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

In base alla relazione tra eventi e il gestore eventi, che può essere considerato la sottoscrizione, l'elemento MediatR può individuare tutti i gestori eventi per ogni evento e attivare ognuno di tali gestori eventi.

### <a name="how-to-handle-domain-events"></a>Come gestire gli eventi di dominio

Infine, il gestore dell'evento implementa in genere codice del livello applicazione che utilizza il repository di infrastruttura per ottenere le aggregazioni aggiuntive necessarie e di eseguire la logica di dominio effetto collaterale. Il codice seguente illustra un esempio.

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
    : IAsyncNotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;
    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // Parameter validations
        //...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ?
            orderStartedEvent.CardTypeId : 1;
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
        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) :
        _buyerRepository.Add(buyer);
        await _buyerRepository.UnitOfWork.SaveEntitiesAsync();
        // Logging code using buyerUpdated info, etc.
    }
}
```

Questo codice del gestore eventi viene considerato codice del livello applicazione, perché Usa il repository di infrastruttura, come spiegato nella sezione successiva nel livello di persistenza di infrastruttura. I gestori di eventi è possibile usare anche altri componenti dell'infrastruttura.

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a>Gli eventi di dominio possono generare eventi di integrazione da pubblicare all'esterno dei limiti microservizio

Infine, è importante ricordare che si potrebbe desiderare di eventi si propagano tra più microservizi. Che viene considerato un evento di integrazione e possono essere pubblicato tramite un bus di eventi da qualsiasi gestore di dominio specifico.

## <a name="conclusions-on-domain-events"></a>Conclusioni sugli eventi di dominio 

Come indicato, utilizzare gli eventi di dominio per implementare in modo esplicito gli effetti collaterali delle modifiche all'interno del dominio. Per utilizzare terminologia DDD, utilizzare gli eventi di dominio per implementare in modo esplicito gli effetti collaterali in uno o più funzioni di aggregazione. Inoltre e per una migliore scalabilità e un minore impatto sui blocchi di database, utilizzare la coerenza eventuale tra funzioni di aggregazione all'interno dello stesso dominio.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Greg Young. Che cos'è un evento di dominio? ** 
     [ *http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)

-   **Jan Stenberg. Eventi del dominio e la coerenza eventuale**
    [*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)

-   **Jimmy Bogard. Un modello di eventi di dominio migliorato**
    [*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)

-   **Vaughn Vernon. Efficace aggregazione progettazione parte II: Effettua aggregazioni lavoro insieme**
    [*http://dddcommunity.org/wp-content/uploads/files/pdf\_articoli/Vernon\_2011\_ 2. pdf*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

-   **Jimmy Bogard. Il dominio rafforzare: eventi del dominio**
    *<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>*

-   **Tony Truong. Esempio di schema di eventi del dominio**
    [*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)

-   **udi Dahan. Come creare completamente incapsulato i modelli di dominio**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)

-   **udi Dahan. Eventi di dominio e richiedere 2**
    [*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)

-   **udi Dahan. Eventi del dominio: Salvation**
    [*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)

-   **Jan Kronquist. Non pubblicare eventi di dominio, li restituiscono. ** 
     [ *https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)

-   **Cesar de la Torre. Visual Studio gli eventi di dominio. Eventi di integrazione nelle architetture DDD e microservizi**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)


>[!div class="step-by-step"]
[Precedente] (client-side-validation.md) [Avanti] (infrastruttura persistenza-livello design.md)
