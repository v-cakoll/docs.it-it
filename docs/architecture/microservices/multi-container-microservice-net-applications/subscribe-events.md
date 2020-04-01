---
title: Sottoscrizione di eventi
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni sui dettagli di pubblicazione e sottoscrizione di eventi di integrazione.
ms.date: 01/30/2020
ms.openlocfilehash: 3bfcdb1766a15b1a8e8deab46055f14e1791c2cc
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523601"
---
# <a name="subscribing-to-events"></a><span data-ttu-id="18460-103">Sottoscrizione di eventi</span><span class="sxs-lookup"><span data-stu-id="18460-103">Subscribing to events</span></span>

<span data-ttu-id="18460-104">Il primo passaggio per poter usare il bus eventi consiste nel sottoscrivere i microservizi agli eventi che devono ricevere.</span><span class="sxs-lookup"><span data-stu-id="18460-104">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="18460-105">Tale operazione deve essere eseguita nei microservizi di tipo ricevitore.</span><span class="sxs-lookup"><span data-stu-id="18460-105">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="18460-106">Il semplice codice seguente mostra che cosa ogni microservizio di tipo ricevitore deve implementare all'avvio del servizio, ovvero nella classe `Startup`, per poter sottoscrivere gli eventi necessari.</span><span class="sxs-lookup"><span data-stu-id="18460-106">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the `Startup` class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="18460-107">In questo caso il microservizio `basket-api` deve sottoscrivere i messaggi `ProductPriceChangedIntegrationEvent` e `OrderStartedIntegrationEvent`.</span><span class="sxs-lookup"><span data-stu-id="18460-107">In this case, the `basket-api` microservice needs to subscribe to `ProductPriceChangedIntegrationEvent` and the `OrderStartedIntegrationEvent` messages.</span></span>

<span data-ttu-id="18460-108">Con la sottoscrizione dell'evento `ProductPriceChangedIntegrationEvent`, ad esempio, il microservizio basket è in grado di riconoscere eventuali modifiche apportate al prezzo di un prodotto e di avvertire l'utente della modifica se tale prodotto è presente nel carrello dell'utente.</span><span class="sxs-lookup"><span data-stu-id="18460-108">For instance, when subscribing to the `ProductPriceChangedIntegrationEvent` event, that makes the basket microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent,
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent,
                   OrderStartedIntegrationEventHandler>();

```

<span data-ttu-id="18460-109">Dopo l'esecuzione di questo codice il microservizio del sottoscrittore sarà in ascolto tramite i canali RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="18460-109">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="18460-110">Quando arrivano messaggi di tipo ProductPriceChangedIntegrationEvent, il codice richiama il gestore dell'evento che è stato passato ad esso ed elabora l'evento.</span><span class="sxs-lookup"><span data-stu-id="18460-110">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="18460-111">Pubblicazione di eventi tramite il bus di eventi</span><span class="sxs-lookup"><span data-stu-id="18460-111">Publishing events through the event bus</span></span>

<span data-ttu-id="18460-112">Il mittente del messaggio (microservizio di origine) pubblica infine gli eventi di integrazione con codice simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="18460-112">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="18460-113">(Questo è un esempio semplificato che non tiene conto dell'atomicità). È necessario implementare codice simile ogni volta che un evento deve essere propagato tra più microservizi, in genere subito dopo il commit di dati o transazioni dal microservizio di origine.</span><span class="sxs-lookup"><span data-stu-id="18460-113">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="18460-114">Per iniziare, l'oggetto di implementazione del bus di eventi (basato su RabbitMQ o su un bus di servizio) verrà inserito a livello del costruttore del costruttore, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="18460-114">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="18460-115">L'oggetto può quindi essere usato dai metodi del controller, come nel metodo UpdateProduct:</span><span class="sxs-lookup"><span data-stu-id="18460-115">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

```csharp
[Route("items")]
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

<span data-ttu-id="18460-116">In questo caso, dal momento che il microservizio di origine è un semplice microservizio CRUD, tale codice viene inserito direttamente in un controller API Web.</span><span class="sxs-lookup"><span data-stu-id="18460-116">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span>

<span data-ttu-id="18460-117">In microservizi più avanzati, ad esempio quando si usano approcci basati su CQRS, può essere implementato nella classe `CommandHandler`, all'interno del metodo `Handle()`.</span><span class="sxs-lookup"><span data-stu-id="18460-117">In more advanced microservices, like when using CQRS approaches, it can be implemented in the `CommandHandler` class, within the `Handle()` method.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="18460-118">Progettazione di atomicità e resilienza quando si esegue la pubblicazione nel bus di eventi</span><span class="sxs-lookup"><span data-stu-id="18460-118">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="18460-119">Quando si pubblicano eventi di integrazione tramite un sistema di messaggistica distribuito, quale il bus di eventi, si presenta il problema dell'aggiornamento del database originale e della pubblicazione di un evento in modo atomico (ovvero, il completamento di entrambe le operazioni o di nessuna delle due).</span><span class="sxs-lookup"><span data-stu-id="18460-119">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event (that is, either both operations complete or none of them).</span></span> <span data-ttu-id="18460-120">Nell'esempio semplificato illustrato in precedenza il codice esegue, ad esempio, il commit dei dati nel database in caso di modifica del prezzo del prodotto e quindi pubblica un messaggio ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="18460-120">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="18460-121">Inizialmente, potrebbe risultare fondamentale che queste due operazioni vengano eseguite in modo atomico.</span><span class="sxs-lookup"><span data-stu-id="18460-121">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="18460-122">Se però si usa una transazione distribuita che interessa il database e il broker messaggi, come in sistemi meno recenti quali [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), questo approccio non è consigliabile per i motivi descritti dal [teorema CAP](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="18460-122">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="18460-123">In pratica, si usano i microservizi per creare sistemi scalabili e a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="18460-123">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="18460-124">Per semplificare, il teorema CAP afferma che non è possibile creare un database (distribuito), o un microservizio proprietario del proprio modello, che sia continuamente disponibile, assolutamente coerente *e* tollerante di qualsiasi partizione.</span><span class="sxs-lookup"><span data-stu-id="18460-124">Simplifying somewhat, the CAP theorem says that you cannot build a (distributed) database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="18460-125">È necessario scegliere due di queste tre proprietà.</span><span class="sxs-lookup"><span data-stu-id="18460-125">You must choose two of these three properties.</span></span>

<span data-ttu-id="18460-126">Nelle architetture basate su microservizi è consigliabile scegliere disponibilità e tolleranza, dando minore importanza alla coerenza assoluta.</span><span class="sxs-lookup"><span data-stu-id="18460-126">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="18460-127">Di conseguenza, nella maggior parte delle moderne applicazioni basate su microservizi si preferisce in genere non usare transazioni distribuite nella messaggistica, come si fa quando si implementano le [transazioni distribuite](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) basate su Windows Distributed Transaction Coordinator (DTC) con [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="18460-127">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="18460-128">Torniamo indietro al problema iniziale e al relativo esempio.</span><span class="sxs-lookup"><span data-stu-id="18460-128">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="18460-129">Se si verifica un arresto anomalo del servizio dopo l'aggiornamento del database (in questo caso, subito dopo la riga di codice con \_context.SaveChangesAsync()), ma prima della pubblicazione dell'evento di integrazione, l'intero sistema potrebbe risultare incoerente.</span><span class="sxs-lookup"><span data-stu-id="18460-129">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="18460-130">Potrebbe trattarsi di un problema business critical, a seconda della specifica operazione di business gestita.</span><span class="sxs-lookup"><span data-stu-id="18460-130">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="18460-131">Come accennato in precedenza nella sezione relativa all'architettura, è possibile adottare diversi approcci per gestire questo problema:</span><span class="sxs-lookup"><span data-stu-id="18460-131">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

- <span data-ttu-id="18460-132">Uso dello [schema Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing) completo.</span><span class="sxs-lookup"><span data-stu-id="18460-132">Using the full [Event Sourcing pattern](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).</span></span>

- <span data-ttu-id="18460-133">Uso dell'[estrazione del log delle transazioni](https://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="18460-133">Using [transaction log mining](https://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

- <span data-ttu-id="18460-134">Uso dello [schema Outbox](https://www.kamilgrzybek.com/design/the-outbox-pattern/).</span><span class="sxs-lookup"><span data-stu-id="18460-134">Using the [Outbox pattern](https://www.kamilgrzybek.com/design/the-outbox-pattern/).</span></span> <span data-ttu-id="18460-135">Si tratta di una tabella transazionale per archiviare gli eventi di integrazione (estendendo la transazione locale).</span><span class="sxs-lookup"><span data-stu-id="18460-135">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="18460-136">Per questo scenario uno degli approcci migliori, se non *il* migliore, consiste nell'usare lo schema Event Sourcing completo.</span><span class="sxs-lookup"><span data-stu-id="18460-136">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="18460-137">In molti scenari di applicazione, tuttavia, potrebbe non essere possibile implementare un sistema Event Sourcing completo.</span><span class="sxs-lookup"><span data-stu-id="18460-137">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="18460-138">Lo schema Event Sourcing implica l'archiviazione dei soli eventi di dominio nel database transazionale, anziché dei dati relativi allo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="18460-138">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="18460-139">L'archiviazione dei soli eventi di dominio può presentare notevoli vantaggi, consentendo ad esempio di poter disporre della cronologia di sistema e poter determinare lo stato del sistema in qualsiasi momento nel passato.</span><span class="sxs-lookup"><span data-stu-id="18460-139">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="18460-140">L'implementazione di un sistema Event Sourcing completo richiede però la ridefinizione dell'architettura della maggior parte del sistema e implica molti altri requisiti e complessità.</span><span class="sxs-lookup"><span data-stu-id="18460-140">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="18460-141">Si supponga, ad esempio, di voler usare un database appositamente pensato per lo schema Event Sourcing, come [Event Store](https://eventstore.org/), oppure un database orientato ai documenti, come Azure Cosmos DB, MongoDB, Cassandra, CouchDB o RavenDB.</span><span class="sxs-lookup"><span data-stu-id="18460-141">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://eventstore.org/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="18460-142">Lo schema Event Sourcing costituisce un valido approccio a questo problema, ma non è la soluzione più semplice a meno che non si abbia già familiarità con Event Sourcing.</span><span class="sxs-lookup"><span data-stu-id="18460-142">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="18460-143">L'approccio basato sull'estrazione del log delle transazioni sembra inizialmente molto agevole.</span><span class="sxs-lookup"><span data-stu-id="18460-143">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="18460-144">Per usare questo approccio, però, è necessario accoppiare il microservizio al log delle transazioni RDBMS, ad esempio il log delle transazioni di SQL Server</span><span class="sxs-lookup"><span data-stu-id="18460-144">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="18460-145">e questo non è auspicabile.</span><span class="sxs-lookup"><span data-stu-id="18460-145">This is probably not desirable.</span></span> <span data-ttu-id="18460-146">Un altro svantaggio è che gli aggiornamenti di basso livello registrati nel log delle transazioni potrebbero non essere allo stesso livello degli eventi di integrazione di alto livello.</span><span class="sxs-lookup"><span data-stu-id="18460-146">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="18460-147">In questo caso il processo di decompilazione di tali operazioni del log delle transazioni può risultare complesso.</span><span class="sxs-lookup"><span data-stu-id="18460-147">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="18460-148">Per un approccio bilanciato è possibile combinare una tabella di database transazionale e un schema Event Sourcing semplificato.</span><span class="sxs-lookup"><span data-stu-id="18460-148">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="18460-149">È possibile usare uno stato quale "pronto per la pubblicazione dell'evento", che viene impostato nell'evento originale quando se ne esegue il commit nella tabella eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="18460-149">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="18460-150">Si prova quindi a pubblicare l'evento nel bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-150">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="18460-151">Se l'azione dell'evento di pubblicazione riesce, si può avviare un'altra transazione nel servizio di origine e cambiare lo stato da "pronto per la pubblicazione dell'evento" in "evento già pubblicato".</span><span class="sxs-lookup"><span data-stu-id="18460-151">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="18460-152">Se l'azione dell'evento di pubblicazione nel bus di eventi non riesce, i dati non saranno ancora incoerenti all'interno di microservizio di origine (perché sono ancora contrassegnati come "pronto per la pubblicazione dell'evento") e alla fine saranno coerenti rispetto al resto dei servizi.</span><span class="sxs-lookup"><span data-stu-id="18460-152">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="18460-153">È sempre possibile usare processi in background per controllare lo stato delle transazioni o degli eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="18460-153">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="18460-154">Se il processo trova un evento nello stato "pronto per la pubblicazione dell'evento", può provare a ripubblicarlo nel il bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-154">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="18460-155">Si noti che con questo approccio, si rendono persistenti solo gli eventi di integrazione per ogni microservizio di origine e solo gli eventi che si vogliono comunicare ad altri microservizi o sistemi esterni.</span><span class="sxs-lookup"><span data-stu-id="18460-155">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="18460-156">Al contrario, in un sistema Event Sourcing, vengono archiviati anche tutti gli eventi di dominio.</span><span class="sxs-lookup"><span data-stu-id="18460-156">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="18460-157">Questo approccio bilanciato è quindi un sistema Event Sourcing semplificato.</span><span class="sxs-lookup"><span data-stu-id="18460-157">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="18460-158">È necessario un elenco di eventi di integrazione con lo stato corrente ("pronto per la pubblicazione" e "pubblicato"),</span><span class="sxs-lookup"><span data-stu-id="18460-158">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="18460-159">ma è necessario implementare questi stati solo per gli eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="18460-159">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="18460-160">In questo approccio, inoltre, non è necessario archiviare tutti i dati di dominio come eventi nel database transazionale, come si farebbe in un sistema Event Sourcing completo.</span><span class="sxs-lookup"><span data-stu-id="18460-160">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="18460-161">Se si usa già un database relazionale, è possibile usare una tabella transazionale peer archiviare gli eventi di integrazione.</span><span class="sxs-lookup"><span data-stu-id="18460-161">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="18460-162">Per ottenere l'atomicità nell'applicazione, si usa un processo in due passaggi basato su transazioni locali.</span><span class="sxs-lookup"><span data-stu-id="18460-162">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="18460-163">In pratica, nello stesso database che contiene le entità di dominio è presente una tabella IntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="18460-163">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="18460-164">Tale tabella funge da assicurazione per garantire l'atomicità in modo che gli eventi di integrazione persistenti vengano inclusi nelle stesse transazioni che stanno eseguendo il commit dei dati di dominio.</span><span class="sxs-lookup"><span data-stu-id="18460-164">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="18460-165">Nel dettaglio il processo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="18460-165">Step by step, the process goes like this:</span></span>

1. <span data-ttu-id="18460-166">L'applicazione avvia una transazione di database locale.</span><span class="sxs-lookup"><span data-stu-id="18460-166">The application begins a local database transaction.</span></span>

2. <span data-ttu-id="18460-167">quindi aggiorna lo stato delle entità di dominio e inserisce un evento nella tabella eventi di integrazione</span><span class="sxs-lookup"><span data-stu-id="18460-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span>

3. <span data-ttu-id="18460-168">Infine esegue il commit della transazione, in modo da consentire di ottenere l'atomicità desiderata e quindi</span><span class="sxs-lookup"><span data-stu-id="18460-168">Finally, it commits the transaction, so you get the desired atomicity and then</span></span>

4. <span data-ttu-id="18460-169">L'evento viene pubblicato in qualche modo (passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="18460-169">You publish the event somehow (next).</span></span>

<span data-ttu-id="18460-170">Quando si implementano i passaggi per la pubblicazione degli eventi, è possibile scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="18460-170">When implementing the steps of publishing the events, you have these choices:</span></span>

- <span data-ttu-id="18460-171">Pubblicare l'evento di integrazione subito dopo il commit della transazione e usare un'altra transazione locale per contrassegnare gli eventi nella tabella come in corso di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="18460-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="18460-172">Usare quindi la tabella come un artefatto per tenere traccia degli eventi di integrazione in caso di problemi nei microservizi remoti ed eseguire le azioni di compensazione sulla base degli eventi di integrazione archiviati.</span><span class="sxs-lookup"><span data-stu-id="18460-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

- <span data-ttu-id="18460-173">Usare la tabella come una sorta di coda.</span><span class="sxs-lookup"><span data-stu-id="18460-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="18460-174">Un processo o un thread applicazione separato esegue una query sulla tabella eventi di integrazione, pubblica gli eventi nel bus di eventi e quindi usa una transazione locale per contrassegnare gli eventi come pubblicati.</span><span class="sxs-lookup"><span data-stu-id="18460-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="18460-175">La figura 6-22 illustra l'architettura relativa al primo di questi approcci.</span><span class="sxs-lookup"><span data-stu-id="18460-175">Figure 6-22 shows the architecture for the first of these approaches.</span></span>

![Diagramma dell'atomicità durante la pubblicazione senza un microservizio di lavoro.](./media/subscribe-events/atomicity-publish-event-bus.png)

<span data-ttu-id="18460-177">**Figura 6-22**.</span><span class="sxs-lookup"><span data-stu-id="18460-177">**Figure 6-22**.</span></span> <span data-ttu-id="18460-178">Atomicità durante la pubblicazione di eventi nel bus di eventi</span><span class="sxs-lookup"><span data-stu-id="18460-178">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="18460-179">Nell'approccio illustrato nella figura 6-22 manca un microservizio worker aggiuntivo che è responsabile della verifica e della conferma del completamento degli eventi di integrazione pubblicati.</span><span class="sxs-lookup"><span data-stu-id="18460-179">The approach illustrated in Figure 6-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="18460-180">In caso di errore, il microservizio worker aggiuntivo è in grado di leggere gli eventi dalla tabella e ripubblicarli, ovvero di ripetere il passaggio numero 2.</span><span class="sxs-lookup"><span data-stu-id="18460-180">In case of failure, that additional checker worker microservice can read events from the table and republish them, that is, repeat step number 2.</span></span>

<span data-ttu-id="18460-181">Nel secondo approccio si usa invece la tabella EventLog come coda e si usa sempre un microservizio worker per pubblicare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="18460-181">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="18460-182">Il processo corrispondente è simile a quello illustrato nella figura 6-23,</span><span class="sxs-lookup"><span data-stu-id="18460-182">In that case, the process is like that shown in Figure 6-23.</span></span> <span data-ttu-id="18460-183">in cui viene illustrato un microservizio aggiuntivo, mentre la tabella è l'unica origine durante la pubblicazione di eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-183">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![Diagramma dell'atomicità durante la pubblicazione con un microservizio di lavoro.](./media/subscribe-events/atomicity-publish-worker-microservice.png)

<span data-ttu-id="18460-185">**Figura 6-23**.</span><span class="sxs-lookup"><span data-stu-id="18460-185">**Figure 6-23**.</span></span> <span data-ttu-id="18460-186">Atomicità durante la pubblicazione di eventi nel bus di eventi con un microservizio worker</span><span class="sxs-lookup"><span data-stu-id="18460-186">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="18460-187">Per semplicità, nell'esempio eShopOnContainers viene usato il primo approccio (senza processi o microservizi di controllo aggiuntivi) oltre al bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-187">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="18460-188">eShopOnContainers non gestisce però tutti i possibili casi di errore.</span><span class="sxs-lookup"><span data-stu-id="18460-188">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="18460-189">In un'applicazione reale distribuita nel cloud è necessario accettare il fatto che i problemi sono inevitabili e che è necessario implementare la logica di verifica e reinvio.</span><span class="sxs-lookup"><span data-stu-id="18460-189">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="18460-190">L'uso della tabella come coda può essere più efficace rispetto al primo approccio se la tabella costituisce l'unica origine degli eventi durante la pubblicazione (con il worker) tramite il bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-190">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them (with the worker) through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="18460-191">Implementazione dell'atomicità durante la pubblicazione di eventi di integrazione tramite il bus di eventi</span><span class="sxs-lookup"><span data-stu-id="18460-191">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="18460-192">Il codice seguente mostra come creare una singola transazione che interessa più oggetti DbContext, ovvero un contesto correlato ai dati originali da aggiornare e un secondo contesto correlato alla tabella IntegrationEventLog.</span><span class="sxs-lookup"><span data-stu-id="18460-192">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="18460-193">Si noti che la transazione nell'esempio di codice seguente non sarà resiliente se le connessioni al database presentano problemi nel momento in cui viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="18460-193">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="18460-194">Questa situazione può verificarsi in sistemi basati sul cloud come Azure SQL DB, che potrebbe spostare database tra server.</span><span class="sxs-lookup"><span data-stu-id="18460-194">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="18460-195">Per l'implementazione di transazioni resilienti in più contesti, vedere la sezione [Implementazione di connessioni SQL resilienti di Entity Framework Core](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) più avanti in questa guida.</span><span class="sxs-lookup"><span data-stu-id="18460-195">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) section later in this guide.</span></span>

<span data-ttu-id="18460-196">Per chiarezza l'esempio seguente mostra l'intero processo in un unico frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="18460-196">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="18460-197">L'implementazione di eShopOnContainers viene in realtà sottoposta a refactoring e questa logica viene suddivisa in più classi in modo che sia più facilmente gestibile.</span><span class="sxs-lookup"><span data-stu-id="18460-197">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem productToUpdate)
{
  var catalogItem =
       await _catalogContext.CatalogItems.SingleOrDefaultAsync(i => i.Id ==
                                                               productToUpdate.Id);
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

  // Just save the updated product if the Product's Price hasn't changed.
  if (!raiseProductPriceChangedEvent)
  {
      await _catalogContext.SaveChangesAsync();
  }
  else  // Publish to event bus only if product price changed
  {
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

      // Publish the integration event through the event bus
      _eventBus.Publish(priceChangedEvent);

      _integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent);
  }

  return Ok();
}

```

<span data-ttu-id="18460-198">Dopo la creazione dell'evento di integrazione ProductPriceChangedIntegrationEvent, la transazione in cui è archiviata l'operazione di dominio originale (aggiornamento dell'elemento del catalogo) include anche la persistenza dell'evento nella tabella EventLog.</span><span class="sxs-lookup"><span data-stu-id="18460-198">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="18460-199">In questo modo diventa una singola transazione e sarà sempre possibile verificare se i messaggi di evento sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="18460-199">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="18460-200">La tabella del log eventi viene aggiornata in modo atomico con l'operazione di database originale, usando una transazione locale sullo stesso database.</span><span class="sxs-lookup"><span data-stu-id="18460-200">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="18460-201">Se una qualsiasi delle operazioni non riesce, viene generata un'eccezione e la transazione esegue il rollback di qualsiasi operazione completata, in modo da garantire la coerenza tra le operazioni di dominio e i messaggi di evento salvati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="18460-201">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages saved to the table.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="18460-202">Ricezione di messaggi dalle sottoscrizioni: gestori degli eventi in microservizi di tipo ricevitore</span><span class="sxs-lookup"><span data-stu-id="18460-202">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="18460-203">Oltre alla logica di sottoscrizione degli eventi, è necessario implementare il codice interno per i gestori degli eventi di integrazione, ad esempio un metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="18460-203">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="18460-204">Nel gestore dell'evento viene specificato dove verranno ricevuti ed elaborati i messaggi di evento di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="18460-204">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="18460-205">Un gestore dell'evento riceve prima un'istanza di evento dal bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-205">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="18460-206">Successivamente individua il componente da elaborare in relazione all'evento di integrazione, propagando l'evento e rendendolo persistente come modifica di stato nel microservizio di tipo ricevitore.</span><span class="sxs-lookup"><span data-stu-id="18460-206">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="18460-207">Ad esempio, se un evento ProductPriceChanged ha origine nel microservizio Catalog, viene gestito nel microservizio basket e cambia lo stato in questo microservizio Basket di tipo ricevitore, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="18460-207">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="18460-208">Il gestore dell'evento deve verificare se il prodotto è presente in una delle istanze del carrello,</span><span class="sxs-lookup"><span data-stu-id="18460-208">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="18460-209">aggiorna il prezzo dell'articolo per ogni articolo del carrello correlato</span><span class="sxs-lookup"><span data-stu-id="18460-209">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="18460-210">e infine crea un avviso da visualizzare all'utente sulla variazione di prezzo, come illustrato nella figura 6-24.</span><span class="sxs-lookup"><span data-stu-id="18460-210">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 6-24.</span></span>

![Screenshot di un browser che mostra la notifica di modifica del prezzo nel carrello utente.](./media/subscribe-events/display-item-price-change.png)

<span data-ttu-id="18460-212">**Figura 6-24**.</span><span class="sxs-lookup"><span data-stu-id="18460-212">**Figure 6-24**.</span></span> <span data-ttu-id="18460-213">Visualizzazione di una variazione di prezzo dell'articolo in un carrello, comunicato dagli eventi di integrazione</span><span class="sxs-lookup"><span data-stu-id="18460-213">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="18460-214">Idempotenza negli eventi dei messaggi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="18460-214">Idempotency in update message events</span></span>

<span data-ttu-id="18460-215">Un aspetto importante degli eventi dei messaggi di aggiornamento è che il messaggio deve essere nuovamente inviato in seguito a un errore che si verifica in un qualsiasi punto nelle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="18460-215">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="18460-216">In caso contrario, un'attività in background potrebbe provare a pubblicare un evento che è già stato pubblicato, creando una condizione di race condition.</span><span class="sxs-lookup"><span data-stu-id="18460-216">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="18460-217">È necessario assicurarsi che gli aggiornamenti siano idempotenti o che forniscano informazioni sufficienti a garantire il rilevamento di un duplicato, la sua rimozione e il reinvio di una sola risposta.</span><span class="sxs-lookup"><span data-stu-id="18460-217">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="18460-218">Come notato in precedenza, con il termine idempotenza si indica un'operazione che può essere eseguita più volte senza modificare il risultato.</span><span class="sxs-lookup"><span data-stu-id="18460-218">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="18460-219">In un ambiente di messaggistica, come durante la comunicazione di eventi, un evento è idempotente se può essere recapitato più volte senza modificare il risultato per il microservizio di tipo ricevitore.</span><span class="sxs-lookup"><span data-stu-id="18460-219">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="18460-220">Tale condizione potrebbe essere necessaria in virtù della natura dell'evento stesso o del modo in cui il sistema gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="18460-220">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="18460-221">L'idempotenza dei messaggi è importante in qualsiasi applicazione che usa la messaggistica, non solo nelle applicazioni che implementano lo schema del bus di eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-221">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="18460-222">Un esempio di un'operazione idempotente è dato da un'istruzione SQL che inserisce dati in una tabella solo se i dati non sono già presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="18460-222">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="18460-223">Non conta il numero di volte in cui si esegue l'istruzione SQL di inserimento: il risultato sarà lo stesso, ovvero la tabella conterrà tali dati.</span><span class="sxs-lookup"><span data-stu-id="18460-223">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="18460-224">Un tale tipo di idempotenza può essere necessario anche quando si gestiscono i messaggi se il messaggio potrebbe potenzialmente essere inviato e di conseguenza elaborato più di una volta.</span><span class="sxs-lookup"><span data-stu-id="18460-224">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="18460-225">Se, ad esempio, in base alla logica di ripetizione un mittente invia più volte lo stesso messaggio, è necessario assicurarsi che sia idempotente.</span><span class="sxs-lookup"><span data-stu-id="18460-225">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="18460-226">È possibile progettare messaggi idempotenti.</span><span class="sxs-lookup"><span data-stu-id="18460-226">It is possible to design idempotent messages.</span></span> <span data-ttu-id="18460-227">Ad esempio, è possibile creare un evento che indica "imposta il prezzo del prodotto su 25 USD" invece di "aggiungi 5 USD al prezzo del prodotto".</span><span class="sxs-lookup"><span data-stu-id="18460-227">For example, you can create an event that says "set the product price to $25" instead of "add $5 to the product price."</span></span> <span data-ttu-id="18460-228">Mentre è possibile elaborare senza problemi il primo messaggio un qualsiasi numero di volte, ottenendo sempre lo stesso risultato,</span><span class="sxs-lookup"><span data-stu-id="18460-228">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="18460-229">non si può dire altrettanto per il secondo messaggio.</span><span class="sxs-lookup"><span data-stu-id="18460-229">That is not true for the second message.</span></span> <span data-ttu-id="18460-230">Ma anche nel primo caso è possibile che non si voglia elaborare il primo evento perché il sistema potrebbe aver inviato un evento di variazione del prezzo più recente e l'elaborazione del primo evento causerebbe la sovrascrittura del nuovo prezzo.</span><span class="sxs-lookup"><span data-stu-id="18460-230">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="18460-231">Un altro esempio è dato da un evento di completamento dell'ordine che viene propagato a più sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="18460-231">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="18460-232">È importante che le informazioni sugli ordini vengano aggiornate in altri sistemi una sola volta, anche se sono presenti eventi di messaggio duplicati per lo stesso evento di completamento dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="18460-232">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="18460-233">È consigliabile definire un certo tipo di identità per ogni evento in modo che sia possibile creare la logica in base alla quale ogni evento deve essere elaborato una sola volta per ogni ricevitore.</span><span class="sxs-lookup"><span data-stu-id="18460-233">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="18460-234">Alcune operazioni di elaborazione dei messaggi sono intrinsecamente idempotenti.</span><span class="sxs-lookup"><span data-stu-id="18460-234">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="18460-235">Se, ad esempio, un sistema genera le anteprime delle immagini, non conta il numero di volte in cui viene elaborato il messaggio relativo all'anteprima generata. Il risultato è che le anteprime vengono generate e sono uguali ogni volta.</span><span class="sxs-lookup"><span data-stu-id="18460-235">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="18460-236">D'altra parte, operazioni quali la chiamata di un gateway di pagamento per ricaricare una carta di credito potrebbero non essere affatto idempotenti.</span><span class="sxs-lookup"><span data-stu-id="18460-236">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="18460-237">In questi casi è necessario assicurarsi che l'effetto dell'elaborazione di un messaggio per più volte sia quello desiderato.</span><span class="sxs-lookup"><span data-stu-id="18460-237">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="18460-238">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="18460-238">Additional resources</span></span>

- <span data-ttu-id="18460-239">**Riconoscimento dell'idempotency dei messaggiHonoring message idempotency** </span><span class="sxs-lookup"><span data-stu-id="18460-239">**Honoring message idempotency** </span></span>\
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591565(v=pandp.10)#honoring-message-idempotency>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="18460-240">Deduplicazione dei messaggi degli eventi di integrazione</span><span class="sxs-lookup"><span data-stu-id="18460-240">Deduplicating integration event messages</span></span>

<span data-ttu-id="18460-241">È possibile assicurarsi che gli eventi dei messaggi vengano inviati ed elaborati una sola volta per ogni sottoscrittore a livelli diversi.</span><span class="sxs-lookup"><span data-stu-id="18460-241">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="18460-242">Un modo consiste nell'usare una funzionalità di deduplicazione offerta dall'infrastruttura di messaggistica in uso.</span><span class="sxs-lookup"><span data-stu-id="18460-242">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="18460-243">Un altro consiste nell'implementare logica personalizzata nel microservizio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="18460-243">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="18460-244">La scelta migliore consiste nell'eseguire convalide sia a livello di trasporto che a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="18460-244">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="18460-245">Deduplicazione degli eventi di messaggio a livello di gestore dell'evento</span><span class="sxs-lookup"><span data-stu-id="18460-245">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="18460-246">Un modo per assicurarsi che un evento venga elaborato una sola volta da qualsiasi ricevitore consiste nell'implementare una determinata logica durante l'elaborazione degli eventi dei messaggi nei gestori degli eventi.</span><span class="sxs-lookup"><span data-stu-id="18460-246">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="18460-247">Questo è ad esempio l'approccio usato nell'applicazione eShopOnContainers, come si può vedere nel [codice sorgente della classe UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) quando riceve un evento di integrazione UserCheckoutAcceptedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="18460-247">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code of the UserCheckoutAcceptedIntegrationEventHandler class](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) when it receives an UserCheckoutAcceptedIntegrationEvent integration event.</span></span> <span data-ttu-id="18460-248">In questo caso viene eseguire il wrapping di CreateOrderCommand con un elemento IdentifiedCommand, usando eventMsg.RequestId come identificatore, prima di inviarlo al gestore comandi.</span><span class="sxs-lookup"><span data-stu-id="18460-248">(In this case we wrap the CreateOrderCommand with an IdentifiedCommand, using the eventMsg.RequestId as an identifier, before sending it to the command handler).</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="18460-249">Deduplicazione dei messaggi quando si usa RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="18460-249">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="18460-250">Quando si verificano errori di rete intermittenti, è possono duplicare i messaggi, ma il ricevitore dei messaggi deve essere pronto per gestire questi messaggi duplicati.</span><span class="sxs-lookup"><span data-stu-id="18460-250">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="18460-251">Se possibile, i ricevitori devono gestire i messaggi in modo idempotente. Questo approccio è preferibile rispetto a quando vengono gestiti in modo esplicito con la deduplicazione.</span><span class="sxs-lookup"><span data-stu-id="18460-251">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="18460-252">Secondo quando indicato nella [documentazione di RabbitMQ](https://www.rabbitmq.com/reliability.html#consumer), "se un messaggio viene recapitato a un consumer e quindi reinserito nella coda, perché ad esempio non è stato confermato prima dell'eliminazione della connessione al consumer, RabbitMQ imposterà il flag di nuovo recapito dopo il successivo recapito allo stesso o a un altro consumer.</span><span class="sxs-lookup"><span data-stu-id="18460-252">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="18460-253">Se il flag di nuovo recapito è impostato, il ricevitore deve tenerlo in considerazione perché il messaggio potrebbe essere già stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="18460-253">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="18460-254">Questo non è però garantito. Il messaggio potrebbe non aver mai raggiunto il ricevitore dopo che ha lasciato il broker di messaggi, probabilmente a causa di problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="18460-254">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="18460-255">D'altra parte, se il flag di nuovo recapito non è impostato, si può essere certi che il messaggio non è stato inviato più volte.</span><span class="sxs-lookup"><span data-stu-id="18460-255">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="18460-256">Il ricevitore deve quindi deduplicare i messaggi o elaborarli in modo idempotente solo se nel messaggio è impostato il flag di nuovo recapito.</span><span class="sxs-lookup"><span data-stu-id="18460-256">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="18460-257">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="18460-257">Additional resources</span></span>

- <span data-ttu-id="18460-258">**Forked eShopOnContainers tramite NServiceBus (software particolare)** </span><span class="sxs-lookup"><span data-stu-id="18460-258">**Forked eShopOnContainers using NServiceBus (Particular Software)** </span></span>\
    <https://go.particular.net/eShopOnContainers>

- <span data-ttu-id="18460-259">**Messaggi guidati da eventi** </span><span class="sxs-lookup"><span data-stu-id="18460-259">**Event Driven Messaging** </span></span>\
    <https://patterns.arcitura.com/soa-patterns/design_patterns/event_driven_messaging>

- <span data-ttu-id="18460-260">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling** </span><span class="sxs-lookup"><span data-stu-id="18460-260">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling** </span></span>\
    <https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/>

- <span data-ttu-id="18460-261">**Canale Publish-Subscribe** </span><span class="sxs-lookup"><span data-stu-id="18460-261">**Publish-Subscribe channel** </span></span>\
    <https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html>

- <span data-ttu-id="18460-262">**Comunicazione tra contesti delimitati** </span><span class="sxs-lookup"><span data-stu-id="18460-262">**Communicating Between Bounded Contexts** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591572(v=pandp.10)>

- <span data-ttu-id="18460-263">**Eventuale coerenza** </span><span class="sxs-lookup"><span data-stu-id="18460-263">**Eventual Consistency** </span></span>\
    <https://en.wikipedia.org/wiki/Eventual_consistency>

- <span data-ttu-id="18460-264">**Philip Brown. Strategie per l'integrazione di contesti delimitati** </span><span class="sxs-lookup"><span data-stu-id="18460-264">**Philip Brown. Strategies for Integrating Bounded Contexts** </span></span>\
    <https://www.culttt.com/2014/11/26/strategies-integrating-bounded-contexts/>

- <span data-ttu-id="18460-265">**Chris Richardson. Sviluppo di microservizi transazionali mediante aggregazioni, approvvigionamento di eventi e CQRS - Parte 2** </span><span class="sxs-lookup"><span data-stu-id="18460-265">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2** </span></span>\
    <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson>

- <span data-ttu-id="18460-266">**Chris Richardson. Modello di approvvigionamento di eventi** </span><span class="sxs-lookup"><span data-stu-id="18460-266">**Chris Richardson. Event Sourcing pattern** </span></span>\
    <https://microservices.io/patterns/data/event-sourcing.html>

- <span data-ttu-id="18460-267">**Presentazione dell'evento Sourcing** </span><span class="sxs-lookup"><span data-stu-id="18460-267">**Introducing Event Sourcing** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591559(v=pandp.10)>

- <span data-ttu-id="18460-268">**Database di Event Store**.</span><span class="sxs-lookup"><span data-stu-id="18460-268">**Event Store database**.</span></span> <span data-ttu-id="18460-269">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="18460-269">Official site.</span></span> \
    <https://geteventstore.com/>

- <span data-ttu-id="18460-270">**Patrick Nommensen. Gestione dei dati basata su eventi per i microservizi** </span><span class="sxs-lookup"><span data-stu-id="18460-270">**Patrick Nommensen. Event-Driven Data Management for Microservices** </span></span>\
    <https://dzone.com/articles/event-driven-data-management-for-microservices-1>

- <span data-ttu-id="18460-271">**Teorema della PAC** </span><span class="sxs-lookup"><span data-stu-id="18460-271">**The CAP Theorem** </span></span>\
    <https://en.wikipedia.org/wiki/CAP_theorem>

- <span data-ttu-id="18460-272">**Che cos'è il teorema CAP**</span><span class="sxs-lookup"><span data-stu-id="18460-272">**What is CAP Theorem?**</span></span> \
    <https://www.quora.com/What-Is-CAP-Theorem-1>

- <span data-ttu-id="18460-273">**Primer di coerenza dei dati** </span><span class="sxs-lookup"><span data-stu-id="18460-273">**Data Consistency Primer** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/dn589800(v=pandp.10)>

- <span data-ttu-id="18460-274">**Rick Saling. Teorema CAP: Perché "tutto è diverso" con il cloud e Internet** </span><span class="sxs-lookup"><span data-stu-id="18460-274">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet** </span></span>\
    <https://docs.microsoft.com/archive/blogs/rickatmicrosoft/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/>

- <span data-ttu-id="18460-275">**Eric Brewer. CAP Dodici anni dopo: come sono cambiate le "regole"** </span><span class="sxs-lookup"><span data-stu-id="18460-275">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed** </span></span>\
    <https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed>

- <span data-ttu-id="18460-276">**Bus di servizio di Azure.Azure Service Bus. Messaggistica negoziata: rilevamento duplicati**  </span><span class="sxs-lookup"><span data-stu-id="18460-276">**Azure Service Bus. Brokered Messaging: Duplicate Detection**  </span></span>\
    <https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25>

- <span data-ttu-id="18460-277">**Reliability Guide** (Guida all'affidabilità), documentazione RabbitMQ </span><span class="sxs-lookup"><span data-stu-id="18460-277">**Reliability Guide** (RabbitMQ documentation) </span></span>\
    <https://www.rabbitmq.com/reliability.html#consumer>

> [!div class="step-by-step"]
> <span data-ttu-id="18460-278">[Successivo](rabbitmq-event-bus-development-test-environment.md)
> [precedente](test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="18460-278">[Previous](rabbitmq-event-bus-development-test-environment.md)
[Next](test-aspnet-core-services-web-apps.md)</span></span>
