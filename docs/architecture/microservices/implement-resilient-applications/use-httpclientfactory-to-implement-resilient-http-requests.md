---
title: Usare IHttpClientFactory per implementare richieste HTTP resilientiUse IHttpClientFactory to implement resilient HTTP requests
description: Informazioni su come usare IHttpClientFactory, disponibile a partire `HttpClient` da .NET Core 2.1, per la creazione di istanze, semplificandone l'uso nelle applicazioni.
ms.date: 03/03/2020
ms.openlocfilehash: 088fb6c7e10ad656247ee4065da5c13d383b2cf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847219"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a>Usare IHttpClientFactory per implementare richieste HTTP resilientiUse IHttpClientFactory to implement resilient HTTP requests

<xref:System.Net.Http.IHttpClientFactory>è un contratto implementato da `DefaultHttpClientFactory`, una factory testata, disponibile <xref:System.Net.Http.HttpClient> a partire da .NET Core 2.1, per la creazione di istanze da utilizzare nelle applicazioni.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Problemi con la classe HttpClient originale disponibile in .NET Core

La classe originale <xref:System.Net.Http.HttpClient> e ben nota può essere facilmente utilizzata, ma in alcuni casi, non viene utilizzata correttamente da molti sviluppatori.

Sebbene questa `IDisposable`classe implementi , la dichiarazione e la creazione di istanze all'interno di un'istruzione `using` non è preferibile perché quando l'oggetto `HttpClient` viene eliminato, il socket sottostante non viene rilasciato immediatamente, il che può causare un problema di _esaurimento_ socket. Per ulteriori informazioni su questo problema, vedere il post di blog [Si sta utilizzando HttpClient errato e sta destabilizzando il software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).

La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione. La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi. Questo problema genera errori `SocketException`. I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](../../../csharp/tutorials/console-webapiclient.md). Questa può essere una buona soluzione per le applicazioni console di breve durata o simili che vengono eseguite un paio di volte al giorno.

Un altro problema che gli sviluppatori incorrere in è quando si utilizza un'istanza condivisa di `HttpClient` in processi a esecuzione prolungata. In una situazione in cui il HttpClient viene creata un'istanza come singleton o un oggetto statico, non riesce a gestire le modifiche DNS come descritto in questo [numero](https://github.com/dotnet/corefx/issues/11224) del repository GitHub dotnet/corefx.

Tuttavia, il problema non `HttpClient` è realmente con di per sé, ma con il <xref:System.Net.Http.HttpMessageHandler> [costruttore predefinito per HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), perché crea una nuova istanza concreta di , ovvero quello con *esaurimento* dei socket e DNS modifica i problemi di cui sopra.

Per risolvere i problemi menzionati in precedenza e rendere `HttpClient` gestibili le istanze, .NET Core 2.1 ha introdotto l'interfaccia <xref:System.Net.Http.IHttpClientFactory> che può essere utilizzata per configurare e creare `HttpClient` istanze in un'app tramite Dependency Injection (DI). Fornisce inoltre estensioni per middleware basato su Polly per sfruttare i vantaggi della delega dei gestori in HttpClient.It also provides extensions for Polly-based middleware to take advantage of delegating handlers in HttpClient.

[Polly](http://www.thepollyproject.org/) è una libreria di gestione degli errori transitori che consente agli sviluppatori di aggiungere resilienza alle applicazioni, usando alcuni criteri predefiniti in modo fluente e thread-safe.

## <a name="benefits-of-using-ihttpclientfactory"></a>Vantaggi dell'utilizzo di IHttpClientFactory

L'implementazione <xref:System.Net.Http.IHttpClientFactory>corrente di <xref:System.Net.Http.IHttpMessageHandlerFactory>, che implementa anche , offre i seguenti vantaggi:

- Fornisce una posizione centrale per `HttpClient` la denominazione e la configurazione di oggetti logici. È ad esempio possibile configurare un client (agente di servizio) preconfigurato per l'accesso a un microservizio specifico.
- Codificare il concetto di middleware in `HttpClient` uscita tramite la delega di gestori e l'implementazione di middleware basato su Polly per sfruttare i criteri di Polly per la resilienza.
- `HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita. È possibile registrare i client HTTP nella factory ed è possibile utilizzare un gestore Polly per utilizzare i criteri Polly per Retry, CircuitBreakers e così via.
- Gestire la <xref:System.Net.Http.HttpMessageHandler> durata per evitare i problemi/problemi `HttpClient` menzionati che possono verificarsi durante la gestione delle durate da soli.

> [!TIP]
> Le `HttpClient` istanze inserite da DI, possono essere `HttpMessageHandler` eliminate in modo sicuro, perché l'oggetto associato è gestito dalla factory. Infatti, le `HttpClient` istanze inserite hanno ambito dal punto di vista DI. *Scoped*

> [!NOTE]
> L'implementazione di `IHttpClientFactory` (`DefaultHttpClientFactory`) è strettamente `Microsoft.Extensions.DependencyInjection` legata all'implementazione DI nel pacchetto NuGet. Per altre informazioni sull'uso di altri contenitori DI, vedere questa discussione di [GitHub](https://github.com/dotnet/extensions/issues/1345).

## <a name="multiple-ways-to-use-ihttpclientfactory"></a>Più modi per usare IHttpClientFactoryMultiple ways to use IHttpClientFactory

Esistono molti modi per usare `IHttpClientFactory` nell'applicazione:

- Utilizzo di base
- Usare client denominati
- Usare client tipizzati
- Usare client generati

Per motivi di brevità, questa guida mostra `IHttpClientFactory`il modo più strutturato per utilizzare , ovvero utilizzare i client tipizzati (modello di agente di servizio). Tuttavia, tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo che copre l'utilizzo `IHttpClientFactory` ](/aspnet/core/fundamentals/http-requests#consumption-patterns).

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a>Come utilizzare client tipizzato con IHttpClientFactory

Che cos'è un "client tipizzato"? E 'solo `HttpClient` un che è preconfigurato per qualche uso specifico. Questa configurazione può includere valori specifici, ad esempio il server di base, le intestazioni HTTP o i timeout.

Il diagramma seguente visualizza l'uso dei client tipizzati con `IHttpClientFactory`.

![Diagramma che mostra l'utilizzo dei client tipizzato con IHttpClientFactory.Diagram showing how typed clients are used with IHttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Figura 8-4**. Utilizzo `IHttpClientFactory` delle classi Client tippizzate.

Nell'immagine precedente, `ClientService` un (utilizzato da un controller `HttpClient` o codice `IHttpClientFactory`client) utilizza un creato dal file registrato. Questa factory assegna `HttpMessageHandler` un da `HttpClient`un pool al file . L'oggetto `HttpClient` può essere configurato con i `IHttpClientFactory` criteri di Polly durante <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*>la registrazione di nel contenitore DI con il metodo di estensione .

Per configurare la <xref:System.Net.Http.IHttpClientFactory> struttura precedente, aggiungere `Microsoft.Extensions.Http` nell'applicazione installando il pacchetto NuGet che include il metodo di <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*> estensione per <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>. Questo metodo di estensione `DefaultHttpClientFactory` registra la classe interna da utilizzare `IHttpClientFactory`come singleton per l'interfaccia . Definisce una configurazione temporanea per l'oggetto <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>. Questo gestore di messaggi (oggetto <xref:System.Net.Http.HttpMessageHandler>), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.

Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

La registrazione dei servizi client, come illustrato `DefaultClientFactory` nel `HttpClient` codice precedente, rende il creare uno standard per ogni servizio.

È anche possibile aggiungere la configurazione specifica dell'istanza nella registrazione per, ad esempio, configurare l'indirizzo di base e aggiungere alcuni criteri di resilienza, come illustrato nel codice seguente:You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

Solo per l'esempio di sake, è possibile visualizzare uno dei criteri di cui sopra nel codice successivo:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

Per ulteriori informazioni sull'utilizzo di Polly, vedere [l'articolo Avanti](implement-http-call-retries-exponential-backoff-polly.md).

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

Come passaggio precedente, è necessario avere le classi di Client tipizzato definite, ad esempio le classi nel codice di esempio, ad esempio 'BasketService', 'CatalogService', 'OrderingService' e così via: un client tipizzato è una classe che accetta un `HttpClient` oggetto (iniettato tramite il relativo costruttore) e lo utilizza per chiamare un servizio HTTP remoto. Ad esempio:

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

Il Client tipizzato (nell'esempio)`CatalogService` viene attivato da DI (Dependency Injection), vale a dire `HttpClient`che può accettare qualsiasi servizio registrato nel relativo costruttore, oltre a .

Un client tipizzato è di fatto un oggetto temporaneo, vale a dire che ne viene creata una nuova istanza ogni volta che è necessario e riceve una nuova istanza `HttpClient` ogni volta che viene costruito. Tuttavia, `HttpMessageHandler` gli oggetti nel pool sono gli `HttpClient` oggetti che vengono riutilizzati da più istanze.

### <a name="use-your-typed-client-classes"></a>Uso di classi di client tipizzato

Infine, una volta implementate le classi tipizzate `AddHttpClient()`e registrate e configurate con , è possibile utilizzarle ovunque sia possibile avere servizi iniettati da DI. Ad esempio, in un codice di pagina Razor o controller di un'app Web MVC, come nel codice seguente da eShopOnContainers:

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

Fino a questo punto, il codice illustrato è solo l'esecuzione di normali richieste Http, ma la 'magia' è disponibile nelle sezioni seguenti in `HttpClient` cui, semplicemente aggiungendo criteri e delegando i gestori ai client tipizzati registrati, tutte le richieste HTTP da eseguire si comporterà tenendo conto di criteri resilienti come tentativi con backoff esponenziale, interruttori di circuito o qualsiasi altro gestore di delega personalizzato per implementare funzionalità di sicurezza aggiuntive, come l'utilizzo di token di autenticazione o qualsiasi altra funzionalità personalizzata.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Uso di HttpClientFactory in .NET Core**  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- **Codice sorgente HttpClientFactory `dotnet/extensions` nel repository GitHub**  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- **Polly (libreria .NET con funzionalità di resilienza e gestione degli errori temporanei)**  
  <http://www.thepollyproject.org/>
  
- **Utilizzo di IHttpClientFactory senza inserimento delle dipendenze (problema di GitHub)Using IHttpClientFactory without dependency injection (GitHub issue)**  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
>[Successivo](implement-resilient-entity-framework-core-sql-connections.md)
>[precedente](implement-http-call-retries-exponential-backoff-polly.md)
