---
title: Uso di un server di database eseguito come un contenitore
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Uso di un server di database eseguito come un contenitore - Solo per lo sviluppo. Informazioni sui motivi.
ms.date: 10/02/2018
ms.openlocfilehash: a508ba734525b24e2f3f00408e2c59c8c00f1898
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291301"
---
# <a name="using-a-database-server-running-as-a-container"></a>Uso di un server di database eseguito come un contenitore

È possibile eseguire i database (SQL Server, PostgreSQL, MySQL e così via) su server autonomi normali, in cluster locali o in servizi PaaS sul cloud come il database SQL di Azure. Per ambienti di sviluppo e test, tuttavia, l'esecuzione dei database come contenitori risulta vantaggiosa, perché non sono presenti dipendenze esterne e l'esecuzione del comando `docker-compose up` basta per avviare l'intera applicazione. L'esecuzione dei database come contenitori risulta inoltre vantaggiosa per i test di integrazione, perché il database viene avviato nel contenitore e viene sempre popolato con gli stessi dati di esempio, in modo che i test siano più prevedibili.

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server in esecuzione come contenitore con un database correlato ai microservizi

In eShopOnContainers è disponibile un contenitore denominato sql.data definito nel file [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) che esegue SQL Server per Linux con tutti i database di SQL Server necessari per i microservizi. È anche possibile avere un contenitore SQL Server per ogni database, ma questo richiederebbe l'assegnazione di altra memoria a Docker. Per i microservizi è importante notare che ogni microservizio è proprietario dei rispettivi dati correlati e quindi del database SQL correlato in questo caso. I database si possono tuttavia trovare ovunque.

Il contenitore SQL Server nell'applicazione di esempio viene configurato con il codice YAML seguente nel file docker-compose.yml, che viene eseguito quando si esegue `docker-compose up`. Si noti che il codice YAML ha consolidato le informazioni di configurazione dal file docker-compose.yml generico e dal file docker-compose.override.yml. È in genere necessario separare le impostazioni dell'ambiente dalle informazioni di base o statiche correlate all'immagine di SQL Server.

```yml
  sql.data:
    image: microsoft/mssql-server-linux:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

Analogamente, invece di usare `docker-compose`, il comando `docker run` seguente può eseguire tale contenitore:

```console
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d microsoft/mssql-server-linux:2017-latest
```

Se tuttavia si distribuisce un'applicazione a più contenitori come eShopOnContainers, risulta più semplice usare il comando `docker-compose up`, in modo che vengano distribuiti tutti i contenitori necessari per l'applicazione.

Quando si avvia questo contenitore SQL Server per la prima volta, il contenitore inizializza SQL Server con la password specificata. Quando SQL Server è in esecuzione come contenitore, è possibile aggiornare il database connettendolo tramite qualsiasi connessione SQL normale, ad esempio da SQL Server Management Studio, Visual Studio o codice C\#.

L'applicazione eShopOnContainers inizializza ogni database di microservizio con dati di esempio eseguendo il seeding del database con dati all'avvio, come illustrato nella sezione seguente.

L'esecuzione di SQL Server come contenitore non è solo utile per una demo, in cui è possibile che non sia disponibile l'accesso a un'istanza di SQL Server. Come indicato, risulta vantaggiosa anche per ambienti di sviluppo e test, perché consente di integrare con facilità i test di integrazione a partire da un'immagine di SQL Server pulita e da dati noti tramite il seeding di nuovi dati di esempio.

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Eseguire l'immagine di SQL Server Docker in Linux, Mac o Windows** \
    [https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker](/sql/linux/sql-server-linux-setup-docker)

- **Connettere ed eseguire query di SQL Server in Linux con sqlcmd** \
    [https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd](/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>Seeding con dati di test all'avvio di un'applicazione Web

Per aggiungere dati al database all'avvio dell'applicazione, è possibile aggiungere codice simile al seguente al metodo Configure nella classe Startup del progetto API Web:

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

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>Confronto tra un database EF Core InMemory e SQL Server eseguito come contenitore

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

### <a name="using-a-redis-cache-service-running-in-a-container"></a>Uso di un servizio cache Redis in esecuzione in un contenitore

È possibile eseguire Redis su un contenitore, in particolare per scenari di sviluppo e test e di modello di verifica. Questo scenario risulta molto vantaggioso, perché consente di eseguire tutte le dipendenze nei contenitori, non solo per i computer di sviluppo locali, ma per gli ambienti di test nelle pipeline di integrazione continua/recapito continuo.

Quando tuttavia si esegue Redis in produzione, è consigliabile cercare una soluzione a disponibilità elevata come Redis Microsoft Azure, eseguita come PaaS (Platform as a Service). Nel codice è sufficiente modificare le stringhe di connessione.

Redis offre un'immagine di Docker con Redis. L'immagine è disponibile da Docker Hub in questo URL:

<https://hub.docker.com/\_/redis/>

È possibile eseguire direttamente un contenitore Docker Redis eseguendo questo comando dell'interfaccia della riga di comando di Docker dal prompt dei comandi:

```console
docker run --name some-redis -d redis
```

L'immagine Redis include expose:6379 (porta usata da Redis), quindi i collegamenti standard dei contenitori la renderanno automaticamente disponibile ai contenitori collegati.

In eShopOnContainers il microservizio basket.api usa una cache Redis eseguita come contenitore. Il contenitore basket.data viene definito come parte del file docker-compose.yml a più contenitori, come illustrato nell'esempio seguente:

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

Il codice nel file docker-compose.yml definisce un contenitore denominato basket.data basato sull'immagine Redis e la porta 6379 viene pubblicata internamente, quindi sarà accessibile solo da altri contenitori in esecuzione entro l'host Docker.

Nel file docker-compose.override.yml infine il microservizio basket.api per l'esempio eShopOnContainers definisce la stringa di connessione da usare per il contenitore Redis:

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```

Come detto in precedenza, il nome del microservizio "basket.data" viene risolto dal DNS della rete interna di Docker.

>[!div class="step-by-step"]
>[Precedente](multi-container-applications-docker-compose.md)
>[Successivo](integration-event-based-microservice-communications.md)
