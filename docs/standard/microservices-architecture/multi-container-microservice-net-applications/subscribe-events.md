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
# <a name="subscribing-to-events"></a><span data-ttu-id="b4c59-104">La sottoscrizione di eventi</span><span class="sxs-lookup"><span data-stu-id="b4c59-104">Subscribing to events</span></span>

<span data-ttu-id="b4c59-105">Il primo passaggio per l'utilizzo del bus di eventi è la sottoscrizione di microservizi per gli eventi da ricevere.</span><span class="sxs-lookup"><span data-stu-id="b4c59-105">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="b4c59-106">Che deve essere eseguita in microservizi il ricevitore.</span><span class="sxs-lookup"><span data-stu-id="b4c59-106">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="b4c59-107">Semplice codice seguente viene illustrato cosa microservizio ogni ricevitore deve implementare all'avvio del servizio (ovvero, all'avvio della classe), in modo che sottoscrive gli eventi è necessario.</span><span class="sxs-lookup"><span data-stu-id="b4c59-107">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the Startup class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="b4c59-108">Ad esempio, il microservizio basket.api deve sottoscrivere i messaggi ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="b4c59-108">For instance, the basket.api microservice needs to subscribe to ProductPriceChangedIntegrationEvent messages.</span></span> <span data-ttu-id="b4c59-109">Questo rende il microservizio conoscenza di eventuali modifiche per il prezzo del prodotto e permette di avvertire l'utente la modifica se il prodotto nel carrello dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-109">This makes the microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

<span data-ttu-id="b4c59-110">Quando si esegue questo codice, il sottoscrittore di microservizio sono in attesa attraverso canali RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="b4c59-110">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="b4c59-111">Quando un messaggio di tipo ProductPriceChangedIntegrationEvent arriva, il codice richiama il gestore dell'evento che viene passato al metodo ed elabora l'evento.</span><span class="sxs-lookup"><span data-stu-id="b4c59-111">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="b4c59-112">Pubblicazione di eventi tramite il bus di eventi</span><span class="sxs-lookup"><span data-stu-id="b4c59-112">Publishing events through the event bus</span></span>

<span data-ttu-id="b4c59-113">Infine, il mittente del messaggio (origine microservizio) pubblica gli eventi di integrazione con un codice simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-113">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="b4c59-114">(Si tratta di un esempio semplificato che non accetta l'atomicità in considerazione). Ogni volta che un evento deve essere propagato attraverso più microservizi, in genere subito dopo il commit di transazioni da microservizio l'origine o dati, è necessario implementare un codice simile.</span><span class="sxs-lookup"><span data-stu-id="b4c59-114">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="b4c59-115">L'oggetto di implementazione bus di eventi (basato su RabbitMQ o su un bus di servizio) in primo luogo, verrà aggiunti al costruttore controller, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c59-115">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="b4c59-116">Quindi è utilizzato da metodi del controller, come nel metodo UpdateProduct:</span><span class="sxs-lookup"><span data-stu-id="b4c59-116">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

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

<span data-ttu-id="b4c59-117">In questo caso, poiché il microservizio di origine è un semplice microservizio CRUD, tale codice viene inserito destra in un controller API Web.</span><span class="sxs-lookup"><span data-stu-id="b4c59-117">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> <span data-ttu-id="b4c59-118">In microservizi più avanzate, è stato implementato nella classe CommandHandler, destra dopo i dati originali viene eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="b4c59-118">In more advanced microservices, it could be implemented in the CommandHandler class, right after the original data is committed.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="b4c59-119">Progettazione di atomicità e resilienza quando si pubblica il bus di eventi</span><span class="sxs-lookup"><span data-stu-id="b4c59-119">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="b4c59-120">Quando si pubblicano eventi di integrazione tramite una funzionalità di messaggistica distribuita del sistema, quali il bus di eventi, è stato riscontrato il problema di aggiornamento del database originale in modo atomico e pubblicazione di un evento.</span><span class="sxs-lookup"><span data-stu-id="b4c59-120">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="b4c59-121">Ad esempio, nell'esempio semplificato illustrato in precedenza, il codice esegue il commit dei dati al database quando il prezzo del prodotto viene modificato e quindi pubblica un messaggio ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="b4c59-121">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="b4c59-122">Inizialmente, potrebbe essere essenziale che queste due operazioni di essere eseguita in modo atomico.</span><span class="sxs-lookup"><span data-stu-id="b4c59-122">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="b4c59-123">Tuttavia, se si utilizza una transazione distribuita riguardano il database e il messaggio di Service broker, come avviene nei sistemi precedenti, ad esempio [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), questa operazione è sconsigliata per i motivi descritti per il [Teorema di estremità](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="b4c59-123">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="b4c59-124">In pratica, è possibile microservizi creare sistemi scalabili e a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="b4c59-124">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="b4c59-125">Semplificando in qualche modo, il teorema di CAP è indicato che non è possibile compilare un database (o un microservizio a cui appartiene il modello) che viene continuamente disponibili, è fortemente coerente, *e* tolleranza d'errore per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-125">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="b4c59-126">È necessario scegliere due di queste tre proprietà.</span><span class="sxs-lookup"><span data-stu-id="b4c59-126">You must choose two of these three properties.</span></span>

<span data-ttu-id="b4c59-127">In architetture basate su microservizi, è consigliabile scegliere disponibilità e tolleranza di errore e si deve togliere coerenza assoluta.</span><span class="sxs-lookup"><span data-stu-id="b4c59-127">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="b4c59-128">Pertanto, in applicazioni basate su microservizio più recenti, in genere non si desidera utilizzare transazioni distribuite nella messaggistica, come avviene quando si implementa [transazioni distribuite](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) dipende la transazione distribuita di Windows Coordinator (DTC) con [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="b4c59-128">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="b4c59-129">Necessario tornare al primo rilascio e il relativo esempio.</span><span class="sxs-lookup"><span data-stu-id="b4c59-129">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="b4c59-130">Se il servizio si blocca dopo aver aggiornato il database (in questo caso, a destra dopo la riga di codice con \_contesto. SaveChangesAsync()), ma prima che l'evento di integrazione viene pubblicato, l'intero sistema potrebbe risultare incoerente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-130">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="b4c59-131">Potrebbe trattarsi di business critico, a seconda dell'operazione di business specifici che si sta utilizzando.</span><span class="sxs-lookup"><span data-stu-id="b4c59-131">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="b4c59-132">Come accennato in precedenza nella sezione architettura, è possibile visualizzare diversi approcci per la gestione di questo problema:</span><span class="sxs-lookup"><span data-stu-id="b4c59-132">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="b4c59-133">Utilizzo del completa [modello di determinazione dell'origine evento](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4c59-133">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="b4c59-134">Utilizzando [data mining del log delle transazioni](http://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="b4c59-134">Using [transaction log mining](http://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="b4c59-135">Utilizzo di [modello di posta in uscita](http://gistlabs.com/2014/05/the-outbox/).</span><span class="sxs-lookup"><span data-stu-id="b4c59-135">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="b4c59-136">Si tratta di una tabella transazionale per archiviare gli eventi di integrazione (estensione della transazione locale).</span><span class="sxs-lookup"><span data-stu-id="b4c59-136">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="b4c59-137">Per questo scenario, usando il modello di determinazione dell'origine evento (ES) completo è uno degli approcci migliori, in caso contrario *il* migliore.</span><span class="sxs-lookup"><span data-stu-id="b4c59-137">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="b4c59-138">In molti scenari di applicazione, tuttavia, potrebbe non essere in grado di implementare un sistema ES completo.</span><span class="sxs-lookup"><span data-stu-id="b4c59-138">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="b4c59-139">ES implica l'archiviazione solo gli eventi di dominio nel database transazionale, anziché archiviare i dati relativi allo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-139">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="b4c59-140">L'archiviazione solo gli eventi di dominio può avere notevoli vantaggi, ad esempio avere la cronologia di sistema disponibile ed essere in grado di determinare lo stato del sistema in qualsiasi momento nel passato.</span><span class="sxs-lookup"><span data-stu-id="b4c59-140">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="b4c59-141">Tuttavia, l'implementazione di un intero sistema ES richiede la ridefinizione dell'architettura la maggior parte del sistema e introduce molte altre complessità e i requisiti.</span><span class="sxs-lookup"><span data-stu-id="b4c59-141">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="b4c59-142">Ad esempio, si desidera utilizzare un database apportato in modo specifico per generare l'evento, ad esempio [archivio eventi](https://geteventstore.com/), o un database orientato ai documenti, ad esempio Azure Cosmos DB, MongoDB, Cassandra, CouchDB o RavenDB.</span><span class="sxs-lookup"><span data-stu-id="b4c59-142">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="b4c59-143">ES costituisce l'approccio ideale per questo problema, ma non la soluzione più semplice a meno che non si ha già familiarità con l'origine evento.</span><span class="sxs-lookup"><span data-stu-id="b4c59-143">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="b4c59-144">L'opzione per utilizzare i log delle transazioni di data mining inizialmente è molto trasparente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-144">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="b4c59-145">Tuttavia, per utilizzare questo approccio, il microservizio deve essere agganciato del log delle transazioni RDBMS, ad esempio il registro delle transazioni di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4c59-145">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="b4c59-146">Si tratta probabilmente non è auspicabile.</span><span class="sxs-lookup"><span data-stu-id="b4c59-146">This is probably not desirable.</span></span> <span data-ttu-id="b4c59-147">Un altro svantaggio è che gli aggiornamenti di basso livello registrati nel log delle transazioni potrebbero non essere lo stesso livello, come gli eventi di integrazione ad alto livello.</span><span class="sxs-lookup"><span data-stu-id="b4c59-147">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="b4c59-148">In questo caso, il processo di decodifica tali operazioni del log delle transazioni possono essere difficile.</span><span class="sxs-lookup"><span data-stu-id="b4c59-148">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="b4c59-149">Un approccio bilanciato è una combinazione di una tabella di database transazionale e di un modello semplificato di ES.</span><span class="sxs-lookup"><span data-stu-id="b4c59-149">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="b4c59-150">È possibile utilizzare uno stato ad esempio "pronto per la pubblicazione dell'evento,", che è impostato nell'evento originale quando eseguito il commit nella tabella di eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-150">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="b4c59-151">Si tenta di pubblicare l'evento per il bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-151">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="b4c59-152">Se l'azione di evento di pubblicazione ha esito positivo, avviare un'altra transazione nel servizio di origine e di spostare lo stato da "pronti per pubblicare l'evento" a "evento già pubblicato."</span><span class="sxs-lookup"><span data-stu-id="b4c59-152">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="b4c59-153">Se l'azione di pubblicazione-event bus nell'evento ha esito negativo, i dati ancora non sarà coerenti all'interno di microservizio di origine, è ancora contrassegnato come "pronti per pubblicare l'evento", e rispetto al resto dei servizi, sarà coerenza.</span><span class="sxs-lookup"><span data-stu-id="b4c59-153">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="b4c59-154">È sempre il controllo dello stato delle transazioni o eventi di integrazione processi in background.</span><span class="sxs-lookup"><span data-stu-id="b4c59-154">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="b4c59-155">Se il processo rileva un evento nello stato "pronto pubblicare l'evento", è possibile provare a pubblicare di nuovo tale evento per il bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-155">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="b4c59-156">Si noti che con questo approccio, vengono inseriti solo gli eventi di integrazione per ogni origine di microservizio e solo gli eventi che si desidera comunicare con altri microservizi o sistemi esterni.</span><span class="sxs-lookup"><span data-stu-id="b4c59-156">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="b4c59-157">Al contrario, in un intero sistema ES, vengono memorizzate anche tutti gli eventi di dominio.</span><span class="sxs-lookup"><span data-stu-id="b4c59-157">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="b4c59-158">Pertanto, questo approccio bilanciato è un sistema ES semplificato.</span><span class="sxs-lookup"><span data-stu-id="b4c59-158">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="b4c59-159">È necessario un elenco di eventi di integrazione con lo stato corrente ("pronto per la pubblicazione" e "pubblicati").</span><span class="sxs-lookup"><span data-stu-id="b4c59-159">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="b4c59-160">Ma è necessario implementare questi stati per gli eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-160">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="b4c59-161">E questo approccio, non è necessaria archiviare tutti i dati di dominio come eventi nel database transazionale, come si farebbe in un intero sistema ES.</span><span class="sxs-lookup"><span data-stu-id="b4c59-161">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="b4c59-162">Se si utilizza già un database relazionale, è possibile utilizzare una tabella transazionale per archiviare gli eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-162">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="b4c59-163">Per garantire l'atomicità dell'applicazione, utilizzare un processo in due passaggi basato su transazioni locali.</span><span class="sxs-lookup"><span data-stu-id="b4c59-163">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="b4c59-164">In pratica, è presente una tabella di IntegrationEvent nello stesso database in cui le entità di dominio.</span><span class="sxs-lookup"><span data-stu-id="b4c59-164">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="b4c59-165">Tale tabella funziona come un insurance per ottenere atomicità in modo che il licenziatario includa persistente eventi di integrazione nelle stesse transazioni vengono eseguito il commit dei dati di dominio.</span><span class="sxs-lookup"><span data-stu-id="b4c59-165">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="b4c59-166">Procedura dettagliata, il processo è il seguente: l'applicazione inizia una transazione di database locale.</span><span class="sxs-lookup"><span data-stu-id="b4c59-166">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="b4c59-167">Quindi, aggiorna lo stato dell'entità di dominio e inserisce un evento nella tabella di eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="b4c59-168">Infine, esegue il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-168">Finally, it commits the transaction.</span></span> <span data-ttu-id="b4c59-169">È possibile ottenere l'atomicità desiderato.</span><span class="sxs-lookup"><span data-stu-id="b4c59-169">You get the desired atomicity.</span></span>

<span data-ttu-id="b4c59-170">Quando si implementa i passaggi necessari per gli eventi di pubblicazione, sono disponibili queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="b4c59-170">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="b4c59-171">Pubblicazione dell'evento di integrazione subito dopo il commit della transazione e utilizzare un'altra transazione locale per contrassegnare gli eventi nella tabella viene pubblicata.</span><span class="sxs-lookup"><span data-stu-id="b4c59-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="b4c59-172">Usare la tabella come un elemento per rilevare gli eventi di integrazione in caso di problemi di microservizi remoto, quindi eseguire le azioni di compensazione basate sugli eventi di integrazione stored.</span><span class="sxs-lookup"><span data-stu-id="b4c59-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="b4c59-173">Utilizzare la tabella come un tipo di coda.</span><span class="sxs-lookup"><span data-stu-id="b4c59-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="b4c59-174">Un thread separato dell'applicazione o un processo esegue una query nella tabella di eventi di integrazione, pubblica gli eventi per il bus di eventi e quindi utilizza una transazione locale per contrassegnare gli eventi pubblicati.</span><span class="sxs-lookup"><span data-stu-id="b4c59-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="b4c59-175">Figura 8-22 illustrata l'architettura per il primo di questi approcci.</span><span class="sxs-lookup"><span data-stu-id="b4c59-175">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="b4c59-176">**Figura 8-22**.</span><span class="sxs-lookup"><span data-stu-id="b4c59-176">**Figure 8-22**.</span></span> <span data-ttu-id="b4c59-177">Atomicità durante la pubblicazione di eventi per il bus di eventi</span><span class="sxs-lookup"><span data-stu-id="b4c59-177">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="b4c59-178">L'approccio illustrato nella figura 8-22 manca un microservizio lavoro aggiuntivi che è responsabile della verifica e che conferma la corretta degli eventi di integrazione pubblicato.</span><span class="sxs-lookup"><span data-stu-id="b4c59-178">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="b4c59-179">In caso di errore, tale microservizio lavoro controllo aggiuntivo può leggere gli eventi dalla tabella e pubblicarli.</span><span class="sxs-lookup"><span data-stu-id="b4c59-179">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="b4c59-180">Descrizione del secondo approccio: usare la tabella di log eventi come una coda e utilizzare sempre un microservizio di lavoro per pubblicare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-180">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="b4c59-181">In tal caso, il processo è, come mostrato nella figura 8-23.</span><span class="sxs-lookup"><span data-stu-id="b4c59-181">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="b4c59-182">Viene illustrato un microservizio aggiuntivo e la tabella è l'unica origine per la pubblicazione di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-182">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="b4c59-183">**Figura 8-23**.</span><span class="sxs-lookup"><span data-stu-id="b4c59-183">**Figure 8-23**.</span></span> <span data-ttu-id="b4c59-184">Atomicità durante la pubblicazione di eventi per il bus di eventi con un microservizio di lavoro</span><span class="sxs-lookup"><span data-stu-id="b4c59-184">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="b4c59-185">Per semplicità, l'esempio eShopOnContainers utilizza il primo approccio (con nessun processi aggiuntivi o controllo microservizi) oltre il bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-185">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="b4c59-186">Tuttavia, il eShopOnContainers non gestisce tutti i casi di errori possibili.</span><span class="sxs-lookup"><span data-stu-id="b4c59-186">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="b4c59-187">In un'applicazione reale distribuita nel cloud, è necessario adottare il fatto che i problemi si verificano alla fine ed è necessario implementare controllare e inviare di nuovo la logica.</span><span class="sxs-lookup"><span data-stu-id="b4c59-187">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="b4c59-188">Utilizzando la tabella come una coda può essere il primo approccio più efficace se si dispone di tale tabella come un'unica origine di eventi durante la relativa pubblicazione tramite il bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-188">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="b4c59-189">Implementazione di atomicità durante la pubblicazione di eventi di integrazione tramite il bus di eventi</span><span class="sxs-lookup"><span data-stu-id="b4c59-189">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="b4c59-190">Il codice seguente viene illustrato come creare una singola transazione che include più oggetti DbContext, ovvero un contesto correlato ai dati originali in corso l'aggiornamento e il contesto secondo correlata alla tabella IntegrationEventLog.</span><span class="sxs-lookup"><span data-stu-id="b4c59-190">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="b4c59-191">Si noti che la transazione nell'esempio di codice riportato di seguito non sarà resiliente se le connessioni al database dispone di qualsiasi problema relativo al momento in cui viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="b4c59-191">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="b4c59-192">Questa situazione può verificarsi in sistemi basati su cloud come il database SQL di Azure, che potrebbe spostare database tra server.</span><span class="sxs-lookup"><span data-stu-id="b4c59-192">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="b4c59-193">Per l'implementazione di transazioni resilienti in più contesti, vedere il [implementazione di connessioni di Entity Framework Core SQL resilienti](#implementing_resilient_EFCore_SQL_conns) sezione più avanti in questa Guida.</span><span class="sxs-lookup"><span data-stu-id="b4c59-193">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](#implementing_resilient_EFCore_SQL_conns) section later in this guide.</span></span>

<span data-ttu-id="b4c59-194">Per maggiore chiarezza, l'esempio seguente viene illustrato l'intero processo in un singolo frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="b4c59-194">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="b4c59-195">Tuttavia, l'implementazione di eShopOnContainers effettivamente viene effettuato il refactoring e suddivise la logica in più classi è facile da gestire.</span><span class="sxs-lookup"><span data-stu-id="b4c59-195">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

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

<span data-ttu-id="b4c59-196">Dopo aver creato l'evento di integrazione ProductPriceChangedIntegrationEvent, la transazione contenente l'operazione di dominio originale (aggiornare l'elemento del catalogo) include anche la persistenza dell'evento nella tabella EventLog.</span><span class="sxs-lookup"><span data-stu-id="b4c59-196">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="b4c59-197">In questo modo è una singola transazione e sarà sempre in grado di controllare se sono stati inviati messaggi di evento.</span><span class="sxs-lookup"><span data-stu-id="b4c59-197">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="b4c59-198">La tabella del log eventi viene aggiornata in modo atomico con l'operazione di database originale, utilizzando una transazione locale nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="b4c59-198">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="b4c59-199">Se una delle operazioni hanno esito negativo, viene generata un'eccezione e la transazione esegue il rollback di qualsiasi operazione completata, in modo da mantenere la coerenza tra le operazioni di dominio e i messaggi di eventi inviati.</span><span class="sxs-lookup"><span data-stu-id="b4c59-199">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="b4c59-200">Ricezione di messaggi dalle sottoscrizioni: gestori nel ricevitore microservizi</span><span class="sxs-lookup"><span data-stu-id="b4c59-200">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="b4c59-201">Oltre alla logica di sottoscrizione di evento, è necessario implementare il codice interno per i gestori di eventi di integrazione (ad esempio un metodo di callback).</span><span class="sxs-lookup"><span data-stu-id="b4c59-201">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="b4c59-202">Il gestore dell'evento è in cui si specifica in cui verranno ricevuti ed elaborati i messaggi di evento di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="b4c59-202">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="b4c59-203">Un gestore eventi riceve un'istanza dell'evento dal bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-203">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="b4c59-204">Quindi individua il componente di elaborazione relativi a tale evento di integrazione, moltiplicazione e salvare in modo permanente l'evento come una modifica nello stato in microservizio il ricevitore.</span><span class="sxs-lookup"><span data-stu-id="b4c59-204">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="b4c59-205">Ad esempio, se un evento ProductPriceChanged microservizio il catalogo, viene gestita in microservizio il carrello e modifica lo stato in questo microservizio di basket ricevitore nonché, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-205">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="b4c59-206">Il gestore dell'evento deve verificare se il prodotto è presente in una delle istanze del carrello.</span><span class="sxs-lookup"><span data-stu-id="b4c59-206">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="b4c59-207">Aggiorna anche il prezzo dell'articolo per ogni voce acquisti correlati.</span><span class="sxs-lookup"><span data-stu-id="b4c59-207">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="b4c59-208">Infine, viene creato un avviso da visualizzare all'utente sulla variazione di prezzo, come illustrato nella figura 8-24.</span><span class="sxs-lookup"><span data-stu-id="b4c59-208">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="b4c59-209">**Figura 8-24**.</span><span class="sxs-lookup"><span data-stu-id="b4c59-209">**Figure 8-24**.</span></span> <span data-ttu-id="b4c59-210">Visualizzazione di una modifica di prezzo dell'elemento in un carrello, comunicato dagli eventi di integrazione</span><span class="sxs-lookup"><span data-stu-id="b4c59-210">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="b4c59-211">Idempotenza negli eventi di messaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b4c59-211">Idempotency in update message events</span></span>

<span data-ttu-id="b4c59-212">Un aspetto importante di eventi messaggio di aggiornamento è che un errore in qualsiasi momento la comunicazione deve provocare il messaggio viene ritentata.</span><span class="sxs-lookup"><span data-stu-id="b4c59-212">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="b4c59-213">In caso contrario, un'attività in background potrebbe provare a pubblicare un evento che è già stato pubblicato, la creazione di una race condition.</span><span class="sxs-lookup"><span data-stu-id="b4c59-213">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="b4c59-214">È necessario per assicurarsi che gli aggiornamenti siano idempotenti o che forniscono informazioni sufficienti per garantire che è possibile rilevare un duplicato, annullare le modifiche e inviare una risposta back solo uno.</span><span class="sxs-lookup"><span data-stu-id="b4c59-214">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="b4c59-215">Come notato in precedenza, idempotenza significa che un'operazione può essere eseguita più volte senza modificare il risultato.</span><span class="sxs-lookup"><span data-stu-id="b4c59-215">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="b4c59-216">In un ambiente di messaggistica, come durante la comunicazione degli eventi, un evento è idempotente se può essere distribuito più volte senza modificare il risultato per il ricevitore di microservizio.</span><span class="sxs-lookup"><span data-stu-id="b4c59-216">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="b4c59-217">Ciò potrebbe essere necessario a causa della natura dell'evento stesso oppure a causa del modo il sistema gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="b4c59-217">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="b4c59-218">Messaggio idempotenza è importante in qualsiasi applicazione che utilizza la messaggistica, non solo nelle applicazioni che implementano lo schema del bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-218">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="b4c59-219">Un esempio di un'operazione idempotente è un'istruzione SQL che inserisce dati in una tabella solo se i dati non sono già nella tabella.</span><span class="sxs-lookup"><span data-stu-id="b4c59-219">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="b4c59-220">Non è importante quante volte eseguire inserire l'istruzione SQL. il risultato sarà lo stesso, ovvero la tabella conterrà tali dati.</span><span class="sxs-lookup"><span data-stu-id="b4c59-220">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="b4c59-221">Idempotenza simile al seguente può essere anche necessario quando si gestiscono i messaggi se il messaggio potrebbe potenzialmente essere inviato e pertanto elaborato solo una volta.</span><span class="sxs-lookup"><span data-stu-id="b4c59-221">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="b4c59-222">Ad esempio, se la logica di ripetizione provoca un mittente di inviare più di una volta esattamente lo stesso messaggio, è necessario assicurarsi che sia idempotente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-222">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="b4c59-223">È possibile progettazione idempotente messaggi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-223">It is possible to design idempotent messages.</span></span> <span data-ttu-id="b4c59-224">Ad esempio, è possibile creare un evento che indica che "impostare il prezzo del prodotto \$25" invece di "aggiungere \$5 per il prezzo del prodotto."</span><span class="sxs-lookup"><span data-stu-id="b4c59-224">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="b4c59-225">In modo sicuro è Impossibile elaborare il primo messaggio qualsiasi numero di volte e il risultato sarà lo stesso.</span><span class="sxs-lookup"><span data-stu-id="b4c59-225">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="b4c59-226">Ciò non è valido per il secondo messaggio.</span><span class="sxs-lookup"><span data-stu-id="b4c59-226">That is not true for the second message.</span></span> <span data-ttu-id="b4c59-227">Ma anche nel primo caso, è possibile evitare di elaborare il primo evento, il sistema può anche avere inviato un evento di modifica di prezzo più recente e si potrebbe sovrascrivere il nuovo prezzo.</span><span class="sxs-lookup"><span data-stu-id="b4c59-227">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="b4c59-228">Un altro esempio potrebbe essere un evento di completamento dell'ordine viene propagato a più sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="b4c59-228">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="b4c59-229">È importante aggiornato le informazioni sugli ordini in altri sistemi in una sola volta, anche se sono presenti eventi messaggio duplicato per l'evento di completamento dell'ordine stesso.</span><span class="sxs-lookup"><span data-stu-id="b4c59-229">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="b4c59-230">È consigliabile utilizzare un tipo di identità per ogni evento in modo che è possibile creare la logica che impone che ogni evento viene elaborata una sola volta per ogni destinatario.</span><span class="sxs-lookup"><span data-stu-id="b4c59-230">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="b4c59-231">Alcune operazioni di elaborazione del messaggio è intrinsecamente idempotente.</span><span class="sxs-lookup"><span data-stu-id="b4c59-231">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="b4c59-232">Ad esempio, se un sistema genera le anteprime delle immagini, non è rilevante quante volte viene elaborato il messaggio relativo all'anteprima generata; il risultato è che le anteprime vengono generate e sono uguali ogni volta.</span><span class="sxs-lookup"><span data-stu-id="b4c59-232">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="b4c59-233">D'altra parte, operazioni quali la chiamata di un gateway di pagamento per ricaricare una carta di credito potrebbero non essere idempotente affatto.</span><span class="sxs-lookup"><span data-stu-id="b4c59-233">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="b4c59-234">In questi casi, è necessario verificare che l'elaborazione di un messaggio più volte abbia l'effetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b4c59-234">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b4c59-235">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b4c59-235">Additional resources</span></span>

-   <span data-ttu-id="b4c59-236">**Messaggio idempotenza rispettando la distinzione tra** (sottotitolo in questa pagina) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4c59-236">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="b4c59-237">Messaggi di evento deduplicazione dell'integrazione</span><span class="sxs-lookup"><span data-stu-id="b4c59-237">Deduplicating integration event messages</span></span>

<span data-ttu-id="b4c59-238">È possibile assicurarsi che gli eventi dei messaggi vengono inviati ed elaborati una sola volta per ogni sottoscrittore a livelli diversi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-238">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="b4c59-239">Un modo consiste nell'utilizzare una funzionalità di deduplicazione offerta dall'infrastruttura di messaggistica in uso.</span><span class="sxs-lookup"><span data-stu-id="b4c59-239">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="b4c59-240">È possibile implementare la logica personalizzata in microservizio la destinazione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-240">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="b4c59-241">La presenza di convalide a livello di trasporto e il livello di applicazione è la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="b4c59-241">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="b4c59-242">Deduplicazione dell'eventi di messaggio a livello di EventHandler</span><span class="sxs-lookup"><span data-stu-id="b4c59-242">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="b4c59-243">Un modo per assicurarsi che un evento viene elaborato una sola volta qualsiasi ricevitore è implementando determinata logica durante l'elaborazione di eventi messaggio nei gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="b4c59-243">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="b4c59-244">Ad esempio, che è l'approccio utilizzato nell'applicazione eShopOnContainers, come si può notare nel [codice sorgente](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) della classe OrdersController quando riceve un comando CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="b4c59-244">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="b4c59-245">(In questo caso viene utilizzato un comando di richiesta HTTP, non un comando basata su messaggi, ma la logica che necessaria per rendere un idempotente di comando basata su messaggi è simile).</span><span class="sxs-lookup"><span data-stu-id="b4c59-245">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="b4c59-246">Deduplicazione del messaggi quando si utilizza RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="b4c59-246">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="b4c59-247">Quando si verificano errori di rete intermittenti, è possono duplicare i messaggi e il destinatario del messaggio deve essere pronto per gestire questi messaggi duplicati.</span><span class="sxs-lookup"><span data-stu-id="b4c59-247">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="b4c59-248">Se possibile, i ricevitori devono gestire i messaggi in modo idempotente, è preferibile rispetto a gestirli in modo esplicito con la deduplicazione.</span><span class="sxs-lookup"><span data-stu-id="b4c59-248">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="b4c59-249">In base al [RabbitMQ documentazione](https://www.rabbitmq.com/reliability.html#consumer), "se un messaggio viene recapitato a un consumer e quindi reinserito nella coda (perché non era stata riconosciuta prima di eliminata la connessione di consumer, ad esempio), RabbitMQ imposterà il flag consegnati nuovamente su in caso di cui viene recapitato nuovamente (se stesso consumer o un'altra).</span><span class="sxs-lookup"><span data-stu-id="b4c59-249">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="b4c59-250">Se è impostato il flag "consegnati nuovamente", il ricevitore deve considerare che, poiché il messaggio potrebbe essere già stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="b4c59-250">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="b4c59-251">Ma che non è garantito. il messaggio non potrebbe aver raggiunto mai il ricevitore dopo che lasciato il gestore di messaggi, probabilmente a causa di problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="b4c59-251">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="b4c59-252">D'altra parte, se il flag "consegnati nuovamente" non è impostato, viene garantito che il messaggio è non stato inviato più volte.</span><span class="sxs-lookup"><span data-stu-id="b4c59-252">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="b4c59-253">Pertanto, il ricevitore deve deduplicare i messaggi o elaborare i messaggi in modo idempotente solo se è impostato il flag "consegnati nuovamente" nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="b4c59-253">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b4c59-254">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b4c59-254">Additional resources</span></span>

-   <span data-ttu-id="b4c59-255">**Basato su messaggistica degli eventi**
    [*http://soapatterns.org/design\_modelli/evento\_driven\_messaggistica*](http://soapatterns.org/design_patterns/event_driven_messaging)</span><span class="sxs-lookup"><span data-stu-id="b4c59-255">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="b4c59-256">**Jimmy Bogard. Refactoring verso resilienza: Valutazione accoppiamento**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="b4c59-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="b4c59-257">**Canale di pubblicazione-sottoscrizione**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="b4c59-257">**Publish-Subscribe channel**
[*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="b4c59-258">**La comunicazione tra contesti di delimitata**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4c59-258">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="b4c59-259">**La coerenza eventuale**
    [*https://en.wikipedia.org/wiki/Eventual\_coerenza*](https://en.wikipedia.org/wiki/Eventual_consistency)</span><span class="sxs-lookup"><span data-stu-id="b4c59-259">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="b4c59-260">**Philip Brown. Strategie per l'integrazione delimitata contesti**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="b4c59-260">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="b4c59-261">**Chris Richardson. Sviluppo di Microservizi transazionale utilizzando funzioni di aggregazione, determinazione dell'origine evento e CQRS - parte 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="b4c59-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="b4c59-262">**Chris Richardson. Schema di eventi sistema acquisti**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="b4c59-262">**Chris Richardson. Event Sourcing pattern**
[*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="b4c59-263">**Introduzione di determinazione dell'origine evento**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4c59-263">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="b4c59-264">**Database dell'archivio eventi**.</span><span class="sxs-lookup"><span data-stu-id="b4c59-264">**Event Store database**.</span></span> <span data-ttu-id="b4c59-265">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="b4c59-265">Official site.</span></span>
    [<span data-ttu-id="b4c59-266">*https://geteventstore.com/*</span><span class="sxs-lookup"><span data-stu-id="b4c59-266">*https://geteventstore.com/*</span></span>](https://geteventstore.com/)

-   <span data-ttu-id="b4c59-267">**Patrick Nommensen. Gestione dei dati per Microservizi basata sugli eventi**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*</span><span class="sxs-lookup"><span data-stu-id="b4c59-267">**Patrick Nommensen. Event-Driven Data Management for Microservices**
*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> *</span></span>

-   <span data-ttu-id="b4c59-268">**Il teorema di CAP**
    [*https://en.wikipedia.org/wiki/CAP\_teorema*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="b4c59-268">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="b4c59-269">**Che cos'è il teorema di CAP? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="b4c59-269">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="b4c59-270">**Nozioni di base della coerenza dei dati**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4c59-270">**Data Consistency Primer**
[*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="b4c59-271">**Rick Saling. Il teorema di CAP: Motivi per cui"tutti gli elementi diversi" con il Cloud e Internet**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="b4c59-271">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="b4c59-272">**Eric Brewer. Estremità dodici anni in un secondo momento: come sono stati modificati i "Regole"**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="b4c59-272">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="b4c59-273">**Che fanno parte di transazioni esterne (DTC)** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span><span class="sxs-lookup"><span data-stu-id="b4c59-273">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="b4c59-274">**Bus di servizio di Azure. La messaggistica negoziata: Rilevamento duplicati**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="b4c59-274">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="b4c59-275">**Guida di affidabilità** (documentazione RabbitMQ) [ *https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span><span class="sxs-lookup"><span data-stu-id="b4c59-275">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="b4c59-276">[Precedente] [Avanti] (test-aspnet-core-services-web-apps.md) (rabbitmq-event-bus-development-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="b4c59-276">[Previous] (rabbitmq-event-bus-development-test-environment.md) [Next] (test-aspnet-core-services-web-apps.md)</span></span>
