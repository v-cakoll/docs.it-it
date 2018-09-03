---
title: Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti
description: HttpClientFactory è una solida factory, disponibile a partire da .NET Core 2.1, per la creazione di istanze `HttpClient` da usare nelle applicazioni.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 07/03/2018
ms.openlocfilehash: 6fd30a9358ca9c07b2a6e2ec591e4c5d7db54ccb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43395540"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a>Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti

`HttpClientFactory` è una solida factory, disponibile a partire da .NET Core 2.1, per la creazione di istanze `HttpClient` da usare nelle applicazioni. 

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Problemi con la classe HttpClient originale disponibile in .NET Core

La classe [HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) originale e ben nota può essere facilmente usata, ma in alcuni casi, non viene usata correttamente da molti sviluppatori. 

Come primo problema, sebbene questa classe sia eliminabile, il suo utilizzo con l'istruzione `using` non rappresenta la scelta migliore perché, anche quando si elimina l'oggetto `HttpClient`, il socket sottostante non viene rilasciato immediatamente e può generare quindi un problema serio di esaurimento di socket. Per altre informazioni su questo problema, vedere il post di blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Uso errato di HttpClient e conseguente destabilizzazione del software).

La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione. La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi. Questo problema genera errori `SocketException`. I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/console-webapiclient). 

Esiste tuttavia un secondo problema con la classe `HttpClient` legato al suo utilizzo come oggetto singleton o statico. In questo caso un oggetto `HttpClient` singleton o statico non rispetta le modifiche DNS, come descritto in questo [problema nel repository di GitHub di .NET Core](https://github.com/dotnet/corefx/issues/11224). 

Per risolvere i problemi menzionati e semplificare la gestione delle istanze di `HttpClient`, .NET Core 2.1 offre un nuovo oggetto `HttpClientFactory` che può essere usato anche per implementare le chiamate HTTP resilienti tramite l'integrazione con Polly.   

## <a name="what-is-httpclientfactory"></a>Scopo di HttpClientFactory

L'oggetto `HttpClientFactory` è progettato per:

- Offrire una posizione centrale per la denominazione e la configurazione di istanze di HttpClient logiche. È ad esempio possibile configurare un client (agente di servizio) che è preconfigurato per accedere a un microservizio specifico.
- Codificare il concetto di middleware in uscita tramite la delega di gestori in `HttpClient` e l'implementazione di middleware basato su Polly per sfruttarne i criteri di resilienza.
- `HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita. Si registrano i client HTTP nella factory ed è anche possibile usare un gestore Polly che consente l'uso dei criteri di Polly per i nuovi tentativi, gli interruttori, ecc.
- Gestire la durata di HttpClientMessageHandlers per evitare i problemi menzionati che possono verificarsi quando si gestiscono le durate di `HttpClient` personalmente. 

## <a name="multiple-ways-to-use-httpclientfactory"></a>Modi diversi di usare HttpClientFactory

Esistono molti modi per usare `HttpClientFactory` nell'applicazione:

- Usare `HttpClientFactory` direttamente
- Usare client denominati
- Usare client tipizzati
- Usare client generati

Per ragioni di brevità, questo materiale sussidiario illustra il modo più strutturato di usare `HttpClientFactory`, che consiste nell'usare i client tipizzati (modello di agente di servizio), ma tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo che descrive l'uso di HttpClientFactory](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?#consumption-patterns).  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a>Come usare i client tipizzati con HttpClientFactory

Il diagramma seguente mostra come vengono usati i client tipizzati con HttpClientFactory.

![Diagramma con un controller MVC che usa un ClientService inserito, che usa internamente un oggetto HttpClient configurato dai criteri di Polly e da HttpClientFactory](./media/image3.5.png)

**Figura 10-4**. Uso di `HttpClientFactory` con classi di client tipizzati.

Impostare prima di tutto `HttpClientFactory` nell'applicazione. Aggiungere un riferimento al pacchetto `Microsoft.Extensions.Http` che include il metodo di estensione `AddHttpClient()` per `IServiceCollection`. Questo metodo di estensione registra l'oggetto `DefaultHttpClientFactory` da usare come oggetto singleton per l'interfaccia `IHttpClientFactory`. Definisce una configurazione temporanea per l'oggetto `HttpMessageHandlerBuilder`. Questo gestore di messaggi (oggetto `HttpMessageHandler`), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.

Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

Semplicemente aggiungendo le classi di client tipizzato con AddHttpClient(), ogni volta che si usa l'oggetto `HttpClient` che verrà inserito nella classe mediante il relativo costruttore, l'oggetto `HttpClient` userà la configurazione e tutti i criteri forniti. Nelle sezioni successive si noteranno tali criteri come tentativi o interruttori di Polly.

### <a name="httpclient-lifetimes"></a>Durate di HttpClient

Ogni volta che si ottiene un oggetto `HttpClient` da IHttpClientFactory, viene restituita una nuova istanza di un oggetto `HttpClient`. Esisterà un HttpMessageHandler** per ogni client denominato o tipizzato. I`HttpClientFactory` eseguirà il pooling delle istanze di HttpMessageHandler create dalla factory per ridurre il consumo di risorse. Un'istanza di HttpMessageHandler può essere riusata dal pool quando si crea una nuova istanza di `HttpClient` se la relativa durata non è scaduta.

Il pooling dei gestori è opportuno poiché ogni gestore si occupa in genere di gestire le proprie connessioni HTTP sottostanti. La creazione di un numero superiore di gestori rispetto a quelli necessari può determinare ritardi di connessione. Alcuni gestori mantengono inoltre le connessioni aperte a tempo indefinito. Ciò può impedire al gestore di reagire alle modifiche DNS.

Gli oggetti HttpMessageHandler nel pool hanno una durata che è l'intervallo di tempo in cui un'istanza di HttpMessageHandler nel pool può essere usata nuovamente. Il valore predefinito è due minuti, ma può essere sostituito in base al cliente denominato o tipizzato. Per eseguirne l'override, chiamare SetHandlerLifetime() nell'oggetto IHttpClientBuilder che viene restituito quando si crea il client, come illustrato nel codice seguente.

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

Ogni client tipizzato o client denominato può avere il proprio valore di durata del gestore configurato. Impostare la durata su InfiniteTimeSpan per disabilitare la scadenza del gestore.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Implementare le classi di client tipizzato che usano l'oggetto HttpClient inserito e configurato

È necessario aver precedentemente definito le classi di client tipizzato, ad esempio le classi nell'esempio di codice, come "BasketService", "CatalogService", "OrderingService" e così via. Un client tipizzato è una classe che accetta un oggetto `HttpClient` (inserito tramite il relativo costruttore) e lo usa per chiamare un qualche servizio HTTP remoto. Ad esempio:

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

Il client tipizzato (nell'esempio CatalogService) viene attivato da DI (Dependency Injection), che significa che accetta qualsiasi servizio registrato nel proprio costruttore, oltre alla classe HttpClient.

Un client tipizzato è, in effetti, un oggetto temporaneo, vale a dire che ne viene creata una nuova istanza ogni volta che è necessaria e riceve una nuova istanza `HttpClient` ogni volta che viene costruito. Gli oggetti HttpMessageHandler nel pool tuttavia sono gli oggetti che vengono riusati da più richieste HTTP.

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

Il codice mostrato esegue finora solo normali richieste HTTP. La magia inizia nelle sezioni seguenti dove, semplicemente aggiungendo criteri e gestori di delega ai client tipizzati registrati, tutte le richieste HTTP che devono essere eseguite da `HttpClient` si comporteranno prendendo in considerazione i criteri di resilienza, ad esempio i tentativi con backoff esponenziale, gli interruttori o qualsiasi altro gestore di delega personalizzato per implementare funzionalità di sicurezza aggiuntive, come l'uso di token di autorizzazione o qualsiasi altra funzionalità personalizzata. 


## <a name="additional-resources"></a>Risorse aggiuntive

-   **Using HttpClientFactory in .NET Core 2.1 (Uso della classe HttpClientFactory in .NET Core 2.1)**
    [*https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)


-   **Repository di GitHub su HttpClientFactory**

    [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)



>[!div class="step-by-step"]
[Previous] (explore-custom-http-call-retries-exponential-backoff.md) [Next] (implement-http-call-retries-exponential-backoff-polly.md)
