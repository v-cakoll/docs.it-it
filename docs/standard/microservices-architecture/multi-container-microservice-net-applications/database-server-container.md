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
# <a name="using-a-database-server-running-as-a-container"></a>Utilizzo di un server di database in esecuzione come un contenitore

È possibile disporre i database (SQL Server, PostgreSQL, MySQL e così via) nei server autonomi regolare, nel cluster locale o in servizi PaaS nel cloud come database SQL di Azure. Tuttavia, per gli ambienti di sviluppo e test, con i database in esecuzione come contenitori sia pratico, poiché tutte le dipendenze esterne, non si dispone e semplicemente in esecuzione la composizione di docker comando avvia l'intera applicazione. Presenza di tali database come contenitori è molto utile per i test di integrazione, anche perché il database viene avviato nel contenitore ed è sempre popolato con gli stessi dati di esempio, in modo test possono essere più prevedibili.

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server in esecuzione come un contenitore con un database di microservizio

In eShopOnContainers, c'è un contenitore denominato sql.data definito nel [docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file che esegue SQL Server per Linux con tutti i database di SQL Server necessari per il microservizi. (Si potrebbe avere anche un contenitore di SQL Server per ogni database, ma che richiederebbe più memoria assegnata a Docker). Il punto in microservizi importante è che ogni microservizio possiede i dati correlati, pertanto il database SQL correlato in questo caso. Ma i database possono trovarsi ovunque.

Il contenitore nell'applicazione di esempio è configurato con il codice seguente YAML nel file docker compose.yml, che viene eseguito quando si esegue SQL Server docker-comporre backup. Si noti che il codice YAML è consolidato informazioni di configurazione dal file docker-compose.yml generico e il file compose.override.yml di docker. (In genere è necessario separare le impostazioni dell'ambiente dalle informazioni di base o statiche correlata all'immagine di SQL Server.)

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

Il seguente comando docker run è possibile eseguire tale contenitore:

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

Tuttavia, se si distribuisce un'applicazione multi-contenitore come eShopOnContainers, è più pratico utilizzare il docker-comporre il comando in modo che venga distribuito a tutti i contenitori necessari per l'applicazione.

Quando si avvia il contenitore di SQL Server per la prima volta, il contenitore Inizializza SQL Server con la password specificata dall'utente. Quando SQL Server è in esecuzione come un contenitore, è possibile aggiornare il database eseguendo la connessione tramite qualsiasi connessione SQL normale, ad esempio da SQL Server Management Studio, Visual Studio o C\# codice.

L'applicazione eShopOnContainers Inizializza ogni database microservizio con dati di esempio seeding dei dati all'avvio, come illustrato nella sezione seguente.

Con SQL Server in esecuzione come un contenitore non è utile solo per una dimostrazione in cui si potrebbe non avere accesso a un'istanza di SQL Server. Come indicato, è inoltre ideale per ambienti di sviluppo e test in modo da poter facilmente eseguire test di integrazione, a partire da un'immagine di SQL Server pulita e dati noti effettuando il seeding di nuovi dati di esempio.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Eseguire l'immagine di SQL Server Docker in Windows, Linux o Mac**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)

-   **Connettersi ed eseguire query di SQL Server in Linux con sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>Il seeding dei dati di test all'avvio dell'applicazione Web

Per aggiungere dati al database all'avvio dell'applicazione, è possibile aggiungere il seguente codice al metodo nella classe di avvio del progetto API Web configura:

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

Il codice seguente nella classe CatalogContextSeed personalizzata consente di popolare i dati.

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

Quando si eseguono test di integrazione, con un modo per generare dati coerenti con i test di integrazione è utile. La possibilità di creare da zero, tra cui un'istanza di SQL Server in esecuzione su un contenitore, è molto utile negli ambienti di test.

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>Database principale InMemory EF rispetto a SQL Server in esecuzione come un contenitore

Un'altra scelta ottimale quando si eseguono test consiste nell'utilizzare il provider di database di Entity Framework InMemory. È possibile specificare che la configurazione nel metodo ConfigureServices della classe di avvio nel progetto API Web:

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

È un'importante catch, tuttavia. Il database in memoria supporta molti vincoli specifici di un determinato database. Ad esempio possibile aggiungere un indice univoco su una colonna nel modello Entity Framework Core e scrivere un test nel database in memoria per verificare che non consente di aggiungere un valore duplicato. Tuttavia, quando si utilizza il database in memoria, non sarà possibile gestire gli indici univoci in una colonna. Pertanto, il database in memoria non si comporta esattamente come un database di SQL Server reale, non viene emulato vincoli specifici del database.

Anche in questo caso, un database in memoria è comunque utile per i test e la creazione di prototipi. Ma se si desidera creare i test di integrazione accurati che prendono in considerazione il comportamento di un'implementazione del database specifico, è necessario utilizzare un database reale, ad esempio SQL Server. A tale scopo, eseguire SQL Server in un contenitore è un ottimo choice e maggiore accurato rispetto al provider del database EF Core InMemory.

### <a name="using-a-redis-cache-service-running-in-a-container"></a>Utilizzo di un servizio cache Redis in esecuzione in un contenitore

È possibile eseguire Redis su un contenitore, soprattutto per lo sviluppo e test e per gli scenari di prova. Questo scenario è pratico, poiché è possibile disporre di tutte le dipendenze in esecuzione in contenitori, non solo per i computer di sviluppo locale, ma per gli ambienti di testing nelle pipeline CI/CD-ROM.

Tuttavia, quando si esegue Redis nell'ambiente di produzione, è preferibile cercare una soluzione a disponibilità elevata come Redis di Microsoft Azure, viene eseguito come un PaaS (piattaforma distribuita come servizio). Nel codice, è sufficiente modificare le stringhe di connessione.

Redis fornisce un'immagine di Docker con Redis. Tale immagine è disponibile dall'Hub Docker a questo URL:

<https://hub.docker.com/_/redis/>

È possibile eseguire direttamente un contenitore Docker Redis eseguendo il comando di Docker CLI seguente nel prompt dei comandi:

```
  docker run --name some-redis -d redis
```

L'immagine di Redis include espongono: 6379 (la porta utilizzata da Redis), in modo standard contenitore collegamento renderà automaticamente disponibili per i contenitori collegati.

In eShopOnContainers, il microservizio basket.api utilizza una cache Redis in esecuzione come un contenitore. Contenitore basket.data è definito come parte del file di multi-contenitore docker-compose.yml, come illustrato nell'esempio seguente:

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

Questo codice di docker-compose.yml definisce un contenitore denominato basket.data basata sull'immagine di redis e pubblicare la porta 6379 internamente, vale a dire che sarà accessibile solo da altri contenitori in esecuzione all'interno dell'host Docker.

Infine, nel file docker compose.override.yml il microservizio basket.api per l'esempio eShopOnContainers definisce la stringa di connessione da utilizzare per tale contenitore Redis:

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
[Precedente] (multi-container-applicazioni-docker-compose.md) [Avanti] (integrazione-eventi-base-microservizio-communications.md)
