---
title: La sottoscrizione di eventi
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | La sottoscrizione di eventi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: fe17b53a39ff2964cd60183e291e2936d3ba28df
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="subscribing-to-events"></a>La sottoscrizione di eventi

Il primo passaggio per l'utilizzo del bus di eventi è la sottoscrizione di microservizi per gli eventi da ricevere. Che deve essere eseguita in microservizi il ricevitore.

Semplice codice seguente viene illustrato cosa microservizio ogni ricevitore deve implementare all'avvio del servizio (ovvero, all'avvio della classe), in modo che sottoscrive gli eventi è necessario. Ad esempio, il microservizio basket.api deve sottoscrivere i messaggi ProductPriceChangedIntegrationEvent. Questo rende il microservizio conoscenza di eventuali modifiche per il prezzo del prodotto e permette di avvertire l'utente la modifica se il prodotto nel carrello dell'utente.

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

Quando si esegue questo codice, il sottoscrittore di microservizio sono in attesa attraverso canali RabbitMQ. Quando un messaggio di tipo ProductPriceChangedIntegrationEvent arriva, il codice richiama il gestore dell'evento che viene passato al metodo ed elabora l'evento.

## <a name="publishing-events-through-the-event-bus"></a>Pubblicazione di eventi tramite il bus di eventi

Infine, il mittente del messaggio (origine microservizio) pubblica gli eventi di integrazione con un codice simile all'esempio seguente. (Si tratta di un esempio semplificato che non accetta l'atomicità in considerazione). Ogni volta che un evento deve essere propagato attraverso più microservizi, in genere subito dopo il commit di transazioni da microservizio l'origine o dati, è necessario implementare un codice simile.

L'oggetto di implementazione bus di eventi (basato su RabbitMQ o su un bus di servizio) in primo luogo, verrà aggiunti al costruttore controller, come illustrato nel codice seguente:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _context;
    private readonly IOptionsSnapshot<Settings> _settings;
    private readonly IEventBus _eventBus;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<Settings> settings,
        IEventBus eventBus)
    {
        _context = context;
        _settings = settings;
        _eventBus = eventBus;
    }
    // ...
}
```

Quindi è utilizzato da metodi del controller, come nel metodo UpdateProduct:

```csharp
[Route("update")]
[HttpPost]
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem product)
{
    var item = await _context.CatalogItems.SingleOrDefaultAsync(
        i => i.Id == product.Id);
    // ...
    if (item.Price != product.Price)
    {
        var oldPrice = item.Price;
        item.Price = product.Price;
        _context.CatalogItems.Update(item);
        var @event = new ProductPriceChangedIntegrationEvent(item.Id,
            item.Price,
            oldPrice);
        // Commit changes in original transaction
        await _context.SaveChangesAsync();
        // Publish integration event to the event bus
        // (RabbitMQ or a service bus underneath)
        _eventBus.Publish(@event);
        // ...
    }
    // ...
}
```

In questo caso, poiché il microservizio di origine è un semplice microservizio CRUD, tale codice viene inserito destra in un controller API Web. In microservizi più avanzate, è stato implementato nella classe CommandHandler, destra dopo i dati originali viene eseguito il commit.

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a>Progettazione di atomicità e resilienza quando si pubblica il bus di eventi

Quando si pubblicano eventi di integrazione tramite una funzionalità di messaggistica distribuita del sistema, quali il bus di eventi, è stato riscontrato il problema di aggiornamento del database originale in modo atomico e pubblicazione di un evento. Ad esempio, nell'esempio semplificato illustrato in precedenza, il codice esegue il commit dei dati al database quando il prezzo del prodotto viene modificato e quindi pubblica un messaggio ProductPriceChangedIntegrationEvent. Inizialmente, potrebbe essere essenziale che queste due operazioni di essere eseguita in modo atomico. Tuttavia, se si utilizza una transazione distribuita riguardano il database e il messaggio di Service broker, come avviene nei sistemi precedenti, ad esempio [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), questa operazione è sconsigliata per i motivi descritti per il [Teorema di estremità](https://www.quora.com/What-Is-CAP-Theorem-1).

In pratica, è possibile microservizi creare sistemi scalabili e a disponibilità elevata. Semplificando in qualche modo, il teorema di CAP è indicato che non è possibile compilare un database (o un microservizio a cui appartiene il modello) che viene continuamente disponibili, è fortemente coerente, *e* tolleranza d'errore per ogni partizione. È necessario scegliere due di queste tre proprietà.

In architetture basate su microservizi, è consigliabile scegliere disponibilità e tolleranza di errore e si deve togliere coerenza assoluta. Pertanto, in applicazioni basate su microservizio più recenti, in genere non si desidera utilizzare transazioni distribuite nella messaggistica, come avviene quando si implementa [transazioni distribuite](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) dipende la transazione distribuita di Windows Coordinator (DTC) con [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).

Necessario tornare al primo rilascio e il relativo esempio. Se il servizio si blocca dopo aver aggiornato il database (in questo caso, a destra dopo la riga di codice con \_contesto. SaveChangesAsync()), ma prima che l'evento di integrazione viene pubblicato, l'intero sistema potrebbe risultare incoerente. Potrebbe trattarsi di business critico, a seconda dell'operazione di business specifici che si sta utilizzando.

Come accennato in precedenza nella sezione architettura, è possibile visualizzare diversi approcci per la gestione di questo problema:

-   Utilizzo del completa [modello di determinazione dell'origine evento](https://msdn.microsoft.com/en-us/library/dn589792.aspx).

-   Utilizzando [data mining del log delle transazioni](http://www.scoop.it/t/sql-server-transaction-log-mining).

-   Utilizzo di [modello di posta in uscita](http://gistlabs.com/2014/05/the-outbox/). Si tratta di una tabella transazionale per archiviare gli eventi di integrazione (estensione della transazione locale).

Per questo scenario, usando il modello di determinazione dell'origine evento (ES) completo è uno degli approcci migliori, in caso contrario *il* migliore. In molti scenari di applicazione, tuttavia, potrebbe non essere in grado di implementare un sistema ES completo. ES implica l'archiviazione solo gli eventi di dominio nel database transazionale, anziché archiviare i dati relativi allo stato corrente. L'archiviazione solo gli eventi di dominio può avere notevoli vantaggi, ad esempio avere la cronologia di sistema disponibile ed essere in grado di determinare lo stato del sistema in qualsiasi momento nel passato. Tuttavia, l'implementazione di un intero sistema ES richiede la ridefinizione dell'architettura la maggior parte del sistema e introduce molte altre complessità e i requisiti. Ad esempio, si desidera utilizzare un database apportato in modo specifico per generare l'evento, ad esempio [archivio eventi](https://geteventstore.com/), o un database orientato ai documenti, ad esempio Azure Cosmos DB, MongoDB, Cassandra, CouchDB o RavenDB. ES costituisce l'approccio ideale per questo problema, ma non la soluzione più semplice a meno che non si ha già familiarità con l'origine evento.

L'opzione per utilizzare i log delle transazioni di data mining inizialmente è molto trasparente. Tuttavia, per utilizzare questo approccio, il microservizio deve essere agganciato del log delle transazioni RDBMS, ad esempio il registro delle transazioni di SQL Server. Si tratta probabilmente non è auspicabile. Un altro svantaggio è che gli aggiornamenti di basso livello registrati nel log delle transazioni potrebbero non essere lo stesso livello, come gli eventi di integrazione ad alto livello. In questo caso, il processo di decodifica tali operazioni del log delle transazioni possono essere difficile.

Un approccio bilanciato è una combinazione di una tabella di database transazionale e di un modello semplificato di ES. È possibile utilizzare uno stato ad esempio "pronto per la pubblicazione dell'evento,", che è impostato nell'evento originale quando eseguito il commit nella tabella di eventi di integrazione. Si tenta di pubblicare l'evento per il bus di eventi. Se l'azione di evento di pubblicazione ha esito positivo, avviare un'altra transazione nel servizio di origine e di spostare lo stato da "pronti per pubblicare l'evento" a "evento già pubblicato."

Se l'azione di pubblicazione-event bus nell'evento ha esito negativo, i dati ancora non sarà coerenti all'interno di microservizio di origine, è ancora contrassegnato come "pronti per pubblicare l'evento", e rispetto al resto dei servizi, sarà coerenza. È sempre il controllo dello stato delle transazioni o eventi di integrazione processi in background. Se il processo rileva un evento nello stato "pronto pubblicare l'evento", è possibile provare a pubblicare di nuovo tale evento per il bus di eventi.

Si noti che con questo approccio, vengono inseriti solo gli eventi di integrazione per ogni origine di microservizio e solo gli eventi che si desidera comunicare con altri microservizi o sistemi esterni. Al contrario, in un intero sistema ES, vengono memorizzate anche tutti gli eventi di dominio.

Pertanto, questo approccio bilanciato è un sistema ES semplificato. È necessario un elenco di eventi di integrazione con lo stato corrente ("pronto per la pubblicazione" e "pubblicati"). Ma è necessario implementare questi stati per gli eventi di integrazione. E questo approccio, non è necessaria archiviare tutti i dati di dominio come eventi nel database transazionale, come si farebbe in un intero sistema ES.

Se si utilizza già un database relazionale, è possibile utilizzare una tabella transazionale per archiviare gli eventi di integrazione. Per garantire l'atomicità dell'applicazione, utilizzare un processo in due passaggi basato su transazioni locali. In pratica, è presente una tabella di IntegrationEvent nello stesso database in cui le entità di dominio. Tale tabella funziona come un insurance per ottenere atomicità in modo che il licenziatario includa persistente eventi di integrazione nelle stesse transazioni vengono eseguito il commit dei dati di dominio.

Procedura dettagliata, il processo è il seguente: l'applicazione inizia una transazione di database locale. Quindi, aggiorna lo stato dell'entità di dominio e inserisce un evento nella tabella di eventi di integrazione. Infine, esegue il commit della transazione. È possibile ottenere l'atomicità desiderato.

Quando si implementa i passaggi necessari per gli eventi di pubblicazione, sono disponibili queste opzioni:

-   Pubblicazione dell'evento di integrazione subito dopo il commit della transazione e utilizzare un'altra transazione locale per contrassegnare gli eventi nella tabella viene pubblicata. Usare la tabella come un elemento per rilevare gli eventi di integrazione in caso di problemi di microservizi remoto, quindi eseguire le azioni di compensazione basate sugli eventi di integrazione stored.

-   Utilizzare la tabella come un tipo di coda. Un thread separato dell'applicazione o un processo esegue una query nella tabella di eventi di integrazione, pubblica gli eventi per il bus di eventi e quindi utilizza una transazione locale per contrassegnare gli eventi pubblicati.

Figura 8-22 illustrata l'architettura per il primo di questi approcci.

![](./media/image23.png)

**Figura 8-22**. Atomicità durante la pubblicazione di eventi per il bus di eventi

L'approccio illustrato nella figura 8-22 manca un microservizio lavoro aggiuntivi che è responsabile della verifica e che conferma la corretta degli eventi di integrazione pubblicato. In caso di errore, tale microservizio lavoro controllo aggiuntivo può leggere gli eventi dalla tabella e pubblicarli.

Descrizione del secondo approccio: usare la tabella di log eventi come una coda e utilizzare sempre un microservizio di lavoro per pubblicare i messaggi. In tal caso, il processo è, come mostrato nella figura 8-23. Viene illustrato un microservizio aggiuntivo e la tabella è l'unica origine per la pubblicazione di eventi.

![](./media/image24.png)

**Figura 8-23**. Atomicità durante la pubblicazione di eventi per il bus di eventi con un microservizio di lavoro

Per semplicità, l'esempio eShopOnContainers utilizza il primo approccio (con nessun processi aggiuntivi o controllo microservizi) oltre il bus di eventi. Tuttavia, il eShopOnContainers non gestisce tutti i casi di errori possibili. In un'applicazione reale distribuita nel cloud, è necessario adottare il fatto che i problemi si verificano alla fine ed è necessario implementare controllare e inviare di nuovo la logica. Utilizzando la tabella come una coda può essere il primo approccio più efficace se si dispone di tale tabella come un'unica origine di eventi durante la relativa pubblicazione tramite il bus di eventi.

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a>Implementazione di atomicità durante la pubblicazione di eventi di integrazione tramite il bus di eventi

Il codice seguente viene illustrato come creare una singola transazione che include più oggetti DbContext, ovvero un contesto correlato ai dati originali in corso l'aggiornamento e il contesto secondo correlata alla tabella IntegrationEventLog.

Si noti che la transazione nell'esempio di codice riportato di seguito non sarà resiliente se le connessioni al database dispone di qualsiasi problema relativo al momento in cui viene eseguito il codice. Questa situazione può verificarsi in sistemi basati su cloud come il database SQL di Azure, che potrebbe spostare database tra server. Per l'implementazione di transazioni resilienti in più contesti, vedere il [implementazione di connessioni di Entity Framework Core SQL resilienti](#implementing_resilient_EFCore_SQL_conns) sezione più avanti in questa Guida.

Per maggiore chiarezza, l'esempio seguente viene illustrato l'intero processo in un singolo frammento di codice. Tuttavia, l'implementazione di eShopOnContainers effettivamente viene effettuato il refactoring e suddivise la logica in più classi è facile da gestire.

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult>
    UpdateProduct([FromBody]CatalogItem productToUpdate)
{
    var catalogItem = await _catalogContext.CatalogItems
        .SingleOrDefaultAsync(i => i.Id == productToUpdate.Id);

    if (catalogItem == null) return NotFound();

    bool raiseProductPriceChangedEvent = false;

    IntegrationEvent priceChangedEvent = null;

    if (catalogItem.Price != productToUpdate.Price)
        raiseProductPriceChangedEvent = true;

    if (raiseProductPriceChangedEvent) // Create event if price has changed
    {
        var oldPrice = catalogItem.Price;
        priceChangedEvent = new ProductPriceChangedIntegrationEvent(catalogItem.Id,
            productToUpdate.Price,
            oldPrice);
    }

    // Update current product
    catalogItem = productToUpdate;
    // Achieving atomicity between original DB and the IntegrationEventLog
    // with a local transaction

    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);

        await _catalogContext.SaveChangesAsync();

        // Save to EventLog only if product price changed
        if(raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
   }

   // Publish to event bus only if product price changed

   if (raiseProductPriceChangedEvent)
   {
       _eventBus.Publish(priceChangedEvent);
       integrationEventLogService.MarkEventAsPublishedAsync(
           priceChangedEvent);
   }

   return Ok();
}
```

Dopo aver creato l'evento di integrazione ProductPriceChangedIntegrationEvent, la transazione contenente l'operazione di dominio originale (aggiornare l'elemento del catalogo) include anche la persistenza dell'evento nella tabella EventLog. In questo modo è una singola transazione e sarà sempre in grado di controllare se sono stati inviati messaggi di evento.

La tabella del log eventi viene aggiornata in modo atomico con l'operazione di database originale, utilizzando una transazione locale nello stesso database. Se una delle operazioni hanno esito negativo, viene generata un'eccezione e la transazione esegue il rollback di qualsiasi operazione completata, in modo da mantenere la coerenza tra le operazioni di dominio e i messaggi di eventi inviati.

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a>Ricezione di messaggi dalle sottoscrizioni: gestori nel ricevitore microservizi

Oltre alla logica di sottoscrizione di evento, è necessario implementare il codice interno per i gestori di eventi di integrazione (ad esempio un metodo di callback). Il gestore dell'evento è in cui si specifica in cui verranno ricevuti ed elaborati i messaggi di evento di un determinato tipo.

Un gestore eventi riceve un'istanza dell'evento dal bus di eventi. Quindi individua il componente di elaborazione relativi a tale evento di integrazione, moltiplicazione e salvare in modo permanente l'evento come una modifica nello stato in microservizio il ricevitore. Ad esempio, se un evento ProductPriceChanged microservizio il catalogo, viene gestita in microservizio il carrello e modifica lo stato in questo microservizio di basket ricevitore nonché, come illustrato nel codice seguente.

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.IntegrationEvents.EventHandling
{
    public class ProductPriceChangedIntegrationEventHandler :
        IIntegrationEventHandler<ProductPriceChangedIntegrationEvent>
    {
        private readonly IBasketRepository _repository;

        public ProductPriceChangedIntegrationEventHandler(
            IBasketRepository repository)
        {
            _repository = repository;
        }

        public async Task Handle(ProductPriceChangedIntegrationEvent @event)
        {
            var userIds = await _repository.GetUsers();
            foreach (var id in userIds)
            {
                var basket = await _repository.GetBasket(id);
                await UpdatePriceInBasketItems(@event.ProductId, @event.NewPrice, basket);
            }
        }

        private async Task UpdatePriceInBasketItems(int productId, decimal newPrice,
            CustomerBasket basket)
        {
            var itemsToUpdate = basket?.Items?.Where(x => int.Parse(x.ProductId) ==
                productId).ToList();
            if (itemsToUpdate != null)
            {
                foreach (var item in itemsToUpdate)
                {
                    if(item.UnitPrice != newPrice)
                    {
                        var originalPrice = item.UnitPrice;
                        item.UnitPrice = newPrice;
                        item.OldUnitPrice = originalPrice;
                    }
                }
                await _repository.UpdateBasket(basket);
            }
        }
    }
}
```

Il gestore dell'evento deve verificare se il prodotto è presente in una delle istanze del carrello. Aggiorna anche il prezzo dell'articolo per ogni voce acquisti correlati. Infine, viene creato un avviso da visualizzare all'utente sulla variazione di prezzo, come illustrato nella figura 8-24.

![](./media/image25.png)

**Figura 8-24**. Visualizzazione di una modifica di prezzo dell'elemento in un carrello, comunicato dagli eventi di integrazione

## <a name="idempotency-in-update-message-events"></a>Idempotenza negli eventi di messaggio di aggiornamento

Un aspetto importante di eventi messaggio di aggiornamento è che un errore in qualsiasi momento la comunicazione deve provocare il messaggio viene ritentata. In caso contrario, un'attività in background potrebbe provare a pubblicare un evento che è già stato pubblicato, la creazione di una race condition. È necessario per assicurarsi che gli aggiornamenti siano idempotenti o che forniscono informazioni sufficienti per garantire che è possibile rilevare un duplicato, annullare le modifiche e inviare una risposta back solo uno.

Come notato in precedenza, idempotenza significa che un'operazione può essere eseguita più volte senza modificare il risultato. In un ambiente di messaggistica, come durante la comunicazione degli eventi, un evento è idempotente se può essere distribuito più volte senza modificare il risultato per il ricevitore di microservizio. Ciò potrebbe essere necessario a causa della natura dell'evento stesso oppure a causa del modo il sistema gestisce l'evento. Messaggio idempotenza è importante in qualsiasi applicazione che utilizza la messaggistica, non solo nelle applicazioni che implementano lo schema del bus di eventi.

Un esempio di un'operazione idempotente è un'istruzione SQL che inserisce dati in una tabella solo se i dati non sono già nella tabella. Non è importante quante volte eseguire inserire l'istruzione SQL. il risultato sarà lo stesso, ovvero la tabella conterrà tali dati. Idempotenza simile al seguente può essere anche necessario quando si gestiscono i messaggi se il messaggio potrebbe potenzialmente essere inviato e pertanto elaborato solo una volta. Ad esempio, se la logica di ripetizione provoca un mittente di inviare più di una volta esattamente lo stesso messaggio, è necessario assicurarsi che sia idempotente.

È possibile progettazione idempotente messaggi. Ad esempio, è possibile creare un evento che indica che "impostare il prezzo del prodotto \$25" invece di "aggiungere \$5 per il prezzo del prodotto." In modo sicuro è Impossibile elaborare il primo messaggio qualsiasi numero di volte e il risultato sarà lo stesso. Ciò non è valido per il secondo messaggio. Ma anche nel primo caso, è possibile evitare di elaborare il primo evento, il sistema può anche avere inviato un evento di modifica di prezzo più recente e si potrebbe sovrascrivere il nuovo prezzo.

Un altro esempio potrebbe essere un evento di completamento dell'ordine viene propagato a più sottoscrittori. È importante aggiornato le informazioni sugli ordini in altri sistemi in una sola volta, anche se sono presenti eventi messaggio duplicato per l'evento di completamento dell'ordine stesso.

È consigliabile utilizzare un tipo di identità per ogni evento in modo che è possibile creare la logica che impone che ogni evento viene elaborata una sola volta per ogni destinatario.

Alcune operazioni di elaborazione del messaggio è intrinsecamente idempotente. Ad esempio, se un sistema genera le anteprime delle immagini, non è rilevante quante volte viene elaborato il messaggio relativo all'anteprima generata; il risultato è che le anteprime vengono generate e sono uguali ogni volta. D'altra parte, operazioni quali la chiamata di un gateway di pagamento per ricaricare una carta di credito potrebbero non essere idempotente affatto. In questi casi, è necessario verificare che l'elaborazione di un messaggio più volte abbia l'effetto desiderato.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Messaggio idempotenza rispettando la distinzione tra** (sottotitolo in questa pagina) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)

## <a name="deduplicating-integration-event-messages"></a>Messaggi di evento deduplicazione dell'integrazione

È possibile assicurarsi che gli eventi dei messaggi vengono inviati ed elaborati una sola volta per ogni sottoscrittore a livelli diversi. Un modo consiste nell'utilizzare una funzionalità di deduplicazione offerta dall'infrastruttura di messaggistica in uso. È possibile implementare la logica personalizzata in microservizio la destinazione. La presenza di convalide a livello di trasporto e il livello di applicazione è la scelta migliore.

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a>Deduplicazione dell'eventi di messaggio a livello di EventHandler

Un modo per assicurarsi che un evento viene elaborato una sola volta qualsiasi ricevitore è implementando determinata logica durante l'elaborazione di eventi messaggio nei gestori eventi. Ad esempio, che è l'approccio utilizzato nell'applicazione eShopOnContainers, come si può notare nel [codice sorgente](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) della classe OrdersController quando riceve un comando CreateOrderCommand. (In questo caso viene utilizzato un comando di richiesta HTTP, non un comando basata su messaggi, ma la logica che necessaria per rendere un idempotente di comando basata su messaggi è simile).

### <a name="deduplicating-messages-when-using-rabbitmq"></a>Deduplicazione del messaggi quando si utilizza RabbitMQ

Quando si verificano errori di rete intermittenti, è possono duplicare i messaggi e il destinatario del messaggio deve essere pronto per gestire questi messaggi duplicati. Se possibile, i ricevitori devono gestire i messaggi in modo idempotente, è preferibile rispetto a gestirli in modo esplicito con la deduplicazione.

In base al [RabbitMQ documentazione](https://www.rabbitmq.com/reliability.html#consumer), "se un messaggio viene recapitato a un consumer e quindi reinserito nella coda (perché non era stata riconosciuta prima di eliminata la connessione di consumer, ad esempio), RabbitMQ imposterà il flag consegnati nuovamente su in caso di cui viene recapitato nuovamente (se stesso consumer o un'altra).

Se è impostato il flag "consegnati nuovamente", il ricevitore deve considerare che, poiché il messaggio potrebbe essere già stato elaborato. Ma che non è garantito. il messaggio non potrebbe aver raggiunto mai il ricevitore dopo che lasciato il gestore di messaggi, probabilmente a causa di problemi di rete. D'altra parte, se il flag "consegnati nuovamente" non è impostato, viene garantito che il messaggio è non stato inviato più volte. Pertanto, il ricevitore deve deduplicare i messaggi o elaborare i messaggi in modo idempotente solo se è impostato il flag "consegnati nuovamente" nel messaggio.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Basato su messaggistica degli eventi**
    [*http://soapatterns.org/design\_modelli/evento\_driven\_messaggistica*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Jimmy Bogard. Refactoring verso resilienza: Valutazione accoppiamento**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)

-   **Canale di pubblicazione-sottoscrizione**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **La comunicazione tra contesti di delimitata**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)

-   **La coerenza eventuale**
    [*https://en.wikipedia.org/wiki/Eventual\_coerenza*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Philip Brown. Strategie per l'integrazione delimitata contesti**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)

-   **Chris Richardson. Sviluppo di Microservizi transazionale utilizzando funzioni di aggregazione, determinazione dell'origine evento e CQRS - parte 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)

-   **Chris Richardson. Schema di eventi sistema acquisti**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)

-   **Introduzione di determinazione dell'origine evento**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)

-   **Database dell'archivio eventi**. Sito ufficiale.
    [*https://geteventstore.com/*](https://geteventstore.com/)

-   **Patrick Nommensen. Gestione dei dati per Microservizi basata sugli eventi**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*

-   **Il teorema di CAP**
    [*https://en.wikipedia.org/wiki/CAP\_teorema*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **Che cos'è il teorema di CAP? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)

-   **Nozioni di base della coerenza dei dati**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)

-   **Rick Saling. Il teorema di CAP: Motivi per cui"tutti gli elementi diversi" con il Cloud e Internet**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)

-   **Eric Brewer. Estremità dodici anni in un secondo momento: come sono stati modificati i "Regole"**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)

-   **Che fanno parte di transazioni esterne (DTC)** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)

-   **Bus di servizio di Azure. La messaggistica negoziata: Rilevamento duplicati**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)

-   **Guida di affidabilità** (documentazione RabbitMQ) [ *https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)




>[!div class="step-by-step"]
[Precedente] [Avanti] (test-aspnet-core-services-web-apps.md) (rabbitmq-event-bus-development-test-environment.md)
