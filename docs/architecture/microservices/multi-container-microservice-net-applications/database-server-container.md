---
title: Usare un server di database in esecuzione come contenitoreUse a database server running as a container
description: Comprendere l'importanza di utilizzare un server di database in esecuzione come contenitore solo per lo sviluppo. Mai per la produzione.
ms.date: 01/30/2020
ms.openlocfilehash: 0cbc933003aac10970814378c27e88b5cb0ddbe5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628527"
---
# <a name="use-a-database-server-running-as-a-container"></a><span data-ttu-id="3fd6a-104">Usare un server di database in esecuzione come contenitoreUse a database server running as a container</span><span class="sxs-lookup"><span data-stu-id="3fd6a-104">Use a database server running as a container</span></span>

<span data-ttu-id="3fd6a-105">È possibile eseguire i database (SQL Server, PostgreSQL, MySQL e così via) su server autonomi normali, in cluster locali o in servizi PaaS sul cloud come il database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="3fd6a-106">Tuttavia, per gli ambienti di sviluppo e test, è utile che i database vengano `docker-compose up` eseguiti come contenitori, perché non si dispone di alcuna dipendenza esterna e si esegue semplicemente il comando per avviare l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-106">However, for development and test environments, having your databases running as containers is convenient, because you don't have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="3fd6a-107">L'esecuzione dei database come contenitori risulta inoltre vantaggiosa per i test di integrazione, perché il database viene avviato nel contenitore e viene sempre popolato con gli stessi dati di esempio, in modo che i test siano più prevedibili.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="3fd6a-108">SQL Server in esecuzione come contenitore con un database correlato ai microservizi</span><span class="sxs-lookup"><span data-stu-id="3fd6a-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="3fd6a-109">In eShopOnContainers è presente un `sqldata`contenitore denominato , come definito nel file [docker-compose.yml,](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) che esegue un'istanza di SQL Server per Linux con i database SQL per tutti i microservizi che ne hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-109">In eShopOnContainers, there's a container named `sqldata`, as defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file, that runs a SQL Server for Linux instance with the SQL databases for all microservices that need one.</span></span>

<span data-ttu-id="3fd6a-110">Un punto chiave nei microservizi è che ogni microservizio possiede i dati correlati, pertanto deve avere un proprio database.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-110">A key point in microservices is that each microservice owns its related data, so it should have its own database.</span></span> <span data-ttu-id="3fd6a-111">Tuttavia, i database possono essere ovunque.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-111">However, the databases can be anywhere.</span></span> <span data-ttu-id="3fd6a-112">In questo caso, sono tutti nello stesso contenitore per mantenere i requisiti di memoria Docker il più basso possibile.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-112">In this case, they are all in the same container to keep Docker memory requirements as low as possible.</span></span> <span data-ttu-id="3fd6a-113">Tenete a mente che questa è una soluzione sufficiente per lo sviluppo e, forse, test, ma non per la produzione.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-113">Keep in mind that this is a good-enough solution for development and, perhaps, testing but not for production.</span></span>

<span data-ttu-id="3fd6a-114">Il contenitore SQL Server nell'applicazione di esempio viene configurato con il codice YAML seguente nel file docker-compose.yml, che viene eseguito quando si esegue `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-114">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="3fd6a-115">Si noti che il codice YAML ha consolidato le informazioni di configurazione dal file docker-compose.yml generico e dal file docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-115">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="3fd6a-116">È in genere necessario separare le impostazioni dell'ambiente dalle informazioni di base o statiche correlate all'immagine di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-116">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="3fd6a-117">Analogamente, invece di usare `docker-compose`, il comando `docker run` seguente può eseguire tale contenitore:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-117">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

<span data-ttu-id="3fd6a-118">Se tuttavia si distribuisce un'applicazione a più contenitori come eShopOnContainers, risulta più semplice usare il comando `docker-compose up`, in modo che vengano distribuiti tutti i contenitori necessari per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-118">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="3fd6a-119">Quando si avvia questo contenitore SQL Server per la prima volta, il contenitore inizializza SQL Server con la password specificata.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-119">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="3fd6a-120">Quando SQL Server è in esecuzione come contenitore, è possibile aggiornare il database connettendolo tramite qualsiasi connessione SQL normale, ad esempio da SQL Server Management Studio, Visual Studio o codice C\#.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-120">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="3fd6a-121">L'applicazione eShopOnContainers inizializza ogni database di microservizio con dati di esempio eseguendo il seeding del database con dati all'avvio, come illustrato nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-121">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="3fd6a-122">L'esecuzione di SQL Server come contenitore non è solo utile per una demo, in cui è possibile che non sia disponibile l'accesso a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-122">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="3fd6a-123">Come indicato, risulta vantaggiosa anche per ambienti di sviluppo e test, perché consente di integrare con facilità i test di integrazione a partire da un'immagine di SQL Server pulita e da dati noti tramite il seeding di nuovi dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-123">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3fd6a-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3fd6a-124">Additional resources</span></span>

- <span data-ttu-id="3fd6a-125">**Eseguire l'immagine Docker di SQL Server in Linux, Mac o Windows** </span><span class="sxs-lookup"><span data-stu-id="3fd6a-125">**Run the SQL Server Docker image on Linux, Mac, or Windows** </span></span>\
  <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- <span data-ttu-id="3fd6a-126">**Connetti ed esegui query su SQL Server su Linux con sqlcmd** </span><span class="sxs-lookup"><span data-stu-id="3fd6a-126">**Connect and query SQL Server on Linux with sqlcmd** </span></span>\
  <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="3fd6a-127">Seeding con dati di test all'avvio di un'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="3fd6a-127">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="3fd6a-128">Per aggiungere dati al database all'avvio dell'applicazione, è `Main` possibile `Program` aggiungere codice simile al seguente al metodo nella classe del progetto API Web:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-128">To add data to the database when the application starts up, you can add code like the following to the `Main` method in the `Program` class of the Web API project:</span></span>

```csharp
public static int Main(string[] args)
{
    var configuration = GetConfiguration();

    Log.Logger = CreateSerilogLogger(configuration);

    try
    {
        Log.Information("Configuring web host ({ApplicationContext})...", AppName);
        var host = CreateHostBuilder(configuration, args);

        Log.Information("Applying migrations ({ApplicationContext})...", AppName);
        host.MigrateDbContext<CatalogContext>((context, services) =>
        {
            var env = services.GetService<IWebHostEnvironment>();
            var settings = services.GetService<IOptions<CatalogSettings>>();
            var logger = services.GetService<ILogger<CatalogContextSeed>>();

            new CatalogContextSeed()
                .SeedAsync(context, env, settings, logger)
                .Wait();
        })
        .MigrateDbContext<IntegrationEventLogContext>((_, __) => { });

        Log.Information("Starting web host ({ApplicationContext})...", AppName);
        host.Run();

        return 0;
    }
    catch (Exception ex)
    {
        Log.Fatal(ex, "Program terminated unexpectedly ({ApplicationContext})!", AppName);
        return 1;
    }
    finally
    {
        Log.CloseAndFlush();
    }
}
```

<span data-ttu-id="3fd6a-129">C'è un avvertimento importante quando si applicano le migrazioni e seeding di un database durante l'avvio del contenitore.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-129">There's an important caveat when applying migrations and seeding a database during container startup.</span></span> <span data-ttu-id="3fd6a-130">Poiché il server di database potrebbe non essere disponibile per qualsiasi motivo, è necessario gestire i tentativi durante l'attesa che il server sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-130">Since the database server might not be available for whatever reason, you must handle retries while waiting for the server to be available.</span></span> <span data-ttu-id="3fd6a-131">Questa logica di ripetizione `MigrateDbContext()` dei tentativi viene gestita dal metodo di estensione, come illustrato nel codice seguente:This retry logic is handled by the extension method, as shown in the following code:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-131">This retry logic is handled by the `MigrateDbContext()` extension method, as shown in the following code:</span></span>

```cs
public static IWebHost MigrateDbContext<TContext>(
    this IWebHost host,
    Action<TContext,
    IServiceProvider> seeder)
      where TContext : DbContext
{
    var underK8s = host.IsInKubernetes();

    using (var scope = host.Services.CreateScope())
    {
        var services = scope.ServiceProvider;

        var logger = services.GetRequiredService<ILogger<TContext>>();

        var context = services.GetService<TContext>();

        try
        {
            logger.LogInformation("Migrating database associated with context {DbContextName}", typeof(TContext).Name);

            if (underK8s)
            {
                InvokeSeeder(seeder, context, services);
            }
            else
            {
                var retry = Policy.Handle<SqlException>()
                    .WaitAndRetry(new TimeSpan[]
                    {
                    TimeSpan.FromSeconds(3),
                    TimeSpan.FromSeconds(5),
                    TimeSpan.FromSeconds(8),
                    });

                //if the sql server container is not created on run docker compose this
                //migration can't fail for network related exception. The retry options for DbContext only
                //apply to transient exceptions
                // Note that this is NOT applied when running some orchestrators (let the orchestrator to recreate the failing service)
                retry.Execute(() => InvokeSeeder(seeder, context, services));
            }

            logger.LogInformation("Migrated database associated with context {DbContextName}", typeof(TContext).Name);
        }
        catch (Exception ex)
        {
            logger.LogError(ex, "An error occurred while migrating the database used on context {DbContextName}", typeof(TContext).Name);
            if (underK8s)
            {
                throw;          // Rethrow under k8s because we rely on k8s to re-run the pod
            }
        }
    }

    return host;
}
```

<span data-ttu-id="3fd6a-132">Il codice seguente nella classe CatalogContextSeed personalizzata popola i dati.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-132">The following code in the custom CatalogContextSeed class populates the data.</span></span>

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

<span data-ttu-id="3fd6a-133">Quando si eseguono test di integrazione, un'opzione per la generazione di dati coerenti con i test di integrazione risulta utile.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-133">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="3fd6a-134">La possibilità di creare qualsiasi elemento da zero, inclusa un'istanza di SQL Server in esecuzione in un contenitore, risulta vantaggiosa per gli ambienti di test.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-134">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="3fd6a-135">Confronto tra un database EF Core InMemory e SQL Server eseguito come contenitore</span><span class="sxs-lookup"><span data-stu-id="3fd6a-135">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="3fd6a-136">Un'altra opzione vantaggiosa per l'esecuzione di test consiste nell'usare il provider di database Entity Framework InMemory.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-136">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="3fd6a-137">È possibile specificare tale configurazione nel metodo ConfigureServices della classe Startup nel progetto API Web:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-137">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

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

<span data-ttu-id="3fd6a-138">Questa opzione presenta tuttavia uno svantaggio significativo.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-138">There is an important catch, though.</span></span> <span data-ttu-id="3fd6a-139">Il database in memoria non supporta molti vincoli specifici per un determinato database.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-139">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="3fd6a-140">È ad esempio possibile aggiungere un indice univoco a una colonna nel modello di EF Core e scrivere un test rispetto al database in memoria per verificare che non consenta l'aggiunta di un valore duplicato.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-140">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="3fd6a-141">Quando tuttavia si usa il database in memoria, non è possibile gestire indici univoci su una colonna.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-141">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="3fd6a-142">Il database in memoria non si comporta quindi esattamente in modo analogo a un database di SQL Server effettivo, poiché non emula i vincoli specifici del database.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-142">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="3fd6a-143">Il database in memoria risulta comunque utile per i test e la creazione di prototipi.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-143">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="3fd6a-144">Se tuttavia si vogliono creare test di integrazione precisi che prendono in considerazione il comportamento di un'implementazione specifica del database, è necessario usare un database effettivo come SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-144">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="3fd6a-145">L'esecuzione di SQL Server in un contenitore per questa finalità è un'opzione ottimale e più precisa rispetto al provider di database EF Core InMemory.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-145">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

## <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="3fd6a-146">Uso di un servizio cache Redis in esecuzione in un contenitore</span><span class="sxs-lookup"><span data-stu-id="3fd6a-146">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="3fd6a-147">È possibile eseguire Redis su un contenitore, in particolare per scenari di sviluppo e test e di modello di verifica.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-147">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="3fd6a-148">Questo scenario risulta molto vantaggioso, perché consente di eseguire tutte le dipendenze nei contenitori, non solo per i computer di sviluppo locali, ma per gli ambienti di test nelle pipeline di integrazione continua/recapito continuo.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-148">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="3fd6a-149">Quando tuttavia si esegue Redis in produzione, è consigliabile cercare una soluzione a disponibilità elevata come Redis Microsoft Azure, eseguita come PaaS (Platform as a Service).</span><span class="sxs-lookup"><span data-stu-id="3fd6a-149">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="3fd6a-150">Nel codice è sufficiente modificare le stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-150">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="3fd6a-151">Redis offre un'immagine di Docker con Redis.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-151">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="3fd6a-152">L'immagine è disponibile da Docker Hub in questo URL:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-152">That image is available from Docker Hub at this URL:</span></span>

<https://hub.docker.com/_/redis/>

<span data-ttu-id="3fd6a-153">È possibile eseguire direttamente un contenitore Docker Redis eseguendo questo comando dell'interfaccia della riga di comando di Docker dal prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-153">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```console
docker run --name some-redis -d redis
```

<span data-ttu-id="3fd6a-154">L'immagine Redis include expose:6379 (porta usata da Redis), quindi i collegamenti standard dei contenitori la renderanno automaticamente disponibile ai contenitori collegati.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-154">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="3fd6a-155">In eShopOnContainers, `basket-api` il microservizio usa una cache Redis in esecuzione come contenitore.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-155">In eShopOnContainers, the `basket-api` microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="3fd6a-156">Tale `basketdata` contenitore è definito come parte del file *docker-compose.yml multi-contenitore,* come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-156">That `basketdata` container is defined as part of the multi-container *docker-compose.yml* file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="3fd6a-157">Questo codice in docker-compose.yml definisce `basketdata` un contenitore denominato in base all'immagine redis e la pubblicazione della porta 6379 internamente.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-157">This code in the docker-compose.yml defines a container named `basketdata` based on the redis image and publishing the port 6379 internally.</span></span> <span data-ttu-id="3fd6a-158">Ciò significa che sarà accessibile solo da altri contenitori in esecuzione all'interno dell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-158">This means that it will only be accessible from other containers running within the Docker host.</span></span>

<span data-ttu-id="3fd6a-159">Infine, nel file *docker-compose.override.yml,* il `basket-api` microservizio per l'esempio eShopOnContainers definisce la stringa di connessione da utilizzare per il contenitore Redis:</span><span class="sxs-lookup"><span data-stu-id="3fd6a-159">Finally, in the *docker-compose.override.yml* file, the `basket-api` microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="3fd6a-160">Come accennato in precedenza, il nome del microservizio `basketdata` viene risolto dal DNS della rete interna di Docker.</span><span class="sxs-lookup"><span data-stu-id="3fd6a-160">As mentioned before, the name of the microservice `basketdata` is resolved by Docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3fd6a-161">[Successivo](multi-container-applications-docker-compose.md)
>[precedente](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="3fd6a-161">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
