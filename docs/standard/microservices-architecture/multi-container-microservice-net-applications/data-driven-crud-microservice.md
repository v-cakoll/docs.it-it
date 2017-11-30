---
title: Creare un microservizio CRUD basati sui dati semplice
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Creare un microservizio CRUD basati sui dati semplice
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b814d344f2c78e7cf57f9e2896cf1d6b52db38d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="edc55-104">Creare un microservizio CRUD basati sui dati semplice</span><span class="sxs-lookup"><span data-stu-id="edc55-104">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="edc55-105">Questa sezione vengono illustrati come creare un semplice creare microservizio che esegue, leggere, aggiornamento e le operazioni di eliminazione (CRUD) su un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="edc55-105">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="edc55-106">Progettazione di un semplice microservizio CRUD</span><span class="sxs-lookup"><span data-stu-id="edc55-106">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="edc55-107">Dal punto di vista della progettazione, questo tipo di microservizio nei contenitori è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="edc55-107">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="edc55-108">Ad esempio il problema da risolvere è semplice, o forse l'implementazione è solo un modello di prova.</span><span class="sxs-lookup"><span data-stu-id="edc55-108">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![](./media/image4.png)

<span data-ttu-id="edc55-109">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="edc55-109">**Figure 8-4**.</span></span> <span data-ttu-id="edc55-110">Progettazione interna per microservizi CRUD semplice</span><span class="sxs-lookup"><span data-stu-id="edc55-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="edc55-111">Un esempio di questo tipo di servizio di unità di dati semplice è il catalogo microservizio dall'applicazione di esempio eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="edc55-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="edc55-112">Questo tipo di servizio implementa tutte le funzionalità in un unico progetto API Web di ASP.NET Core che include le classi per il modello di dati, la logica di business e il relativo codice di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="edc55-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="edc55-113">Anche i dati correlati vengono archiviati in un database in esecuzione in SQL Server (come un altro contenitore per scopi di sviluppo/test), ma potrebbe essere anche qualsiasi regolare host di SQL Server, come illustrato nella figura 8-5.</span><span class="sxs-lookup"><span data-stu-id="edc55-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 8-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="edc55-114">**Figura 8-5**.</span><span class="sxs-lookup"><span data-stu-id="edc55-114">**Figure 8-5**.</span></span> <span data-ttu-id="edc55-115">Progettazione di semplice microservizio dati basato su/CRUD</span><span class="sxs-lookup"><span data-stu-id="edc55-115">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="edc55-116">Quando si sviluppa questo tipo di servizio, è necessario solo [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) e una API di accesso ai dati o ORM come [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="edc55-116">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="edc55-117">È anche possibile generare [Swagger](http://swagger.io/) metadati automaticamente tramiti [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) per fornire una descrizione delle funzionalità offerte del servizio, come illustrato nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="edc55-117">You could also generate [Swagger](http://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="edc55-118">Si noti che esegue SQL Server all'interno di un contenitore Docker è ideale per ambienti di sviluppo, poiché tutte le dipendenze possono esistere fino a un server di database e in esecuzione senza la necessità di eseguire il provisioning di un database nel cloud o locale.</span><span class="sxs-lookup"><span data-stu-id="edc55-118">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="edc55-119">Ciò risulta molto utile quando si esegue l'integrazione di test.</span><span class="sxs-lookup"><span data-stu-id="edc55-119">This is very convenient when running integration tests.</span></span> <span data-ttu-id="edc55-120">Tuttavia, per ambienti di produzione, eseguire un server di database in un contenitore non è consigliabile, perché in genere non si ottengono disponibilità elevata con tale approccio.</span><span class="sxs-lookup"><span data-stu-id="edc55-120">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="edc55-121">Per un ambiente di produzione in Azure, è consigliabile utilizzare database SQL di Azure o qualsiasi altra tecnologia di database che può fornire la disponibilità elevata e scalabilità elevate.</span><span class="sxs-lookup"><span data-stu-id="edc55-121">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="edc55-122">Ad esempio, per un approccio NoSQL, è possibile scegliere di DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="edc55-122">For example, for a NoSQL approach, you might choose DocumentDB.</span></span>

<span data-ttu-id="edc55-123">Infine, modificando i file di metadati Dockerfile e docker compose.yml, è possibile configurare la modalità verrà creato l'immagine di questo contenitore, quale immagine di base di utilizzo, limiti più Progettazione impostazioni, ad esempio i nomi interni ed esterni e le porte TCP.</span><span class="sxs-lookup"><span data-stu-id="edc55-123">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span> 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="edc55-124">Implementazione di un semplice microservizio CRUD con ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="edc55-124">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="edc55-125">Per implementare una semplice microservizio CRUD utilizzando Visual Studio e .NET Core, è innanzitutto necessario creare un semplice progetto API Web di ASP.NET Core (in esecuzione su .NET Core che consentono di eseguire in un host Linux Docker), come illustrato nella figura 8-6.</span><span class="sxs-lookup"><span data-stu-id="edc55-125">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 8-6.</span></span>

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  <span data-ttu-id="edc55-126">![](./media/image6.png)   ![](./media/image7.png)</span><span class="sxs-lookup"><span data-stu-id="edc55-126">![](./media/image6.png)   ![](./media/image7.png)</span></span>
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

<span data-ttu-id="edc55-127">**Figura 8-6**.</span><span class="sxs-lookup"><span data-stu-id="edc55-127">**Figure 8-6**.</span></span> <span data-ttu-id="edc55-128">Creazione di un progetto di API Web di ASP.NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="edc55-128">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="edc55-129">Dopo aver creato il progetto, è possibile implementare i controller MVC, come in qualsiasi altro progetto API Web, utilizzando l'API di Entity Framework o altre API.</span><span class="sxs-lookup"><span data-stu-id="edc55-129">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="edc55-130">Nel progetto eShopOnContainers.Catalog.API, è possibile notare che le dipendenze principale per tale microservizio sono semplicemente ASP.NET Core stesso, Entity Framework e Swashbuckle, come illustrato nella figura 8-7.</span><span class="sxs-lookup"><span data-stu-id="edc55-130">In the eShopOnContainers.Catalog.API project, you can see that the main dependencies for that microservice are just ASP.NET Core itself, Entity Framework, and Swashbuckle, as shown in Figure 8-7.</span></span>

![](./media/image8.PNG)

<span data-ttu-id="edc55-131">**Figura 8-7**.</span><span class="sxs-lookup"><span data-stu-id="edc55-131">**Figure 8-7**.</span></span> <span data-ttu-id="edc55-132">Dipendenze in un semplice microservizio CRUD Web API</span><span class="sxs-lookup"><span data-stu-id="edc55-132">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="edc55-133">Implementazione dei servizi API Web CRUD con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="edc55-133">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="edc55-134">Componenti di base di Entity Framework (EF) è un tipo semplice, estendibile e e tecnologia di accesso multipiattaforma versione dei dati di Entity Framework più diffusi.</span><span class="sxs-lookup"><span data-stu-id="edc55-134">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="edc55-135">EF Core è un mapping relazionale a oggetti (ORM) che consente agli sviluppatori .NET di utilizzare un database utilizzando gli oggetti .NET.</span><span class="sxs-lookup"><span data-stu-id="edc55-135">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="edc55-136">Il catalogo di microservizio Usa Entity Framework e il provider SQL Server perché il database è in esecuzione in un contenitore con SQL Server per l'immagine di Linux Docker.</span><span class="sxs-lookup"><span data-stu-id="edc55-136">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="edc55-137">Tuttavia, il database può essere distribuito in qualsiasi Server SQL, ad esempio Windows locale o nel database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="edc55-137">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="edc55-138">L'unica cosa che è necessario modificare è una stringa di connessione in microservizio di ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="edc55-138">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="add-entity-framework-core-to-your-dependencies"></a><span data-ttu-id="edc55-139">Aggiungere le dipendenze di Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="edc55-139">Add Entity Framework Core to your dependencies</span></span>

<span data-ttu-id="edc55-140">È possibile installare il pacchetto NuGet per il provider di database che si desidera utilizzare, in questo caso SQL Server, dall'IDE di Visual Studio o con la console di NuGet.</span><span class="sxs-lookup"><span data-stu-id="edc55-140">You can install the NuGet package for the database provider you want to use, in this case SQL Server, from within the Visual Studio IDE or with the NuGet console.</span></span> <span data-ttu-id="edc55-141">Utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="edc55-141">Use the following command:</span></span>

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a><span data-ttu-id="edc55-142">Il modello di dati</span><span class="sxs-lookup"><span data-stu-id="edc55-142">The data model</span></span>

<span data-ttu-id="edc55-143">Con Entity Framework Core, accesso ai dati viene eseguita tramite un modello.</span><span class="sxs-lookup"><span data-stu-id="edc55-143">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="edc55-144">Un modello è costituito da classi di entità e un contesto derivato che rappresenta una sessione con il database, che consente di eseguire una query e salvare i dati.</span><span class="sxs-lookup"><span data-stu-id="edc55-144">A model is made up of entity classes and a derived context that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="edc55-145">È possibile generare un modello da un database esistente, manualmente un modello in modo che corrisponda al database di codice o usare le migrazioni di Entity Framework per creare un database dal modello (e sviluppare, come il modello viene modificato nel tempo).</span><span class="sxs-lookup"><span data-stu-id="edc55-145">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model (and evolve it as your model changes over time).</span></span> <span data-ttu-id="edc55-146">Per il catalogo di microservizio viene usato l'approccio ultimo.</span><span class="sxs-lookup"><span data-stu-id="edc55-146">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="edc55-147">È possibile vedere un esempio della classe di entità CatalogItem nell'esempio di codice seguente, che è un semplice oggetto CLR precedente normale ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) classe di entità.</span><span class="sxs-lookup"><span data-stu-id="edc55-147">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public CatalogItem() { }
}
```

<span data-ttu-id="edc55-148">È inoltre necessario un elemento DbContext che rappresenta una sessione con il database.</span><span class="sxs-lookup"><span data-stu-id="edc55-148">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="edc55-149">Per il catalogo di microservizio, la classe di CatalogContext deriva dalla classe di base DbContext, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="edc55-149">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }

    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

<span data-ttu-id="edc55-150">È possibile avere codice aggiuntivo nell'implementazione DbContext.</span><span class="sxs-lookup"><span data-stu-id="edc55-150">You can have additional code in the DbContext implementation.</span></span> <span data-ttu-id="edc55-151">Ad esempio, nell'applicazione di esempio, è necessario un metodo OnModelCreating nella classe CatalogContext che popola automaticamente i dati di esempio la prima volta che tenta di accedere al database.</span><span class="sxs-lookup"><span data-stu-id="edc55-151">For example, in the sample application, we have an OnModelCreating method in the CatalogContext class that automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="edc55-152">Questo metodo è utile per i dati demo.</span><span class="sxs-lookup"><span data-stu-id="edc55-152">This method is useful for demo data.</span></span> <span data-ttu-id="edc55-153">È anche possibile utilizzare il metodo OnModelCreating per personalizzare i mapping di entità di database o oggetti con molti altri [punti di estendibilità EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span><span class="sxs-lookup"><span data-stu-id="edc55-153">You can also use the OnModelCreating method to customize object/database entity mappings with many other [EF extensibility points](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

<span data-ttu-id="edc55-154">È possibile visualizzare altri dettagli sulla OnModelCreating nel [che implementa il livello di persistenza di infrastruttura con Entity Framework Core](#implementing_infrastructure_persistence) sezione più avanti in questo manuale.</span><span class="sxs-lookup"><span data-stu-id="edc55-154">You can see further details about OnModelCreating in the [Implementing the infrastructure-persistence layer with Entity Framework Core](#implementing_infrastructure_persistence) section later in this book.</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="edc55-155">Eseguire query sui dati da controller API Web</span><span class="sxs-lookup"><span data-stu-id="edc55-155">Querying data from Web API controllers</span></span>

<span data-ttu-id="edc55-156">Le istanze di classi di entità vengono in genere recuperate dal database di utilizzando Language Integrated Query (LINQ), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="edc55-156">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ??
           throw new ArgumentNullException(nameof(catalogIntegrationEventService));
        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
    [FromQuery]int pageIndex = 0)
    {
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

##### <a name="saving-data"></a><span data-ttu-id="edc55-157">Salvataggio di dati</span><span class="sxs-lookup"><span data-stu-id="edc55-157">Saving data</span></span>

<span data-ttu-id="edc55-158">Dati vengano creati, eliminati e modificati nel database utilizzando le istanze di classi di entità.</span><span class="sxs-lookup"><span data-stu-id="edc55-158">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="edc55-159">È possibile aggiungere codice analogo al livello di codice seguente (dati fittizi, in questo caso) ai controller di Web API.</span><span class="sxs-lookup"><span data-stu-id="edc55-159">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="edc55-160">Inserimento di dipendenze nel controller di ASP.NET Core e API Web</span><span class="sxs-lookup"><span data-stu-id="edc55-160">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="edc55-161">In ASP.NET Core è possibile utilizzare Dependency Injection (DI) predefinita.</span><span class="sxs-lookup"><span data-stu-id="edc55-161">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="edc55-162">Non è necessario configurare un contenitore Inversion of Control (IoC) di terze parti, anche se è possibile collegare il contenitore IoC preferito nell'infrastruttura ASP.NET Core se si desidera.</span><span class="sxs-lookup"><span data-stu-id="edc55-162">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="edc55-163">In questo caso, significa che è possibile inserire direttamente il DBContext EF richiesto o altri repository tramite il costruttore del controller.</span><span class="sxs-lookup"><span data-stu-id="edc55-163">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span> <span data-ttu-id="edc55-164">Nell'esempio precedente la classe CatalogController, ci stiamo inserendo un oggetto di tipo CatalogContext e altri oggetti tramite il costruttore CatalogController.</span><span class="sxs-lookup"><span data-stu-id="edc55-164">In the example above of the CatalogController class, we are injecting an object of CatalogContext type plus other objects through the CatalogController constructor.</span></span>

<span data-ttu-id="edc55-165">Una configurazione per impostare il progetto API Web importante è la registrazione della classe DbContext in un contenitore di inversione di controllo del servizio.</span><span class="sxs-lookup"><span data-stu-id="edc55-165">An important configuration to set up in the Web API project is the DbContext class registration into the service’s IoC container.</span></span> <span data-ttu-id="edc55-166">In genere non nella classe di avvio chiamando i servizi. Metodo AddDbContext all'interno del metodo ConfigureServices, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="edc55-166">You typically do so in the Startup class by calling the services.AddDbContext method inside the ConfigureServices method, as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
               typeof(Startup).
               GetTypeInfo().
               Assembly.
               GetName().Name);

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

### <a name="additional-resources"></a><span data-ttu-id="edc55-167">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="edc55-167">Additional resources</span></span>

-   <span data-ttu-id="edc55-168">**Eseguire query sui dati**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span><span class="sxs-lookup"><span data-stu-id="edc55-168">**Querying Data**
[*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span></span>

-   <span data-ttu-id="edc55-169">**Il salvataggio dei dati**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span><span class="sxs-lookup"><span data-stu-id="edc55-169">**Saving Data**
[*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span></span>

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="edc55-170">Il DB connessione stringa variabili e di ambiente utilizzate dai contenitori di Docker</span><span class="sxs-lookup"><span data-stu-id="edc55-170">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="edc55-171">È possibile utilizzare le impostazioni di ASP.NET Core e aggiungere una proprietà ConnectionString nel file Settings, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="edc55-171">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

```csharp
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

<span data-ttu-id="edc55-172">Il file Settings può avere valori predefiniti per la proprietà ConnectionString o per qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="edc55-172">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="edc55-173">Tuttavia, queste proprietà verranno sovrascritte dai valori delle variabili di ambiente specificata nel file compose.override.yml di docker.</span><span class="sxs-lookup"><span data-stu-id="edc55-173">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file.</span></span>

<span data-ttu-id="edc55-174">Da file di docker compose.yml o compose.override.yml di docker, è possibile inizializzare le variabili di ambiente in modo che Docker verrà impostarli come variabili di ambiente del sistema operativo, come illustrato nel seguente file di docker compose.override.yml (la connessione stringa e altre righe di eseguire il wrapping in questo esempio, ma potrebbe eseguire il wrapping in un file).</span><span class="sxs-lookup"><span data-stu-id="edc55-174">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    - ExternalCatalogBaseUrl=http://10.0.75.1:5101
    #- ExternalCatalogBaseUrl=http://dockerhoststaging.westus.cloudapp.azure.com:5101
  
  ports:
    - "5101:5101"
```

<span data-ttu-id="edc55-175">I file di docker compose.yml a livello di soluzione non solo i file di configurazione a livello di progetto o microservizio più flessibili, ma anche più sicura.</span><span class="sxs-lookup"><span data-stu-id="edc55-175">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure.</span></span> <span data-ttu-id="edc55-176">È consigliabile che le immagini Docker che si compila per microservizio non contengano il docker-compose.yml file, solo i file binari e i file di configurazione per ogni microservizio, tra cui Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="edc55-176">Consider that the Docker images that you build per microservice do not contain the docker-compose.yml files, only binary files and configuration files for each microservice, including the Dockerfile.</span></span> <span data-ttu-id="edc55-177">Ma non viene distribuito il file di docker compose.yml insieme all'applicazione; utilizzato solo in fase di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="edc55-177">But the docker-compose.yml file is not deployed along with your application; it is used only at deployment time.</span></span> <span data-ttu-id="edc55-178">Di conseguenza, i valori delle variabili di ambiente in tali file docker compose.yml (anche senza crittografia i valori) consiste nell'inserire più sicura dell'inserimento di tali valori nei file di configurazione .NET regolari distribuiti con il codice.</span><span class="sxs-lookup"><span data-stu-id="edc55-178">Therefore, placing environment variables values in those docker-compose.yml files (even without encrypting the values) is more secure than placing those values in regular .NET configuration files that are deployed with your code.</span></span>

<span data-ttu-id="edc55-179">Infine, è possibile ottenere tale valore dal codice utilizzando la configurazione\["ConnectionString"\], come illustrato nel metodo ConfigureServices in un esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="edc55-179">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="edc55-180">Tuttavia, per ambienti di produzione, potrebbe voler altri modi di explorer in modalità di archiviazione di informazioni riservate come le stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="edc55-180">However, for production environments, you might want to explorer additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="edc55-181">In genere che verranno gestiti da orchestrator la scelta, come è possibile eseguire con [Docker Swarm gestione segreti](https://docs.docker.com/engine/swarm/secrets/).</span><span class="sxs-lookup"><span data-stu-id="edc55-181">Usually that will be managed by your chosen orchestrator, like you can do with [Docker Swarm secrets management](https://docs.docker.com/engine/swarm/secrets/).</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="edc55-182">Implementazione di controllo delle versioni in ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="edc55-182">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="edc55-183">Come modificare i requisiti aziendali, è possibile aggiungere nuove raccolte di risorse, potrebbero modificare le relazioni tra le risorse e potrebbe essere modificata la struttura dei dati nelle risorse.</span><span class="sxs-lookup"><span data-stu-id="edc55-183">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="edc55-184">L'aggiornamento di un'API Web per gestire i nuovi requisiti è un processo relativamente semplice, ma è necessario considerare gli effetti che tali modifiche hanno su applicazioni client che utilizzano l'API Web.</span><span class="sxs-lookup"><span data-stu-id="edc55-184">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="edc55-185">Anche se lo sviluppatore di progettazione e implementazione di un'API Web ha il controllo completo su tale API, lo sviluppatore non hanno lo stesso livello di controllo sulle applicazioni client che potrebbe essere compilato da organizzazioni di terze parti opera in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="edc55-185">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="edc55-186">Controllo delle versioni consente un'API Web indicare le funzionalità e risorse che espone.</span><span class="sxs-lookup"><span data-stu-id="edc55-186">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="edc55-187">Un'applicazione client può quindi inviare richieste a una versione specifica di una funzione o una risorsa.</span><span class="sxs-lookup"><span data-stu-id="edc55-187">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="edc55-188">Esistono diversi approcci per implementare il controllo delle versioni:</span><span class="sxs-lookup"><span data-stu-id="edc55-188">There are several approaches to implement versioning:</span></span>

-   <span data-ttu-id="edc55-189">Controllo delle versioni URI</span><span class="sxs-lookup"><span data-stu-id="edc55-189">URI versioning</span></span>

-   <span data-ttu-id="edc55-190">Controllo delle versioni delle stringhe di query</span><span class="sxs-lookup"><span data-stu-id="edc55-190">Query string versioning</span></span>

-   <span data-ttu-id="edc55-191">Controllo delle versioni di intestazione</span><span class="sxs-lookup"><span data-stu-id="edc55-191">Header versioning</span></span>

<span data-ttu-id="edc55-192">Stringa di query e controllo delle versioni URI sono più semplici da implementare.</span><span class="sxs-lookup"><span data-stu-id="edc55-192">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="edc55-193">Controllo delle versioni di intestazione è un buon approccio.</span><span class="sxs-lookup"><span data-stu-id="edc55-193">Header versioning is a good approach.</span></span> <span data-ttu-id="edc55-194">Tuttavia, il controllo delle versioni dell'intestazione non come esplicita e semplice come il controllo delle versioni URI.</span><span class="sxs-lookup"><span data-stu-id="edc55-194">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="edc55-195">Poiché il controllo delle versioni di URL è il più semplice e più esplicito, l'applicazione di esempio eShopOnContainers utilizza il controllo delle versioni URI.</span><span class="sxs-lookup"><span data-stu-id="edc55-195">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="edc55-196">Il controllo delle versioni URI, come l'applicazione di esempio eShopOnContainers ogni volta che si modifica l'API Web o modificare lo schema di risorse, aggiungere un numero di versione per l'URI per ogni risorsa.</span><span class="sxs-lookup"><span data-stu-id="edc55-196">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="edc55-197">URI esistenti continueranno a funzionare come prima, la restituzione di risorse che è conforme allo schema che corrisponde alla versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="edc55-197">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="edc55-198">Come illustrato nell'esempio di codice seguente, la versione può essere impostata utilizzando l'attributo della Route nell'API Web, che rende esplicita nell'URI della versione (v1 in questo caso).</span><span class="sxs-lookup"><span data-stu-id="edc55-198">As shown in the following code example, the version can be set by using the Route attribute in the Web API, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="edc55-199">Questo meccanismo di controllo delle versioni è semplice e dipende dal server di routing della richiesta all'endpoint appropriato.</span><span class="sxs-lookup"><span data-stu-id="edc55-199">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="edc55-200">Per un controllo delle versioni più sofisticata e il metodo migliore quando si usa REST, tuttavia, è necessario utilizzare hypermedia e implementare [HATEOAS (Hypertext come motore di stato dell'applicazione)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span><span class="sxs-lookup"><span data-stu-id="edc55-200">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="edc55-201">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="edc55-201">Additional resources</span></span>

-   <span data-ttu-id="edc55-202">**Scott Hanselman. Controllo delle versioni API Web RESTful Core ASP.NET semplificato**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span><span class="sxs-lookup"><span data-stu-id="edc55-202">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
[*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span></span>

-   <span data-ttu-id="edc55-203">**Controllo delle versioni di un'API web RESTful**</span><span class="sxs-lookup"><span data-stu-id="edc55-203">**Versioning a RESTful web API**</span></span>

    [<span data-ttu-id="edc55-204">*https://docs.microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*</span><span class="sxs-lookup"><span data-stu-id="edc55-204">*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*</span></span>](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   <span data-ttu-id="edc55-205">**Roy Fielding. Controllo delle versioni e Hypermedia REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span><span class="sxs-lookup"><span data-stu-id="edc55-205">**Roy Fielding. Versioning, Hypermedia, and REST**
[*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span></span>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="edc55-206">La generazione di metadati di Swagger descrizione dall'API Web di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="edc55-206">Generating Swagger description metadata from your ASP.NET Core Web API</span></span> 

<span data-ttu-id="edc55-207">[Swagger](http://swagger.io/) è un framework di uso comune open source eseguito da un grande ecosistema di strumenti che consentono di progettazione, compilazione, documento e utilizzare le API REST.</span><span class="sxs-lookup"><span data-stu-id="edc55-207">[Swagger](http://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="edc55-208">È sempre lo standard per il dominio di metadati API descrizione.</span><span class="sxs-lookup"><span data-stu-id="edc55-208">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="edc55-209">È necessario includere i metadati Swagger descrizione con qualsiasi tipo di microservizio, microservizi basati sui dati o informazioni avanzate microservizi basati su dominio (come descritto nella sezione seguente).</span><span class="sxs-lookup"><span data-stu-id="edc55-209">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="edc55-210">Il cuore di Swagger è specifica di Swagger API descrizione metadati in un file JSON o YAML.</span><span class="sxs-lookup"><span data-stu-id="edc55-210">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="edc55-211">La specifica crea il contratto per l'API, che riporta in dettaglio tutte le risorse e operazioni sia un uomo e machine readable formato per sviluppare in modo semplice, individuazione e l'integrazione RESTful.</span><span class="sxs-lookup"><span data-stu-id="edc55-211">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="edc55-212">La specifica è la base della specifica OpenAPI (OAS) ed è sviluppata in una comunità open, trasparente e di collaborazione per standardizzare le modalità di interfacce REST sono definite.</span><span class="sxs-lookup"><span data-stu-id="edc55-212">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="edc55-213">La specifica definisce la struttura di come è possibile individuare un servizio e come le relative funzionalità riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="edc55-213">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="edc55-214">Per ulteriori informazioni, inclusi un editor di web e gli esempi di specifiche di Swagger di aziende come da Spotify, Uber, il margine di flessibilità e Microsoft, visitare il sito di Swagger (<http://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="edc55-214">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<http://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="edc55-215">Perché utilizzare Swagger?</span><span class="sxs-lookup"><span data-stu-id="edc55-215">Why use Swagger?</span></span>

<span data-ttu-id="edc55-216">I motivi principali per generare i metadati Swagger per le API sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="edc55-216">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="edc55-217">**Possibilità per gli altri prodotti integrare le API e utilizzare automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="edc55-217">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="edc55-218">Decine di prodotti e [strumenti esterna](http://swagger.io/commercial-tools/) e molti [Framework e librerie](http://swagger.io/open-source-integrations/) supportano Swagger.</span><span class="sxs-lookup"><span data-stu-id="edc55-218">Dozens of products and [commercial tools](http://swagger.io/commercial-tools/) and many [libraries and frameworks](http://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="edc55-219">Microsoft ha prodotti di alto livello e gli strumenti che possono automaticamente utilizzare API basate su Swagger, ad esempio le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="edc55-219">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

-   <span data-ttu-id="edc55-220">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="edc55-220">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="edc55-221">È possibile generare automaticamente le classi client .NET per la chiamata di Swagger.</span><span class="sxs-lookup"><span data-stu-id="edc55-221">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="edc55-222">This</span><span class="sxs-lookup"><span data-stu-id="edc55-222">This</span></span>

-   <span data-ttu-id="edc55-223">strumento può essere utilizzato da CLI e inoltre si integra con Visual Studio di facile utilizzo tramite l'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="edc55-223">tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

-   <span data-ttu-id="edc55-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="edc55-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span></span> <span data-ttu-id="edc55-225">È possibile eseguire automaticamente [utilizzare e integrare le API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) un alto livello flusso di lavoro Microsoft Flow, senza programmazione competenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="edc55-225">You can automatically [use and integrate your API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

-   <span data-ttu-id="edc55-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="edc55-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span></span> <span data-ttu-id="edc55-227">È possibile utilizzare automaticamente le API di [App per dispositivi mobili PowerApps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) compilati con [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), con nessuna programmazione competenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="edc55-227">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), with no programming skills required.</span></span>

-   <span data-ttu-id="edc55-228">[Servizio App di Azure logica app](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="edc55-228">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="edc55-229">È possibile eseguire automaticamente [utilizzare e integrare le API in un'App di Azure App Service logica](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), con nessuna programmazione competenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="edc55-229">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="edc55-230">**Possibilità di generare automaticamente la documentazione dell'API**.</span><span class="sxs-lookup"><span data-stu-id="edc55-230">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="edc55-231">Quando si crea l'API REST su larga scala, ad esempio applicazioni basate su microservizio complesse, è necessario gestire molti endpoint con diversi modelli di dati utilizzati nel payload di richiesta e risposta.</span><span class="sxs-lookup"><span data-stu-id="edc55-231">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="edc55-232">Con la documentazione e per avere un Esplora API a tinta unita, che si ottiene con Swagger, è chiave per la riuscita delle API e adozione dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="edc55-232">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="edc55-233">I metadati di swagger sono ciò che Microsoft Flow, PowerApps e App di logica di Azure Usa per comprendere come utilizzare le API e connettersi a essi.</span><span class="sxs-lookup"><span data-stu-id="edc55-233">Swagger’s metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="edc55-234">Come automatizzare la generazione di metadati Swagger API con il pacchetto Swashbuckle NuGet</span><span class="sxs-lookup"><span data-stu-id="edc55-234">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="edc55-235">Generazione metadati Swagger manualmente (in un file JSON o YAML) può essere noioso lavoro.</span><span class="sxs-lookup"><span data-stu-id="edc55-235">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="edc55-236">Tuttavia, è possibile automatizzare l'individuazione delle API dei servizi API Web ASP.NET utilizzando il [pacchetto Swashbuckle NuGet](http://aka.ms/swashbuckledotnetcore) per generare dinamicamente i metadati Swagger API.</span><span class="sxs-lookup"><span data-stu-id="edc55-236">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](http://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="edc55-237">Swashbuckle genera automaticamente i metadati Swagger per i progetti ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="edc55-237">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="edc55-238">Supporta i progetti API Web di ASP.NET Core e l'API Web ASP.NET tradizionale e altre caratteristiche, ad esempio Azure API App, App Mobile di Azure, Azure Service Fabric microservizi basati su ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="edc55-238">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="edc55-239">Supporta inoltre semplice API Web per i contenitori, come in per il riferimento applicazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="edc55-239">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="edc55-240">Swashbuckle combina esplorazione di API e Swagger o [dell'interfaccia utente swagger](https://github.com/swagger-api/swagger-ui) per fornire la documentazione e un'individuazione avanzata esperienza per consentire agli utenti di API.</span><span class="sxs-lookup"><span data-stu-id="edc55-240">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="edc55-241">Oltre il motore di generazione metadati Swagger, Swashbuckle contiene anche una versione incorporata di swagger-interfaccia utente, verrà utilizzato automaticamente backup una volta installato Swashbuckle.</span><span class="sxs-lookup"><span data-stu-id="edc55-241">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="edc55-242">Ciò significa che è possibile integrare dell'API di un'interfaccia utente per consentire agli sviluppatori di utilizzare l'API di individuazione nice.</span><span class="sxs-lookup"><span data-stu-id="edc55-242">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="edc55-243">Poiché viene generato automaticamente, consentendo di concentrarsi sulla compilazione l'API richiede una quantità limitata di codice e la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="edc55-243">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="edc55-244">Il risultato per l'esplorazione di API sarà come nella figura 8-8.</span><span class="sxs-lookup"><span data-stu-id="edc55-244">The result for the API Explorer looks like Figure 8-8.</span></span>

![](./media/image9.png)

<span data-ttu-id="edc55-245">**Figura 8-8**.</span><span class="sxs-lookup"><span data-stu-id="edc55-245">**Figure 8-8**.</span></span> <span data-ttu-id="edc55-246">Esplora API Swashbuckle in base ai metadati di Swagger: eShopOnContainers microservizio del catalogo</span><span class="sxs-lookup"><span data-stu-id="edc55-246">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="edc55-247">Esplora API non è in questo caso la cosa più importante.</span><span class="sxs-lookup"><span data-stu-id="edc55-247">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="edc55-248">Dopo aver creato un'API Web in grado di descrivere se stesso nei metadati di Swagger, l'API è facilmente utilizzabile da strumenti basati su Swagger, inclusi i generatori di codice di classe proxy client che possono essere destinati a più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="edc55-248">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="edc55-249">Ad esempio, come accennato, [AutoRest](https://github.com/Azure/AutoRest) genera automaticamente le classi client .NET.</span><span class="sxs-lookup"><span data-stu-id="edc55-249">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="edc55-250">Ma strumenti aggiuntivi, come [swagger codegen](https://github.com/swagger-api/swagger-codegen) sono anche disponibili, che consente la generazione del codice del client API librerie stub del server e documentazione automaticamente.</span><span class="sxs-lookup"><span data-stu-id="edc55-250">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="edc55-251">Attualmente, Swashbuckle è costituito da due pacchetti NuGet: Swashbuckle.SwaggerGen e Swashbuckle.SwaggerUi.</span><span class="sxs-lookup"><span data-stu-id="edc55-251">Currently, Swashbuckle consists of two NuGet packages: Swashbuckle.SwaggerGen and Swashbuckle.SwaggerUi.</span></span> <span data-ttu-id="edc55-252">Il primo fornisce funzionalità per generare uno o più documenti Swagger direttamente dall'implementazione di API ed esporli come endpoint JSON.</span><span class="sxs-lookup"><span data-stu-id="edc55-252">The former provides functionality to generate one or more Swagger documents directly from your API implementation and expose them as JSON endpoints.</span></span> <span data-ttu-id="edc55-253">Quest'ultimo fornisce una versione dello strumento dell'interfaccia utente swagger che può essere gestita dall'applicazione e con i documenti Swagger generati per descrivere l'API incorporata.</span><span class="sxs-lookup"><span data-stu-id="edc55-253">The latter provides an embedded version of the swagger-ui tool that can be served by your application and powered by the generated Swagger documents to describe your API.</span></span> <span data-ttu-id="edc55-254">Tuttavia, le versioni più recenti di Swashbuckle eseguire il wrapping con la metapackage Swashbuckle.AspNetCore.</span><span class="sxs-lookup"><span data-stu-id="edc55-254">However, the latest versions of Swashbuckle wrap these with the Swashbuckle.AspNetCore metapackage.</span></span>

<span data-ttu-id="edc55-255">Si noti che per i progetti .NET Core Web API, è necessario utilizzare [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) versione 1.0.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="edc55-255">Note that for .NET Core Web API projects, you need to use [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) version 1.0.0 or later.</span></span>

<span data-ttu-id="edc55-256">Dopo aver installato i pacchetti NuGet nel progetto API Web, è necessario configurare Swagger nella classe di avvio, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="edc55-256">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code:</span></span>

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...
        services.AddSwaggerGen();
        services.ConfigureSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SingleApiVersion(new Swashbuckle.Swagger.Model.Info()
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API",
                TermsOfService = "eShopOnContainers terms of service"
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
            .UseSwaggerUi();
    }
}
```

<span data-ttu-id="edc55-257">Al termine, è possibile avviare l'applicazione e passare i seguenti endpoint Swagger JSON e l'interfaccia utente utilizzando gli URL come queste:</span><span class="sxs-lookup"><span data-stu-id="edc55-257">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

<span data-ttu-id="edc55-258">Si è visto in precedenza l'interfaccia utente generato creato da Swashbuckle per un URL come http://&lt;l'url della radice&gt;swagger / dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="edc55-258">You previously saw the generated UI created by Swashbuckle for a URL like http://&lt;your-root-url&gt;/swagger/ui.</span></span> <span data-ttu-id="edc55-259">Nella figura 8-9 è inoltre possibile visualizzare come è possibile testare qualsiasi metodo API.</span><span class="sxs-lookup"><span data-stu-id="edc55-259">In Figure 8-9 you can also see how you can test any API method.</span></span>

![](./media/image10.png)

<span data-ttu-id="edc55-260">**Figura 8-9**.</span><span class="sxs-lookup"><span data-stu-id="edc55-260">**Figure 8-9**.</span></span> <span data-ttu-id="edc55-261">Swashbuckle test UI il metodo API o gli elementi del catalogo</span><span class="sxs-lookup"><span data-stu-id="edc55-261">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="edc55-262">Figura 8-10 vengono visualizzati i metadati di Swagger JSON generato dal microservizio eShopOnContainers (ovvero gli strumenti da utilizzare di sotto) quando si richiedono &lt;l'url della radice&gt;/swagger/v1/swagger.json utilizzando [Postman](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="edc55-262">Figure 8-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request &lt;your-root-url&gt;/swagger/v1/swagger.json using [Postman](https://www.getpostman.com/).</span></span>

![](./media/image11.png)

<span data-ttu-id="edc55-263">**Figura 8-10**.</span><span class="sxs-lookup"><span data-stu-id="edc55-263">**Figure 8-10**.</span></span> <span data-ttu-id="edc55-264">Metadati swagger JSON</span><span class="sxs-lookup"><span data-stu-id="edc55-264">Swagger JSON metadata</span></span>

<span data-ttu-id="edc55-265">È semplice.</span><span class="sxs-lookup"><span data-stu-id="edc55-265">It is that simple.</span></span> <span data-ttu-id="edc55-266">E poiché viene generato automaticamente, i metadati di Swagger aumenterà quando si aggiungono ulteriori funzionalità all'API.</span><span class="sxs-lookup"><span data-stu-id="edc55-266">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="edc55-267">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="edc55-267">Additional resources</span></span>

-   <span data-ttu-id="edc55-268">**ASP.NET Web API Guida pagine utilizzando Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span><span class="sxs-lookup"><span data-stu-id="edc55-268">**ASP.NET Web API Help Pages using Swagger**
[*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="edc55-269">[Precedente] (microservizio-applicazione-design.md) [Avanti] (multi-container-applicazioni-docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="edc55-269">[Previous] (microservice-application-design.md) [Next] (multi-container-applications-docker-compose.md)</span></span>
