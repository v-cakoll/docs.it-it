---
title: Creazione di un microservizio CRUD semplice basato sui dati
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni sulla creazione di un microservizio CRUD semplice basato sui dati nel contesto di un'applicazione di microservizi.
ms.date: 01/30/2020
ms.openlocfilehash: b72d7defed81e57e2971c5e2b53df2d86b2dc947
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502339"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="5902f-103">Creazione di un microservizio CRUD semplice basato sui dati</span><span class="sxs-lookup"><span data-stu-id="5902f-103">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="5902f-104">Questa sezione spiega come creare un semplice microservizio che esegue operazioni CRUD (create, read, update, delete), ovvero di creazione, lettura, aggiornamento ed eliminazione, su un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="5902f-104">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="5902f-105">Progettazione di un microservizio CRUD semplice</span><span class="sxs-lookup"><span data-stu-id="5902f-105">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="5902f-106">Dal punto di vista della progettazione, questo tipo di microservizio in contenitori è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="5902f-106">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="5902f-107">È probabile che il problema da risolvere sia semplice o che l'implementazione sia solo un modello di verifica.</span><span class="sxs-lookup"><span data-stu-id="5902f-107">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![Diagramma che illustra un semplice schema di progettazione interno del microservizio CRUD.](./media/data-driven-crud-microservice/internal-design-simple-crud-microservices.png)

<span data-ttu-id="5902f-109">**Figura 6-4**.</span><span class="sxs-lookup"><span data-stu-id="5902f-109">**Figure 6-4**.</span></span> <span data-ttu-id="5902f-110">Progettazione interna per microservizi CRUD semplici</span><span class="sxs-lookup"><span data-stu-id="5902f-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="5902f-111">Un esempio di questo tipo di servizio semplice basato sui dati è il microservizio Catalog dall'applicazione di esempio eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="5902f-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="5902f-112">Questo tipo di servizio implementa tutte le funzionalità in un unico progetto API Web ASP.NET Core che include le classi per il relativo modello di dati, la relativa logica di business e il relativo codice di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="5902f-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="5902f-113">Archivia anche i dati correlati in un database in esecuzione in SQL Server (come un altro contenitore per scopi di sviluppo/test), ma potrebbe essere anche un qualsiasi normale host di SQL Server, come illustrato nella Figura 6-5.</span><span class="sxs-lookup"><span data-stu-id="5902f-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 6-5.</span></span>

![Diagramma che mostra un contenitore microservizio basato sui dati o CRUD.](./media/data-driven-crud-microservice/simple-data-driven-crud-microservice.png)

<span data-ttu-id="5902f-115">**Figura 6-5**.</span><span class="sxs-lookup"><span data-stu-id="5902f-115">**Figure 6-5**.</span></span> <span data-ttu-id="5902f-116">Progettazione di un microservizio CRUD/basato sui dati semplice</span><span class="sxs-lookup"><span data-stu-id="5902f-116">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="5902f-117">Il diagramma precedente Mostra il microservizio del catalogo logico, che include il database del catalogo, che può essere o meno nello stesso host docker.</span><span class="sxs-lookup"><span data-stu-id="5902f-117">The previous diagram shows the logical Catalog microservice, that includes its Catalog database, which can be or not in the same Docker host.</span></span> <span data-ttu-id="5902f-118">Il database nello stesso host Docker può essere utile per lo sviluppo, ma non per la produzione.</span><span class="sxs-lookup"><span data-stu-id="5902f-118">Having the database in the same Docker host might be good for development, but not for production.</span></span> <span data-ttu-id="5902f-119">Quando si sviluppa questo tipo di servizio, sono necessari solo [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) e una API di accesso ai dati oppure ORM come [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="5902f-119">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="5902f-120">È anche possibile generare automaticamente metadati [Swagger](https://swagger.io/) tramite [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) per fornire una descrizione delle funzionalità offerte del servizio, come spiegato nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="5902f-120">You could also generate [Swagger](https://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="5902f-121">Si noti che poter eseguire un server di database, come SQL Server, all'interno di un contenitore Docker è ideale per gli ambienti di sviluppo, perché garantisce che tutte le dipendenze siano attive e in esecuzione senza dover eseguire il provisioning di un database nel cloud o in locale.</span><span class="sxs-lookup"><span data-stu-id="5902f-121">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="5902f-122">Questo risulta molto utile quando si eseguono test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="5902f-122">This is very convenient when running integration tests.</span></span> <span data-ttu-id="5902f-123">Per ambienti di produzione, però, è consigliabile non eseguire un server di database in un contenitore perché in genere tale approccio non garantisce una disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="5902f-123">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="5902f-124">Per un ambiente di produzione in Azure, è consigliabile usare Azure SQL DB o una qualsiasi altra tecnologia di database in grado di offrire disponibilità e scalabilità elevate.</span><span class="sxs-lookup"><span data-stu-id="5902f-124">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="5902f-125">Per un approccio NoSQL è ad esempio possibile scegliere CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="5902f-125">For example, for a NoSQL approach, you might choose CosmosDB.</span></span>

<span data-ttu-id="5902f-126">Modificando infine i file di metadati di Dockerfile e di docker-compose.yml, è possibile configurare la modalità di creazione dell'immagine di questo contenitore, ovvero quale immagine di base userà, oltre ad impostazioni di progettazione, come i nomi interni ed esterni e le porte TCP.</span><span class="sxs-lookup"><span data-stu-id="5902f-126">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span>

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="5902f-127">Implementazione di un microservizio CRUD semplice con ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5902f-127">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="5902f-128">Per implementare un microservizio CRUD semplice con .NET Core e Visual Studio, è innanzitutto necessario creare un progetto API Web ASP.NET Core semplice (in esecuzione in .NET Core, in modo che sia eseguibile in un host Docker Linux), come illustrato nella Figura 6-6.</span><span class="sxs-lookup"><span data-stu-id="5902f-128">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 6-6.</span></span>

![Screenshot di Visual Studio che illustra la configurazione del progetto.](./media/data-driven-crud-microservice/create-asp-net-core-web-api-project.png)

<span data-ttu-id="5902f-130">**Figura 6-6**.</span><span class="sxs-lookup"><span data-stu-id="5902f-130">**Figure 6-6**.</span></span> <span data-ttu-id="5902f-131">Creazione di un progetto API Web ASP.NET Core in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5902f-131">Creating an ASP.NET Core Web API project in Visual Studio 2019</span></span>

<span data-ttu-id="5902f-132">Per creare un progetto API Web ASP.NET Core, selezionare prima un'applicazione Web ASP.NET Core, quindi selezionare il tipo di API.</span><span class="sxs-lookup"><span data-stu-id="5902f-132">To create an ASP.NET Core Web API Project, first select an ASP.NET Core Web Application and then select the API type.</span></span> <span data-ttu-id="5902f-133">Dopo aver creato il progetto, è possibile implementare i controller MVC, come in qualsiasi altro progetto API Web, usando l'API di Entity Framework o altre API.</span><span class="sxs-lookup"><span data-stu-id="5902f-133">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="5902f-134">In un nuovo progetto API Web è possibile notare che l'unica dipendenza presente in tale microservizio è su ASP.NET Core stesso.</span><span class="sxs-lookup"><span data-stu-id="5902f-134">In a new Web API project, you can see that the only dependency you have in that microservice is on ASP.NET Core itself.</span></span> <span data-ttu-id="5902f-135">Internamente, all'interno della dipendenza *Microsoft. AspNetCore. All* , fa riferimento Entity Framework e molti altri pacchetti NuGet di .NET Core, come illustrato nella figura 6-7.</span><span class="sxs-lookup"><span data-stu-id="5902f-135">Internally, within the *Microsoft.AspNetCore.All* dependency, it is referencing Entity Framework and many other .NET Core NuGet packages, as shown in Figure 6-7.</span></span>

![Screenshot di Visual Studio che mostra le dipendenze NuGet di Catalog. API.](./media/data-driven-crud-microservice/simple-crud-web-api-microservice-dependencies.png)

<span data-ttu-id="5902f-137">**Figura 6-7**.</span><span class="sxs-lookup"><span data-stu-id="5902f-137">**Figure 6-7**.</span></span> <span data-ttu-id="5902f-138">Dipendenze in un microservizio API Web CRUD semplice</span><span class="sxs-lookup"><span data-stu-id="5902f-138">Dependencies in a simple CRUD Web API microservice</span></span>

<span data-ttu-id="5902f-139">Il progetto API include riferimenti al pacchetto NuGet Microsoft.AspNetCore.App, che a sua volta include riferimenti a tutti i pacchetti essenziali.</span><span class="sxs-lookup"><span data-stu-id="5902f-139">The API project includes references to the Microsoft.AspNetCore.App NuGet package, that includes references to all essential packages.</span></span> <span data-ttu-id="5902f-140">Può anche includere altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5902f-140">It could include some other packages as well.</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="5902f-141">Implementazione di servizi API Web CRUD con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="5902f-141">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="5902f-142">Entity Framework (EF) Core è una versione semplice, estendibile e multipiattaforma della tecnologia di accesso dati Entity Framework più diffusa.</span><span class="sxs-lookup"><span data-stu-id="5902f-142">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="5902f-143">EF Core è un mapper relazionale a oggetti che consente agli sviluppatori di .NET di usare un database con gli oggetti .NET.</span><span class="sxs-lookup"><span data-stu-id="5902f-143">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="5902f-144">Il microservizio Catalog usa Entity Framework e il provider SQL Server perché il relativo database è in esecuzione in un contenitore con l'immagine di SQL Server per Linux Docker.</span><span class="sxs-lookup"><span data-stu-id="5902f-144">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="5902f-145">Il database può però essere distribuito in qualsiasi istanza di SQL Server, ad esempio Windows locale o Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="5902f-145">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="5902f-146">L'unico elemento da modificare è la stringa di connessione nel microservizio API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5902f-146">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="the-data-model"></a><span data-ttu-id="5902f-147">Modello di dati</span><span class="sxs-lookup"><span data-stu-id="5902f-147">The data model</span></span>

<span data-ttu-id="5902f-148">Con Entity Framework Core, l'accesso ai dati viene eseguito tramite un modello.</span><span class="sxs-lookup"><span data-stu-id="5902f-148">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="5902f-149">Un modello è costituito da classi di entità (modello di dominio) e da un contesto derivato (DbContext) che rappresenta una sessione con il database, per eseguire una query e salvare i dati.</span><span class="sxs-lookup"><span data-stu-id="5902f-149">A model is made up of (domain model) entity classes and a derived context (DbContext) that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="5902f-150">È possibile generare un modello da un database esistente, scrivere manualmente il codice di un modello in modo che corrisponda al database oppure usare migrazioni di Entity Framework per creare un database a partire dal modello, usando l'approccio incentrato sul codice (che facilita lo sviluppo del database di pari passo con l'evoluzione del modello nel tempo).</span><span class="sxs-lookup"><span data-stu-id="5902f-150">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model, using the code-first approach (that makes it easy to evolve the database as your model changes over time).</span></span> <span data-ttu-id="5902f-151">Per il microservizio Catalog viene usato l'ultimo approccio.</span><span class="sxs-lookup"><span data-stu-id="5902f-151">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="5902f-152">Nell'esempio di codice seguente è incluso un esempio della classe di entità CatalogItem, che è una semplice classe di entità [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) (Plain Old CLR Object).</span><span class="sxs-lookup"><span data-stu-id="5902f-152">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureFileName { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public int AvailableStock { get; set; }
    public int RestockThreshold { get; set; }
    public int MaxStockThreshold { get; set; }

    public bool OnReorder { get; set; }
    public CatalogItem() { }

    // Additional code ...
}
```

<span data-ttu-id="5902f-153">È inoltre necessario una classe DbContext che rappresenta una sessione con il database.</span><span class="sxs-lookup"><span data-stu-id="5902f-153">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="5902f-154">Per il microservizio Catalog la classe CatalogContext deriva dalla classe di base di DbContext, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5902f-154">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    { }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...
}
```

<span data-ttu-id="5902f-155">Possono esistere altre implementazioni di `DbContext`.</span><span class="sxs-lookup"><span data-stu-id="5902f-155">You can have additional `DbContext` implementations.</span></span> <span data-ttu-id="5902f-156">Ad esempio, nel microservizio Catalog.API di esempio, è presente un secondo elemento `DbContext` denominato `CatalogContextSeed` in cui inserisce automaticamente i dati di esempio la prima volta che prova ad accedere al database.</span><span class="sxs-lookup"><span data-stu-id="5902f-156">For example, in the sample Catalog.API microservice, there's a second `DbContext` named `CatalogContextSeed` where it automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="5902f-157">Questo metodo è utile anche per i dati di demo e per scenari di test automatizzati.</span><span class="sxs-lookup"><span data-stu-id="5902f-157">This method is useful for demo data and for automated testing scenarios, as well.</span></span>

<span data-ttu-id="5902f-158">All'interno di `DbContext` si usa il metodo `OnModelCreating` per personalizzare i mapping di entità di oggetto/database e altri [punti di estendibilità di Entity Framework](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span><span class="sxs-lookup"><span data-stu-id="5902f-158">Within the `DbContext`, you use the `OnModelCreating` method to customize object/database entity mappings and other [EF extensibility points](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="5902f-159">Esecuzione di query sui dati da controller API Web</span><span class="sxs-lookup"><span data-stu-id="5902f-159">Querying data from Web API controllers</span></span>

<span data-ttu-id="5902f-160">Per recuperare le istanze di classi di entità dal database si usa in genere LINQ (Language Integrated Query), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5902f-160">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(
        CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService
            ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        context.ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("items")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType(typeof(IEnumerable<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType((int)HttpStatusCode.BadRequest)]
    public async Task<IActionResult> ItemsAsync(
        [FromQuery]int pageSize = 10,
        [FromQuery]int pageIndex = 0,
        string ids = null)
    {
        if (!string.IsNullOrEmpty(ids))
        {
            var items = await GetItemsByIdsAsync(ids);

            if (!items.Any())
            {
                return BadRequest("ids value invalid. Must be comma-separated list of numbers");
            }

            return Ok(items);
        }

        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();

        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();

        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);

        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);

        return Ok(model);
    }
    //...
}
```

##### <a name="saving-data"></a><span data-ttu-id="5902f-161">Salvataggio di dati</span><span class="sxs-lookup"><span data-stu-id="5902f-161">Saving data</span></span>

<span data-ttu-id="5902f-162">I dati vengano creati, eliminati e modificati nel database tramite le istanze di classi di entità.</span><span class="sxs-lookup"><span data-stu-id="5902f-162">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="5902f-163">È possibile aggiungere codice analogo all'esempio hardcoded seguente (dati fittizi, in questo caso) ai controller API Web.</span><span class="sxs-lookup"><span data-stu-id="5902f-163">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="5902f-164">Inserimento delle dipendenze in ASP.NET Core e controller API Web</span><span class="sxs-lookup"><span data-stu-id="5902f-164">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="5902f-165">In ASP.NET Core è possibile usare il modello predefinito di inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="5902f-165">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="5902f-166">Non è necessario configurare un contenitore IoC (Inversion of Control) di terze parti, anche se è possibile inserire il contenitore IoC preferito nell'infrastruttura ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5902f-166">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="5902f-167">In questo caso, è possibile inserire direttamente la classe DBContext richiesta di Entity Framework o altri repository tramite il costruttore del controller.</span><span class="sxs-lookup"><span data-stu-id="5902f-167">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span>

<span data-ttu-id="5902f-168">Nell'esempio precedente della classe `CatalogController` si inseriscono un oggetto di tipo `CatalogContext` e altri oggetti tramite il costruttore `CatalogController()`.</span><span class="sxs-lookup"><span data-stu-id="5902f-168">In the example above of the `CatalogController` class, we are injecting an object of `CatalogContext` type plus other objects through the `CatalogController()` constructor.</span></span>

<span data-ttu-id="5902f-169">Un'importante configurazione da definire nel progetto API Web è la registrazione della classe DbContext nel contenitore IoC del servizio.</span><span class="sxs-lookup"><span data-stu-id="5902f-169">An important configuration to set up in the Web API project is the DbContext class registration into the service's IoC container.</span></span> <span data-ttu-id="5902f-170">Questa operazione viene in genere eseguita nella classe `Startup` chiamando il metodo `services.AddDbContext<DbContext>()` all'interno del metodo `ConfigureServices()`, come illustrato nell'esempio **semplificato** seguente:</span><span class="sxs-lookup"><span data-stu-id="5902f-170">You typically do so in the `Startup` class by calling the `services.AddDbContext<DbContext>()` method inside the `ConfigureServices()` method, as shown in the following **simplified** example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.MigrationsAssembly(
                typeof(Startup).GetTypeInfo().Assembly.GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...
}
```

### <a name="additional-resources"></a><span data-ttu-id="5902f-171">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5902f-171">Additional resources</span></span>

- <span data-ttu-id="5902f-172">**Esecuzione di query su dati** </span><span class="sxs-lookup"><span data-stu-id="5902f-172">**Querying Data** </span></span>\
  [https://docs.microsoft.com/ef/core/querying/index](/ef/core/querying/index)

- <span data-ttu-id="5902f-173">**Salvataggio di dati** </span><span class="sxs-lookup"><span data-stu-id="5902f-173">**Saving Data** </span></span>\
  [https://docs.microsoft.com/ef/core/saving/index](/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="5902f-174">Stringa di connessione di database e variabili di ambiente usate dai contenitori Docker</span><span class="sxs-lookup"><span data-stu-id="5902f-174">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="5902f-175">È possibile usare le impostazioni di ASP.NET Core e aggiungere una proprietà ConnectionString al file settings.json come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5902f-175">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

```json
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

<span data-ttu-id="5902f-176">Il file settings.json può contenere valori predefiniti per la proprietà ConnectionString o per qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="5902f-176">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="5902f-177">Quando si usa Docker, però, tali proprietà verranno però sovrascritte dai valori delle variabili di ambiente specificate nel file docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="5902f-177">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file, when using Docker.</span></span>

<span data-ttu-id="5902f-178">Dal file docker-compose.yml o docker-compose.override.yml è possibile inizializzare le variabili di ambiente in modo che Docker le configuri automaticamente come variabili di ambiente del sistema operativo, come illustrato nel file docker-compose.override.yml seguente. In questo esempio la stringa di connessione e le altre righe vanno a capo, ma dovrebbero rimanere sulla stessa riga nel file dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5902f-178">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

```yml
# docker-compose.override.yml

#
catalog-api:
  environment:
    - ConnectionString=Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

<span data-ttu-id="5902f-179">I file docker-compose.yml a livello di soluzione non sono solo più flessibili dei file di configurazione a livello di progetto o microservizio, ma anche più sicuri se si sostituiscono le variabili di ambiente dichiarate nei file docker-compose con i valori impostati dagli strumenti di distribuzione, ad esempio dalle attività di distribuzione di Azure DevOps Services Docker.</span><span class="sxs-lookup"><span data-stu-id="5902f-179">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure if you override the environment variables declared at the docker-compose files with values set from your deployment tools, like from Azure DevOps Services Docker deployment tasks.</span></span>

<span data-ttu-id="5902f-180">Per ottenere infine tale valore dal codice, è possibile usare Configuration\["ConnectionString"\], come illustrato nel metodo ConfigureServices in un esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="5902f-180">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="5902f-181">Per ambienti di produzione, però, è possibile che si voglia esplorare altre modalità di archiviazione dei segreti, ad esempio le stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="5902f-181">However, for production environments, you might want to explore additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="5902f-182">Un metodo ottimale per la gestione dei segreti dell'applicazione è l'uso di [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="5902f-182">An excellent way to manage application secrets is using [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="5902f-183">Azure Key Vault contribuisce ad archiviare proteggere i segreti e le chiavi di crittografia usati dai servizi e dalle applicazioni cloud dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5902f-183">Azure Key Vault helps to store and safeguard cryptographic keys and secrets used by your cloud applications and services.</span></span> <span data-ttu-id="5902f-184">Un segreto è un elemento sul quale di desidera avere un controllo restrittivo, ad esempio le chiavi API, le stringhe di connessione, le password e così via. Il controllo restrittivo include *tra le altre caratteristiche* la registrazione dell'uso, l'impostazione della scadenza e la gestione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="5902f-184">A secret is anything you want to keep strict control of, like API keys, connection strings, passwords, etc. and strict control includes usage logging, setting expiration, managing access, *among others*.</span></span>

<span data-ttu-id="5902f-185">Azure Key Vault consente un livello di controllo molto dettagliato sull'uso dei segreti dell'applicazione, senza che altri utenti debbano conoscerli.</span><span class="sxs-lookup"><span data-stu-id="5902f-185">Azure Key Vault allows a very detailed control level of the application secrets usage without the need to let anyone know them.</span></span> <span data-ttu-id="5902f-186">I segreti possono anche essere ruotati per la sicurezza avanzata, senza interrompere lo sviluppo o il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="5902f-186">The secrets can even be rotated for enhanced security without disrupting development or operations.</span></span>

<span data-ttu-id="5902f-187">Le applicazioni devono essere registrate in Active Directory per l'organizzazione, in modo che possano usare Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5902f-187">Applications have to be registered in the organization's Active Directory, so they can use the Key Vault.</span></span>

<span data-ttu-id="5902f-188">Per informazioni dettagliate, vedere la *documentazione Concetti di Key Vault*.</span><span class="sxs-lookup"><span data-stu-id="5902f-188">You can check the *Key Vault Concepts documentation* for more details.</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="5902f-189">Implementazione del controllo delle versioni in API Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5902f-189">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="5902f-190">In seguito alla modifica dei requisiti di business, è possibile che vengano aggiunte nuove raccolte di risorse, che le relazioni tra le risorse cambino e che la struttura dei dati nelle risorse subisca modifiche.</span><span class="sxs-lookup"><span data-stu-id="5902f-190">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="5902f-191">L'aggiornamento di un'API Web in modo che possa gestire i nuovi requisiti è un processo relativamente semplice, ma è necessario considerare gli effetti che tali modifiche avranno sulle applicazioni client che utilizzano l'API Web.</span><span class="sxs-lookup"><span data-stu-id="5902f-191">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="5902f-192">Anche se lo sviluppatore che progetta e implementa un'API Web dispone del controllo completo su tale API, non può avere lo stesso livello di controllo sulle applicazioni client che potrebbero essere create da organizzazioni di terze parti operanti in remoto.</span><span class="sxs-lookup"><span data-stu-id="5902f-192">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="5902f-193">Il controllo delle versioni consente a un'API Web di indicare le funzionalità e le risorse che espone.</span><span class="sxs-lookup"><span data-stu-id="5902f-193">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="5902f-194">Un'applicazione client può quindi inviare richieste a una versione specifica di una funzione o di una risorsa.</span><span class="sxs-lookup"><span data-stu-id="5902f-194">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="5902f-195">Esistono diversi approcci per l'implementazione del controllo delle versioni:</span><span class="sxs-lookup"><span data-stu-id="5902f-195">There are several approaches to implement versioning:</span></span>

- <span data-ttu-id="5902f-196">Controllo delle versioni dell'URI</span><span class="sxs-lookup"><span data-stu-id="5902f-196">URI versioning</span></span>

- <span data-ttu-id="5902f-197">Controllo delle versioni della stringa di query</span><span class="sxs-lookup"><span data-stu-id="5902f-197">Query string versioning</span></span>

- <span data-ttu-id="5902f-198">Controllo delle versioni dell'intestazione</span><span class="sxs-lookup"><span data-stu-id="5902f-198">Header versioning</span></span>

<span data-ttu-id="5902f-199">Il controllo delle versioni della stringa di query e dell'URI sono i più semplici da implementare.</span><span class="sxs-lookup"><span data-stu-id="5902f-199">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="5902f-200">Il controllo delle versioni dell'intestazione costituisce un valido approccio,</span><span class="sxs-lookup"><span data-stu-id="5902f-200">Header versioning is a good approach.</span></span> <span data-ttu-id="5902f-201">ma non è esplicito e semplice come il controllo delle versioni dell'URI.</span><span class="sxs-lookup"><span data-stu-id="5902f-201">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="5902f-202">Dal momento che è il più semplice e il più esplicito, il controllo delle versioni dell'URI è l'approccio usato nell'applicazione di esempio eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="5902f-202">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="5902f-203">Con il controllo delle versioni dell'URI, secondo l'implementazione dell'applicazione di esempio eShopOnContainers, ogni volta che si modifica l'API Web o si cambia lo schema delle risorse, per ogni risorsa viene aggiunto un numero di versione all'URI.</span><span class="sxs-lookup"><span data-stu-id="5902f-203">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="5902f-204">Gli URI esistenti continueranno a funzionare come prima, restituendo le risorse conformi allo schema che corrisponde alla versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="5902f-204">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="5902f-205">Come illustrato nell'esempio di codice seguente, è possibile impostare la versione usando l'attributo Route nel controller API Web, in modo da renderla esplicita nell'URI (v1 in questo caso).</span><span class="sxs-lookup"><span data-stu-id="5902f-205">As shown in the following code example, the version can be set by using the Route attribute in the Web API controller, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="5902f-206">Questo meccanismo di controllo delle versioni è semplice e dipende dal server che inoltra la richiesta all'endpoint appropriato.</span><span class="sxs-lookup"><span data-stu-id="5902f-206">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="5902f-207">Per un controllo delle versioni più sofisticato e per il metodo migliore quando si usa REST, tuttavia, è opportuno usare ipermedia e implementare [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).</span><span class="sxs-lookup"><span data-stu-id="5902f-207">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5902f-208">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5902f-208">Additional resources</span></span>

- <span data-ttu-id="5902f-209">**Scott Hansel. ASP.NET Core il controllo delle versioni dell'API Web RESTful** semplificato </span><span class="sxs-lookup"><span data-stu-id="5902f-209">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy** </span></span>\
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- <span data-ttu-id="5902f-210">**Versioning a RESTful web API (Controllo delle versioni delle API Web RESTful)**  </span><span class="sxs-lookup"><span data-stu-id="5902f-210">**Versioning a RESTful web API** </span></span>\
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- <span data-ttu-id="5902f-211">**Fielding di Roy. Controllo delle versioni, ipermedia e REST** </span><span class="sxs-lookup"><span data-stu-id="5902f-211">**Roy Fielding. Versioning, Hypermedia, and REST** </span></span>\
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="5902f-212">Generazione dei metadati delle descrizioni Swagger dall'API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5902f-212">Generating Swagger description metadata from your ASP.NET Core Web API</span></span>

<span data-ttu-id="5902f-213">[Swagger](https://swagger.io/) è un framework open source di uso comune basato su un vasto ecosistema di strumenti che consentono di progettare, creare, documentare e utilizzare API RESTful.</span><span class="sxs-lookup"><span data-stu-id="5902f-213">[Swagger](https://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="5902f-214">Si sta affermando come lo standard per il dominio dei metadati delle descrizioni di API.</span><span class="sxs-lookup"><span data-stu-id="5902f-214">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="5902f-215">È opportuno includere i metadati delle descrizioni Swagger con qualsiasi tipo di microservizio, sia quelli basati sui dati che quelli più avanzati basati su dominio, come descritto nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="5902f-215">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="5902f-216">L'elemento centrale di Swagger è la specifica Swagger, costituita dai metadati delle descrizioni di API salvati in un file JSON o YAML.</span><span class="sxs-lookup"><span data-stu-id="5902f-216">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="5902f-217">La specifica crea il contratto RESTful per l'API, che elenca in dettaglio tutte le risorse e le operazioni sia nel formato leggibile che in quello macchina, per agevolare lo sviluppo, l'individuazione e l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="5902f-217">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="5902f-218">La specifica è la base della specifica OpenAPI (OAS) ed è sviluppata in una community aperta, trasparente e collaborativa allo scopo di standardizzare le modalità di definizione delle interfacce RESTful.</span><span class="sxs-lookup"><span data-stu-id="5902f-218">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="5902f-219">La specifica definisce la struttura in base alla quale è possibile individuare un servizio e riconoscerne le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5902f-219">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="5902f-220">Per altre informazioni, incluso un editor Web ed esempi di specifiche Swagger rese disponibili da società quali Spotify, Uber, Slack e Microsoft, visitare il sito di Swagger (<https://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="5902f-220">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<https://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="5902f-221">Perché usare Swagger?</span><span class="sxs-lookup"><span data-stu-id="5902f-221">Why use Swagger?</span></span>

<span data-ttu-id="5902f-222">I motivi principali per generare i metadati di Swagger per le API sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="5902f-222">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="5902f-223">**Consentire ad altri prodotti di utilizzare e integrare automaticamente le API**.</span><span class="sxs-lookup"><span data-stu-id="5902f-223">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="5902f-224">Decine di prodotti e [strumenti in commercio](https://swagger.io/commercial-tools/), oltre a numerosi [framework e librerie](https://swagger.io/open-source-integrations/) supportano Swagger.</span><span class="sxs-lookup"><span data-stu-id="5902f-224">Dozens of products and [commercial tools](https://swagger.io/commercial-tools/) and many [libraries and frameworks](https://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="5902f-225">Microsoft offre prodotti e strumenti di alto livello in grado di utilizzare automaticamente API basate su Swagger, tra cui:</span><span class="sxs-lookup"><span data-stu-id="5902f-225">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

- <span data-ttu-id="5902f-226">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="5902f-226">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="5902f-227">È possibile generare automaticamente le classi client .NET per chiamare Swagger.</span><span class="sxs-lookup"><span data-stu-id="5902f-227">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="5902f-228">Questo strumento può essere usato dall'interfaccia della riga di comando ed è inoltre integrato in Visual Studio in modo da poterlo usare più facilmente tramite l'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="5902f-228">This tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

- <span data-ttu-id="5902f-229">[Microsoft Flow](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5902f-229">[Microsoft Flow](https://flow.microsoft.com/).</span></span> <span data-ttu-id="5902f-230">È possibile [usare e integrare automaticamente l'API](https://flow.microsoft.com/blog/integrating-custom-api/) in un flusso di lavoro Microsoft Flow di alto livello senza che siano necessarie competenze di programmazione.</span><span class="sxs-lookup"><span data-stu-id="5902f-230">You can automatically [use and integrate your API](https://flow.microsoft.com/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

- <span data-ttu-id="5902f-231">[Microsoft PowerApps](https://powerapps.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5902f-231">[Microsoft PowerApps](https://powerapps.microsoft.com/).</span></span> <span data-ttu-id="5902f-232">È possibile utilizzare automaticamente l'API da [app per dispositivi mobili PowerApps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) create con [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/) senza che siano necessarie competenze di programmazione.</span><span class="sxs-lookup"><span data-stu-id="5902f-232">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/), with no programming skills required.</span></span>

- <span data-ttu-id="5902f-233">[App per la logica del servizio app di Azure](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="5902f-233">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="5902f-234">È possibile [usare e integrare automaticamente l'API in un'app per la logica del servizio app di Azure](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api) senza che siano necessarie competenze di programmazione.</span><span class="sxs-lookup"><span data-stu-id="5902f-234">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="5902f-235">**Consente di generare automaticamente la documentazione dell'API**.</span><span class="sxs-lookup"><span data-stu-id="5902f-235">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="5902f-236">Quando si creano API RESTful su vasta scala, ad esempio applicazioni complesse basate su microservizi, è necessario gestire molti endpoint con modelli di dati diversi usati nei payload di richiesta e risposta.</span><span class="sxs-lookup"><span data-stu-id="5902f-236">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="5902f-237">Poter disporre della documentazione adeguata e di un solido strumento Esplora API, come avviene con Swagger, è di fondamentale importanza per l'applicazione delle API e per fare in modo che vengano adottate dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="5902f-237">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="5902f-238">Microsoft Flow, PowerApps e le app per la logica di Azure usano proprio i metadati di Swagger per sapere come usare le API e connettersi ad esse.</span><span class="sxs-lookup"><span data-stu-id="5902f-238">Swagger's metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

<span data-ttu-id="5902f-239">Sono disponibili diverse opzioni per automatizzare la generazione di metadati di Swagger per le applicazioni API REST di ASP.NET Core, sotto forma di pagine della Guida dell'API funzionale basate su *swagger-ui*.</span><span class="sxs-lookup"><span data-stu-id="5902f-239">There are several options to automate Swagger metadata generation for ASP.NET Core REST API applications, in the form of functional API help pages, based on *swagger-ui*.</span></span>

<span data-ttu-id="5902f-240">Probabilmente la conoscenza migliore è [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) , che è attualmente usata in [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) e verrà illustrata in dettaglio in questa guida, ma è anche possibile usare [NSwag](https://github.com/RSuter/NSwag), che può generare typescript e c\# client API, oltre ai controller c\#, da una specifica spavalderia o openapi e persino eseguendo la scansione del file con estensione dll che contiene i controller, usando [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).</span><span class="sxs-lookup"><span data-stu-id="5902f-240">Probably the best know is [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) which is currently used in [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) and we'll cover in some detail in this guide but there's also the option to use [NSwag](https://github.com/RSuter/NSwag), which can generate Typescript and C\# API clients, as well as C\# controllers, from a Swagger or OpenAPI specification and even by scanning the .dll that contains the controllers, using [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="5902f-241">Come automatizzare la generazione di metadati di Swagger per le API con il pacchetto NuGet Swashbuckle</span><span class="sxs-lookup"><span data-stu-id="5902f-241">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="5902f-242">La generazione manuale di metadati di Swagger, in un file JSON o YAML, può essere un lavoro noioso.</span><span class="sxs-lookup"><span data-stu-id="5902f-242">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="5902f-243">È però possibile automatizzare l'individuazione delle API per i servizi delle API Web ASP.NET usando il [pacchetto NuGet Swashbuckle](https://aka.ms/swashbuckledotnetcore) per generare dinamicamente i metadati di Swagger per le API.</span><span class="sxs-lookup"><span data-stu-id="5902f-243">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](https://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="5902f-244">Swashbuckle genera automaticamente i metadati di Swagger per i progetti di API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5902f-244">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="5902f-245">Supporta i progetti API Web ASP.NET Core e l'API Web ASP.NET tradizionale, oltre a qualsiasi altra versione, ad esempio i microservizi delle app per le API di Azure, per le app per dispositivi mobili di Azure e Azure Service Fabric basati su ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5902f-245">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="5902f-246">Supporta anche API Web semplici distribuite nei contenitori, come nel caso dell'applicazione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5902f-246">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="5902f-247">Swashbuckle combina Esplora API e Swagger o [swagger-ui](https://github.com/swagger-api/swagger-ui) per offrire un'esperienza di individuazione e documentazione completa per i consumer di API.</span><span class="sxs-lookup"><span data-stu-id="5902f-247">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="5902f-248">Oltre al motore di generazione dei metadati di Swagger, Swashbuckle contiene anche una versione incorporata di swagger-ui, che verrà eseguito automaticamente una volta installato Swashbuckle.</span><span class="sxs-lookup"><span data-stu-id="5902f-248">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="5902f-249">Questo significa che è possibile offrire a corredo dell'API con una comoda interfaccia utente di individuazione per consentire agli sviluppatori di usare l'API.</span><span class="sxs-lookup"><span data-stu-id="5902f-249">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="5902f-250">Tale interfaccia richiede una minima quantità di codice e manutenzione perché è generata automaticamente, consentendo all'utente di concentrare l'attenzione sulla creazione dell'API.</span><span class="sxs-lookup"><span data-stu-id="5902f-250">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="5902f-251">Il risultato per Esplora API è simile a quello illustrato nella Figura 6-8.</span><span class="sxs-lookup"><span data-stu-id="5902f-251">The result for the API Explorer looks like Figure 6-8.</span></span>

![Screenshot di spavalderia API Explorer che Visualizza l'API eShopOContainers.](./media/data-driven-crud-microservice/swagger-metadata-eshoponcontainers-catalog-microservice.png)

<span data-ttu-id="5902f-253">**Figura 6-8**.</span><span class="sxs-lookup"><span data-stu-id="5902f-253">**Figure 6-8**.</span></span> <span data-ttu-id="5902f-254">Interfaccia Esplora API Swashbuckle basato su metadati di Swagger: microservizio Catalog di eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="5902f-254">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="5902f-255">L'API dell'interfaccia utente di Swagger generata da Swashbuckle include tutte le azioni pubblicate.</span><span class="sxs-lookup"><span data-stu-id="5902f-255">The Swashbuckle generated Swagger UI API documentation includes all published actions.</span></span> <span data-ttu-id="5902f-256">Ma l'interfaccia Esplora API non è l'aspetto più interessante in questo caso.</span><span class="sxs-lookup"><span data-stu-id="5902f-256">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="5902f-257">Dopo aver creato un'API Web in grado di descrivere se stessa nei metadati di Swagger, è possibile usare facilmente l'API da strumenti basati su Swagger, inclusi i generatori di codice di classe proxy client che possono essere destinati a più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="5902f-257">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="5902f-258">Come già accennato, ad esempio, [AutoRest](https://github.com/Azure/AutoRest) genera automaticamente classi client .NET.</span><span class="sxs-lookup"><span data-stu-id="5902f-258">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="5902f-259">Ma sono disponibili anche strumenti aggiuntivi, come [swagger codegen](https://github.com/swagger-api/swagger-codegen), che consente di generare automaticamente il codice di librerie client API, stub server e documentazione.</span><span class="sxs-lookup"><span data-stu-id="5902f-259">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="5902f-260">Attualmente Swashbuckle è costituito da cinque pacchetti NuGet interni sotto il metapacchetto di alto livello [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) per le applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5902f-260">Currently, Swashbuckle consists of five internal NuGet packages under the high-level meta- package [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) for ASP.NET Core applications.</span></span>

<span data-ttu-id="5902f-261">Dopo aver installato questi pacchetti NuGet nel progetto API Web, è necessario configurare spavalderia nella classe startup, come nel codice **semplificato** seguente:</span><span class="sxs-lookup"><span data-stu-id="5902f-261">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following **simplified** code:</span></span>

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...

        // Add framework services.
        services.AddSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SwaggerDoc("v1", new OpenApiInfo
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample"
            });
        });

        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
            });
    }
}
```

<span data-ttu-id="5902f-262">Al termine, è possibile avviare l'applicazione e sfogliare gli endpoint dell'interfaccia utente e JSON di Swagger seguenti usando URL simili a questi:</span><span class="sxs-lookup"><span data-stu-id="5902f-262">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```console
  http://<your-root-url>/swagger/v1/swagger.json

  http://<your-root-url>/swagger/
```

<span data-ttu-id="5902f-263">In precedenza è stata illustrata l'interfaccia utente generata creata da Swashbuckle per un URL come `http://<your-root-url>/swagger`.</span><span class="sxs-lookup"><span data-stu-id="5902f-263">You previously saw the generated UI created by Swashbuckle for a URL like `http://<your-root-url>/swagger`.</span></span> <span data-ttu-id="5902f-264">Nella Figura 6-9 è anche possibile vedere come eseguire il test di un qualsiasi metodo di API.</span><span class="sxs-lookup"><span data-stu-id="5902f-264">In Figure 6-9 you can also see how you can test any API method.</span></span>

![Screenshot dell'interfaccia utente di spavalderia che Mostra gli strumenti di test disponibili.](./media/data-driven-crud-microservice/swashbuckle-ui-testing.png)

<span data-ttu-id="5902f-266">**Figura 6-9**.</span><span class="sxs-lookup"><span data-stu-id="5902f-266">**Figure 6-9**.</span></span> <span data-ttu-id="5902f-267">Test del metodo API Catalog/Items nell'interfaccia utente di Swashbuckle</span><span class="sxs-lookup"><span data-stu-id="5902f-267">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="5902f-268">I dettagli dell'API interfaccia utente di Swagger visualizzano un esempio della risposta e possono essere usati per eseguire l'API reale, molto utile per l'individuazione degli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="5902f-268">The Swagger UI API detail shows a sample of the response and can be used to execute the real API, which is great for developer discovery.</span></span> <span data-ttu-id="5902f-269">Nella figura 6-10 sono illustrati i metadati JSON di Swagger generati dal microservizio eShopOnContainers (ovvero quello che gli strumenti usano nel livello sottostante) quando si richiede `http://<your-root-url>/swagger/v1/swagger.json` con [Postman](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="5902f-269">Figure 6-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request `http://<your-root-url>/swagger/v1/swagger.json` using [Postman](https://www.getpostman.com/).</span></span>

![Screenshot di un'interfaccia utente di esempio che mostra i metadati di spavalderia JSON.](./media/data-driven-crud-microservice/swagger-json-metadata.png)

<span data-ttu-id="5902f-271">**Figura 6-10**.</span><span class="sxs-lookup"><span data-stu-id="5902f-271">**Figure 6-10**.</span></span> <span data-ttu-id="5902f-272">Metadati JSON di Swagger</span><span class="sxs-lookup"><span data-stu-id="5902f-272">Swagger JSON metadata</span></span>

<span data-ttu-id="5902f-273">È davvero semplice.</span><span class="sxs-lookup"><span data-stu-id="5902f-273">It is that simple.</span></span> <span data-ttu-id="5902f-274">E dal momento che vengono generati automaticamente, i metadati di Swagger aumenteranno quando si aggiungeranno ulteriori funzionalità all'API.</span><span class="sxs-lookup"><span data-stu-id="5902f-274">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5902f-275">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5902f-275">Additional resources</span></span>

- <span data-ttu-id="5902f-276">**Pagine della Guida dell'API Web ASP.NET con Swagger** </span><span class="sxs-lookup"><span data-stu-id="5902f-276">**ASP.NET Web API Help Pages using Swagger** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger](/aspnet/core/tutorials/web-api-help-pages-using-swagger)

- <span data-ttu-id="5902f-277">**Introduzione a Swashbuckle e ad ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="5902f-277">**Get started with Swashbuckle and ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle](/aspnet/core/tutorials/getting-started-with-swashbuckle)

- <span data-ttu-id="5902f-278">**Introduzione a NSwag e ad ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="5902f-278">**Get started with NSwag and ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag](/aspnet/core/tutorials/getting-started-with-nswag)

> [!div class="step-by-step"]
> <span data-ttu-id="5902f-279">[Precedente](microservice-application-design.md)
> [Successivo](multi-container-applications-docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="5902f-279">[Previous](microservice-application-design.md)
[Next](multi-container-applications-docker-compose.md)</span></span>
