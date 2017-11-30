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
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Creare un microservizio CRUD basati sui dati semplice

Questa sezione vengono illustrati come creare un semplice creare microservizio che esegue, leggere, aggiornamento e le operazioni di eliminazione (CRUD) su un'origine dati.

## <a name="designing-a-simple-crud-microservice"></a>Progettazione di un semplice microservizio CRUD

Dal punto di vista della progettazione, questo tipo di microservizio nei contenitori è molto semplice. Ad esempio il problema da risolvere è semplice, o forse l'implementazione è solo un modello di prova.

![](./media/image4.png)

**Figura 8-4**. Progettazione interna per microservizi CRUD semplice

Un esempio di questo tipo di servizio di unità di dati semplice è il catalogo microservizio dall'applicazione di esempio eShopOnContainers. Questo tipo di servizio implementa tutte le funzionalità in un unico progetto API Web di ASP.NET Core che include le classi per il modello di dati, la logica di business e il relativo codice di accesso ai dati. Anche i dati correlati vengono archiviati in un database in esecuzione in SQL Server (come un altro contenitore per scopi di sviluppo/test), ma potrebbe essere anche qualsiasi regolare host di SQL Server, come illustrato nella figura 8-5.

![](./media/image5.png)

**Figura 8-5**. Progettazione di semplice microservizio dati basato su/CRUD

Quando si sviluppa questo tipo di servizio, è necessario solo [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) e una API di accesso ai dati o ORM come [Entity Framework Core](https://docs.microsoft.com/ef/core/index). È anche possibile generare [Swagger](http://swagger.io/) metadati automaticamente tramiti [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) per fornire una descrizione delle funzionalità offerte del servizio, come illustrato nella sezione successiva.

Si noti che esegue SQL Server all'interno di un contenitore Docker è ideale per ambienti di sviluppo, poiché tutte le dipendenze possono esistere fino a un server di database e in esecuzione senza la necessità di eseguire il provisioning di un database nel cloud o locale. Ciò risulta molto utile quando si esegue l'integrazione di test. Tuttavia, per ambienti di produzione, eseguire un server di database in un contenitore non è consigliabile, perché in genere non si ottengono disponibilità elevata con tale approccio. Per un ambiente di produzione in Azure, è consigliabile utilizzare database SQL di Azure o qualsiasi altra tecnologia di database che può fornire la disponibilità elevata e scalabilità elevate. Ad esempio, per un approccio NoSQL, è possibile scegliere di DocumentDB.

Infine, modificando i file di metadati Dockerfile e docker compose.yml, è possibile configurare la modalità verrà creato l'immagine di questo contenitore, quale immagine di base di utilizzo, limiti più Progettazione impostazioni, ad esempio i nomi interni ed esterni e le porte TCP. 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Implementazione di un semplice microservizio CRUD con ASP.NET Core

Per implementare una semplice microservizio CRUD utilizzando Visual Studio e .NET Core, è innanzitutto necessario creare un semplice progetto API Web di ASP.NET Core (in esecuzione su .NET Core che consentono di eseguire in un host Linux Docker), come illustrato nella figura 8-6.

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  ![](./media/image6.png)   ![](./media/image7.png)
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

**Figura 8-6**. Creazione di un progetto di API Web di ASP.NET Core in Visual Studio

Dopo aver creato il progetto, è possibile implementare i controller MVC, come in qualsiasi altro progetto API Web, utilizzando l'API di Entity Framework o altre API. Nel progetto eShopOnContainers.Catalog.API, è possibile notare che le dipendenze principale per tale microservizio sono semplicemente ASP.NET Core stesso, Entity Framework e Swashbuckle, come illustrato nella figura 8-7.

![](./media/image8.PNG)

**Figura 8-7**. Dipendenze in un semplice microservizio CRUD Web API

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Implementazione dei servizi API Web CRUD con Entity Framework Core

Componenti di base di Entity Framework (EF) è un tipo semplice, estendibile e e tecnologia di accesso multipiattaforma versione dei dati di Entity Framework più diffusi. EF Core è un mapping relazionale a oggetti (ORM) che consente agli sviluppatori .NET di utilizzare un database utilizzando gli oggetti .NET.

Il catalogo di microservizio Usa Entity Framework e il provider SQL Server perché il database è in esecuzione in un contenitore con SQL Server per l'immagine di Linux Docker. Tuttavia, il database può essere distribuito in qualsiasi Server SQL, ad esempio Windows locale o nel database SQL di Azure. L'unica cosa che è necessario modificare è una stringa di connessione in microservizio di ASP.NET Web API.

#### <a name="add-entity-framework-core-to-your-dependencies"></a>Aggiungere le dipendenze di Entity Framework Core

È possibile installare il pacchetto NuGet per il provider di database che si desidera utilizzare, in questo caso SQL Server, dall'IDE di Visual Studio o con la console di NuGet. Utilizzare il seguente comando:

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a>Il modello di dati

Con Entity Framework Core, accesso ai dati viene eseguita tramite un modello. Un modello è costituito da classi di entità e un contesto derivato che rappresenta una sessione con il database, che consente di eseguire una query e salvare i dati. È possibile generare un modello da un database esistente, manualmente un modello in modo che corrisponda al database di codice o usare le migrazioni di Entity Framework per creare un database dal modello (e sviluppare, come il modello viene modificato nel tempo). Per il catalogo di microservizio viene usato l'approccio ultimo. È possibile vedere un esempio della classe di entità CatalogItem nell'esempio di codice seguente, che è un semplice oggetto CLR precedente normale ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) classe di entità.

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

È inoltre necessario un elemento DbContext che rappresenta una sessione con il database. Per il catalogo di microservizio, la classe di CatalogContext deriva dalla classe di base DbContext, come illustrato nell'esempio seguente:

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

È possibile avere codice aggiuntivo nell'implementazione DbContext. Ad esempio, nell'applicazione di esempio, è necessario un metodo OnModelCreating nella classe CatalogContext che popola automaticamente i dati di esempio la prima volta che tenta di accedere al database. Questo metodo è utile per i dati demo. È anche possibile utilizzare il metodo OnModelCreating per personalizzare i mapping di entità di database o oggetti con molti altri [punti di estendibilità EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

È possibile visualizzare altri dettagli sulla OnModelCreating nel [che implementa il livello di persistenza di infrastruttura con Entity Framework Core](#implementing_infrastructure_persistence) sezione più avanti in questo manuale.

##### <a name="querying-data-from-web-api-controllers"></a>Eseguire query sui dati da controller API Web

Le istanze di classi di entità vengono in genere recuperate dal database di utilizzando Language Integrated Query (LINQ), come illustrato nell'esempio seguente:

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

##### <a name="saving-data"></a>Salvataggio di dati

Dati vengano creati, eliminati e modificati nel database utilizzando le istanze di classi di entità. È possibile aggiungere codice analogo al livello di codice seguente (dati fittizi, in questo caso) ai controller di Web API.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Inserimento di dipendenze nel controller di ASP.NET Core e API Web

In ASP.NET Core è possibile utilizzare Dependency Injection (DI) predefinita. Non è necessario configurare un contenitore Inversion of Control (IoC) di terze parti, anche se è possibile collegare il contenitore IoC preferito nell'infrastruttura ASP.NET Core se si desidera. In questo caso, significa che è possibile inserire direttamente il DBContext EF richiesto o altri repository tramite il costruttore del controller. Nell'esempio precedente la classe CatalogController, ci stiamo inserendo un oggetto di tipo CatalogContext e altri oggetti tramite il costruttore CatalogController.

Una configurazione per impostare il progetto API Web importante è la registrazione della classe DbContext in un contenitore di inversione di controllo del servizio. In genere non nella classe di avvio chiamando i servizi. Metodo AddDbContext all'interno del metodo ConfigureServices, come illustrato nell'esempio seguente:

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

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Eseguire query sui dati**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

-   **Il salvataggio dei dati**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Il DB connessione stringa variabili e di ambiente utilizzate dai contenitori di Docker

È possibile utilizzare le impostazioni di ASP.NET Core e aggiungere una proprietà ConnectionString nel file Settings, come illustrato nell'esempio seguente:

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

Il file Settings può avere valori predefiniti per la proprietà ConnectionString o per qualsiasi altra proprietà. Tuttavia, queste proprietà verranno sovrascritte dai valori delle variabili di ambiente specificata nel file compose.override.yml di docker.

Da file di docker compose.yml o compose.override.yml di docker, è possibile inizializzare le variabili di ambiente in modo che Docker verrà impostarli come variabili di ambiente del sistema operativo, come illustrato nel seguente file di docker compose.override.yml (la connessione stringa e altre righe di eseguire il wrapping in questo esempio, ma potrebbe eseguire il wrapping in un file).

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

I file di docker compose.yml a livello di soluzione non solo i file di configurazione a livello di progetto o microservizio più flessibili, ma anche più sicura. È consigliabile che le immagini Docker che si compila per microservizio non contengano il docker-compose.yml file, solo i file binari e i file di configurazione per ogni microservizio, tra cui Dockerfile. Ma non viene distribuito il file di docker compose.yml insieme all'applicazione; utilizzato solo in fase di distribuzione. Di conseguenza, i valori delle variabili di ambiente in tali file docker compose.yml (anche senza crittografia i valori) consiste nell'inserire più sicura dell'inserimento di tali valori nei file di configurazione .NET regolari distribuiti con il codice.

Infine, è possibile ottenere tale valore dal codice utilizzando la configurazione\["ConnectionString"\], come illustrato nel metodo ConfigureServices in un esempio di codice precedente.

Tuttavia, per ambienti di produzione, potrebbe voler altri modi di explorer in modalità di archiviazione di informazioni riservate come le stringhe di connessione. In genere che verranno gestiti da orchestrator la scelta, come è possibile eseguire con [Docker Swarm gestione segreti](https://docs.docker.com/engine/swarm/secrets/).

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Implementazione di controllo delle versioni in ASP.NET Web API

Come modificare i requisiti aziendali, è possibile aggiungere nuove raccolte di risorse, potrebbero modificare le relazioni tra le risorse e potrebbe essere modificata la struttura dei dati nelle risorse. L'aggiornamento di un'API Web per gestire i nuovi requisiti è un processo relativamente semplice, ma è necessario considerare gli effetti che tali modifiche hanno su applicazioni client che utilizzano l'API Web. Anche se lo sviluppatore di progettazione e implementazione di un'API Web ha il controllo completo su tale API, lo sviluppatore non hanno lo stesso livello di controllo sulle applicazioni client che potrebbe essere compilato da organizzazioni di terze parti opera in modalità remota.

Controllo delle versioni consente un'API Web indicare le funzionalità e risorse che espone. Un'applicazione client può quindi inviare richieste a una versione specifica di una funzione o una risorsa. Esistono diversi approcci per implementare il controllo delle versioni:

-   Controllo delle versioni URI

-   Controllo delle versioni delle stringhe di query

-   Controllo delle versioni di intestazione

Stringa di query e controllo delle versioni URI sono più semplici da implementare. Controllo delle versioni di intestazione è un buon approccio. Tuttavia, il controllo delle versioni dell'intestazione non come esplicita e semplice come il controllo delle versioni URI. Poiché il controllo delle versioni di URL è il più semplice e più esplicito, l'applicazione di esempio eShopOnContainers utilizza il controllo delle versioni URI.

Il controllo delle versioni URI, come l'applicazione di esempio eShopOnContainers ogni volta che si modifica l'API Web o modificare lo schema di risorse, aggiungere un numero di versione per l'URI per ogni risorsa. URI esistenti continueranno a funzionare come prima, la restituzione di risorse che è conforme allo schema che corrisponde alla versione richiesta.

Come illustrato nell'esempio di codice seguente, la versione può essere impostata utilizzando l'attributo della Route nell'API Web, che rende esplicita nell'URI della versione (v1 in questo caso).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Questo meccanismo di controllo delle versioni è semplice e dipende dal server di routing della richiesta all'endpoint appropriato. Per un controllo delle versioni più sofisticata e il metodo migliore quando si usa REST, tuttavia, è necessario utilizzare hypermedia e implementare [HATEOAS (Hypertext come motore di stato dell'applicazione)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Scott Hanselman. Controllo delle versioni API Web RESTful Core ASP.NET semplificato**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

-   **Controllo delle versioni di un'API web RESTful**

    [*https://docs.microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Controllo delle versioni e Hypermedia REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>La generazione di metadati di Swagger descrizione dall'API Web di ASP.NET Core 

[Swagger](http://swagger.io/) è un framework di uso comune open source eseguito da un grande ecosistema di strumenti che consentono di progettazione, compilazione, documento e utilizzare le API REST. È sempre lo standard per il dominio di metadati API descrizione. È necessario includere i metadati Swagger descrizione con qualsiasi tipo di microservizio, microservizi basati sui dati o informazioni avanzate microservizi basati su dominio (come descritto nella sezione seguente).

Il cuore di Swagger è specifica di Swagger API descrizione metadati in un file JSON o YAML. La specifica crea il contratto per l'API, che riporta in dettaglio tutte le risorse e operazioni sia un uomo e machine readable formato per sviluppare in modo semplice, individuazione e l'integrazione RESTful.

La specifica è la base della specifica OpenAPI (OAS) ed è sviluppata in una comunità open, trasparente e di collaborazione per standardizzare le modalità di interfacce REST sono definite.

La specifica definisce la struttura di come è possibile individuare un servizio e come le relative funzionalità riconosciuto. Per ulteriori informazioni, inclusi un editor di web e gli esempi di specifiche di Swagger di aziende come da Spotify, Uber, il margine di flessibilità e Microsoft, visitare il sito di Swagger (<http://swagger.io>).

### <a name="why-use-swagger"></a>Perché utilizzare Swagger?

I motivi principali per generare i metadati Swagger per le API sono i seguenti.

**Possibilità per gli altri prodotti integrare le API e utilizzare automaticamente**. Decine di prodotti e [strumenti esterna](http://swagger.io/commercial-tools/) e molti [Framework e librerie](http://swagger.io/open-source-integrations/) supportano Swagger. Microsoft ha prodotti di alto livello e gli strumenti che possono automaticamente utilizzare API basate su Swagger, ad esempio le operazioni seguenti:

-   [AutoRest](https://github.com/Azure/AutoRest). È possibile generare automaticamente le classi client .NET per la chiamata di Swagger. This

-   strumento può essere utilizzato da CLI e inoltre si integra con Visual Studio di facile utilizzo tramite l'interfaccia utente grafica.

-   [Microsoft Flow](https://flow.microsoft.com/en-us/). È possibile eseguire automaticamente [utilizzare e integrare le API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) un alto livello flusso di lavoro Microsoft Flow, senza programmazione competenze necessarie.

-   [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/). È possibile utilizzare automaticamente le API di [App per dispositivi mobili PowerApps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) compilati con [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), con nessuna programmazione competenze necessarie.

-   [Servizio App di Azure logica app](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). È possibile eseguire automaticamente [utilizzare e integrare le API in un'App di Azure App Service logica](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), con nessuna programmazione competenze necessarie.

**Possibilità di generare automaticamente la documentazione dell'API**. Quando si crea l'API REST su larga scala, ad esempio applicazioni basate su microservizio complesse, è necessario gestire molti endpoint con diversi modelli di dati utilizzati nel payload di richiesta e risposta. Con la documentazione e per avere un Esplora API a tinta unita, che si ottiene con Swagger, è chiave per la riuscita delle API e adozione dagli sviluppatori.

I metadati di swagger sono ciò che Microsoft Flow, PowerApps e App di logica di Azure Usa per comprendere come utilizzare le API e connettersi a essi.

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Come automatizzare la generazione di metadati Swagger API con il pacchetto Swashbuckle NuGet

Generazione metadati Swagger manualmente (in un file JSON o YAML) può essere noioso lavoro. Tuttavia, è possibile automatizzare l'individuazione delle API dei servizi API Web ASP.NET utilizzando il [pacchetto Swashbuckle NuGet](http://aka.ms/swashbuckledotnetcore) per generare dinamicamente i metadati Swagger API.

Swashbuckle genera automaticamente i metadati Swagger per i progetti ASP.NET Web API. Supporta i progetti API Web di ASP.NET Core e l'API Web ASP.NET tradizionale e altre caratteristiche, ad esempio Azure API App, App Mobile di Azure, Azure Service Fabric microservizi basati su ASP.NET. Supporta inoltre semplice API Web per i contenitori, come in per il riferimento applicazione distribuita.

Swashbuckle combina esplorazione di API e Swagger o [dell'interfaccia utente swagger](https://github.com/swagger-api/swagger-ui) per fornire la documentazione e un'individuazione avanzata esperienza per consentire agli utenti di API. Oltre il motore di generazione metadati Swagger, Swashbuckle contiene anche una versione incorporata di swagger-interfaccia utente, verrà utilizzato automaticamente backup una volta installato Swashbuckle.

Ciò significa che è possibile integrare dell'API di un'interfaccia utente per consentire agli sviluppatori di utilizzare l'API di individuazione nice. Poiché viene generato automaticamente, consentendo di concentrarsi sulla compilazione l'API richiede una quantità limitata di codice e la manutenzione. Il risultato per l'esplorazione di API sarà come nella figura 8-8.

![](./media/image9.png)

**Figura 8-8**. Esplora API Swashbuckle in base ai metadati di Swagger: eShopOnContainers microservizio del catalogo

Esplora API non è in questo caso la cosa più importante. Dopo aver creato un'API Web in grado di descrivere se stesso nei metadati di Swagger, l'API è facilmente utilizzabile da strumenti basati su Swagger, inclusi i generatori di codice di classe proxy client che possono essere destinati a più piattaforme. Ad esempio, come accennato, [AutoRest](https://github.com/Azure/AutoRest) genera automaticamente le classi client .NET. Ma strumenti aggiuntivi, come [swagger codegen](https://github.com/swagger-api/swagger-codegen) sono anche disponibili, che consente la generazione del codice del client API librerie stub del server e documentazione automaticamente.

Attualmente, Swashbuckle è costituito da due pacchetti NuGet: Swashbuckle.SwaggerGen e Swashbuckle.SwaggerUi. Il primo fornisce funzionalità per generare uno o più documenti Swagger direttamente dall'implementazione di API ed esporli come endpoint JSON. Quest'ultimo fornisce una versione dello strumento dell'interfaccia utente swagger che può essere gestita dall'applicazione e con i documenti Swagger generati per descrivere l'API incorporata. Tuttavia, le versioni più recenti di Swashbuckle eseguire il wrapping con la metapackage Swashbuckle.AspNetCore.

Si noti che per i progetti .NET Core Web API, è necessario utilizzare [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) versione 1.0.0 o versione successiva.

Dopo aver installato i pacchetti NuGet nel progetto API Web, è necessario configurare Swagger nella classe di avvio, come illustrato nel codice seguente:

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

Al termine, è possibile avviare l'applicazione e passare i seguenti endpoint Swagger JSON e l'interfaccia utente utilizzando gli URL come queste:

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

Si è visto in precedenza l'interfaccia utente generato creato da Swashbuckle per un URL come http://&lt;l'url della radice&gt;swagger / dell'interfaccia utente. Nella figura 8-9 è inoltre possibile visualizzare come è possibile testare qualsiasi metodo API.

![](./media/image10.png)

**Figura 8-9**. Swashbuckle test UI il metodo API o gli elementi del catalogo

Figura 8-10 vengono visualizzati i metadati di Swagger JSON generato dal microservizio eShopOnContainers (ovvero gli strumenti da utilizzare di sotto) quando si richiedono &lt;l'url della radice&gt;/swagger/v1/swagger.json utilizzando [Postman](https://www.getpostman.com/).

![](./media/image11.png)

**Figura 8-10**. Metadati swagger JSON

È semplice. E poiché viene generato automaticamente, i metadati di Swagger aumenterà quando si aggiungono ulteriori funzionalità all'API.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **ASP.NET Web API Guida pagine utilizzando Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)


>[!div class="step-by-step"]
[Precedente] (microservizio-applicazione-design.md) [Avanti] (multi-container-applicazioni-docker-compose.md)
