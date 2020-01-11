---
title: Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti
description: Informazioni su come usare HttpClientFactory, disponibile a partire da .NET Core 2.1, per la creazione di istanze `HttpClient`, semplificandone l'uso nelle applicazioni.
ms.date: 08/08/2019
ms.openlocfilehash: 1a6d65509d669166e73ad907b506bae7fa26536d
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900319"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a>Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti

`HttpClientFactory` è una solida factory, disponibile a partire da .NET Core 2.1, per la creazione di istanze <xref:System.Net.Http.HttpClient> da usare nelle applicazioni.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Problemi con la classe HttpClient originale disponibile in .NET Core

La classe <xref:System.Net.Http.HttpClient> originale e nota può essere utilizzata facilmente, ma in alcuni casi non viene utilizzata correttamente da molti sviluppatori.

Come primo problema, sebbene questa classe sia eliminabile, il suo utilizzo con l'istruzione `using` non rappresenta la scelta migliore perché, anche quando si elimina l'oggetto `HttpClient`, il socket sottostante non viene rilasciato immediatamente e può generare quindi un problema serio di esaurimento di socket. Per altre informazioni su questo problema, vedere il post di blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Uso errato di HttpClient e conseguente destabilizzazione del software).

La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione. La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi. Questo problema genera errori `SocketException`. I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](../../../csharp/tutorials/console-webapiclient.md).

Esiste tuttavia un secondo problema con la classe `HttpClient` legato al suo utilizzo come oggetto singleton o statico. In questo caso, un singleton o un `HttpClient` statico non rispetta le modifiche DNS, come illustrato in questo [problema](https://github.com/dotnet/corefx/issues/11224) nel repository GitHub DotNet/CoreFx.

Per risolvere i problemi menzionati e semplificare la gestione delle istanze di `HttpClient`, in .NET Core 2.1 è stato introdotto un nuovo oggetto `HttpClientFactory` che può essere usato anche per implementare le chiamate HTTP resilienti tramite l'integrazione con Polly.

[Polly](http://www.thepollyproject.org/) è una libreria di gestione degli errori temporanei che consente agli sviluppatori di aggiungere resilienza alle applicazioni, usando alcuni criteri predefiniti in modo Fluent e thread-safe.

## <a name="what-is-httpclientfactory"></a>Scopo di HttpClientFactory

L'oggetto `HttpClientFactory` è progettato per:

- Fornire una posizione centralizzata per la denominazione e la configurazione di oggetti di `HttpClient` logici. È ad esempio possibile configurare un client (agente di servizio) preconfigurato per l'accesso a un microservizio specifico.
- Codificare il concetto di middleware in uscita tramite la delega di gestori in `HttpClient` e l'implementazione di middleware basato su Polly per sfruttarne i criteri di resilienza.
- `HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita. Si registrano client HTTP nella Factory ed è possibile usare un gestore Polly per usare i criteri di Polly per i tentativi, interruttori e così via.
- Gestire la durata di `HttpClientMessageHandlers` per evitare i problemi o i problemi indicati che possono verificarsi quando si gestiscono autonomamente `HttpClient` durate.

> [!NOTE]
> `HttpClientFactory` è strettamente legata all'implementazione di inserimento delle dipendenze nel pacchetto NuGet `Microsoft.Extensions.DependencyInjection`. Per altre informazioni sull'uso di altri contenitori di inserimento di dipendenze, vedere questa [discussione su GitHub](https://github.com/dotnet/extensions/issues/1345).

## <a name="multiple-ways-to-use-httpclientfactory"></a>Modi diversi di usare HttpClientFactory

Esistono molti modi per usare `HttpClientFactory` nell'applicazione:

- Usare `HttpClientFactory` direttamente
- Usare client denominati
- Usare client tipizzati
- Usare client generati

Per brevità, questo materiale sussidiario illustra il modo più strutturato per utilizzare `HttpClientFactory`, ovvero l'utilizzo di client tipizzati (modello di agente di servizio). Tuttavia, tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo relativo all'utilizzo di HttpClientFactory](/aspnet/core/fundamentals/http-requests#consumption-patterns).

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a>Come usare i client tipizzati con HttpClientFactory

Che cos'è un "client tipizzato"? È semplicemente un elemento `HttpClient` configurato al momento dell'inserimento da `DefaultHttpClientFactory`.

Il diagramma seguente visualizza l'uso dei client tipizzati con `HttpClientFactory`.

![Diagramma che illustra la modalità di utilizzo dei client tipizzati con HttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Figura 8-4**. Uso di HttpClientFactory con le classi client tipizzati.

Nell'immagine precedente, un ClientService (usato da un controller o da un codice client) usa un `HttpClient` creato dal `IHttpClientFactory`registrato. Questa factory assegna la `HttpClient` una `HttpMessageHandler` da un pool gestito. La `HttpClient` può essere configurata con i criteri di Polly quando si registrano i `IHttpClientFactory` nel contenitore DI inserimento delle dipendenze con il metodo di estensione `AddHttpClient`.

Per configurare la struttura precedente, aggiungere `HttpClientFactory` nell'applicazione installando il pacchetto NuGet `Microsoft.Extensions.Http` che include il metodo di estensione `AddHttpClient()` per `IServiceCollection`. Questo metodo di estensione registra l'oggetto `DefaultHttpClientFactory` da usare come oggetto singleton per l'interfaccia `IHttpClientFactory`. Definisce una configurazione temporanea per l'oggetto `HttpMessageHandlerBuilder`. Questo gestore di messaggi (oggetto `HttpMessageHandler`), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.

Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

La registrazione dei servizi client come illustrato nel codice precedente rende la `DefaultClientFactory` creare un `HttpClient` standard per ogni servizio.

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

Gli oggetti `HttpMessageHandler` nel pool hanno una durata, che è l'intervallo di tempo in cui un'istanza di `HttpMessageHandler` nel pool può essere usata nuovamente. Il valore predefinito è due minuti, ma può essere sostituito in base al cliente tipizzato. Per eseguire l'override, chiamare `SetHandlerLifetime()` nell'elemento `IHttpClientBuilder` restituito al momento della creazione del client, come illustrato nel codice seguente:

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

Ogni client tipizzato o client denominato può avere un proprio valore configurato di durata del gestore. Impostare la durata su `InfiniteTimeSpan` per disabilitare la scadenza del gestore.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Implementare le classi di client tipizzato che usano l'oggetto HttpClient inserito e configurato

È necessario avere definito in precedenza le classi di client tipizzato, ad esempio le classi nell'esempio di codice come "BasketService", "CatalogService", "OrderingService" e così via. Un client tipizzato è una classe che accetta un oggetto `HttpClient` (inserito tramite il relativo costruttore) e lo usa per chiamare un servizio HTTP remoto. Ad esempio:

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

Il client tipizzato (CatalogService nell'esempio) viene attivato da DI (Dependency Injection) e ciò significa che accetta qualsiasi servizio registrato nel proprio costruttore oltre alla classe HttpClient.

Un client tipizzato è di fatto un oggetto temporaneo, vale a dire che ne viene creata una nuova istanza ogni volta che è necessario e riceve una nuova istanza `HttpClient` ogni volta che viene costruito. Gli oggetti HttpMessageHandler nel pool tuttavia sono gli oggetti che vengono riusati da più richieste HTTP.

### <a name="use-your-typed-client-classes"></a>Uso di classi di client tipizzato

Infine, una volta che le classi tipizzate sono state implementate e sono state registrate con `AddHttpClient()`, è possibile usarle ovunque sia possibile inserire i servizi in base a. Ad esempio, in un codice della pagina Razor o in un controller di un'app Web MVC, come nel codice seguente da eShopOnContainers:

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

Il codice visualizzato fino a questo punto esegue solo normali richieste HTTP. La parte sorprendente inizia nelle sezioni seguenti, dove aggiungendo semplicemente criteri e gestori di delega ai client tipizzati registrati, tutte le richieste HTTP che devono essere eseguite da `HttpClient` funzionano tenendo in considerazione i criteri di resilienza, ad esempio i tentativi con backoff esponenziale, gli interruttori o qualsiasi altro gestore di delega personalizzato per implementare funzionalità di sicurezza aggiuntive, come l'uso di token di autorizzazione o qualsiasi altra funzionalità personalizzata.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Uso di HttpClientFactory in .NET Core**  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- **HttpClientFactory codice sorgente nel repository GitHub `dotnet/extensions`**  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- **Polly (libreria .NET con funzionalità di resilienza e di gestione degli errori temporanei)**  
  <http://www.thepollyproject.org/>
  
- **Uso di HttpClientFactory senza inserimento delle dipendenze (problema di GitHub)**  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
>[Precedente](explore-custom-http-call-retries-exponential-backoff.md)
>[Successivo](implement-http-call-retries-exponential-backoff-polly.md)
