---
title: Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti
description: Informazioni su come usare HttpClientFactory, disponibile a partire da .NET Core 2.1, per la creazione di istanze `HttpClient`, semplificandone l'uso nelle applicazioni.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 6af30ae3b5111e026be6ec89d266338b88cf22b2
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362641"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a>Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti

`HttpClientFactory` è una solida factory, disponibile a partire da .NET Core 2.1, per la creazione di istanze <xref:System.Net.Http.HttpClient> da usare nelle applicazioni.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Problemi con la classe HttpClient originale disponibile in .NET Core

La classe [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) originale e ben nota può essere usata facilmente, ma in alcuni casi non viene usata correttamente dagli sviluppatori. 

Come primo problema, sebbene questa classe sia eliminabile, il suo utilizzo con l'istruzione `using` non rappresenta la scelta migliore perché, anche quando si elimina l'oggetto `HttpClient`, il socket sottostante non viene rilasciato immediatamente e può generare quindi un problema serio di esaurimento di socket. Per altre informazioni su questo problema, vedere il post di blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Uso errato di HttpClient e conseguente destabilizzazione del software).

La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione. La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi. Questo problema genera errori `SocketException`. I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](/dotnet/csharp/tutorials/console-webapiclient). 

Esiste tuttavia un secondo problema con la classe `HttpClient` legato al suo utilizzo come oggetto singleton o statico. In questo caso un oggetto `HttpClient` singleton o statico non rispetta le modifiche DNS, come descritto in questo [problema nel repository di GitHub di .NET Core](https://github.com/dotnet/corefx/issues/11224). 

Per risolvere i problemi menzionati e semplificare la gestione delle istanze di `HttpClient`, .NET Core 2.1 offre un nuovo oggetto `HttpClientFactory` che può essere usato anche per implementare le chiamate HTTP resilienti tramite l'integrazione con Polly.   

## <a name="what-is-httpclientfactory"></a>Scopo di HttpClientFactory

L'oggetto `HttpClientFactory` è progettato per:

- Offrire una posizione centrale per la denominazione e la configurazione di istanze di HttpClient logiche. È ad esempio possibile configurare un client (agente di servizio) preconfigurato per l'accesso a un microservizio specifico.
- Codificare il concetto di middleware in uscita tramite la delega di gestori in `HttpClient` e l'implementazione di middleware basato su Polly per sfruttarne i criteri di resilienza.
- `HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita. Si registrano i client HTTP nella factory ed è anche possibile usare un gestore Polly che consente l'uso dei criteri di Polly per i nuovi tentativi, gli interruttori, ecc.
- Gestire la durata di HttpClientMessageHandlers per evitare i problemi menzionati che possono verificarsi quando si gestiscono le durate di `HttpClient` personalmente. 

## <a name="multiple-ways-to-use-httpclientfactory"></a>Modi diversi di usare HttpClientFactory

Esistono molti modi per usare `HttpClientFactory` nell'applicazione:

- Usare `HttpClientFactory` direttamente
- Usare client denominati
- Usare client tipizzati
- Usare client generati

Per ragioni di brevità, questo materiale sussidiario illustra il modo più strutturato per usare `HttpClientFactory`, che consiste nell'usare i client tipizzati (modello di agente del servizio), ma tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo che descrive l'uso di HttpClientFactory](/aspnet/core/fundamentals/http-requests?#consumption-patterns).  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a>Come usare i client tipizzati con HttpClientFactory

Che cos'è un "client tipizzato"? È semplicemente un elemento `HttpClient` configurato al momento dell'inserimento da `DefaultHttpClientFactory`.

Il diagramma seguente visualizza l'uso dei client tipizzati con `HttpClientFactory`.

![Un ClientService (usato da un controller o da codice client) usa un HttpClient creato dalla IHttpClientFactory registrata. Questa factory assegna a HttpClient un HttpMessageHandler da un pool gestito. HttpClient può essere configurato con i criteri di Polly quando si registra la IHttpClientFactory nel contenitore di inserimento delle dipendenze con il metodo di estensione AddHttpClient.](./media/image3.5.png)

**Figura 8-4**. Uso di HttpClientFactory con le classi client tipizzati.

In primo luogo configurare `HttpClientFactory` nell'applicazione, aggiungendo un riferimento al pacchetto `Microsoft.Extensions.Http` che include il metodo di estensione `AddHttpClient()` per `IServiceCollection`. Questo metodo di estensione registra l'oggetto `DefaultHttpClientFactory` da usare come oggetto singleton per l'interfaccia `IHttpClientFactory`. Definisce una configurazione temporanea per l'oggetto `HttpMessageHandlerBuilder`. Questo gestore di messaggi (oggetto `HttpMessageHandler`), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.

Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

La registrazione dei servizi client illustrata nel codice precedente consente a `DefaultClientFactory` di creare un `HttpClient` configurato in modo specifico per ogni servizio, come illustrato nel paragrafo successivo.

Mediante la semplice registrazione della classe del servizio client con `AddHttpClient()` l'oggetto `HttpClient` che viene inserito nella classe userà la configurazione e i criteri forniti al momento della registrazione. Nelle sezioni successive questi criteri verranno visualizzati come tentativi o interruttori di Polly.

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

Dopo avere implementato le classi del tipo e averle registrate con AddHttpClient(), è possibile usarle ovunque si possano avere servizi inseriti da DI, ad esempio in qualsiasi codice di Razor Pages o qualsiasi controller di un'app Web MVC, come nel seguente codice estratto da eShopOnContainers.

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

- **Using HttpClientFactory in .NET Core 2.1**\ (Uso di HttpClientFactory in .NET Core 2.1)
  [*https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)

- **Repository di GitHub su HttpClientFactory**\
  [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)

>[!div class="step-by-step"]
>[Precedente](explore-custom-http-call-retries-exponential-backoff.md)
>[Successivo](implement-http-call-retries-exponential-backoff-polly.md)