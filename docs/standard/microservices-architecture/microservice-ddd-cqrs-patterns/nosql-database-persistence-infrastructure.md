---
title: Utilizzo di database NoSQL come un'infrastruttura di persistenza
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Utilizzo di database NoSQL come un'infrastruttura di persistenza
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e4b63511069b89cc5761ce7ed64f09e9035a56a3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="321ea-104">Utilizzo di database NoSQL come un'infrastruttura di persistenza</span><span class="sxs-lookup"><span data-stu-id="321ea-104">Using NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="321ea-105">Quando si utilizzano database NoSQL per il livello di dati di infrastruttura, in genere non si esegue una ORM come Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="321ea-105">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="321ea-106">Utilizzare l'API fornito dal motore di database NoSQL, ad esempio Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB o tabelle di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="321ea-106">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="321ea-107">Tuttavia, quando si utilizza un database NoSQL, in particolare un database orientato ai documenti come Azure Cosmos DB, CouchDB o RavenDB, la modalità di progettazione del modello con aggregazioni DDD è parzialmente simile a come si può procede in Entity Framework Core, per quanto riguarda l'identificazione del radici di aggregazione, le classi di entità figlio e le classi di oggetti valore.</span><span class="sxs-lookup"><span data-stu-id="321ea-107">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="321ea-108">Tuttavia, infine, la selezione del database avrà impatto nella progettazione.</span><span class="sxs-lookup"><span data-stu-id="321ea-108">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="321ea-109">Quando si utilizza un database orientato ai documenti, si implementa un'aggregazione come un unico documento, serializzato in JSON o un altro formato.</span><span class="sxs-lookup"><span data-stu-id="321ea-109">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="321ea-110">Tuttavia, l'utilizzo del database è trasparente da un punto di vista di dominio modello codice.</span><span class="sxs-lookup"><span data-stu-id="321ea-110">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="321ea-111">Quando si utilizza un database NoSQL, comunque utilizza le classi di entità e le classi di radice di aggregazione, ma con una maggiore flessibilità rispetto all'utilizzo di Entity Framework Core perché la persistenza non è relazionale.</span><span class="sxs-lookup"><span data-stu-id="321ea-111">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="321ea-112">La differenza consiste nel mantenere come modello.</span><span class="sxs-lookup"><span data-stu-id="321ea-112">The difference is in how you persist that model.</span></span> <span data-ttu-id="321ea-113">Se è implementato il modello di dominio basato su classi di entità POCO, indipendente la persistenza dell'infrastruttura, potrebbe apparire come è possibile spostare in un'infrastruttura di persistenza diverso, anche da relazionali per NoSQL.</span><span class="sxs-lookup"><span data-stu-id="321ea-113">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="321ea-114">Tuttavia, che non deve essere l'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="321ea-114">However, that should not be your goal.</span></span> <span data-ttu-id="321ea-115">Sono sempre presenti vincoli nei diversi database effettuerà il push si torna, pertanto, non sarà in grado di avere lo stesso modello per relazionale o nei database NoSQL.</span><span class="sxs-lookup"><span data-stu-id="321ea-115">There are always constraints in the different databases will push you back, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="321ea-116">La modifica di modelli di persistenza non sarebbe superflua, in quanto le transazioni e operazioni di persistenza saranno molto diverse.</span><span class="sxs-lookup"><span data-stu-id="321ea-116">Changing persistence models would not be trivial, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="321ea-117">Ad esempio, in un database orientato ai documenti, è sufficiente per una radice di aggregazione di più proprietà della raccolta figlio.</span><span class="sxs-lookup"><span data-stu-id="321ea-117">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="321ea-118">In un database relazionale, l'esecuzione di query più proprietà della raccolta figlio è il numero, poiché si ottiene un'istruzione SQL UNION ALL da Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="321ea-118">In a relational database, querying multiple child collection properties is awful, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="321ea-119">Con lo stesso modello di dominio per i database relazionali o nei database NoSQL non è semplice e non provarlo.</span><span class="sxs-lookup"><span data-stu-id="321ea-119">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try it.</span></span> <span data-ttu-id="321ea-120">È importante progettare il modello con una conoscenza di come i dati verrà utilizzato in ogni database specifico.</span><span class="sxs-lookup"><span data-stu-id="321ea-120">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="321ea-121">Un vantaggio quando si utilizza database NoSQL è che le entità sono più denormalizzate, in modo non si imposta un mapping di tabella.</span><span class="sxs-lookup"><span data-stu-id="321ea-121">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="321ea-122">Modello di dominio può essere più flessibile rispetto all'utilizzo di un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="321ea-122">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="321ea-123">Quando si progetta il modello di dominio in base alle aggregazioni, lo spostamento di database NoSQL e database orientati agli documento potrebbero essere ancora più semplici rispetto all'utilizzo di un database relazionale, poiché le aggregazioni di che progettazione sono simili a serializzare documenti in un database orientato ai documenti.</span><span class="sxs-lookup"><span data-stu-id="321ea-123">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="321ea-124">È quindi possibile includere in tali contenitori"" tutte le informazioni che necessarie per tale aggregazione.</span><span class="sxs-lookup"><span data-stu-id="321ea-124">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="321ea-125">Ad esempio, il codice JSON seguente è un esempio di implementazione di un'aggregazione di ordine quando si utilizza un database orientato ai documenti.</span><span class="sxs-lookup"><span data-stu-id="321ea-125">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="321ea-126">È simile all'ordine di aggregazione che sono implementate nell'esempio eShopOnContainers, ma senza l'utilizzo di Entity Framework Core sotto.</span><span class="sxs-lookup"><span data-stu-id="321ea-126">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

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

<span data-ttu-id="321ea-127">Quando si utilizza un C\# modello per implementare l'aggregazione da utilizzare da uno strumento come Azure Cosmos DB SDK, la funzione di aggregazione è simile a C\# classi POCO utilizzate con Entity Framework di base.</span><span class="sxs-lookup"><span data-stu-id="321ea-127">When you use a C\# model to implement the aggregate to be used by something like the Azure Cosmos DB SDK, the aggregate is similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="321ea-128">La differenza consiste nella modalità di utilizzo dei livelli di applicazione e dell'infrastruttura, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="321ea-128">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH DOCUMENTDB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).
// This can be saved as JSON as is without converting into rows/columns.
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

OrderItem orderItem2 = new OrderItem
{
    Id = 20170012,
    ProductId = "123457",
    ProductName = ".NET Mug",
    UnitPrice = 15,
    Units = 1,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);

// *** End of Domain Model Code ***
//...
// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, order);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

<span data-ttu-id="321ea-129">È possibile vedere che la modalità di utilizzo con il modello di dominio può essere simile al modo in cui che è utilizzato nel livello del modello di dominio quando l'infrastruttura è Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="321ea-129">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="321ea-130">È comunque possibile usare gli stessi metodi di aggregazione radice per garantire la coerenza e invarianti convalide all'interno dell'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="321ea-130">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="321ea-131">Tuttavia, quando è mantenere il modello nel database NoSQL, il codice e modifica di API in modo significativo rispetto al codice di Entity Framework Core o qualsiasi altro codice relative ai database relazionali.</span><span class="sxs-lookup"><span data-stu-id="321ea-131">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="321ea-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="321ea-132">Additional resources</span></span>

-   <span data-ttu-id="321ea-133">**Modellazione dei dati in DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span><span class="sxs-lookup"><span data-stu-id="321ea-133">**Modeling data in DocumentDB**
[*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span></span>

-   <span data-ttu-id="321ea-134">**Vaughn Vernon. Archivio di aggregazione di basati su dominio progettazione ideale? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span><span class="sxs-lookup"><span data-stu-id="321ea-134">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**
[*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span></span>

-   <span data-ttu-id="321ea-135">**Un archivio di eventi per .NET indipendente dalla persistenza.**</span><span class="sxs-lookup"><span data-stu-id="321ea-135">**A persistence agnostic Event Store for .NET.**</span></span> <span data-ttu-id="321ea-136">Repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="321ea-136">GitHub repo.</span></span>
    [<span data-ttu-id="321ea-137">*https://github.com/NEventStore/NEventStore*</span><span class="sxs-lookup"><span data-stu-id="321ea-137">*https://github.com/NEventStore/NEventStore*</span></span>](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
<span data-ttu-id="321ea-138">[Precedente] [Avanti] (microservice-application-layer-web-api-design.md) (infrastructure-persistence-layer-implemenation-entity-framework-core.md)</span><span class="sxs-lookup"><span data-stu-id="321ea-138">[Previous] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Next] (microservice-application-layer-web-api-design.md)</span></span>
