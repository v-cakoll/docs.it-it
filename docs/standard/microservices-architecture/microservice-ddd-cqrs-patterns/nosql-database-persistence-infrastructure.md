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
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a>Utilizzo di database NoSQL come un'infrastruttura di persistenza

Quando si utilizzano database NoSQL per il livello di dati di infrastruttura, in genere non si esegue una ORM come Entity Framework Core. Utilizzare l'API fornito dal motore di database NoSQL, ad esempio Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB o tabelle di archiviazione di Azure.

Tuttavia, quando si utilizza un database NoSQL, in particolare un database orientato ai documenti come Azure Cosmos DB, CouchDB o RavenDB, la modalità di progettazione del modello con aggregazioni DDD è parzialmente simile a come si può procede in Entity Framework Core, per quanto riguarda l'identificazione del radici di aggregazione, le classi di entità figlio e le classi di oggetti valore. Tuttavia, infine, la selezione del database avrà impatto nella progettazione.

Quando si utilizza un database orientato ai documenti, si implementa un'aggregazione come un unico documento, serializzato in JSON o un altro formato. Tuttavia, l'utilizzo del database è trasparente da un punto di vista di dominio modello codice. Quando si utilizza un database NoSQL, comunque utilizza le classi di entità e le classi di radice di aggregazione, ma con una maggiore flessibilità rispetto all'utilizzo di Entity Framework Core perché la persistenza non è relazionale.

La differenza consiste nel mantenere come modello. Se è implementato il modello di dominio basato su classi di entità POCO, indipendente la persistenza dell'infrastruttura, potrebbe apparire come è possibile spostare in un'infrastruttura di persistenza diverso, anche da relazionali per NoSQL. Tuttavia, che non deve essere l'obiettivo. Sono sempre presenti vincoli nei diversi database effettuerà il push si torna, pertanto, non sarà in grado di avere lo stesso modello per relazionale o nei database NoSQL. La modifica di modelli di persistenza non sarebbe superflua, in quanto le transazioni e operazioni di persistenza saranno molto diverse.

Ad esempio, in un database orientato ai documenti, è sufficiente per una radice di aggregazione di più proprietà della raccolta figlio. In un database relazionale, l'esecuzione di query più proprietà della raccolta figlio è il numero, poiché si ottiene un'istruzione SQL UNION ALL da Entity Framework. Con lo stesso modello di dominio per i database relazionali o nei database NoSQL non è semplice e non provarlo. È importante progettare il modello con una conoscenza di come i dati verrà utilizzato in ogni database specifico.

Un vantaggio quando si utilizza database NoSQL è che le entità sono più denormalizzate, in modo non si imposta un mapping di tabella. Modello di dominio può essere più flessibile rispetto all'utilizzo di un database relazionale.

Quando si progetta il modello di dominio in base alle aggregazioni, lo spostamento di database NoSQL e database orientati agli documento potrebbero essere ancora più semplici rispetto all'utilizzo di un database relazionale, poiché le aggregazioni di che progettazione sono simili a serializzare documenti in un database orientato ai documenti. È quindi possibile includere in tali contenitori"" tutte le informazioni che necessarie per tale aggregazione.

Ad esempio, il codice JSON seguente è un esempio di implementazione di un'aggregazione di ordine quando si utilizza un database orientato ai documenti. È simile all'ordine di aggregazione che sono implementate nell'esempio eShopOnContainers, ma senza l'utilizzo di Entity Framework Core sotto.

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

Quando si utilizza un C\# modello per implementare l'aggregazione da utilizzare da uno strumento come Azure Cosmos DB SDK, la funzione di aggregazione è simile a C\# classi POCO utilizzate con Entity Framework di base. La differenza consiste nella modalità di utilizzo dei livelli di applicazione e dell'infrastruttura, come illustrato nel codice seguente:

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

È possibile vedere che la modalità di utilizzo con il modello di dominio può essere simile al modo in cui che è utilizzato nel livello del modello di dominio quando l'infrastruttura è Entity Framework. È comunque possibile usare gli stessi metodi di aggregazione radice per garantire la coerenza e invarianti convalide all'interno dell'aggregazione.

Tuttavia, quando è mantenere il modello nel database NoSQL, il codice e modifica di API in modo significativo rispetto al codice di Entity Framework Core o qualsiasi altro codice relative ai database relazionali.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Modellazione dei dati in DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)

-   **Vaughn Vernon. Archivio di aggregazione di basati su dominio progettazione ideale? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)

-   **Un archivio di eventi per .NET indipendente dalla persistenza.** Repository di GitHub.
    [*https://github.com/NEventStore/NEventStore*](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
[Precedente] [Avanti] (microservice-application-layer-web-api-design.md) (infrastructure-persistence-layer-implemenation-entity-framework-core.md)
