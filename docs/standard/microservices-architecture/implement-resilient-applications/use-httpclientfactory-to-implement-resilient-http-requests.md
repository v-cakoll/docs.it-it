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
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="e7eb2-103">Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti</span><span class="sxs-lookup"><span data-stu-id="e7eb2-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="e7eb2-104">`HttpClientFactory` è una solida factory, disponibile a partire da .NET Core 2.1, per la creazione di istanze <xref:System.Net.Http.HttpClient> da usare nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="e7eb2-105">Problemi con la classe HttpClient originale disponibile in .NET Core</span><span class="sxs-lookup"><span data-stu-id="e7eb2-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="e7eb2-106">La classe [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) originale e ben nota può essere usata facilmente, ma in alcuni casi non viene usata correttamente dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-106">The original and well-known [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span> 

<span data-ttu-id="e7eb2-107">Come primo problema, sebbene questa classe sia eliminabile, il suo utilizzo con l'istruzione `using` non rappresenta la scelta migliore perché, anche quando si elimina l'oggetto `HttpClient`, il socket sottostante non viene rilasciato immediatamente e può generare quindi un problema serio di esaurimento di socket.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="e7eb2-108">Per altre informazioni su questo problema, vedere il post di blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Uso errato di HttpClient e conseguente destabilizzazione del software).</span><span class="sxs-lookup"><span data-stu-id="e7eb2-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="e7eb2-109">La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="e7eb2-110">La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="e7eb2-111">Questo problema genera errori `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="e7eb2-112">I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](/dotnet/csharp/tutorials/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="e7eb2-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](/dotnet/csharp/tutorials/console-webapiclient).</span></span> 

<span data-ttu-id="e7eb2-113">Esiste tuttavia un secondo problema con la classe `HttpClient` legato al suo utilizzo come oggetto singleton o statico.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="e7eb2-114">In questo caso un oggetto `HttpClient` singleton o statico non rispetta le modifiche DNS, come descritto in questo [problema nel repository di GitHub di .NET Core](https://github.com/dotnet/corefx/issues/11224).</span><span class="sxs-lookup"><span data-stu-id="e7eb2-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue at the .NET Core GitHub repo](https://github.com/dotnet/corefx/issues/11224).</span></span> 

<span data-ttu-id="e7eb2-115">Per risolvere i problemi menzionati e semplificare la gestione delle istanze di `HttpClient`, .NET Core 2.1 offre un nuovo oggetto `HttpClientFactory` che può essere usato anche per implementare le chiamate HTTP resilienti tramite l'integrazione con Polly.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 offers a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>   

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="e7eb2-116">Scopo di HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="e7eb2-116">What is HttpClientFactory</span></span>

<span data-ttu-id="e7eb2-117">L'oggetto `HttpClientFactory` è progettato per:</span><span class="sxs-lookup"><span data-stu-id="e7eb2-117">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="e7eb2-118">Offrire una posizione centrale per la denominazione e la configurazione di istanze di HttpClient logiche.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-118">Provide a central location for naming and configuring logical HttpClients.</span></span> <span data-ttu-id="e7eb2-119">È ad esempio possibile configurare un client (agente di servizio) preconfigurato per l'accesso a un microservizio specifico.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-119">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="e7eb2-120">Codificare il concetto di middleware in uscita tramite la delega di gestori in `HttpClient` e l'implementazione di middleware basato su Polly per sfruttarne i criteri di resilienza.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-120">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="e7eb2-121">`HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-121">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="e7eb2-122">Si registrano i client HTTP nella factory ed è anche possibile usare un gestore Polly che consente l'uso dei criteri di Polly per i nuovi tentativi, gli interruttori, ecc.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-122">You register http clients into the factory plus you can use a Polly handler that allows Polly policies to be used for Retry, CircuitBreakers, etc.</span></span>
- <span data-ttu-id="e7eb2-123">Gestire la durata di HttpClientMessageHandlers per evitare i problemi menzionati che possono verificarsi quando si gestiscono le durate di `HttpClient` personalmente.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-123">Manage the lifetime of HttpClientMessageHandlers to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span> 

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="e7eb2-124">Modi diversi di usare HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="e7eb2-124">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="e7eb2-125">Esistono molti modi per usare `HttpClientFactory` nell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e7eb2-125">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="e7eb2-126">Usare `HttpClientFactory` direttamente</span><span class="sxs-lookup"><span data-stu-id="e7eb2-126">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="e7eb2-127">Usare client denominati</span><span class="sxs-lookup"><span data-stu-id="e7eb2-127">Use Named Clients</span></span>
- <span data-ttu-id="e7eb2-128">Usare client tipizzati</span><span class="sxs-lookup"><span data-stu-id="e7eb2-128">Use Typed Clients</span></span>
- <span data-ttu-id="e7eb2-129">Usare client generati</span><span class="sxs-lookup"><span data-stu-id="e7eb2-129">Use Generated Clients</span></span>

<span data-ttu-id="e7eb2-130">Per ragioni di brevità, questo materiale sussidiario illustra il modo più strutturato per usare `HttpClientFactory`, che consiste nell'usare i client tipizzati (modello di agente del servizio), ma tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo che descrive l'uso di HttpClientFactory](/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="e7eb2-130">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory` that's to use Typed Clients (Service Agent pattern), but all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span></span>  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="e7eb2-131">Come usare i client tipizzati con HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="e7eb2-131">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="e7eb2-132">Che cos'è un "client tipizzato"?</span><span class="sxs-lookup"><span data-stu-id="e7eb2-132">So, what's a "Typed Client"?</span></span> <span data-ttu-id="e7eb2-133">È semplicemente un elemento `HttpClient` configurato al momento dell'inserimento da `DefaultHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-133">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="e7eb2-134">Il diagramma seguente visualizza l'uso dei client tipizzati con `HttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-134">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![Un ClientService (usato da un controller o da codice client) usa un HttpClient creato dalla IHttpClientFactory registrata.](./media/image3.5.png)

<span data-ttu-id="e7eb2-138">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-138">**Figure 8-4**.</span></span> <span data-ttu-id="e7eb2-139">Uso di HttpClientFactory con le classi client tipizzati.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-139">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="e7eb2-140">In primo luogo configurare `HttpClientFactory` nell'applicazione, aggiungendo un riferimento al pacchetto `Microsoft.Extensions.Http` che include il metodo di estensione `AddHttpClient()` per `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-140">First, setup `HttpClientFactory` in your application, adding a reference to the `Microsoft.Extensions.Http` package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="e7eb2-141">Questo metodo di estensione registra l'oggetto `DefaultHttpClientFactory` da usare come oggetto singleton per l'interfaccia `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-141">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="e7eb2-142">Definisce una configurazione temporanea per l'oggetto `HttpMessageHandlerBuilder`.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-142">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="e7eb2-143">Questo gestore di messaggi (oggetto `HttpMessageHandler`), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-143">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="e7eb2-144">Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-144">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="e7eb2-145">La registrazione dei servizi client illustrata nel codice precedente consente a `DefaultClientFactory` di creare un `HttpClient` configurato in modo specifico per ogni servizio, come illustrato nel paragrafo successivo.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-145">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create an `HttpClient` configured specifically for each service, as we'll explain in the next paragraph.</span></span>

<span data-ttu-id="e7eb2-146">Mediante la semplice registrazione della classe del servizio client con `AddHttpClient()` l'oggetto `HttpClient` che viene inserito nella classe userà la configurazione e i criteri forniti al momento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-146">Just by registering your client service class with `AddHttpClient()`, the `HttpClient` object that will be injected into your class will use the configuration and policies provided upon registration.</span></span> <span data-ttu-id="e7eb2-147">Nelle sezioni successive questi criteri verranno visualizzati come tentativi o interruttori di Polly.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-147">In the next sections, you'll see those policies like Polly’s retries or circuit-breakers.</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="e7eb2-148">Durate di HttpClient</span><span class="sxs-lookup"><span data-stu-id="e7eb2-148">HttpClient lifetimes</span></span>

<span data-ttu-id="e7eb2-149">Ogni volta che si ottiene un oggetto `HttpClient` da `IHttpClientFactory` viene restituita una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-149">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="e7eb2-150">Tuttavia ogni `HttpClient` usa un `HttpMessageHandler` in pool e riusato da `IHttpClientFactory` per ridurre il consumo di risorse, a condizione che la durata di `HttpMessageHandler` non sia scaduta.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-150">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="e7eb2-151">Il pooling dei gestori è opportuno poiché ogni gestore si occupa in genere di gestire le proprie connessioni HTTP sottostanti. La creazione di un numero superiore di gestori rispetto a quelli necessari può determinare ritardi di connessione.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-151">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="e7eb2-152">Alcuni gestori mantengono inoltre le connessioni aperte a tempo indefinito. Ciò può impedire al gestore di reagire alle modifiche DNS.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-152">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="e7eb2-153">Gli oggetti `HttpMessageHandler` nel pool hanno una durata, che è l'intervallo di tempo in cui un'istanza di `HttpMessageHandler` nel pool può essere usata nuovamente.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-153">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="e7eb2-154">Il valore predefinito è due minuti, ma può essere sostituito in base al cliente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-154">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="e7eb2-155">Per eseguire l'override, chiamare `SetHandlerLifetime()` nell'elemento `IHttpClientBuilder` restituito al momento della creazione del client, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e7eb2-155">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

<span data-ttu-id="e7eb2-156">Ogni client tipizzato o client denominato può avere un proprio valore configurato di durata del gestore.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-156">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="e7eb2-157">Impostare la durata su `InfiniteTimeSpan` per disabilitare la scadenza del gestore.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-157">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="e7eb2-158">Implementare le classi di client tipizzato che usano l'oggetto HttpClient inserito e configurato</span><span class="sxs-lookup"><span data-stu-id="e7eb2-158">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="e7eb2-159">È necessario avere definito in precedenza le classi di client tipizzato, ad esempio le classi nell'esempio di codice come "BasketService", "CatalogService", "OrderingService" e così via. Un client tipizzato è una classe che accetta un oggetto `HttpClient` (inserito tramite il relativo costruttore) e lo usa per chiamare un servizio HTTP remoto.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-159">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="e7eb2-160">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7eb2-160">For example:</span></span>

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

<span data-ttu-id="e7eb2-161">Il client tipizzato (CatalogService nell'esempio) viene attivato da DI (Dependency Injection) e ciò significa che accetta qualsiasi servizio registrato nel proprio costruttore oltre alla classe HttpClient.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-161">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="e7eb2-162">Un client tipizzato è di fatto un oggetto temporaneo, vale a dire che ne viene creata una nuova istanza ogni volta che è necessario e riceve una nuova istanza `HttpClient` ogni volta che viene costruito.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-162">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="e7eb2-163">Gli oggetti HttpMessageHandler nel pool tuttavia sono gli oggetti che vengono riusati da più richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-163">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="e7eb2-164">Uso di classi di client tipizzato</span><span class="sxs-lookup"><span data-stu-id="e7eb2-164">Use your Typed Client classes</span></span>

<span data-ttu-id="e7eb2-165">Dopo avere implementato le classi del tipo e averle registrate con AddHttpClient(), è possibile usarle ovunque si possano avere servizi inseriti da DI, ad esempio in qualsiasi codice di Razor Pages o qualsiasi controller di un'app Web MVC, come nel seguente codice estratto da eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-165">Finally, once you have your type classes implemented and have them registered with AddHttpClient(), you can use it anywhere you can have services injected by DI, for example in any Razor page code or any controller of an MVC web app, like in the following code from eShopOnContainers.</span></span>

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

<span data-ttu-id="e7eb2-166">Il codice visualizzato fino a questo punto esegue solo normali richieste HTTP. La parte sorprendente inizia nelle sezioni seguenti, dove aggiungendo semplicemente criteri e gestori di delega ai client tipizzati registrati, tutte le richieste HTTP che devono essere eseguite da `HttpClient` funzionano tenendo in considerazione i criteri di resilienza, ad esempio i tentativi con backoff esponenziale, gli interruttori o qualsiasi altro gestore di delega personalizzato per implementare funzionalità di sicurezza aggiuntive, come l'uso di token di autorizzazione o qualsiasi altra funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e7eb2-166">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="e7eb2-167">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e7eb2-167">Additional resources</span></span>

- <span data-ttu-id="e7eb2-168">**Using HttpClientFactory in .NET Core 2.1**\ (Uso di HttpClientFactory in .NET Core 2.1)</span><span class="sxs-lookup"><span data-stu-id="e7eb2-168">**Using HttpClientFactory in .NET Core 2.1**\\</span></span>
  [*https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)

- <span data-ttu-id="e7eb2-169">**Repository di GitHub su HttpClientFactory**\\</span><span class="sxs-lookup"><span data-stu-id="e7eb2-169">**HttpClientFactory GitHub repo**\\</span></span>
  [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)

>[!div class="step-by-step"]
><span data-ttu-id="e7eb2-170">[Precedente](explore-custom-http-call-retries-exponential-backoff.md)
>[Successivo](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="e7eb2-170">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>