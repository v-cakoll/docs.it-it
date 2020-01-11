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
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="b31e1-103">Usare HttpClientFactory per l'implementazione di richieste HTTP resilienti</span><span class="sxs-lookup"><span data-stu-id="b31e1-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="b31e1-104">`HttpClientFactory` è una solida factory, disponibile a partire da .NET Core 2.1, per la creazione di istanze <xref:System.Net.Http.HttpClient> da usare nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b31e1-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="b31e1-105">Problemi con la classe HttpClient originale disponibile in .NET Core</span><span class="sxs-lookup"><span data-stu-id="b31e1-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="b31e1-106">La classe <xref:System.Net.Http.HttpClient> originale e nota può essere utilizzata facilmente, ma in alcuni casi non viene utilizzata correttamente da molti sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="b31e1-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="b31e1-107">Come primo problema, sebbene questa classe sia eliminabile, il suo utilizzo con l'istruzione `using` non rappresenta la scelta migliore perché, anche quando si elimina l'oggetto `HttpClient`, il socket sottostante non viene rilasciato immediatamente e può generare quindi un problema serio di esaurimento di socket.</span><span class="sxs-lookup"><span data-stu-id="b31e1-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="b31e1-108">Per altre informazioni su questo problema, vedere il post di blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Uso errato di HttpClient e conseguente destabilizzazione del software).</span><span class="sxs-lookup"><span data-stu-id="b31e1-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="b31e1-109">La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b31e1-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="b31e1-110">La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi.</span><span class="sxs-lookup"><span data-stu-id="b31e1-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="b31e1-111">Questo problema genera errori `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="b31e1-112">I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](../../../csharp/tutorials/console-webapiclient.md).</span><span class="sxs-lookup"><span data-stu-id="b31e1-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span>

<span data-ttu-id="b31e1-113">Esiste tuttavia un secondo problema con la classe `HttpClient` legato al suo utilizzo come oggetto singleton o statico.</span><span class="sxs-lookup"><span data-stu-id="b31e1-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="b31e1-114">In questo caso, un singleton o un `HttpClient` statico non rispetta le modifiche DNS, come illustrato in questo [problema](https://github.com/dotnet/corefx/issues/11224) nel repository GitHub DotNet/CoreFx.</span><span class="sxs-lookup"><span data-stu-id="b31e1-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue](https://github.com/dotnet/corefx/issues/11224) at the dotnet/corefx GitHub repository.</span></span>

<span data-ttu-id="b31e1-115">Per risolvere i problemi menzionati e semplificare la gestione delle istanze di `HttpClient`, in .NET Core 2.1 è stato introdotto un nuovo oggetto `HttpClientFactory` che può essere usato anche per implementare le chiamate HTTP resilienti tramite l'integrazione con Polly.</span><span class="sxs-lookup"><span data-stu-id="b31e1-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>

<span data-ttu-id="b31e1-116">[Polly](http://www.thepollyproject.org/) è una libreria di gestione degli errori temporanei che consente agli sviluppatori di aggiungere resilienza alle applicazioni, usando alcuni criteri predefiniti in modo Fluent e thread-safe.</span><span class="sxs-lookup"><span data-stu-id="b31e1-116">[Polly](http://www.thepollyproject.org/) is transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="b31e1-117">Scopo di HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="b31e1-117">What is HttpClientFactory</span></span>

<span data-ttu-id="b31e1-118">L'oggetto `HttpClientFactory` è progettato per:</span><span class="sxs-lookup"><span data-stu-id="b31e1-118">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="b31e1-119">Fornire una posizione centralizzata per la denominazione e la configurazione di oggetti di `HttpClient` logici.</span><span class="sxs-lookup"><span data-stu-id="b31e1-119">Provide a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="b31e1-120">È ad esempio possibile configurare un client (agente di servizio) preconfigurato per l'accesso a un microservizio specifico.</span><span class="sxs-lookup"><span data-stu-id="b31e1-120">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="b31e1-121">Codificare il concetto di middleware in uscita tramite la delega di gestori in `HttpClient` e l'implementazione di middleware basato su Polly per sfruttarne i criteri di resilienza.</span><span class="sxs-lookup"><span data-stu-id="b31e1-121">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="b31e1-122">`HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="b31e1-122">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="b31e1-123">Si registrano client HTTP nella Factory ed è possibile usare un gestore Polly per usare i criteri di Polly per i tentativi, interruttori e così via.</span><span class="sxs-lookup"><span data-stu-id="b31e1-123">You register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="b31e1-124">Gestire la durata di `HttpClientMessageHandlers` per evitare i problemi o i problemi indicati che possono verificarsi quando si gestiscono autonomamente `HttpClient` durate.</span><span class="sxs-lookup"><span data-stu-id="b31e1-124">Manage the lifetime of `HttpClientMessageHandlers` to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="b31e1-125">`HttpClientFactory` è strettamente legata all'implementazione di inserimento delle dipendenze nel pacchetto NuGet `Microsoft.Extensions.DependencyInjection`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-125">`HttpClientFactory` is tightly tied to the dependency injection (DI) implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="b31e1-126">Per altre informazioni sull'uso di altri contenitori di inserimento di dipendenze, vedere questa [discussione su GitHub](https://github.com/dotnet/extensions/issues/1345).</span><span class="sxs-lookup"><span data-stu-id="b31e1-126">For more information about using other dependency injection containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="b31e1-127">Modi diversi di usare HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="b31e1-127">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="b31e1-128">Esistono molti modi per usare `HttpClientFactory` nell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="b31e1-128">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="b31e1-129">Usare `HttpClientFactory` direttamente</span><span class="sxs-lookup"><span data-stu-id="b31e1-129">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="b31e1-130">Usare client denominati</span><span class="sxs-lookup"><span data-stu-id="b31e1-130">Use Named Clients</span></span>
- <span data-ttu-id="b31e1-131">Usare client tipizzati</span><span class="sxs-lookup"><span data-stu-id="b31e1-131">Use Typed Clients</span></span>
- <span data-ttu-id="b31e1-132">Usare client generati</span><span class="sxs-lookup"><span data-stu-id="b31e1-132">Use Generated Clients</span></span>

<span data-ttu-id="b31e1-133">Per brevità, questo materiale sussidiario illustra il modo più strutturato per utilizzare `HttpClientFactory`, ovvero l'utilizzo di client tipizzati (modello di agente di servizio).</span><span class="sxs-lookup"><span data-stu-id="b31e1-133">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="b31e1-134">Tuttavia, tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo relativo all'utilizzo di HttpClientFactory](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="b31e1-134">However, all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="b31e1-135">Come usare i client tipizzati con HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="b31e1-135">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="b31e1-136">Che cos'è un "client tipizzato"?</span><span class="sxs-lookup"><span data-stu-id="b31e1-136">So, what's a "Typed Client"?</span></span> <span data-ttu-id="b31e1-137">È semplicemente un elemento `HttpClient` configurato al momento dell'inserimento da `DefaultHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-137">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="b31e1-138">Il diagramma seguente visualizza l'uso dei client tipizzati con `HttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-138">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![Diagramma che illustra la modalità di utilizzo dei client tipizzati con HttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="b31e1-140">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="b31e1-140">**Figure 8-4**.</span></span> <span data-ttu-id="b31e1-141">Uso di HttpClientFactory con le classi client tipizzati.</span><span class="sxs-lookup"><span data-stu-id="b31e1-141">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="b31e1-142">Nell'immagine precedente, un ClientService (usato da un controller o da un codice client) usa un `HttpClient` creato dal `IHttpClientFactory`registrato.</span><span class="sxs-lookup"><span data-stu-id="b31e1-142">In the above image, a ClientService (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="b31e1-143">Questa factory assegna la `HttpClient` una `HttpMessageHandler` da un pool gestito.</span><span class="sxs-lookup"><span data-stu-id="b31e1-143">This factory assigns the `HttpClient` an `HttpMessageHandler` from a pool it manages.</span></span> <span data-ttu-id="b31e1-144">La `HttpClient` può essere configurata con i criteri di Polly quando si registrano i `IHttpClientFactory` nel contenitore DI inserimento delle dipendenze con il metodo di estensione `AddHttpClient`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-144">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method `AddHttpClient`.</span></span>

<span data-ttu-id="b31e1-145">Per configurare la struttura precedente, aggiungere `HttpClientFactory` nell'applicazione installando il pacchetto NuGet `Microsoft.Extensions.Http` che include il metodo di estensione `AddHttpClient()` per `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-145">To configure the above structure, add `HttpClientFactory` in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="b31e1-146">Questo metodo di estensione registra l'oggetto `DefaultHttpClientFactory` da usare come oggetto singleton per l'interfaccia `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-146">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="b31e1-147">Definisce una configurazione temporanea per l'oggetto `HttpMessageHandlerBuilder`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-147">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="b31e1-148">Questo gestore di messaggi (oggetto `HttpMessageHandler`), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.</span><span class="sxs-lookup"><span data-stu-id="b31e1-148">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="b31e1-149">Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="b31e1-149">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="b31e1-150">La registrazione dei servizi client come illustrato nel codice precedente rende la `DefaultClientFactory` creare un `HttpClient` standard per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="b31e1-150">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="b31e1-151">È anche possibile aggiungere la configurazione specifica dell'istanza nella registrazione a, ad esempio, configurare l'indirizzo di base e aggiungere alcuni criteri di resilienza, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b31e1-151">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="b31e1-152">Per l'esempio, è possibile visualizzare uno dei criteri precedenti nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b31e1-152">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="b31e1-153">Per altre informazioni sull'uso di Polly, vedere l' [articolo successivo](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="b31e1-153">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="b31e1-154">Durate di HttpClient</span><span class="sxs-lookup"><span data-stu-id="b31e1-154">HttpClient lifetimes</span></span>

<span data-ttu-id="b31e1-155">Ogni volta che si ottiene un oggetto `HttpClient` da `IHttpClientFactory` viene restituita una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="b31e1-155">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="b31e1-156">Tuttavia ogni `HttpClient` usa un `HttpMessageHandler` in pool e riusato da `IHttpClientFactory` per ridurre il consumo di risorse, a condizione che la durata di `HttpMessageHandler` non sia scaduta.</span><span class="sxs-lookup"><span data-stu-id="b31e1-156">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="b31e1-157">Il pooling dei gestori è opportuno poiché ogni gestore si occupa in genere di gestire le proprie connessioni HTTP sottostanti. La creazione di un numero superiore di gestori rispetto a quelli necessari può determinare ritardi di connessione.</span><span class="sxs-lookup"><span data-stu-id="b31e1-157">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="b31e1-158">Alcuni gestori mantengono inoltre le connessioni aperte a tempo indefinito. Ciò può impedire al gestore di reagire alle modifiche DNS.</span><span class="sxs-lookup"><span data-stu-id="b31e1-158">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="b31e1-159">Gli oggetti `HttpMessageHandler` nel pool hanno una durata, che è l'intervallo di tempo in cui un'istanza di `HttpMessageHandler` nel pool può essere usata nuovamente.</span><span class="sxs-lookup"><span data-stu-id="b31e1-159">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="b31e1-160">Il valore predefinito è due minuti, ma può essere sostituito in base al cliente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="b31e1-160">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="b31e1-161">Per eseguire l'override, chiamare `SetHandlerLifetime()` nell'elemento `IHttpClientBuilder` restituito al momento della creazione del client, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b31e1-161">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="b31e1-162">Ogni client tipizzato o client denominato può avere un proprio valore configurato di durata del gestore.</span><span class="sxs-lookup"><span data-stu-id="b31e1-162">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="b31e1-163">Impostare la durata su `InfiniteTimeSpan` per disabilitare la scadenza del gestore.</span><span class="sxs-lookup"><span data-stu-id="b31e1-163">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="b31e1-164">Implementare le classi di client tipizzato che usano l'oggetto HttpClient inserito e configurato</span><span class="sxs-lookup"><span data-stu-id="b31e1-164">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="b31e1-165">È necessario avere definito in precedenza le classi di client tipizzato, ad esempio le classi nell'esempio di codice come "BasketService", "CatalogService", "OrderingService" e così via. Un client tipizzato è una classe che accetta un oggetto `HttpClient` (inserito tramite il relativo costruttore) e lo usa per chiamare un servizio HTTP remoto.</span><span class="sxs-lookup"><span data-stu-id="b31e1-165">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="b31e1-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b31e1-166">For example:</span></span>

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

<span data-ttu-id="b31e1-167">Il client tipizzato (CatalogService nell'esempio) viene attivato da DI (Dependency Injection) e ciò significa che accetta qualsiasi servizio registrato nel proprio costruttore oltre alla classe HttpClient.</span><span class="sxs-lookup"><span data-stu-id="b31e1-167">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="b31e1-168">Un client tipizzato è di fatto un oggetto temporaneo, vale a dire che ne viene creata una nuova istanza ogni volta che è necessario e riceve una nuova istanza `HttpClient` ogni volta che viene costruito.</span><span class="sxs-lookup"><span data-stu-id="b31e1-168">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="b31e1-169">Gli oggetti HttpMessageHandler nel pool tuttavia sono gli oggetti che vengono riusati da più richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="b31e1-169">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="b31e1-170">Uso di classi di client tipizzato</span><span class="sxs-lookup"><span data-stu-id="b31e1-170">Use your Typed Client classes</span></span>

<span data-ttu-id="b31e1-171">Infine, una volta che le classi tipizzate sono state implementate e sono state registrate con `AddHttpClient()`, è possibile usarle ovunque sia possibile inserire i servizi in base a.</span><span class="sxs-lookup"><span data-stu-id="b31e1-171">Finally, once you have your typed classes implemented and have them registered with `AddHttpClient()`, you can use them wherever you can have services injected by DI.</span></span> <span data-ttu-id="b31e1-172">Ad esempio, in un codice della pagina Razor o in un controller di un'app Web MVC, come nel codice seguente da eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="b31e1-172">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="b31e1-173">Il codice visualizzato fino a questo punto esegue solo normali richieste HTTP. La parte sorprendente inizia nelle sezioni seguenti, dove aggiungendo semplicemente criteri e gestori di delega ai client tipizzati registrati, tutte le richieste HTTP che devono essere eseguite da `HttpClient` funzionano tenendo in considerazione i criteri di resilienza, ad esempio i tentativi con backoff esponenziale, gli interruttori o qualsiasi altro gestore di delega personalizzato per implementare funzionalità di sicurezza aggiuntive, come l'uso di token di autorizzazione o qualsiasi altra funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b31e1-173">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b31e1-174">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b31e1-174">Additional resources</span></span>

- <span data-ttu-id="b31e1-175">**Uso di HttpClientFactory in .NET Core**</span><span class="sxs-lookup"><span data-stu-id="b31e1-175">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="b31e1-176">**HttpClientFactory codice sorgente nel repository GitHub `dotnet/extensions`**</span><span class="sxs-lookup"><span data-stu-id="b31e1-176">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="b31e1-177">**Polly (libreria .NET con funzionalità di resilienza e di gestione degli errori temporanei)**</span><span class="sxs-lookup"><span data-stu-id="b31e1-177">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="b31e1-178">**Uso di HttpClientFactory senza inserimento delle dipendenze (problema di GitHub)**</span><span class="sxs-lookup"><span data-stu-id="b31e1-178">**Using HttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="b31e1-179">[Precedente](explore-custom-http-call-retries-exponential-backoff.md)
>[Successivo](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="b31e1-179">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
