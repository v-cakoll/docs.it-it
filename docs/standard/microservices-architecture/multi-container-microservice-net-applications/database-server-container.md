---
title: Utilizzo di un server di database in esecuzione come un contenitore
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Utilizzo di un server di database in esecuzione come un contenitore
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7e5f33c4e7edf9d0d4551c5125976fcb8fda392f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="c0ef0-104">Utilizzo di un server di database in esecuzione come un contenitore</span><span class="sxs-lookup"><span data-stu-id="c0ef0-104">Using a database server running as a container</span></span>

<span data-ttu-id="c0ef0-105">È possibile disporre i database (SQL Server, PostgreSQL, MySQL e così via) nei server autonomi regolare, nel cluster locale o in servizi PaaS nel cloud come database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="c0ef0-106">Tuttavia, per gli ambienti di sviluppo e test, con i database in esecuzione come contenitori sia pratico, poiché tutte le dipendenze esterne, non si dispone e semplicemente in esecuzione la composizione di docker comando avvia l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency, and simply running the docker-compose command starts the whole application.</span></span> <span data-ttu-id="c0ef0-107">Presenza di tali database come contenitori è molto utile per i test di integrazione, anche perché il database viene avviato nel contenitore ed è sempre popolato con gli stessi dati di esempio, in modo test possono essere più prevedibili.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="c0ef0-108">SQL Server in esecuzione come un contenitore con un database di microservizio</span><span class="sxs-lookup"><span data-stu-id="c0ef0-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="c0ef0-109">In eShopOnContainers, c'è un contenitore denominato sql.data definito nel [docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file che esegue SQL Server per Linux con tutti i database di SQL Server necessari per il microservizi.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="c0ef0-110">(Si potrebbe avere anche un contenitore di SQL Server per ogni database, ma che richiederebbe più memoria assegnata a Docker). Il punto in microservizi importante è che ogni microservizio possiede i dati correlati, pertanto il database SQL correlato in questo caso.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="c0ef0-111">Ma i database possono trovarsi ovunque.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="c0ef0-112">Il contenitore nell'applicazione di esempio è configurato con il codice seguente YAML nel file docker compose.yml, che viene eseguito quando si esegue SQL Server docker-comporre backup.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run docker-compose up.</span></span> <span data-ttu-id="c0ef0-113">Si noti che il codice YAML è consolidato informazioni di configurazione dal file docker-compose.yml generico e il file compose.override.yml di docker.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="c0ef0-114">(In genere è necessario separare le impostazioni dell'ambiente dalle informazioni di base o statiche correlata all'immagine di SQL Server.)</span><span class="sxs-lookup"><span data-stu-id="c0ef0-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

<span data-ttu-id="c0ef0-115">Il seguente comando docker run è possibile eseguire tale contenitore:</span><span class="sxs-lookup"><span data-stu-id="c0ef0-115">The following docker run command can run that container:</span></span>

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

<span data-ttu-id="c0ef0-116">Tuttavia, se si distribuisce un'applicazione multi-contenitore come eShopOnContainers, è più pratico utilizzare il docker-comporre il comando in modo che venga distribuito a tutti i contenitori necessari per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the docker-compose up command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="c0ef0-117">Quando si avvia il contenitore di SQL Server per la prima volta, il contenitore Inizializza SQL Server con la password specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="c0ef0-118">Quando SQL Server è in esecuzione come un contenitore, è possibile aggiornare il database eseguendo la connessione tramite qualsiasi connessione SQL normale, ad esempio da SQL Server Management Studio, Visual Studio o C\# codice.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="c0ef0-119">L'applicazione eShopOnContainers Inizializza ogni database microservizio con dati di esempio seeding dei dati all'avvio, come illustrato nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="c0ef0-120">Con SQL Server in esecuzione come un contenitore non è utile solo per una dimostrazione in cui si potrebbe non avere accesso a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="c0ef0-121">Come indicato, è inoltre ideale per ambienti di sviluppo e test in modo da poter facilmente eseguire test di integrazione, a partire da un'immagine di SQL Server pulita e dati noti effettuando il seeding di nuovi dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="c0ef0-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c0ef0-122">Additional resources</span></span>

-   <span data-ttu-id="c0ef0-123">**Eseguire l'immagine di SQL Server Docker in Windows, Linux o Mac**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span><span class="sxs-lookup"><span data-stu-id="c0ef0-123">**Run the SQL Server Docker image on Linux, Mac, or Windows**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span></span>

-   <span data-ttu-id="c0ef0-124">**Connettersi ed eseguire query di SQL Server in Linux con sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="c0ef0-124">**Connect and query SQL Server on Linux with sqlcmd**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span></span>

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="c0ef0-125">Il seeding dei dati di test all'avvio dell'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="c0ef0-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="c0ef0-126">Per aggiungere dati al database all'avvio dell'applicazione, è possibile aggiungere il seguente codice al metodo nella classe di avvio del progetto API Web configura:</span><span class="sxs-lookup"><span data-stu-id="c0ef0-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

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

<span data-ttu-id="c0ef0-127">Il codice seguente nella classe CatalogContextSeed personalizzata consente di popolare i dati.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

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

<span data-ttu-id="c0ef0-128">Quando si eseguono test di integrazione, con un modo per generare dati coerenti con i test di integrazione è utile.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="c0ef0-129">La possibilità di creare da zero, tra cui un'istanza di SQL Server in esecuzione su un contenitore, è molto utile negli ambienti di test.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="c0ef0-130">Database principale InMemory EF rispetto a SQL Server in esecuzione come un contenitore</span><span class="sxs-lookup"><span data-stu-id="c0ef0-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="c0ef0-131">Un'altra scelta ottimale quando si eseguono test consiste nell'utilizzare il provider di database di Entity Framework InMemory.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="c0ef0-132">È possibile specificare che la configurazione nel metodo ConfigureServices della classe di avvio nel progetto API Web:</span><span class="sxs-lookup"><span data-stu-id="c0ef0-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

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

<span data-ttu-id="c0ef0-133">È un'importante catch, tuttavia.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-133">There is an important catch, though.</span></span> <span data-ttu-id="c0ef0-134">Il database in memoria supporta molti vincoli specifici di un determinato database.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="c0ef0-135">Ad esempio possibile aggiungere un indice univoco su una colonna nel modello Entity Framework Core e scrivere un test nel database in memoria per verificare che non consente di aggiungere un valore duplicato.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="c0ef0-136">Tuttavia, quando si utilizza il database in memoria, non sarà possibile gestire gli indici univoci in una colonna.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="c0ef0-137">Pertanto, il database in memoria non si comporta esattamente come un database di SQL Server reale, non viene emulato vincoli specifici del database.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="c0ef0-138">Anche in questo caso, un database in memoria è comunque utile per i test e la creazione di prototipi.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="c0ef0-139">Ma se si desidera creare i test di integrazione accurati che prendono in considerazione il comportamento di un'implementazione del database specifico, è necessario utilizzare un database reale, ad esempio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="c0ef0-140">A tale scopo, eseguire SQL Server in un contenitore è un ottimo choice e maggiore accurato rispetto al provider del database EF Core InMemory.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="c0ef0-141">Utilizzo di un servizio cache Redis in esecuzione in un contenitore</span><span class="sxs-lookup"><span data-stu-id="c0ef0-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="c0ef0-142">È possibile eseguire Redis su un contenitore, soprattutto per lo sviluppo e test e per gli scenari di prova.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="c0ef0-143">Questo scenario è pratico, poiché è possibile disporre di tutte le dipendenze in esecuzione in contenitori, non solo per i computer di sviluppo locale, ma per gli ambienti di testing nelle pipeline CI/CD-ROM.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="c0ef0-144">Tuttavia, quando si esegue Redis nell'ambiente di produzione, è preferibile cercare una soluzione a disponibilità elevata come Redis di Microsoft Azure, viene eseguito come un PaaS (piattaforma distribuita come servizio).</span><span class="sxs-lookup"><span data-stu-id="c0ef0-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="c0ef0-145">Nel codice, è sufficiente modificare le stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="c0ef0-146">Redis fornisce un'immagine di Docker con Redis.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="c0ef0-147">Tale immagine è disponibile dall'Hub Docker a questo URL:</span><span class="sxs-lookup"><span data-stu-id="c0ef0-147">That image is available from Docker Hub at this URL:</span></span>

<span data-ttu-id="c0ef0-148"><https://hub.docker.com/_/redis/></span><span class="sxs-lookup"><span data-stu-id="c0ef0-148"><https://hub.docker.com/_/redis/></span></span>

<span data-ttu-id="c0ef0-149">È possibile eseguire direttamente un contenitore Docker Redis eseguendo il comando di Docker CLI seguente nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="c0ef0-149">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```
  docker run --name some-redis -d redis
```

<span data-ttu-id="c0ef0-150">L'immagine di Redis include espongono: 6379 (la porta utilizzata da Redis), in modo standard contenitore collegamento renderà automaticamente disponibili per i contenitori collegati.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-150">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="c0ef0-151">In eShopOnContainers, il microservizio basket.api utilizza una cache Redis in esecuzione come un contenitore.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-151">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="c0ef0-152">Contenitore basket.data è definito come parte del file di multi-contenitore docker-compose.yml, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c0ef0-152">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="c0ef0-153">Questo codice di docker-compose.yml definisce un contenitore denominato basket.data basata sull'immagine di redis e pubblicare la porta 6379 internamente, vale a dire che sarà accessibile solo da altri contenitori in esecuzione all'interno dell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="c0ef0-153">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="c0ef0-154">Infine, nel file docker compose.override.yml il microservizio basket.api per l'esempio eShopOnContainers definisce la stringa di connessione da utilizzare per tale contenitore Redis:</span><span class="sxs-lookup"><span data-stu-id="c0ef0-154">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
<span data-ttu-id="c0ef0-155">[Precedente] (multi-container-applicazioni-docker-compose.md) [Avanti] (integrazione-eventi-base-microservizio-communications.md)</span><span class="sxs-lookup"><span data-stu-id="c0ef0-155">[Previous] (multi-container-applications-docker-compose.md) [Next] (integration-event-based-microservice-communications.md)</span></span>
