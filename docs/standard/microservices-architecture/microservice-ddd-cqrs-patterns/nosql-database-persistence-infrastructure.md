---
title: Uso di database NoSQL come infrastruttura di persistenza
description: Architettura di Microservizi .NET per applicazioni .NET in contenitori | Informazioni sull'uso di database NoSQL in generale e di Azure Cosmos DB in particolare come opzione per l'implementazione della persistenza.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/08/2018
ms.openlocfilehash: 720c33fb4af197198f8ee1a21c5e1dc6dad24ce3
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150865"
---
# <a name="use-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="8949a-103">Usare i database NoSQL come infrastruttura di persistenza</span><span class="sxs-lookup"><span data-stu-id="8949a-103">Use NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="8949a-104">Quando si usano i database NoSQL per il livello dati dell'infrastruttura, in genere non si usa un ORM come Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="8949a-104">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="8949a-105">bensì l'API fornita dal motore NoSQL, ad esempio Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB o dalle tabelle di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="8949a-105">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="8949a-106">Tuttavia, quando si usa un database NoSQL, in particolare un database orientato ai documenti come Azure Cosmos DB, CouchDB o RavenDB, la modalità di progettazione del modello con aggregazioni DDD è quasi analoga a quella usata in EF Core, per quanto riguarda l'identificazione delle radici di aggregazione, delle classi di entità figlio e delle classi di oggetti valore.</span><span class="sxs-lookup"><span data-stu-id="8949a-106">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="8949a-107">In definitiva, quindi, la selezione del database influirà sulla progettazione.</span><span class="sxs-lookup"><span data-stu-id="8949a-107">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="8949a-108">Quando si usa un database orientato ai documenti, si implementa un'aggregazione come singolo documento, serializzato in JSON o in un altro formato.</span><span class="sxs-lookup"><span data-stu-id="8949a-108">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="8949a-109">Tuttavia, l'uso del database è trasparente dal punto di vista del codice del modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="8949a-109">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="8949a-110">Quando si usa un database NoSQL, si usano comunque le classi di entità e le classi di radici di aggregazione, ma con una maggiore flessibilità rispetto all'uso di EF Core perché la persistenza non è relazionale.</span><span class="sxs-lookup"><span data-stu-id="8949a-110">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="8949a-111">La differenza consiste nel modo in cui viene reso persistente tale modello.</span><span class="sxs-lookup"><span data-stu-id="8949a-111">The difference is in how you persist that model.</span></span> <span data-ttu-id="8949a-112">Se è stato implementato un modello di dominio basato su classi di entità POCO, indipendenti dalla persistenza dell'infrastruttura, potrebbe sembrare che sia possibile spostarsi in un'infrastruttura di persistenza diversa, anche da relazionale a NoSQL.</span><span class="sxs-lookup"><span data-stu-id="8949a-112">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="8949a-113">L'obiettivo tuttavia non deve essere questo.</span><span class="sxs-lookup"><span data-stu-id="8949a-113">However, that should not be your goal.</span></span> <span data-ttu-id="8949a-114">Sono sempre presenti vincoli e vantaggi/svantaggi nelle diverse tecnologie di database, pertanto non è possibile avere lo stesso modello per i database relazionali o NoSQL.</span><span class="sxs-lookup"><span data-stu-id="8949a-114">There are always constraints and trade-offs in the different database technologies, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="8949a-115">Cambiare i modelli di persistenza non è semplice, perché le transazioni e le operazioni di persistenza saranno molto diverse.</span><span class="sxs-lookup"><span data-stu-id="8949a-115">Changing persistence models is not a trivial task, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="8949a-116">Ad esempio, in un database orientato ai documenti, una radice di aggregazione può avere più proprietà di raccolta figlio.</span><span class="sxs-lookup"><span data-stu-id="8949a-116">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="8949a-117">In un database relazionale l'esecuzione di query su più proprietà di raccolta figlio è difficile da ottimizzare, perché EF restituisce un'istruzione SQL UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="8949a-117">In a relational database, querying multiple child collection properties is not easily optimized, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="8949a-118">L'uso dello stesso modello di dominio per database relazionali o NoSQL non è semplice ed è sconsigliato.</span><span class="sxs-lookup"><span data-stu-id="8949a-118">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try to do it.</span></span> <span data-ttu-id="8949a-119">È importante progettare il modello avendo ben chiaro come usare i dati in ogni database specifico.</span><span class="sxs-lookup"><span data-stu-id="8949a-119">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="8949a-120">Un vantaggio quando si usano i database NoSQL è che le entità sono più denormalizzate, in modo da non dover impostare un mapping di tabelle.</span><span class="sxs-lookup"><span data-stu-id="8949a-120">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="8949a-121">Un modello di dominio può essere più flessibile rispetto all'uso di un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="8949a-121">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="8949a-122">Quando si progetta un modello di dominio basato sulle aggregazioni, il passaggio ai database NoSQL e orientati ai documenti potrebbe essere ancora più semplice rispetto all'uso di un database relazionale, perché le aggregazioni che si progettano sono simili ai documenti serializzati in un database orientato ai documenti.</span><span class="sxs-lookup"><span data-stu-id="8949a-122">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="8949a-123">È quindi possibile includere in tali "contenitori" tutte le informazioni che potrebbero essere necessarie per tale aggregazione.</span><span class="sxs-lookup"><span data-stu-id="8949a-123">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="8949a-124">Ad esempio, il codice JSON seguente è un'implementazione di esempio di un'aggregazione di un ordine quando si usa un database orientato ai documenti.</span><span class="sxs-lookup"><span data-stu-id="8949a-124">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="8949a-125">È simile all'aggregazione di un ordine implementata nell'esempio eShopOnContainers, ma senza l'uso congiunto di EF Core.</span><span class="sxs-lookup"><span data-stu-id="8949a-125">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

```json
{
    "id": "2017001",
    "orderDate": "2/25/2017",
    "buyerId": "1234567",
    "address": [
        {
        "street": "100 One Microsoft Way",
        "city": "Redmond",
        "state": "WA",
        "zip": "98052",
        "country": "U.S."
        }
    ],
    "orderItems": [
        {"id": 20170011, "productId": "123456", "productName": ".NET T-Shirt",
        "unitPrice": 25, "units": 2, "discount": 0},
        {"id": 20170012, "productId": "123457", "productName": ".NET Mug",
        "unitPrice": 15, "units": 1, "discount": 0}
    ]
}
```

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a><span data-ttu-id="8949a-126">Introduzione ad Azure Cosmos DB e all'API nativa di Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8949a-126">Introduction to Azure Cosmos DB and the native Cosmos DB API</span></span>

<span data-ttu-id="8949a-127">[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) è il servizio di database distribuito globalmente di Microsoft per le applicazioni di importanza strategica.</span><span class="sxs-lookup"><span data-stu-id="8949a-127">[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) is Microsoft's globally distributed database service for mission-critical applications.</span></span> <span data-ttu-id="8949a-128">Azure Cosmos DB offre una [distribuzione globale chiavi in mano](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), una [scalabilità elastica in termini di produttività e archiviazione](https://docs.microsoft.com/azure/cosmos-db/partition-data) a livello mondiale, latenze pari a singole unità di millisecondi al 99° percentile, [cinque livelli di coerenza ben definiti](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) e disponibilità elevata garantita, il tutto supportato da [contratti di servizio leader di settore](https://azure.microsoft.com/support/legal/sla/cosmos-db/).</span><span class="sxs-lookup"><span data-stu-id="8949a-128">Azure Cosmos DB provides [turn-key global distribution](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), [elastic scaling of throughput and storage](https://docs.microsoft.com/azure/cosmos-db/partition-data) worldwide, single-digit millisecond latencies at the 99th percentile, [five well-defined consistency levels](https://docs.microsoft.com/azure/cosmos-db/consistency-levels), and guaranteed high availability, all backed by [industry-leading SLAs](https://azure.microsoft.com/support/legal/sla/cosmos-db/).</span></span> <span data-ttu-id="8949a-129">Azure Cosmos DB [indicizza automaticamente i dati](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) senza doversi preoccupare della gestione dello schema e dell'indice.</span><span class="sxs-lookup"><span data-stu-id="8949a-129">Azure Cosmos DB [automatically indexes data](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) without requiring you to deal with schema and index management.</span></span> <span data-ttu-id="8949a-130">È multimodello e supporta modelli di dati documento, chiave-valore, grafo e a colonne.</span><span class="sxs-lookup"><span data-stu-id="8949a-130">It is multi-model and supports document, key-value, graph, and columnar data models.</span></span>

<span data-ttu-id="8949a-131">![Azure Cosmos DB è un database a bassa latenza garantita distribuito globalmente e accessibile con quattro protocolli API.</span><span class="sxs-lookup"><span data-stu-id="8949a-131">![Azure Cosmos DB is a globally distributed guaranteed low-latency database that can be accessed with four API protocols.</span></span> <span data-ttu-id="8949a-132">](./media/image19.1.png)
**Figura 7-19**.</span><span class="sxs-lookup"><span data-stu-id="8949a-132">](./media/image19.1.png)
**Figure 7-19**.</span></span> <span data-ttu-id="8949a-133">Distribuzione globale di Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8949a-133">Azure Cosmos DB global distribution</span></span>

<span data-ttu-id="8949a-134">Quando si usa un modello C\# per implementare l'aggregazione da usare con l'API di Azure Cosmos DB, l'aggregazione può essere simile alle classi POCO in C\# usate con EF Core.</span><span class="sxs-lookup"><span data-stu-id="8949a-134">When you use a C\# model to implement the aggregate to be used by the Azure Cosmos DB API, the aggregate can be similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="8949a-135">La differenza consiste nella modalità di utilizzo dai livelli applicazione e infrastruttura, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8949a-135">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH AZURE COSMOS DB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).

Order orderAggregate = new Order
{
    Id = "2017001",
    OrderDate = new DateTime(2005, 7, 1),
    BuyerId = "1234567",
    PurchaseOrderNumber = "PO18009186470"
}

Address address = new Address
{
    Street = "100 One Microsoft Way",
    City = "Redmond",
    State = "WA",
    Zip = "98052",
    Country = "U.S."
}

orderAggregate.UpdateAddress(address);

OrderItem orderItem1 = new OrderItem
{
    Id = 20170011,
    ProductId = "123456",
    ProductName = ".NET T-Shirt",
    UnitPrice = 25,
    Units = 2,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
// *** End of Domain Model Code ***

// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, orderAggregate);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

<span data-ttu-id="8949a-136">È possibile notare che la modalità di utilizzo nel modello di dominio può essere simile a quella nel livello del modello di dominio quando l'infrastruttura è EF.</span><span class="sxs-lookup"><span data-stu-id="8949a-136">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="8949a-137">È comunque possibile usare gli stessi metodi delle radici di aggregazione per garantire coerenza, invarianti e convalide all'interno dell'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="8949a-137">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="8949a-138">Tuttavia, quando si rende persistente il modello nel database NoSQL, il codice e l'API cambiano in modo significativo rispetto al codice di EF Core o a qualsiasi altro codice correlato ai database relazionali.</span><span class="sxs-lookup"><span data-stu-id="8949a-138">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

## <a name="implement-net-code-targeting-mongodb-and-azure-cosmos-db"></a><span data-ttu-id="8949a-139">Implementare il codice .NET per MongoDB e Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8949a-139">Implement .NET code targeting MongoDB and Azure Cosmos DB</span></span>

### <a name="use-azure-cosmos-db-from-net-containers"></a><span data-ttu-id="8949a-140">Usare Azure Cosmos DB dai contenitori .NET</span><span class="sxs-lookup"><span data-stu-id="8949a-140">Use Azure Cosmos DB from .NET containers</span></span>

<span data-ttu-id="8949a-141">È possibile accedere ai database Azure Cosmos DB dal codice .NET in esecuzione nei contenitori come da qualsiasi altra applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="8949a-141">You can access Azure Cosmos DB databases from .NET code running in containers, like from any other .NET application.</span></span> <span data-ttu-id="8949a-142">Ad esempio, i microservizi Locations.API e Marketing.API in eShopOnContainers vengono implementati in modo da poter usare i database Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="8949a-142">For instance, the Locations.API and Marketing.API microservices in eShopOnContainers are implemented so they can consume Azure Cosmos DB databases.</span></span>

<span data-ttu-id="8949a-143">Tuttavia, c'è una limitazione in Azure Cosmos DB per quanto riguarda l'ambiente di sviluppo Docker.</span><span class="sxs-lookup"><span data-stu-id="8949a-143">However, there’s a limitation in Azure Cosmos DB from a Docker development environment point of view.</span></span> <span data-ttu-id="8949a-144">Anche quando c'è un [emulatore di Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/local-emulator) locale in grado di essere eseguito in un computer di sviluppo locale (ad esempio, un PC), a partire dal 2017 è supportato solo Windows e non Linux.</span><span class="sxs-lookup"><span data-stu-id="8949a-144">Even when there’s a on-premises [Azure Cosmos DB Emulator](https://docs.microsoft.com/azure/cosmos-db/local-emulator) able to run in a local development machine (like a PC), as of late 2017, it just supports Windows, not Linux.</span></span> 

<span data-ttu-id="8949a-145">È anche possibile eseguire questo emulatore in Docker, ma solo per i contenitori Windows e non per i contenitori Linux.</span><span class="sxs-lookup"><span data-stu-id="8949a-145">There is also the possibility to run this emulator on Docker, but just on Windows Containers, not with Linux Containers.</span></span> <span data-ttu-id="8949a-146">Si tratta di una difficoltà iniziale per l'ambiente di sviluppo se l'applicazione viene distribuita come contenitori Linux, poiché al momento non è possibile distribuire contemporaneamente contenitori Linux e Windows in Docker per Windows.</span><span class="sxs-lookup"><span data-stu-id="8949a-146">That is an initial handicap for the development environment if your application is deployed as Linux containers, since, currently, you cannot deploy Linux and Windows Containers on Docker for Windows at the same time.</span></span> <span data-ttu-id="8949a-147">Tutti i contenitori da distribuire devono essere per Linux o per Windows.</span><span class="sxs-lookup"><span data-stu-id="8949a-147">Either all containers being deployed have to be for Linux or for Windows.</span></span>

<span data-ttu-id="8949a-148">La distribuzione ideale e più semplice per una soluzione di sviluppo/test consiste nel poter distribuire i sistemi di database come contenitori insieme ai contenitori personalizzati in modo che gli ambienti di sviluppo/test siano sempre coerenti.</span><span class="sxs-lookup"><span data-stu-id="8949a-148">The ideal and more straightforward deployment for a dev/test solution is to be able to deploy your database systems as containers along with your custom containers so your dev/test environments are always consistent.</span></span>

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a><span data-ttu-id="8949a-149">Usare l'API MongoDB per contenitori Linux/Windows di sviluppo/test locali con Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8949a-149">Use MongoDB API for local dev/test Linux/Windows containers plus Azure Cosmos DB</span></span>

<span data-ttu-id="8949a-150">I database Cosmos DB supportano l'API MongoDB per .NET, nonché il protocollo di collegamento MongoDB nativo.</span><span class="sxs-lookup"><span data-stu-id="8949a-150">Cosmos DB databases support MongoDB API for .NET as well as the native MongoDB wire protocol.</span></span> <span data-ttu-id="8949a-151">Ciò significa che usando i driver esistenti, un'applicazione scritta per MongoDB può comunicare ora con Cosmos DB e usare i database Cosmos DB anziché i database MongoDB, come illustrato nella figura 7-20.</span><span class="sxs-lookup"><span data-stu-id="8949a-151">This means that by using existing drivers, your application written for MongoDB can now communicate with Cosmos DB and use Cosmos DB databases instead of MongoDB databases, as shown in Figure 7-20.</span></span>

<span data-ttu-id="8949a-152">![Cosmos DB supporta l'API MongoDB per .NET e il protocollo di trasmissione MongoDB. È possibile passare facilmente da MongoDB a Cosmos DB.](./media/image19.2.png)
**Figura 7-20**.</span><span class="sxs-lookup"><span data-stu-id="8949a-152">![Cosmos DB supports MongoDB API for .NET and MongoDB wire protocol, you can easily switch from MongoDb to Cosmos DB.](./media/image19.2.png)
**Figure 7-20**.</span></span> <span data-ttu-id="8949a-153">Uso dell'API MongoDB e del protocollo per accedere ad Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8949a-153">Using MongoDB API and protocol to access Azure Cosmos DB</span></span>

<span data-ttu-id="8949a-154">Questo approccio è molto utile per i modelli di verifica in ambienti Docker con contenitori Linux perché l'[immagine MongoDB Docker](https://hub.docker.com/r/_/mongo/) è un'immagine multi-arch che supporta i contenitori Docker Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="8949a-154">This is a very convenient approach for proof of concepts in Docker environments with Linux containers because the [MongoDB Docker image](https://hub.docker.com/r/_/mongo/) is a multi-arch image that supports Docker Linux containers and Docker Windows containers.</span></span>

<span data-ttu-id="8949a-155">Come illustrato nell'immagine seguente, con l'API MongoDB eShopOnContainers supporta i contenitori MongoDB Linux e Windows per l'ambiente di sviluppo locale, ma è possibile passare a una soluzione cloud PaaS scalabile come Azure Cosmos DB semplicemente [modificando la stringa di connessione MongoDB in modo da puntare ad Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).</span><span class="sxs-lookup"><span data-stu-id="8949a-155">As shown in the following image, by using the MongoDB API, eShopOnContainers supports MongoDB Linux and Windows containers for the local development environment but then, you can move to a scalable, PaaS cloud solution as Azure Cosmos DB by simply [changing the MongoDB connection string to point to Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).</span></span>

<span data-ttu-id="8949a-156">![Il microservizio Locations in eShopOnContainers viene implementato usando MongoDB, ma può essere passato a Cosmos DB semplicemente modificando la stringa di connessione.](./media/image20-bis.png)
**Figura 7-21**.</span><span class="sxs-lookup"><span data-stu-id="8949a-156">![The Location microservice in eShopOnContainers is implemented using MongoDB, but can be switched over to Cosmos DB by just changing the connection string.](./media/image20-bis.png)
**Figure 7-21**.</span></span> <span data-ttu-id="8949a-157">eShopOnContainers con contenitori MongoDB per un ambiente di sviluppo o Azure Cosmos DB di produzione</span><span class="sxs-lookup"><span data-stu-id="8949a-157">eShopOnContainers using MongoDB containers for dev-env or Azure Cosmos DB for production</span></span>

<span data-ttu-id="8949a-158">Azure Cosmos DB di produzione viene eseguito nel cloud di Azure come servizio PaaS e scalabile.</span><span class="sxs-lookup"><span data-stu-id="8949a-158">The production Azure Cosmos DB would be running in Azure’s cloud as a PaaS and scalable service.</span></span>

<span data-ttu-id="8949a-159">I contenitori .NET Core personalizzati possono essere eseguiti in un host Docker di sviluppo locale (con Docker per Windows in un computer Windows 10) o essere distribuiti in un ambiente di produzione, ad esempio Kubernetes in Azure AKS o Azure Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="8949a-159">Your custom .NET Core containers can run on a local development Docker host (that is using Docker for Windows in a Windows 10 machine) or be deployed into a production environment, like Kubernetes in Azure AKS or Azure Service Fabric.</span></span> <span data-ttu-id="8949a-160">In questo secondo ambiente è possibile distribuire solo i contenitori .NET Core personalizzati ma non il contenitore MongoDB perché viene usato Azure Cosmos DB nel cloud per la gestione dei dati nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="8949a-160">In this second environment, you would deploy only the .NET Core custom containers but not the MongoDB container since you’d be using Azure Cosmos DB in the cloud for handling the data in production.</span></span>

<span data-ttu-id="8949a-161">Un evidente vantaggio dell'uso dell'API MongoDB è che la soluzione può essere eseguita in entrambi i motori di database, MongoDB o Azure Cosmos DB, pertanto le migrazioni in ambienti diversi dovrebbero risultare semplici.</span><span class="sxs-lookup"><span data-stu-id="8949a-161">A clear benefit of using the MongoDB API is that your solution could run in both database engines, MongoDB or Azure Cosmos DB, so migrations to different environments should be easy.</span></span> <span data-ttu-id="8949a-162">Tuttavia, talvolta è utile usare un'API nativa, ovvero l'API Cosmos DB nativa, per sfruttare al meglio le funzionalità di un motore di database specifico.</span><span class="sxs-lookup"><span data-stu-id="8949a-162">However, sometimes it is worthwhile to use a native API (that is the native Cosmos DB API) in order to take full advantage of the capabilities of a specific database engine.</span></span>

<span data-ttu-id="8949a-163">Per un ulteriore confronto tra l'uso di MongoDB rispetto a Cosmos DB nel cloud, vedere i [vantaggi dell'uso di Azure Cosmos DB in questa pagina](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction).</span><span class="sxs-lookup"><span data-stu-id="8949a-163">For further comparison between simply using MongoDB versus Cosmos DB in the cloud, see the [Benefits of using Azure Cosmos DB in this page](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction).</span></span> 

### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a><span data-ttu-id="8949a-164">Analizzare l'approccio per le applicazioni di produzione: API MongoDB rispetto all'API Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8949a-164">Analyze your approach for production applications: MongoDB API vs. Cosmos DB API</span></span>

<span data-ttu-id="8949a-165">In eShopOnContainers viene usata l'API MongoDB perché fondamentalmente la priorità è quella di avere un ambiente di sviluppo/test coerente con un database NoSQL che potrebbe essere usato anche con Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="8949a-165">In eShopOnContainers, we’re using MongoDB API because our priority was fundamentally to have a consistent dev/test environment using a NoSQL database that could also work with Azure Cosmos DB.</span></span>

<span data-ttu-id="8949a-166">Tuttavia, se si prevede di usare l'API MongoDB per accedere ad Azure Cosmos DB in Azure per le applicazioni di produzione, è necessario analizzare le differenze di funzionalità e prestazioni quando si usa l'API MongoDB per accedere ai database Azure Cosmos DB rispetto all'uso dell'API Azure Cosmos DB nativa.</span><span class="sxs-lookup"><span data-stu-id="8949a-166">However, if you planning to use MongoDB API to access Azure Cosmos DB in Azure for production applications, you should analyze the differences in capabilities and performance when using MongoDB API to access Azure Cosmos DB databases compared to using the native Azure Cosmos DB API.</span></span> <span data-ttu-id="8949a-167">Se non ci sono differenze, è possibile usare l'API MongoDB e sfruttare il vantaggio di supportare contemporaneamente due motori di database NoSQL.</span><span class="sxs-lookup"><span data-stu-id="8949a-167">If it is similar you can use MongoDB API and you get the benefit of supporting two NoSQL database engines at the same time.</span></span>

<span data-ttu-id="8949a-168">È anche possibile usare i cluster MongoDB come database di produzione nel cloud di Azure con il [servizio Azure MongoDB](https://www.mongodb.com/scale/mongodb-azure-service).</span><span class="sxs-lookup"><span data-stu-id="8949a-168">You could also use MongoDB clusters as the production database in Azure’s cloud, too, with [MongoDB Azure Service](https://www.mongodb.com/scale/mongodb-azure-service).</span></span> <span data-ttu-id="8949a-169">Ma non si tratta di un servizio PaaS fornito da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8949a-169">But that is not a PaaS service provided by Microsoft.</span></span> <span data-ttu-id="8949a-170">In questo caso, Azure ospita solo tale soluzione proveniente da MongoDB.</span><span class="sxs-lookup"><span data-stu-id="8949a-170">In this case, Azure is just hosting that solution coming from MongoDB.</span></span>

<span data-ttu-id="8949a-171">In pratica, è solo una dichiarazione per indicare che non è necessario usare sempre l'API MongoDB rispetto ad Azure Cosmos DB, come è stato fatto in eShopOnContainers perché rappresentava una scelta adatta per i contenitori Linux.</span><span class="sxs-lookup"><span data-stu-id="8949a-171">Basically, this is just a disclaimer stating that you shouldn’t always use MongoDB API against Azure Cosmos DB, as we did in eShopOnContainers because it was a convenient choice for Linux containers.</span></span> <span data-ttu-id="8949a-172">La decisione deve basarsi sulle esigenze specifiche e sui test che è necessario eseguire per l'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="8949a-172">The decision should be based on the specific needs and tests you need to do for your production application.</span></span>

### <a name="the-code-use-mongodb-api-in-net-core-applications"></a><span data-ttu-id="8949a-173">Il codice: usare l'API MongoDB nelle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="8949a-173">The code: Use MongoDB API in .NET Core applications</span></span>

<span data-ttu-id="8949a-174">L'API MongoDB per .NET è basata sui pacchetti NuGet che è necessario aggiungere ai progetti, come nel progetto Locations.API illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="8949a-174">MongoDB API for .NET is based on NuGet packages that you need to add to your projects, like in the Locations.API project shown in the the following figure.</span></span>

![Vista di Esplora soluzioni che visualizza le dipendenze in nei pacchetti NuGet di MongoDB.](./media/image21-bis.png)

<span data-ttu-id="8949a-176">**Figura 7-22**.</span><span class="sxs-lookup"><span data-stu-id="8949a-176">**Figure 7-22**.</span></span> <span data-ttu-id="8949a-177">Riferimenti di pacchetti NuGet dell'API MongoDB in un progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="8949a-177">MongoDB API NuGet packages references in a .NET Core project</span></span>

<span data-ttu-id="8949a-178">Il codice verrà esaminato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8949a-178">Let's investigate the code in the following sections.</span></span>

#### <a name="a-model-used-by-mongodb-api"></a><span data-ttu-id="8949a-179">Modello usato dall'API MongoDB</span><span class="sxs-lookup"><span data-stu-id="8949a-179">A Model used by MongoDB API</span></span>

<span data-ttu-id="8949a-180">In primo luogo, è necessario definire un modello che conterrà i dati provenienti dal database nello spazio di memoria dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8949a-180">First, you need to define a model that will hold the data coming from the database in your application’s memory space.</span></span> <span data-ttu-id="8949a-181">Di seguito è riportato un esempio del modello usato per Locations in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8949a-181">Here’s an example of the model used for Locations at eShopOnContainers.</span></span>

```csharp
using MongoDB.Bson;
using MongoDB.Bson.Serialization.Attributes;
using MongoDB.Driver.GeoJsonObjectModel;
using System.Collections.Generic;

public class Locations
{
    [BsonId]
    [BsonRepresentation(BsonType.ObjectId)]
    public string Id { get; set; }
    public int LocationId { get; set; }
    public string Code { get; set; }
    [BsonRepresentation(BsonType.ObjectId)]
    public string Parent_Id { get; set; }
    public string Description { get; set; }
    public double Latitude { get; set; }
    public double Longitude { get; set; }
    public GeoJsonPoint<GeoJson2DGeographicCoordinates> Location 
                                                             { get; private set; }
    public GeoJsonPolygon<GeoJson2DGeographicCoordinates> Polygon 
                                                             { get; private set; }
    public void SetLocation(double lon, double lat) => SetPosition(lon, lat);
    public void SetArea(List<GeoJson2DGeographicCoordinates> coordinatesList) 
                                                    => SetPolygon(coordinatesList);

    private void SetPosition(double lon, double lat)
    {
        Latitude = lat;
        Longitude = lon;
        Location = new GeoJsonPoint<GeoJson2DGeographicCoordinates>(
            new GeoJson2DGeographicCoordinates(lon, lat));
    }

    private void SetPolygon(List<GeoJson2DGeographicCoordinates> coordinatesList)
    {
        Polygon = new GeoJsonPolygon<GeoJson2DGeographicCoordinates>(
                  new GeoJsonPolygonCoordinates<GeoJson2DGeographicCoordinates>(
                  new GeoJsonLinearRingCoordinates<GeoJson2DGeographicCoordinates>(
                                                                 coordinatesList)));
    }
}
```

<span data-ttu-id="8949a-182">È possibile notare che ci sono alcuni attributi e tipi provenienti dai pacchetti NuGet di MongoDB.</span><span class="sxs-lookup"><span data-stu-id="8949a-182">You can see there are a few attributes and types coming from the MongoDB NuGet packages.</span></span>

<span data-ttu-id="8949a-183">I database NoSQL sono in genere particolarmente adatti per essere usati con i dati gerarchici non relazionali.</span><span class="sxs-lookup"><span data-stu-id="8949a-183">NoSQL databases are usually very well suited for working with non-relational hierarchical data.</span></span> <span data-ttu-id="8949a-184">In questo esempio vengono usati i tipi MongoDB adatti soprattutto per le geo-localizzazioni come `GeoJson2DGeographicCoordinates`.</span><span class="sxs-lookup"><span data-stu-id="8949a-184">In this example, we are using MongoDB types especially made for geo-locations, like `GeoJson2DGeographicCoordinates`.</span></span>

#### <a name="retrieve-the-database-and-the-collection"></a><span data-ttu-id="8949a-185">Recuperare il database e la raccolta</span><span class="sxs-lookup"><span data-stu-id="8949a-185">Retrieve the database and the collection</span></span>

<span data-ttu-id="8949a-186">In eShopOnContainers, è stato creato un contesto di database personalizzato in cui viene implementato il codice per recuperare il database e l'oggetto MongoCollections, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8949a-186">In eShopOnContainers, we have created a custom database context where we implement the code to retrieve the database and the MongoCollections, as in the following code.</span></span>

```csharp
public class LocationsContext
{
    private readonly IMongoDatabase _database = null;

    public LocationsContext(IOptions<LocationSettings> settings)
    {
        var client = new MongoClient(settings.Value.ConnectionString);
        if (client != null)
            _database = client.GetDatabase(settings.Value.Database);
    }

    public IMongoCollection<Locations> Locations
    {
        get
        {
            return _database.GetCollection<Locations>("Locations");
        }
    }       
}
```

#### <a name="retrieve-the-data"></a><span data-ttu-id="8949a-187">Recuperare i dati</span><span class="sxs-lookup"><span data-stu-id="8949a-187">Retrieve the data</span></span>

<span data-ttu-id="8949a-188">Nel codice C#, come i controller API Web o l'implementazione personalizzata di repository, è possibile scrivere un codice simile al seguente quando si esegue una query tramite l'API MongoDB.</span><span class="sxs-lookup"><span data-stu-id="8949a-188">In C# code, like Web API controllers or custom Repositories implementation, you can write similar code to the following when querying through the MongoDB API.</span></span> <span data-ttu-id="8949a-189">Si noti che l'oggetto `_context` è un'istanza della classe `LocationsContext` precedente.</span><span class="sxs-lookup"><span data-stu-id="8949a-189">Note that the `_context` object is an instance of the previous `LocationsContext` class.</span></span>

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a><span data-ttu-id="8949a-190">Usare una variabile di ambiente nel file docker-compose.override.yml per la stringa di connessione di MongoDB</span><span class="sxs-lookup"><span data-stu-id="8949a-190">Use an env-var in the docker-compose.override.yml file for the MongoDB connection string</span></span>

<span data-ttu-id="8949a-191">Quando si crea un oggetto MongoClient, è necessario un parametro fondamentale che è esattamente il parametro `ConnectionString` che punta al database corretto.</span><span class="sxs-lookup"><span data-stu-id="8949a-191">When creating a MongoClient object, it needs a fundamental parameter which is precisely the `ConnectionString` parameter pointing to the right database.</span></span> <span data-ttu-id="8949a-192">Nel caso di eShopOnContainers, la stringa di connessione può puntare a un contenitore Docker MongoDB locale o a un database Azure Cosmos DB di "produzione".</span><span class="sxs-lookup"><span data-stu-id="8949a-192">In the case of eShopOnContainers, the connection string can point to a local MongoDB Docker container or to a “production” Azure Cosmos DB database.</span></span>  <span data-ttu-id="8949a-193">La stringa di connessione proviene dalle variabili di ambiente definite nei file `docker-compose.override.yml` usati quando per eseguire la distribuzione con docker-compose o Visual Studio, come illustrato nel codice yml seguente.</span><span class="sxs-lookup"><span data-stu-id="8949a-193">That connection string comes from the environment variables defined in the `docker-compose.override.yml` files used when deploying with docker-compose or Visual Studio, as in the following yml code.</span></span>

```yml
# docker-compose.override.yml
version: '3.4'
services:
  # Other services
  locations.api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}

```

<span data-ttu-id="8949a-194">La variabile di ambiente `ConnectionString` viene risolta in questo modo: se la variabile globale `ESHOP_AZURE_COSMOSDB` viene definita nel file `.env` con la stringa di connessione di Azure Cosmos DB, verrà usata per accedere al database Azure Cosmos DB nel cloud.</span><span class="sxs-lookup"><span data-stu-id="8949a-194">The `ConnectionString` environment variable is resolved this way: If the `ESHOP_AZURE_COSMOSDB` global variable is defined in the `.env` file with the Azure Cosmos DB connection string, it will use it to access the Azure Cosmos DB database in the cloud.</span></span> <span data-ttu-id="8949a-195">Se non è definita, assume il valore mongodb://nosql.data e usa il contenitore mongodb di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8949a-195">If it’s not defined, it will take the mongodb://nosql.data value and use the development mongodb container.</span></span>

<span data-ttu-id="8949a-196">Il codice seguente illustra il file `.env` con la variabile di ambiente globale della stringa di connessione di Azure Cosmos DB, come implementato in eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="8949a-196">The following code shows the `.env` file with the Azure Cosmos DB connection string global environment variable, as implemented in eShopOnContainers:</span></span>

```yml
# .env file, in eShopOnContainers root folder
# Other Docker environment variables

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost
ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=<YourDockerHostIP>

#ESHOP_AZURE_COSMOSDB=<YourAzureCosmosDBConnData>

#Other environment variables for additional Azure infrastructure assets
#ESHOP_AZURE_REDIS_BASKET_DB=<YourAzureRedisBasketInfo>
#ESHOP_AZURE_STORAGE_CATALOG_URL=<YourAzureStorage_Catalog_BLOB_URL>
#ESHOP_AZURE_SERVICE_BUS=<YourAzureServiceBusInfo>
```

<span data-ttu-id="8949a-197">È necessario rimuovere il commento dalla riga ESHOP_AZURE_COSMOSDB e aggiornarla con la stringa di connessione di Azure Cosmos DB ottenuta dal portale di Azure come descritto in [Connettere un'applicazione MongoDB ad Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).</span><span class="sxs-lookup"><span data-stu-id="8949a-197">You should uncomment the ESHOP_AZURE_COSMOSDB line and update it with your Azure Cosmos DB connection string obtained from the Azure portal as explained in [Connect a MongoDB application to Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).</span></span>

<span data-ttu-id="8949a-198">Se la variabile globale `ESHOP_AZURE_COSMOSDB` è vuota, ovvero è impostata come commento nel file `.env`, il contenitore usa una stringa di connessione di MongoDB predefinita che punta al contenitore MongoDB locale distribuito in eShopOnContainers denominato `nosql.data` e definito nel file docker-compose, come illustrato nel codice yml seguente.</span><span class="sxs-lookup"><span data-stu-id="8949a-198">If the `ESHOP_AZURE_COSMOSDB` global variable is empty, meaning that it is commented out in the `.env` file, then the container uses a default MongoDB connection string pointing to the local MongoDB container deployed in eShopOnContainers which is named `nosql.data` and was defined at the docker-compose file, as shown in the following .yml code.</span></span> 

``` yml
# docker-compose.yml
version: '3.4'
services:
  # ...Other services...
  nosql.data:
    image: mongo
```

#### <a name="additional-resources"></a><span data-ttu-id="8949a-199">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8949a-199">Additional resources</span></span>

- <span data-ttu-id="8949a-200">**Modellazione dei dati di un documento per un database NoSQL** \\</span><span class="sxs-lookup"><span data-stu-id="8949a-200">**Modeling document data for NoSQL databases** \\</span></span>
  [*https://docs.microsoft.com/azure/cosmos-db/modeling-data*](https://docs.microsoft.com/azure/cosmos-db/modeling-data)

- <span data-ttu-id="8949a-201">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**</span><span class="sxs-lookup"><span data-stu-id="8949a-201">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**</span></span> \
  [*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)

- <span data-ttu-id="8949a-202">**Introduzione ad Azure Cosmos DB: API MongoDB**  \\</span><span class="sxs-lookup"><span data-stu-id="8949a-202">**Introduction to Azure Cosmos DB: API for MongoDB**  \\</span></span>
  [*https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction*](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)

- <span data-ttu-id="8949a-203">**Azure Cosmos DB: Creare un'app Web per le API MongoDB con .NET e il portale di Azure**  \\</span><span class="sxs-lookup"><span data-stu-id="8949a-203">**Azure Cosmos DB: Build a MongoDB API web app with .NET and the Azure portal**  \\</span></span>
  [*https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet*](https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet )

- <span data-ttu-id="8949a-204">**Usare l'emulatore di Azure Cosmos DB per sviluppo e test locali**  \\</span><span class="sxs-lookup"><span data-stu-id="8949a-204">**Use the Azure Cosmos DB Emulator for local development and testing**  \\</span></span>
  [*https://docs.microsoft.com/azure/cosmos-db/local-emulator*](https://docs.microsoft.com/azure/cosmos-db/local-emulator)

- <span data-ttu-id="8949a-205">**Connettere un'applicazione MongoDB ad Azure Cosmos DB**  \\</span><span class="sxs-lookup"><span data-stu-id="8949a-205">**Connect a MongoDB application to Azure Cosmos DB**  \\</span></span>
  [*https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account*](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account)

- <span data-ttu-id="8949a-206">**Immagine Docker dell'emulatore Cosmos DB (contenitore Windows)**  \\</span><span class="sxs-lookup"><span data-stu-id="8949a-206">**The Cosmos DB Emulator Docker image (Windows Container)**  \\</span></span>
  [*https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/*](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/)

- <span data-ttu-id="8949a-207">**Immagine Docker di MongoDB (contenitore Linux e Windows)**  \\</span><span class="sxs-lookup"><span data-stu-id="8949a-207">**The MongoDB Docker image (Linux and Windows Container)**  \\</span></span>
  [*https://hub.docker.com/r/_/mongo/*](https://hub.docker.com/r/_/mongo/)

- <span data-ttu-id="8949a-208">**Azure Cosmos DB: usare Studio 3T con un account API di MongoDB**  \\</span><span class="sxs-lookup"><span data-stu-id="8949a-208">**Use MongoChef (Studio 3T) with an Azure Cosmos DB: API for MongoDB account**  \\</span></span>
  [*https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef*](https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef)

>[!div class="step-by-step"]
><span data-ttu-id="8949a-209">[Precedente](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
>[Successivo](microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="8949a-209">[Previous](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
[Next](microservice-application-layer-web-api-design.md)</span></span>