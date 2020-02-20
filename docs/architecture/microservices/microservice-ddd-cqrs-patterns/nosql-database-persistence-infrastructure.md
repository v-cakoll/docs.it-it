---
title: Uso di database NoSQL come infrastruttura di persistenza
description: Comprendere l'uso di database NoSql in generale e Azure Cosmos DB in particolare, come opzione per implementare la persistenza.
ms.date: 01/30/2020
ms.openlocfilehash: 7da4141d9aadc4aaa265ac97d328bc4b7569a0cb
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502380"
---
# <a name="use-nosql-databases-as-a-persistence-infrastructure"></a>Usare i database NoSQL come infrastruttura di persistenza

Quando si usano i database NoSQL per il livello dati dell'infrastruttura, in genere non si usa un ORM come Entity Framework Core bensì l'API fornita dal motore NoSQL, ad esempio Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB o dalle tabelle di archiviazione di Azure.

Tuttavia, quando si usa un database NoSQL, in particolare un database orientato ai documenti come Azure Cosmos DB, CouchDB o RavenDB, la modalità di progettazione del modello con aggregazioni DDD è quasi analoga a quella usata in EF Core, per quanto riguarda l'identificazione delle radici di aggregazione, delle classi di entità figlio e delle classi di oggetti valore. In definitiva, quindi, la selezione del database influirà sulla progettazione.

Quando si usa un database orientato ai documenti, si implementa un'aggregazione come singolo documento, serializzato in JSON o in un altro formato. Tuttavia, l'uso del database è trasparente dal punto di vista del codice del modello di dominio. Quando si usa un database NoSQL, si usano comunque le classi di entità e le classi di radici di aggregazione, ma con una maggiore flessibilità rispetto all'uso di EF Core perché la persistenza non è relazionale.

La differenza consiste nel modo in cui viene reso persistente tale modello. Se è stato implementato un modello di dominio basato su classi di entità POCO, indipendenti dalla persistenza dell'infrastruttura, potrebbe sembrare che sia possibile spostarsi in un'infrastruttura di persistenza diversa, anche da relazionale a NoSQL. L'obiettivo tuttavia non deve essere questo. Sono sempre presenti vincoli e vantaggi/svantaggi nelle diverse tecnologie di database, pertanto non è possibile avere lo stesso modello per i database relazionali o NoSQL. Cambiare i modelli di persistenza non è semplice, perché le transazioni e le operazioni di persistenza saranno molto diverse.

Ad esempio, in un database orientato ai documenti, una radice di aggregazione può avere più proprietà di raccolta figlio. In un database relazionale l'esecuzione di query su più proprietà di raccolta figlio è difficile da ottimizzare, perché EF restituisce un'istruzione SQL UNION ALL. L'uso dello stesso modello di dominio per database relazionali o NoSQL non è semplice ed è sconsigliato. È importante progettare il modello avendo ben chiaro come usare i dati in ogni database specifico.

Un vantaggio quando si usano i database NoSQL è che le entità sono più denormalizzate, in modo da non dover impostare un mapping di tabelle. Un modello di dominio può essere più flessibile rispetto all'uso di un database relazionale.

Quando si progetta un modello di dominio basato sulle aggregazioni, il passaggio ai database NoSQL e orientati ai documenti potrebbe essere ancora più semplice rispetto all'uso di un database relazionale, perché le aggregazioni che si progettano sono simili ai documenti serializzati in un database orientato ai documenti. È quindi possibile includere in tali "contenitori" tutte le informazioni che potrebbero essere necessarie per tale aggregazione.

Ad esempio, il codice JSON seguente è un'implementazione di esempio di un'aggregazione di un ordine quando si usa un database orientato ai documenti. È simile all'aggregazione di un ordine implementata nell'esempio eShopOnContainers, ma senza l'uso congiunto di EF Core.

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

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a>Introduzione ad Azure Cosmos DB e all'API nativa di Cosmos DB

[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) è il servizio di database distribuito globalmente di Microsoft per le applicazioni di importanza strategica. Azure Cosmos DB offre una [distribuzione globale chiavi in mano](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), una [scalabilità elastica in termini di produttività e archiviazione](https://docs.microsoft.com/azure/cosmos-db/partition-data) a livello mondiale, latenze pari a singole unità di millisecondi al 99° percentile, [cinque livelli di coerenza ben definiti](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) e disponibilità elevata garantita, il tutto supportato da [contratti di servizio leader di settore](https://azure.microsoft.com/support/legal/sla/cosmos-db/). Azure Cosmos DB [indicizza automaticamente i dati](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) senza doversi preoccupare della gestione dello schema e dell'indice. È multimodello e supporta modelli di dati documento, chiave-valore, grafo e a colonne.

![Diagramma che mostra la distribuzione globale Azure Cosmos DB.](./media/nosql-database-persistence-infrastructure/azure-cosmos-db-global-distribution.png)

**Figura 7-19**. Distribuzione globale di Azure Cosmos DB

Quando si usa un modello C\# per implementare l'aggregazione da usare con l'API di Azure Cosmos DB, l'aggregazione può essere simile alle classi POCO in C\# usate con EF Core. La differenza consiste nella modalità di utilizzo dai livelli applicazione e infrastruttura, come illustrato nel codice seguente:

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

È possibile notare che la modalità di utilizzo nel modello di dominio può essere simile a quella nel livello del modello di dominio quando l'infrastruttura è EF. È comunque possibile usare gli stessi metodi delle radici di aggregazione per garantire coerenza, invarianti e convalide all'interno dell'aggregazione.

Tuttavia, quando si rende persistente il modello nel database NoSQL, il codice e l'API cambiano in modo significativo rispetto al codice di EF Core o a qualsiasi altro codice correlato ai database relazionali.

## <a name="implement-net-code-targeting-mongodb-and-azure-cosmos-db"></a>Implementare il codice .NET per MongoDB e Azure Cosmos DB

### <a name="use-azure-cosmos-db-from-net-containers"></a>Usare Azure Cosmos DB dai contenitori .NET

È possibile accedere ai database Azure Cosmos DB dal codice .NET in esecuzione nei contenitori come da qualsiasi altra applicazione .NET. Ad esempio, i microservizi Locations.API e Marketing.API in eShopOnContainers vengono implementati in modo da poter usare i database Azure Cosmos DB.

Tuttavia, c'è una limitazione in Azure Cosmos DB per quanto riguarda l'ambiente di sviluppo Docker. Anche se è presente un [emulatore Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/local-emulator) locale che può essere eseguito in un computer di sviluppo locale, supporta solo Windows. Linux e macOS non sono supportati.

È anche possibile eseguire questo emulatore in Docker, ma solo nei contenitori di Windows, non con i contenitori Linux. Si tratta di un handicap iniziale per l'ambiente di sviluppo, se l'applicazione viene distribuita come contenitori Linux, dal momento che attualmente non è possibile distribuire i contenitori Linux e Windows in Docker per Windows nello stesso momento. Tutti i contenitori da distribuire devono essere per Linux o per Windows.

La distribuzione ideale e più semplice per una soluzione di sviluppo/test consiste nel poter distribuire i sistemi di database come contenitori insieme ai contenitori personalizzati in modo che gli ambienti di sviluppo/test siano sempre coerenti.

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a>Usare l'API MongoDB per contenitori Linux/Windows di sviluppo/test locali con Azure Cosmos DB

I database Cosmos DB supportano l'API MongoDB per .NET, nonché il protocollo di collegamento MongoDB nativo. Ciò significa che usando i driver esistenti, un'applicazione scritta per MongoDB può comunicare ora con Cosmos DB e usare i database Cosmos DB anziché i database MongoDB, come illustrato nella figura 7-20.

![Diagramma che illustra che Cosmos DB supporta il protocollo wire di .NET e MongoDB.](./media/nosql-database-persistence-infrastructure/mongodb-api-wire-protocol.png)

**Figura 7-20**. Uso dell'API MongoDB e del protocollo per accedere ad Azure Cosmos DB

Questo approccio è molto utile per i modelli di verifica in ambienti Docker con contenitori Linux perché l'[immagine MongoDB Docker](https://hub.docker.com/r/_/mongo/) è un'immagine multi-arch che supporta i contenitori Docker Linux e Windows.

Come illustrato nell'immagine seguente, con l'API MongoDB eShopOnContainers supporta i contenitori MongoDB Linux e Windows per l'ambiente di sviluppo locale, ma è possibile passare a una soluzione cloud PaaS scalabile come Azure Cosmos DB semplicemente [modificando la stringa di connessione MongoDB in modo da puntare ad Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).

![Diagramma che mostra che il microservizio percorso in eShopOnContainers può usare Cosmos DB o Mongo DB.](./media/nosql-database-persistence-infrastructure/eshoponcontainers-mongodb-containers.png)

**Figura 7-21**. eShopOnContainers con contenitori MongoDB per un ambiente di sviluppo o Azure Cosmos DB di produzione

Azure Cosmos DB di produzione viene eseguito nel cloud di Azure come servizio PaaS e scalabile.

I contenitori .NET Core personalizzati possono essere eseguiti in un host Docker di sviluppo locale (con Docker per Windows in un computer Windows 10) o essere distribuiti in un ambiente di produzione, ad esempio Kubernetes nel servizio Azure Kubernetes o Azure Service Fabric. In questo secondo ambiente è possibile distribuire solo i contenitori .NET Core personalizzati ma non il contenitore MongoDB perché viene usato Azure Cosmos DB nel cloud per la gestione dei dati nell'ambiente di produzione.

Un evidente vantaggio dell'uso dell'API MongoDB è che la soluzione può essere eseguita in entrambi i motori di database, MongoDB o Azure Cosmos DB, pertanto le migrazioni in ambienti diversi dovrebbero risultare semplici. Tuttavia, talvolta è utile usare un'API nativa, ovvero l'API Cosmos DB nativa, per sfruttare al meglio le funzionalità di un motore di database specifico.

Per un ulteriore confronto tra l'uso di MongoDB rispetto a Cosmos DB nel cloud, vedere i [vantaggi dell'uso di Azure Cosmos DB in questa pagina](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction).

### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a>Analizzare l'approccio per le applicazioni di produzione: API MongoDB e API Cosmos DB

In eShopOnContainers viene usata l'API MongoDB perché fondamentalmente la priorità è quella di avere un ambiente di sviluppo/test coerente con un database NoSQL che potrebbe essere usato anche con Azure Cosmos DB.

Tuttavia, se si prevede di usare l'API MongoDB per accedere ad Azure Cosmos DB in Azure per le applicazioni di produzione, è necessario analizzare le differenze di funzionalità e prestazioni quando si usa l'API MongoDB per accedere ai database Azure Cosmos DB rispetto all'uso dell'API Azure Cosmos DB nativa. Se non ci sono differenze, è possibile usare l'API MongoDB e sfruttare il vantaggio di supportare contemporaneamente due motori di database NoSQL.

È anche possibile usare i cluster MongoDB come database di produzione nel cloud di Azure con il [servizio Azure MongoDB](https://www.mongodb.com/scale/mongodb-azure-service). Ma non si tratta di un servizio PaaS fornito da Microsoft. In questo caso, Azure ospita solo tale soluzione proveniente da MongoDB.

In pratica, è solo una dichiarazione per indicare che non è necessario usare sempre l'API MongoDB rispetto ad Azure Cosmos DB, come è stato fatto in eShopOnContainers perché rappresentava una scelta adatta per i contenitori Linux. La decisione deve basarsi sulle esigenze specifiche e sui test che è necessario eseguire per l'applicazione di produzione.

### <a name="the-code-use-mongodb-api-in-net-core-applications"></a>Il codice: usare l'API MongoDB nelle applicazioni .NET Core

L'API MongoDB per .NET è basata sui pacchetti NuGet che è necessario aggiungere ai progetti, come nel progetto Locations.API illustrato nella figura seguente.

![Screenshot delle dipendenze nei pacchetti NuGet di MongoDB.](./media/nosql-database-persistence-infrastructure/mongodb-api-nuget-packages.png)

**Figura 7-22**. Riferimenti di pacchetti NuGet dell'API MongoDB in un progetto .NET Core

Il codice verrà esaminato nelle sezioni seguenti.

#### <a name="a-model-used-by-mongodb-api"></a>Modello usato dall'API MongoDB

In primo luogo, è necessario definire un modello che conterrà i dati provenienti dal database nello spazio di memoria dell'applicazione. Di seguito è riportato un esempio del modello usato per Locations in eShopOnContainers.

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

È possibile notare che ci sono alcuni attributi e tipi provenienti dai pacchetti NuGet di MongoDB.

I database NoSQL sono in genere particolarmente adatti per essere usati con i dati gerarchici non relazionali. In questo esempio vengono usati i tipi MongoDB adatti soprattutto per le geo-localizzazioni come `GeoJson2DGeographicCoordinates`.

#### <a name="retrieve-the-database-and-the-collection"></a>Recuperare il database e la raccolta

In eShopOnContainers, è stato creato un contesto di database personalizzato in cui viene implementato il codice per recuperare il database e l'oggetto MongoCollections, come illustrato nel codice seguente.

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

#### <a name="retrieve-the-data"></a>Recuperare i dati

Nel codice C#, come i controller API Web o l'implementazione personalizzata di repository, è possibile scrivere un codice simile al seguente quando si esegue una query tramite l'API MongoDB. Si noti che l'oggetto `_context` è un'istanza della classe `LocationsContext` precedente.

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a>Usare una variabile di ambiente nel file docker-compose.override.yml per la stringa di connessione di MongoDB

Quando si crea un oggetto MongoClient, è necessario un parametro fondamentale che è esattamente il parametro `ConnectionString` che punta al database corretto. Nel caso di eShopOnContainers, la stringa di connessione può puntare a un contenitore Docker MongoDB locale o a un database Azure Cosmos DB di "produzione".  La stringa di connessione proviene dalle variabili di ambiente definite nei file `docker-compose.override.yml` usati quando per eseguire la distribuzione con docker-compose o Visual Studio, come illustrato nel codice yml seguente.

```yml
# docker-compose.override.yml
version: '3.4'
services:
  # Other services
  locations-api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}

```

La variabile di ambiente `ConnectionString` viene risolta in questo modo: se la variabile globale `ESHOP_AZURE_COSMOSDB` viene definita nel file `.env` con la stringa di connessione di Azure Cosmos DB, verrà usata per accedere al database Azure Cosmos DB nel cloud. Se non è definito, utilizzerà il valore `mongodb://nosqldata` e userà il contenitore MongoDB di sviluppo.

Il codice seguente illustra il file `.env` con la variabile di ambiente globale della stringa di connessione di Azure Cosmos DB, come implementato in eShopOnContainers:

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

Rimuovere il commento dalla riga di ESHOP_AZURE_COSMOSDB e aggiornarla con la stringa di connessione Azure Cosmos DB ottenuta dalla portale di Azure come illustrato in [connettere un'applicazione MongoDB a Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).

Se la `ESHOP_AZURE_COSMOSDB` variabile globale è vuota, vale a dire che è impostata come commento nel file di `.env`, il contenitore usa una stringa di connessione predefinita di MongoDB. Questa stringa di connessione punta al contenitore MongoDB locale distribuito in eShopOnContainers denominato `nosqldata` ed è stato definito nel file Docker-compose, come illustrato nel codice. yml seguente:

``` yml
# docker-compose.yml
version: '3.4'
services:
  # ...Other services...
  nosqldata:
    image: mongo
```

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Modellazione dei dati di un documento per un database NoSQL** \
  <https://docs.microsoft.com/azure/cosmos-db/modeling-data>

- **Vaughn Vernon. L'archivio di aggregazione di progettazione basato su dominio ideale?** \
  <https://kalele.io/blog-posts/the-ideal-domain-driven-design-aggregate-store/>

- **Introduzione ad Azure Cosmos DB: API MongoDB**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction>

- **Azure Cosmos DB: Creare un'app Web per le API MongoDB con .NET e il portale di Azure**  \
  <https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet>

- **Usare l'emulatore di Azure Cosmos DB per sviluppo e test locali**  \
  <https://docs.microsoft.com/azure/cosmos-db/local-emulator>

- **Connettere un'applicazione MongoDB ad Azure Cosmos DB**  \
  <https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account>

- **Immagine Docker dell'emulatore Cosmos DB (contenitore Windows)**   \
  <https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/>

- **Immagine Docker di MongoDB (contenitore Linux e Windows)**   \
  <https://hub.docker.com/_/mongo/>

- **Azure Cosmos DB: usare Studio 3T con un account API di MongoDB**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef>

>[!div class="step-by-step"]
>[Precedente](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
>[Successivo](microservice-application-layer-web-api-design.md)
