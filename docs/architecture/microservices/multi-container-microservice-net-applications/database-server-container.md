---
title: Uso di un server di database eseguito come un contenitore
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Uso di un server di database eseguito come un contenitore - Solo per lo sviluppo. Informazioni sui motivi.
ms.date: 10/02/2018
ms.openlocfilehash: 3e655e26be2d6132577b0494db39d9c2e8b9aacd
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039845"
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="574b2-104">Uso di un server di database eseguito come un contenitore</span><span class="sxs-lookup"><span data-stu-id="574b2-104">Using a database server running as a container</span></span>

<span data-ttu-id="574b2-105">È possibile eseguire i database (SQL Server, PostgreSQL, MySQL e così via) su server autonomi normali, in cluster locali o in servizi PaaS sul cloud come il database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="574b2-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="574b2-106">Per ambienti di sviluppo e test, tuttavia, l'esecuzione dei database come contenitori risulta vantaggiosa, perché non sono presenti dipendenze esterne e l'esecuzione del comando `docker-compose up` basta per avviare l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="574b2-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="574b2-107">L'esecuzione dei database come contenitori risulta inoltre vantaggiosa per i test di integrazione, perché il database viene avviato nel contenitore e viene sempre popolato con gli stessi dati di esempio, in modo che i test siano più prevedibili.</span><span class="sxs-lookup"><span data-stu-id="574b2-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="574b2-108">SQL Server in esecuzione come contenitore con un database correlato ai microservizi</span><span class="sxs-lookup"><span data-stu-id="574b2-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="574b2-109">In eShopOnContainers è disponibile un contenitore denominato sql.data definito nel file [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) che esegue SQL Server per Linux con tutti i database di SQL Server necessari per i microservizi.</span><span class="sxs-lookup"><span data-stu-id="574b2-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="574b2-110">È anche possibile avere un contenitore SQL Server per ogni database, ma questo richiederebbe l'assegnazione di altra memoria a Docker. Per i microservizi è importante notare che ogni microservizio è proprietario dei rispettivi dati correlati e quindi del database SQL correlato in questo caso.</span><span class="sxs-lookup"><span data-stu-id="574b2-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="574b2-111">I database si possono tuttavia trovare ovunque.</span><span class="sxs-lookup"><span data-stu-id="574b2-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="574b2-112">Il contenitore SQL Server nell'applicazione di esempio viene configurato con il codice YAML seguente nel file docker-compose.yml, che viene eseguito quando si esegue `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="574b2-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="574b2-113">Si noti che il codice YAML ha consolidato le informazioni di configurazione dal file docker-compose.yml generico e dal file docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="574b2-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="574b2-114">È in genere necessario separare le impostazioni dell'ambiente dalle informazioni di base o statiche correlate all'immagine di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="574b2-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sql.data:
    image: microsoft/mssql-server-linux:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="574b2-115">Analogamente, invece di usare `docker-compose`, il comando `docker run` seguente può eseguire tale contenitore:</span><span class="sxs-lookup"><span data-stu-id="574b2-115">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```console
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d microsoft/mssql-server-linux:2017-latest
```

<span data-ttu-id="574b2-116">Se tuttavia si distribuisce un'applicazione a più contenitori come eShopOnContainers, risulta più semplice usare il comando `docker-compose up`, in modo che vengano distribuiti tutti i contenitori necessari per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="574b2-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="574b2-117">Quando si avvia questo contenitore SQL Server per la prima volta, il contenitore inizializza SQL Server con la password specificata.</span><span class="sxs-lookup"><span data-stu-id="574b2-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="574b2-118">Quando SQL Server è in esecuzione come contenitore, è possibile aggiornare il database connettendolo tramite qualsiasi connessione SQL normale, ad esempio da SQL Server Management Studio, Visual Studio o codice C\#.</span><span class="sxs-lookup"><span data-stu-id="574b2-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="574b2-119">L'applicazione eShopOnContainers inizializza ogni database di microservizio con dati di esempio eseguendo il seeding del database con dati all'avvio, come illustrato nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="574b2-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="574b2-120">L'esecuzione di SQL Server come contenitore non è solo utile per una demo, in cui è possibile che non sia disponibile l'accesso a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="574b2-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="574b2-121">Come indicato, risulta vantaggiosa anche per ambienti di sviluppo e test, perché consente di integrare con facilità i test di integrazione a partire da un'immagine di SQL Server pulita e da dati noti tramite il seeding di nuovi dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="574b2-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="574b2-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="574b2-122">Additional resources</span></span>

- <span data-ttu-id="574b2-123">**Eseguire l'immagine di SQL Server Docker in Linux, Mac o Windows** </span><span class="sxs-lookup"><span data-stu-id="574b2-123">**Run the SQL Server Docker image on Linux, Mac, or Windows** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker](/sql/linux/sql-server-linux-setup-docker)

- <span data-ttu-id="574b2-124">**Connettere ed eseguire query di SQL Server in Linux con sqlcmd** </span><span class="sxs-lookup"><span data-stu-id="574b2-124">**Connect and query SQL Server on Linux with sqlcmd** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd](/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="574b2-125">Seeding con dati di test all'avvio di un'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="574b2-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="574b2-126">Per aggiungere dati al database all'avvio dell'applicazione, è possibile aggiungere codice simile al seguente al metodo Configure nella classe Startup del progetto API Web:</span><span class="sxs-lookup"><span data-stu-id="574b2-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code...
    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure code...
        // Seed data through our custom class
        CatalogContextSeed.SeedAsync(app)
            .Wait();
        // Other Configure code...
    }
}
```

<span data-ttu-id="574b2-127">Il codice seguente nella classe CatalogContextSeed personalizzata popola i dati.</span><span class="sxs-lookup"><span data-stu-id="574b2-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

```csharp
public class CatalogContextSeed
{
    public static async Task SeedAsync(IApplicationBuilder applicationBuilder)
    {
        var context = (CatalogContext)applicationBuilder
            .ApplicationServices.GetService(typeof(CatalogContext));
        using (context)
        {
            context.Database.Migrate();
            if (!context.CatalogBrands.Any())
            {
                context.CatalogBrands.AddRange(
                    GetPreconfiguredCatalogBrands());
                await context.SaveChangesAsync();
            }
            if (!context.CatalogTypes.Any())
            {
                context.CatalogTypes.AddRange(
                    GetPreconfiguredCatalogTypes());
                await context.SaveChangesAsync();
            }
        }
    }

    static IEnumerable<CatalogBrand> GetPreconfiguredCatalogBrands()
    {
        return new List<CatalogBrand>()
       {
           new CatalogBrand() { Brand = "Azure"},
           new CatalogBrand() { Brand = ".NET" },
           new CatalogBrand() { Brand = "Visual Studio" },
           new CatalogBrand() { Brand = "SQL Server" }
       };
    }

    static IEnumerable<CatalogType> GetPreconfiguredCatalogTypes()
    {
        return new List<CatalogType>()
        {
            new CatalogType() { Type = "Mug"},
            new CatalogType() { Type = "T-Shirt" },
            new CatalogType() { Type = "Backpack" },
            new CatalogType() { Type = "USB Memory Stick" }
        };
    }
}
```

<span data-ttu-id="574b2-128">Quando si eseguono test di integrazione, un'opzione per la generazione di dati coerenti con i test di integrazione risulta utile.</span><span class="sxs-lookup"><span data-stu-id="574b2-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="574b2-129">La possibilità di creare qualsiasi elemento da zero, inclusa un'istanza di SQL Server in esecuzione in un contenitore, risulta vantaggiosa per gli ambienti di test.</span><span class="sxs-lookup"><span data-stu-id="574b2-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="574b2-130">Confronto tra un database EF Core InMemory e SQL Server eseguito come contenitore</span><span class="sxs-lookup"><span data-stu-id="574b2-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="574b2-131">Un'altra opzione vantaggiosa per l'esecuzione di test consiste nell'usare il provider di database Entity Framework InMemory.</span><span class="sxs-lookup"><span data-stu-id="574b2-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="574b2-132">È possibile specificare tale configurazione nel metodo ConfigureServices della classe Startup nel progetto API Web:</span><span class="sxs-lookup"><span data-stu-id="574b2-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code ...
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IConfiguration>(Configuration);
        // DbContext using an InMemory database provider
        services.AddDbContext<CatalogContext>(opt => opt.UseInMemoryDatabase());
        //(Alternative: DbContext using a SQL Server provider
        //services.AddDbContext<CatalogContext>(c =>
        //{
            // c.UseSqlServer(Configuration["ConnectionString"]);
            //
        //});
    }
  
    // Other Startup code ...
}
```

<span data-ttu-id="574b2-133">Questa opzione presenta tuttavia uno svantaggio significativo.</span><span class="sxs-lookup"><span data-stu-id="574b2-133">There is an important catch, though.</span></span> <span data-ttu-id="574b2-134">Il database in memoria non supporta molti vincoli specifici per un determinato database.</span><span class="sxs-lookup"><span data-stu-id="574b2-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="574b2-135">È ad esempio possibile aggiungere un indice univoco a una colonna nel modello di EF Core e scrivere un test rispetto al database in memoria per verificare che non consenta l'aggiunta di un valore duplicato.</span><span class="sxs-lookup"><span data-stu-id="574b2-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="574b2-136">Quando tuttavia si usa il database in memoria, non è possibile gestire indici univoci su una colonna.</span><span class="sxs-lookup"><span data-stu-id="574b2-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="574b2-137">Il database in memoria non si comporta quindi esattamente in modo analogo a un database di SQL Server effettivo, poiché non emula i vincoli specifici del database.</span><span class="sxs-lookup"><span data-stu-id="574b2-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="574b2-138">Il database in memoria risulta comunque utile per i test e la creazione di prototipi.</span><span class="sxs-lookup"><span data-stu-id="574b2-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="574b2-139">Se tuttavia si vogliono creare test di integrazione precisi che prendono in considerazione il comportamento di un'implementazione specifica del database, è necessario usare un database effettivo come SQL Server.</span><span class="sxs-lookup"><span data-stu-id="574b2-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="574b2-140">L'esecuzione di SQL Server in un contenitore per questa finalità è un'opzione ottimale e più precisa rispetto al provider di database EF Core InMemory.</span><span class="sxs-lookup"><span data-stu-id="574b2-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="574b2-141">Uso di un servizio cache Redis in esecuzione in un contenitore</span><span class="sxs-lookup"><span data-stu-id="574b2-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="574b2-142">È possibile eseguire Redis su un contenitore, in particolare per scenari di sviluppo e test e di modello di verifica.</span><span class="sxs-lookup"><span data-stu-id="574b2-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="574b2-143">Questo scenario risulta molto vantaggioso, perché consente di eseguire tutte le dipendenze nei contenitori, non solo per i computer di sviluppo locali, ma per gli ambienti di test nelle pipeline di integrazione continua/recapito continuo.</span><span class="sxs-lookup"><span data-stu-id="574b2-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="574b2-144">Quando tuttavia si esegue Redis in produzione, è consigliabile cercare una soluzione a disponibilità elevata come Redis Microsoft Azure, eseguita come PaaS (Platform as a Service).</span><span class="sxs-lookup"><span data-stu-id="574b2-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="574b2-145">Nel codice è sufficiente modificare le stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="574b2-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="574b2-146">Redis offre un'immagine di Docker con Redis.</span><span class="sxs-lookup"><span data-stu-id="574b2-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="574b2-147">L'immagine è disponibile da Docker Hub in questo URL:</span><span class="sxs-lookup"><span data-stu-id="574b2-147">That image is available from Docker Hub at this URL:</span></span>

<https://hub.docker.com/\_/redis/>

<span data-ttu-id="574b2-148">È possibile eseguire direttamente un contenitore Docker Redis eseguendo questo comando dell'interfaccia della riga di comando di Docker dal prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="574b2-148">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```console
  docker run --name some-redis -d redis
```

<span data-ttu-id="574b2-149">L'immagine Redis include expose:6379 (porta usata da Redis), quindi i collegamenti standard dei contenitori la renderanno automaticamente disponibile ai contenitori collegati.</span><span class="sxs-lookup"><span data-stu-id="574b2-149">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="574b2-150">In eShopOnContainers il microservizio basket.api usa una cache Redis eseguita come contenitore.</span><span class="sxs-lookup"><span data-stu-id="574b2-150">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="574b2-151">Il contenitore basket.data viene definito come parte del file docker-compose.yml a più contenitori, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="574b2-151">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="574b2-152">Il codice nel file docker-compose.yml definisce un contenitore denominato basket.data basato sull'immagine Redis e la porta 6379 viene pubblicata internamente, quindi sarà accessibile solo da altri contenitori in esecuzione entro l'host Docker.</span><span class="sxs-lookup"><span data-stu-id="574b2-152">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="574b2-153">Nel file docker-compose.override.yml infine il microservizio basket.api per l'esempio eShopOnContainers definisce la stringa di connessione da usare per il contenitore Redis:</span><span class="sxs-lookup"><span data-stu-id="574b2-153">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="574b2-154">Come detto in precedenza, il nome del microservizio "basket.data" viene risolto dal DNS della rete interna di Docker.</span><span class="sxs-lookup"><span data-stu-id="574b2-154">As mentioned before, the name of the microservice "basket.data" is resolved by docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="574b2-155">[Precedente](multi-container-applications-docker-compose.md)
>[Successivo](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="574b2-155">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
