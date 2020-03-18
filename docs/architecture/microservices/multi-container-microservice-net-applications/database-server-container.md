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
# <a name="use-a-database-server-running-as-a-container"></a>Usare un server di database in esecuzione come contenitoreUse a database server running as a container

È possibile eseguire i database (SQL Server, PostgreSQL, MySQL e così via) su server autonomi normali, in cluster locali o in servizi PaaS sul cloud come il database SQL di Azure. Tuttavia, per gli ambienti di sviluppo e test, è utile che i database vengano `docker-compose up` eseguiti come contenitori, perché non si dispone di alcuna dipendenza esterna e si esegue semplicemente il comando per avviare l'intera applicazione. L'esecuzione dei database come contenitori risulta inoltre vantaggiosa per i test di integrazione, perché il database viene avviato nel contenitore e viene sempre popolato con gli stessi dati di esempio, in modo che i test siano più prevedibili.

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server in esecuzione come contenitore con un database correlato ai microservizi

In eShopOnContainers è presente un `sqldata`contenitore denominato , come definito nel file [docker-compose.yml,](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) che esegue un'istanza di SQL Server per Linux con i database SQL per tutti i microservizi che ne hanno bisogno.

Un punto chiave nei microservizi è che ogni microservizio possiede i dati correlati, pertanto deve avere un proprio database. Tuttavia, i database possono essere ovunque. In questo caso, sono tutti nello stesso contenitore per mantenere i requisiti di memoria Docker il più basso possibile. Tenete a mente che questa è una soluzione sufficiente per lo sviluppo e, forse, test, ma non per la produzione.

Il contenitore SQL Server nell'applicazione di esempio viene configurato con il codice YAML seguente nel file docker-compose.yml, che viene eseguito quando si esegue `docker-compose up`. Si noti che il codice YAML ha consolidato le informazioni di configurazione dal file docker-compose.yml generico e dal file docker-compose.override.yml. È in genere necessario separare le impostazioni dell'ambiente dalle informazioni di base o statiche correlate all'immagine di SQL Server.

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

Analogamente, invece di usare `docker-compose`, il comando `docker run` seguente può eseguire tale contenitore:

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

Se tuttavia si distribuisce un'applicazione a più contenitori come eShopOnContainers, risulta più semplice usare il comando `docker-compose up`, in modo che vengano distribuiti tutti i contenitori necessari per l'applicazione.

Quando si avvia questo contenitore SQL Server per la prima volta, il contenitore inizializza SQL Server con la password specificata. Quando SQL Server è in esecuzione come contenitore, è possibile aggiornare il database connettendolo tramite qualsiasi connessione SQL normale, ad esempio da SQL Server Management Studio, Visual Studio o codice C\#.

L'applicazione eShopOnContainers inizializza ogni database di microservizio con dati di esempio eseguendo il seeding del database con dati all'avvio, come illustrato nella sezione seguente.

L'esecuzione di SQL Server come contenitore non è solo utile per una demo, in cui è possibile che non sia disponibile l'accesso a un'istanza di SQL Server. Come indicato, risulta vantaggiosa anche per ambienti di sviluppo e test, perché consente di integrare con facilità i test di integrazione a partire da un'immagine di SQL Server pulita e da dati noti tramite il seeding di nuovi dati di esempio.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Eseguire l'immagine Docker di SQL Server in Linux, Mac o Windows** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- **Connetti ed esegui query su SQL Server su Linux con sqlcmd** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a>Seeding con dati di test all'avvio di un'applicazione Web

Per aggiungere dati al database all'avvio dell'applicazione, è `Main` possibile `Program` aggiungere codice simile al seguente al metodo nella classe del progetto API Web:

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

C'è un avvertimento importante quando si applicano le migrazioni e seeding di un database durante l'avvio del contenitore. Poiché il server di database potrebbe non essere disponibile per qualsiasi motivo, è necessario gestire i tentativi durante l'attesa che il server sia disponibile. Questa logica di ripetizione `MigrateDbContext()` dei tentativi viene gestita dal metodo di estensione, come illustrato nel codice seguente:This retry logic is handled by the extension method, as shown in the following code:

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

Il codice seguente nella classe CatalogContextSeed personalizzata popola i dati.

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

Quando si eseguono test di integrazione, un'opzione per la generazione di dati coerenti con i test di integrazione risulta utile. La possibilità di creare qualsiasi elemento da zero, inclusa un'istanza di SQL Server in esecuzione in un contenitore, risulta vantaggiosa per gli ambienti di test.

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>Confronto tra un database EF Core InMemory e SQL Server eseguito come contenitore

Un'altra opzione vantaggiosa per l'esecuzione di test consiste nell'usare il provider di database Entity Framework InMemory. È possibile specificare tale configurazione nel metodo ConfigureServices della classe Startup nel progetto API Web:

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

Questa opzione presenta tuttavia uno svantaggio significativo. Il database in memoria non supporta molti vincoli specifici per un determinato database. È ad esempio possibile aggiungere un indice univoco a una colonna nel modello di EF Core e scrivere un test rispetto al database in memoria per verificare che non consenta l'aggiunta di un valore duplicato. Quando tuttavia si usa il database in memoria, non è possibile gestire indici univoci su una colonna. Il database in memoria non si comporta quindi esattamente in modo analogo a un database di SQL Server effettivo, poiché non emula i vincoli specifici del database.

Il database in memoria risulta comunque utile per i test e la creazione di prototipi. Se tuttavia si vogliono creare test di integrazione precisi che prendono in considerazione il comportamento di un'implementazione specifica del database, è necessario usare un database effettivo come SQL Server. L'esecuzione di SQL Server in un contenitore per questa finalità è un'opzione ottimale e più precisa rispetto al provider di database EF Core InMemory.

## <a name="using-a-redis-cache-service-running-in-a-container"></a>Uso di un servizio cache Redis in esecuzione in un contenitore

È possibile eseguire Redis su un contenitore, in particolare per scenari di sviluppo e test e di modello di verifica. Questo scenario risulta molto vantaggioso, perché consente di eseguire tutte le dipendenze nei contenitori, non solo per i computer di sviluppo locali, ma per gli ambienti di test nelle pipeline di integrazione continua/recapito continuo.

Quando tuttavia si esegue Redis in produzione, è consigliabile cercare una soluzione a disponibilità elevata come Redis Microsoft Azure, eseguita come PaaS (Platform as a Service). Nel codice è sufficiente modificare le stringhe di connessione.

Redis offre un'immagine di Docker con Redis. L'immagine è disponibile da Docker Hub in questo URL:

<https://hub.docker.com/_/redis/>

È possibile eseguire direttamente un contenitore Docker Redis eseguendo questo comando dell'interfaccia della riga di comando di Docker dal prompt dei comandi:

```console
docker run --name some-redis -d redis
```

L'immagine Redis include expose:6379 (porta usata da Redis), quindi i collegamenti standard dei contenitori la renderanno automaticamente disponibile ai contenitori collegati.

In eShopOnContainers, `basket-api` il microservizio usa una cache Redis in esecuzione come contenitore. Tale `basketdata` contenitore è definito come parte del file *docker-compose.yml multi-contenitore,* come illustrato nell'esempio seguente:

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

Questo codice in docker-compose.yml definisce `basketdata` un contenitore denominato in base all'immagine redis e la pubblicazione della porta 6379 internamente. Ciò significa che sarà accessibile solo da altri contenitori in esecuzione all'interno dell'host Docker.

Infine, nel file *docker-compose.override.yml,* il `basket-api` microservizio per l'esempio eShopOnContainers definisce la stringa di connessione da utilizzare per il contenitore Redis:

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

Come accennato in precedenza, il nome del microservizio `basketdata` viene risolto dal DNS della rete interna di Docker.

>[!div class="step-by-step"]
>[Successivo](multi-container-applications-docker-compose.md)
>[precedente](integration-event-based-microservice-communications.md)
