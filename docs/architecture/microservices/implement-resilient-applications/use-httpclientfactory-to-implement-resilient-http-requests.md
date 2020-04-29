---
title: Usare IHttpClientFactory per l'implementazione di richieste HTTP resilienti
description: Informazioni su come usare IHttpClientFactory, disponibile a partire da .NET Core 2,1, `HttpClient` per la creazione di istanze, semplificando l'uso nelle applicazioni.
ms.date: 03/03/2020
ms.openlocfilehash: ade26208a931faa456c8e267def2caef7a3f32de
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507299"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a>Usare IHttpClientFactory per l'implementazione di richieste HTTP resilienti

<xref:System.Net.Http.IHttpClientFactory>è un contratto implementato da `DefaultHttpClientFactory`, una factory dogmatica, disponibile a partire da .net core 2,1 <xref:System.Net.Http.HttpClient> , per la creazione di istanze da usare nelle applicazioni.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Problemi con la classe HttpClient originale disponibile in .NET Core

La classe originale e Nota <xref:System.Net.Http.HttpClient> può essere facilmente utilizzata, ma in alcuni casi non viene utilizzata correttamente da molti sviluppatori.

Mentre questa classe implementa `IDisposable`, la dichiarazione e la creazione di un'istanza `using` in un'istruzione non è preferibile perché quando l' `HttpClient` oggetto viene eliminato, il socket sottostante non viene rilasciato immediatamente e questo può causare un problema di _esaurimento del socket_ . Per altre informazioni su questo problema, vedere il post di Blog relativo all' [uso di HttpClient errato ed](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)è in corso la destabilizzazione del software.

La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione. La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi. Questo problema genera errori `SocketException`. I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](../../../csharp/tutorials/console-webapiclient.md). Questa può essere una soluzione efficace per le app console di breve durata o simili eseguite alcune volte al giorno.

Un altro problema che gli sviluppatori eseguono è quando si utilizza un'istanza `HttpClient` condivisa di nei processi a esecuzione prolungata. In una situazione in cui viene creata un'istanza di HttpClient come singleton o oggetto statico, non riesce a gestire le modifiche DNS come descritto in questo [problema](https://github.com/dotnet/runtime/issues/18348) del repository GitHub DotNet/Runtime.

Tuttavia, il problema non è di `HttpClient` per sé, ma con il [costruttore predefinito per HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), perché crea una nuova istanza concreta di <xref:System.Net.Http.HttpMessageHandler>, ovvero quella con i problemi di *esaurimento dei socket* e le modifiche DNS indicate in precedenza.

Per risolvere i problemi menzionati in precedenza e `HttpClient` per rendere gestibili le istanze, .net core <xref:System.Net.Http.IHttpClientFactory> 2,1 ha introdotto l'interfaccia che può essere usata `HttpClient` per configurare e creare istanze in un'app tramite l'inserimento di dipendenze (di). Fornisce anche le estensioni per il middleware basato su Polly per sfruttare i vantaggi delegare i gestori in HttpClient.

[Polly](http://www.thepollyproject.org/) è una libreria di gestione degli errori temporanei che consente agli sviluppatori di aggiungere resilienza alle applicazioni, usando alcuni criteri predefiniti in modo Fluent e thread-safe.

## <a name="benefits-of-using-ihttpclientfactory"></a>Vantaggi dell'uso di IHttpClientFactory

L'implementazione corrente di <xref:System.Net.Http.IHttpClientFactory>, che implementa <xref:System.Net.Http.IHttpMessageHandlerFactory>anche, offre i vantaggi seguenti:

- Fornisce una posizione centrale per la denominazione e la `HttpClient` configurazione di oggetti logici. È ad esempio possibile configurare un client (agente di servizio) preconfigurato per l'accesso a un microservizio specifico.
- Codificare il concetto di middleware in uscita tramite delega dei gestori in `HttpClient` e implementazione del middleware basato su Polly per sfruttare i criteri di Polly per la resilienza.
- `HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita. È possibile registrare i client HTTP nella Factory ed è possibile usare un gestore Polly per usare i criteri di Polly per riprovare, interruttori e così via.
- Gestire la durata di <xref:System.Net.Http.HttpMessageHandler> per evitare i problemi o i problemi indicati che possono verificarsi quando `HttpClient` si gestiscono le durate stesse.

> [!TIP]
> Le `HttpClient` istanze inserite da di, possono essere eliminate in modo sicuro, perché l'oggetto associato `HttpMessageHandler` è gestito dalla factory. In realtà, le `HttpClient` istanze inserite hanno come *ambito* una prospettiva di inserimento.

> [!NOTE]
> L'implementazione di `IHttpClientFactory` (`DefaultHttpClientFactory`) è strettamente legata all'implementazione di di nel pacchetto `Microsoft.Extensions.DependencyInjection` NuGet. Per altre informazioni sull'uso di altri contenitori DI, vedere questa [discussione su GitHub](https://github.com/dotnet/extensions/issues/1345).

## <a name="multiple-ways-to-use-ihttpclientfactory"></a>Diversi modi per usare IHttpClientFactory

Esistono molti modi per usare `IHttpClientFactory` nell'applicazione:

- Utilizzo di base
- Usare client denominati
- Usare client tipizzati
- Usare client generati

Per motivi di brevità, questo materiale sussidiario illustra il modo più strutturato per usare `IHttpClientFactory`, ovvero l'uso di client tipizzati (modello di agente di servizio). Tuttavia, tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo `IHttpClientFactory` per quanto riguarda l'utilizzo](/aspnet/core/fundamentals/http-requests#consumption-patterns).

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a>Come usare i client tipizzati con IHttpClientFactory

Che cos'è un "client tipizzato"? Si tratta solo di `HttpClient` un preconfigurato per un uso specifico. Questa configurazione può includere valori specifici, ad esempio server di base, intestazioni HTTP o timeout.

Il diagramma seguente visualizza l'uso dei client tipizzati con `IHttpClientFactory`.

![Diagramma che illustra la modalità di utilizzo dei client tipizzati con IHttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Figura 8-4**. Utilizzando `IHttpClientFactory` con le classi client tipizzate.

Nell'immagine precedente, un `ClientService` (usato da un controller o codice client) usa un oggetto `HttpClient` creato dall'oggetto registrato `IHttpClientFactory`. Questa factory assegna un `HttpMessageHandler` da un pool a. `HttpClient` La `HttpClient` può essere configurata con i criteri di Polly durante `IHttpClientFactory` la registrazione DI nel contenitore di DI con <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*>il metodo di estensione.

Per configurare la struttura precedente, aggiungere <xref:System.Net.Http.IHttpClientFactory> nell'applicazione installando il `Microsoft.Extensions.Http` pacchetto NuGet che include il <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*> metodo di estensione per <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>. Questo metodo di estensione registra la `DefaultHttpClientFactory` classe interna da utilizzare come singleton per l'interfaccia `IHttpClientFactory`. Definisce una configurazione temporanea per l'oggetto <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>. Questo gestore di messaggi (oggetto <xref:System.Net.Http.HttpMessageHandler>), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.

Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

La registrazione dei servizi client come illustrato nel codice precedente consente di `DefaultClientFactory` creare uno standard `HttpClient` per ogni servizio.

È anche possibile aggiungere la configurazione specifica dell'istanza nella registrazione a, ad esempio, configurare l'indirizzo di base e aggiungere alcuni criteri di resilienza, come illustrato nel codice seguente:

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

Per l'esempio, è possibile visualizzare uno dei criteri precedenti nel codice seguente:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

Per altre informazioni sull'uso di Polly, vedere l' [articolo successivo](implement-http-call-retries-exponential-backoff-polly.md).

### <a name="httpclient-lifetimes"></a>Durate di HttpClient

Ogni volta che si ottiene un oggetto `HttpClient` da `IHttpClientFactory` viene restituita una nuova istanza. Tuttavia ogni `HttpClient` usa un `HttpMessageHandler` in pool e riusato da `IHttpClientFactory` per ridurre il consumo di risorse, a condizione che la durata di `HttpMessageHandler` non sia scaduta.

Il pooling dei gestori è opportuno poiché ogni gestore si occupa in genere di gestire le proprie connessioni HTTP sottostanti. La creazione di un numero superiore di gestori rispetto a quelli necessari può determinare ritardi di connessione. Alcuni gestori mantengono inoltre le connessioni aperte a tempo indefinito. Ciò può impedire al gestore di reagire alle modifiche DNS.

Gli oggetti `HttpMessageHandler` nel pool hanno una durata, che è l'intervallo di tempo in cui un'istanza di `HttpMessageHandler` nel pool può essere usata nuovamente. Il valore predefinito è due minuti, ma può essere sostituito in base al cliente tipizzato. Per eseguire l'override, chiamare `SetHandlerLifetime()` nell'elemento <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> restituito al momento della creazione del client, come illustrato nel codice seguente:

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

Ogni client tipizzato o client denominato può avere un proprio valore configurato di durata del gestore. Impostare la durata su `InfiniteTimeSpan` per disabilitare la scadenza del gestore.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Implementare le classi di client tipizzato che usano l'oggetto HttpClient inserito e configurato

Come passaggio precedente, è necessario definire le classi client tipizzate, ad esempio le classi nel codice di esempio, come "BasketService", "CatalogService", "OrderingService" e così via. un client tipizzato è una classe che accetta un `HttpClient` oggetto (inserito tramite il costruttore) e lo usa per chiamare un servizio HTTP remoto. Ad esempio:

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take,
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl,
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

Il client tipizzato`CatalogService` (nell'esempio) viene attivato da di (inserimento di dipendenze), ovvero può accettare qualsiasi servizio registrato nel relativo costruttore, oltre a `HttpClient`.

Un client tipizzato è di fatto un oggetto temporaneo, vale a dire che ne viene creata una nuova istanza ogni volta che è necessario e riceve una nuova istanza `HttpClient` ogni volta che viene costruito. Tuttavia, gli `HttpMessageHandler` oggetti nel pool sono gli oggetti riutilizzati da più `HttpClient` istanze.

### <a name="use-your-typed-client-classes"></a>Uso di classi di client tipizzato

Infine, una volta che le classi tipizzate sono state implementate e sono state `AddHttpClient()`registrate e configurate con, è possibile usarle ovunque sia possibile inserire i servizi da di. Ad esempio, in un codice della pagina Razor o in un controller di un'app Web MVC, come nel codice seguente da eShopOnContainers:

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) =>
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied,
                                               int? TypesFilterApplied,
                                               int? page,
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0,
                                                            itemsPage,
                                                            BrandFilterApplied,
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

Fino a questo punto, il codice illustrato sta semplicemente eseguendo richieste HTTP regolari, ma il "Magic" è disponibile nelle sezioni seguenti in cui, con l'aggiunta di criteri e la delega dei gestori ai client tipizzati registrati, tutte le richieste HTTP eseguite da `HttpClient` comportano l'esecuzione di criteri resilienti come i tentativi con backoff esponenziale, interruttori o qualsiasi altro gestore di delega personalizzato per implementare funzionalità di sicurezza aggiuntive, ad esempio l'uso di token di autenticazione o qualsiasi altra funzionalità personalizzata.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Uso di HttpClientFactory in .NET Core**  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- **Codice sorgente HttpClientFactory nel repository `dotnet/extensions` GitHub**  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- **Polly (libreria .NET con funzionalità di resilienza e gestione degli errori temporanei)**  
  <http://www.thepollyproject.org/>
  
- **Uso di IHttpClientFactory senza inserimento delle dipendenze (problema di GitHub)**  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
>[Precedente](implement-resilient-entity-framework-core-sql-connections.md)
>[successivo](implement-http-call-retries-exponential-backoff-polly.md)
