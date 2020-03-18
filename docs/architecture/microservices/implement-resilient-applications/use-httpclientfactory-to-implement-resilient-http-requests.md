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
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="471c2-103">Usare IHttpClientFactory per implementare richieste HTTP resilientiUse IHttpClientFactory to implement resilient HTTP requests</span><span class="sxs-lookup"><span data-stu-id="471c2-103">Use IHttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="471c2-104"><xref:System.Net.Http.IHttpClientFactory>è un contratto implementato da `DefaultHttpClientFactory`, una factory testata, disponibile <xref:System.Net.Http.HttpClient> a partire da .NET Core 2.1, per la creazione di istanze da utilizzare nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="471c2-104"><xref:System.Net.Http.IHttpClientFactory> is a contract implemented by `DefaultHttpClientFactory`, an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="471c2-105">Problemi con la classe HttpClient originale disponibile in .NET Core</span><span class="sxs-lookup"><span data-stu-id="471c2-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="471c2-106">La classe originale <xref:System.Net.Http.HttpClient> e ben nota può essere facilmente utilizzata, ma in alcuni casi, non viene utilizzata correttamente da molti sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="471c2-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="471c2-107">Sebbene questa `IDisposable`classe implementi , la dichiarazione e la creazione di istanze all'interno di un'istruzione `using` non è preferibile perché quando l'oggetto `HttpClient` viene eliminato, il socket sottostante non viene rilasciato immediatamente, il che può causare un problema di _esaurimento_ socket.</span><span class="sxs-lookup"><span data-stu-id="471c2-107">While this class implements `IDisposable`, declaring and instantiating it within a `using` statement is not preferred because when the `HttpClient` object gets disposed of, the underlying socket is not immediately released, which can lead to a _socket exhaustion_ problem.</span></span> <span data-ttu-id="471c2-108">Per ulteriori informazioni su questo problema, vedere il post di blog [Si sta utilizzando HttpClient errato e sta destabilizzando il software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="471c2-108">For more information about this issue, see the blog post [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span></span>

<span data-ttu-id="471c2-109">La classe `HttpClient` è pertanto destinata a essere avviata una sola volta e a essere riusata nell'arco della vita di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="471c2-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="471c2-110">La creazione di un'istanza di una classe `HttpClient` per ogni richiesta esaurisce il numero di socket disponibili con carichi voluminosi.</span><span class="sxs-lookup"><span data-stu-id="471c2-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="471c2-111">Questo problema genera errori `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="471c2-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="471c2-112">I possibili approcci per risolvere il problema si basano sulla creazione dell'oggetto `HttpClient` come oggetto singleton o statico, come illustrato in questo [articolo di Microsoft sull'utilizzo della classe HttpClient](../../../csharp/tutorials/console-webapiclient.md).</span><span class="sxs-lookup"><span data-stu-id="471c2-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span> <span data-ttu-id="471c2-113">Questa può essere una buona soluzione per le applicazioni console di breve durata o simili che vengono eseguite un paio di volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="471c2-113">This can be a good solution for short-lived console apps or similar that are run a few times a day.</span></span>

<span data-ttu-id="471c2-114">Un altro problema che gli sviluppatori incorrere in è quando si utilizza un'istanza condivisa di `HttpClient` in processi a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="471c2-114">Another issue that developers run into is when using a shared instance of `HttpClient` in long running processes.</span></span> <span data-ttu-id="471c2-115">In una situazione in cui il HttpClient viene creata un'istanza come singleton o un oggetto statico, non riesce a gestire le modifiche DNS come descritto in questo [numero](https://github.com/dotnet/corefx/issues/11224) del repository GitHub dotnet/corefx.</span><span class="sxs-lookup"><span data-stu-id="471c2-115">In a situation where the HttpClient is instantiated as a singleton or a static object, it fails to handle the DNS changes as described in this [issue](https://github.com/dotnet/corefx/issues/11224) of the dotnet/corefx GitHub repository.</span></span>

<span data-ttu-id="471c2-116">Tuttavia, il problema non `HttpClient` è realmente con di per sé, ma con il <xref:System.Net.Http.HttpMessageHandler> [costruttore predefinito per HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), perché crea una nuova istanza concreta di , ovvero quello con *esaurimento* dei socket e DNS modifica i problemi di cui sopra.</span><span class="sxs-lookup"><span data-stu-id="471c2-116">However, the issue isn't really with `HttpClient` per se, but with the [default constructor for HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), because it creates a new concrete instance of <xref:System.Net.Http.HttpMessageHandler>, which is the one that has *sockets exhaustion* and DNS changes issues mentioned above.</span></span>

<span data-ttu-id="471c2-117">Per risolvere i problemi menzionati in precedenza e rendere `HttpClient` gestibili le istanze, .NET Core 2.1 ha introdotto l'interfaccia <xref:System.Net.Http.IHttpClientFactory> che può essere utilizzata per configurare e creare `HttpClient` istanze in un'app tramite Dependency Injection (DI).</span><span class="sxs-lookup"><span data-stu-id="471c2-117">To address the issues mentioned above and to make `HttpClient` instances manageable, .NET Core 2.1 introduced the <xref:System.Net.Http.IHttpClientFactory> interface which can be used to configure and create `HttpClient` instances in an app through Dependency Injection (DI).</span></span> <span data-ttu-id="471c2-118">Fornisce inoltre estensioni per middleware basato su Polly per sfruttare i vantaggi della delega dei gestori in HttpClient.It also provides extensions for Polly-based middleware to take advantage of delegating handlers in HttpClient.</span><span class="sxs-lookup"><span data-stu-id="471c2-118">It also provides extensions for Polly-based middleware to take advantage of delegating handlers in HttpClient.</span></span>

<span data-ttu-id="471c2-119">[Polly](http://www.thepollyproject.org/) è una libreria di gestione degli errori transitori che consente agli sviluppatori di aggiungere resilienza alle applicazioni, usando alcuni criteri predefiniti in modo fluente e thread-safe.</span><span class="sxs-lookup"><span data-stu-id="471c2-119">[Polly](http://www.thepollyproject.org/) is a transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="benefits-of-using-ihttpclientfactory"></a><span data-ttu-id="471c2-120">Vantaggi dell'utilizzo di IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="471c2-120">Benefits of using IHttpClientFactory</span></span>

<span data-ttu-id="471c2-121">L'implementazione <xref:System.Net.Http.IHttpClientFactory>corrente di <xref:System.Net.Http.IHttpMessageHandlerFactory>, che implementa anche , offre i seguenti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="471c2-121">The current implementation of <xref:System.Net.Http.IHttpClientFactory>, that also implements <xref:System.Net.Http.IHttpMessageHandlerFactory>, offers the following benefits:</span></span>

- <span data-ttu-id="471c2-122">Fornisce una posizione centrale per `HttpClient` la denominazione e la configurazione di oggetti logici.</span><span class="sxs-lookup"><span data-stu-id="471c2-122">Provides a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="471c2-123">È ad esempio possibile configurare un client (agente di servizio) preconfigurato per l'accesso a un microservizio specifico.</span><span class="sxs-lookup"><span data-stu-id="471c2-123">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="471c2-124">Codificare il concetto di middleware in `HttpClient` uscita tramite la delega di gestori e l'implementazione di middleware basato su Polly per sfruttare i criteri di Polly per la resilienza.</span><span class="sxs-lookup"><span data-stu-id="471c2-124">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly's policies for resiliency.</span></span>
- <span data-ttu-id="471c2-125">`HttpClient` include già il concetto di delega di gestori concatenati per le richieste HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="471c2-125">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="471c2-126">È possibile registrare i client HTTP nella factory ed è possibile utilizzare un gestore Polly per utilizzare i criteri Polly per Retry, CircuitBreakers e così via.</span><span class="sxs-lookup"><span data-stu-id="471c2-126">You can register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="471c2-127">Gestire la <xref:System.Net.Http.HttpMessageHandler> durata per evitare i problemi/problemi `HttpClient` menzionati che possono verificarsi durante la gestione delle durate da soli.</span><span class="sxs-lookup"><span data-stu-id="471c2-127">Manage the lifetime of <xref:System.Net.Http.HttpMessageHandler> to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!TIP]
> <span data-ttu-id="471c2-128">Le `HttpClient` istanze inserite da DI, possono essere `HttpMessageHandler` eliminate in modo sicuro, perché l'oggetto associato è gestito dalla factory.</span><span class="sxs-lookup"><span data-stu-id="471c2-128">The `HttpClient` instances injected by DI, can be disposed of safely, because the associated `HttpMessageHandler` is managed by the factory.</span></span> <span data-ttu-id="471c2-129">Infatti, le `HttpClient` istanze inserite hanno ambito dal punto di vista DI. *Scoped*</span><span class="sxs-lookup"><span data-stu-id="471c2-129">As a matter of fact, injected `HttpClient` instances are *Scoped* from a DI perspective.</span></span>

> [!NOTE]
> <span data-ttu-id="471c2-130">L'implementazione di `IHttpClientFactory` (`DefaultHttpClientFactory`) è strettamente `Microsoft.Extensions.DependencyInjection` legata all'implementazione DI nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="471c2-130">The implementation of `IHttpClientFactory` (`DefaultHttpClientFactory`) is tightly tied to the DI implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="471c2-131">Per altre informazioni sull'uso di altri contenitori DI, vedere questa discussione di [GitHub](https://github.com/dotnet/extensions/issues/1345).</span><span class="sxs-lookup"><span data-stu-id="471c2-131">For more information about using other DI containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-ihttpclientfactory"></a><span data-ttu-id="471c2-132">Più modi per usare IHttpClientFactoryMultiple ways to use IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="471c2-132">Multiple ways to use IHttpClientFactory</span></span>

<span data-ttu-id="471c2-133">Esistono molti modi per usare `IHttpClientFactory` nell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="471c2-133">There are several ways that you can use `IHttpClientFactory` in your application:</span></span>

- <span data-ttu-id="471c2-134">Utilizzo di base</span><span class="sxs-lookup"><span data-stu-id="471c2-134">Basic usage</span></span>
- <span data-ttu-id="471c2-135">Usare client denominati</span><span class="sxs-lookup"><span data-stu-id="471c2-135">Use Named Clients</span></span>
- <span data-ttu-id="471c2-136">Usare client tipizzati</span><span class="sxs-lookup"><span data-stu-id="471c2-136">Use Typed Clients</span></span>
- <span data-ttu-id="471c2-137">Usare client generati</span><span class="sxs-lookup"><span data-stu-id="471c2-137">Use Generated Clients</span></span>

<span data-ttu-id="471c2-138">Per motivi di brevità, questa guida mostra `IHttpClientFactory`il modo più strutturato per utilizzare , ovvero utilizzare i client tipizzati (modello di agente di servizio).</span><span class="sxs-lookup"><span data-stu-id="471c2-138">For the sake of brevity, this guidance shows the most structured way to use `IHttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="471c2-139">Tuttavia, tutte le opzioni sono documentate e sono attualmente elencate in questo [articolo che copre l'utilizzo `IHttpClientFactory` ](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="471c2-139">However, all options are documented and are currently listed in this [article covering the `IHttpClientFactory` usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a><span data-ttu-id="471c2-140">Come utilizzare client tipizzato con IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="471c2-140">How to use Typed Clients with IHttpClientFactory</span></span>

<span data-ttu-id="471c2-141">Che cos'è un "client tipizzato"?</span><span class="sxs-lookup"><span data-stu-id="471c2-141">So, what's a "Typed Client"?</span></span> <span data-ttu-id="471c2-142">E 'solo `HttpClient` un che è preconfigurato per qualche uso specifico.</span><span class="sxs-lookup"><span data-stu-id="471c2-142">It's just an `HttpClient` that's pre-configured for some specific use.</span></span> <span data-ttu-id="471c2-143">Questa configurazione può includere valori specifici, ad esempio il server di base, le intestazioni HTTP o i timeout.</span><span class="sxs-lookup"><span data-stu-id="471c2-143">This configuration can include specific values such as the base server, HTTP headers or time outs.</span></span>

<span data-ttu-id="471c2-144">Il diagramma seguente visualizza l'uso dei client tipizzati con `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="471c2-144">The following diagram shows how Typed Clients are used with `IHttpClientFactory`:</span></span>

![Diagramma che mostra l'utilizzo dei client tipizzato con IHttpClientFactory.Diagram showing how typed clients are used with IHttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="471c2-146">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="471c2-146">**Figure 8-4**.</span></span> <span data-ttu-id="471c2-147">Utilizzo `IHttpClientFactory` delle classi Client tippizzate.</span><span class="sxs-lookup"><span data-stu-id="471c2-147">Using `IHttpClientFactory` with Typed Client classes.</span></span>

<span data-ttu-id="471c2-148">Nell'immagine precedente, `ClientService` un (utilizzato da un controller `HttpClient` o codice `IHttpClientFactory`client) utilizza un creato dal file registrato.</span><span class="sxs-lookup"><span data-stu-id="471c2-148">In the above image, a `ClientService` (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="471c2-149">Questa factory assegna `HttpMessageHandler` un da `HttpClient`un pool al file .</span><span class="sxs-lookup"><span data-stu-id="471c2-149">This factory assigns an `HttpMessageHandler` from a pool to the `HttpClient`.</span></span> <span data-ttu-id="471c2-150">L'oggetto `HttpClient` può essere configurato con i `IHttpClientFactory` criteri di Polly durante <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*>la registrazione di nel contenitore DI con il metodo di estensione .</span><span class="sxs-lookup"><span data-stu-id="471c2-150">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*>.</span></span>

<span data-ttu-id="471c2-151">Per configurare la <xref:System.Net.Http.IHttpClientFactory> struttura precedente, aggiungere `Microsoft.Extensions.Http` nell'applicazione installando il pacchetto NuGet che include il metodo di <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*> estensione per <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span><span class="sxs-lookup"><span data-stu-id="471c2-151">To configure the above structure, add <xref:System.Net.Http.IHttpClientFactory> in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*> extension method for <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="471c2-152">Questo metodo di estensione `DefaultHttpClientFactory` registra la classe interna da utilizzare `IHttpClientFactory`come singleton per l'interfaccia .</span><span class="sxs-lookup"><span data-stu-id="471c2-152">This extension method registers the internal `DefaultHttpClientFactory` class to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="471c2-153">Definisce una configurazione temporanea per l'oggetto <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>.</span><span class="sxs-lookup"><span data-stu-id="471c2-153">It defines a transient configuration for the <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>.</span></span> <span data-ttu-id="471c2-154">Questo gestore di messaggi (oggetto <xref:System.Net.Http.HttpMessageHandler>), estratto da un pool, viene usato dall'oggetto `HttpClient` restituito dalla factory.</span><span class="sxs-lookup"><span data-stu-id="471c2-154">This message handler (<xref:System.Net.Http.HttpMessageHandler> object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="471c2-155">Nel codice successivo è possibile vedere come usare `AddHttpClient()` per registrare i client tipizzati (agenti di servizio) che devono usare `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="471c2-155">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="471c2-156">La registrazione dei servizi client, come illustrato `DefaultClientFactory` nel `HttpClient` codice precedente, rende il creare uno standard per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="471c2-156">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="471c2-157">È anche possibile aggiungere la configurazione specifica dell'istanza nella registrazione per, ad esempio, configurare l'indirizzo di base e aggiungere alcuni criteri di resilienza, come illustrato nel codice seguente:You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span><span class="sxs-lookup"><span data-stu-id="471c2-157">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="471c2-158">Solo per l'esempio di sake, è possibile visualizzare uno dei criteri di cui sopra nel codice successivo:</span><span class="sxs-lookup"><span data-stu-id="471c2-158">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="471c2-159">Per ulteriori informazioni sull'utilizzo di Polly, vedere [l'articolo Avanti](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="471c2-159">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="471c2-160">Durate di HttpClient</span><span class="sxs-lookup"><span data-stu-id="471c2-160">HttpClient lifetimes</span></span>

<span data-ttu-id="471c2-161">Ogni volta che si ottiene un oggetto `HttpClient` da `IHttpClientFactory` viene restituita una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="471c2-161">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="471c2-162">Tuttavia ogni `HttpClient` usa un `HttpMessageHandler` in pool e riusato da `IHttpClientFactory` per ridurre il consumo di risorse, a condizione che la durata di `HttpMessageHandler` non sia scaduta.</span><span class="sxs-lookup"><span data-stu-id="471c2-162">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="471c2-163">Il pooling dei gestori è opportuno poiché ogni gestore si occupa in genere di gestire le proprie connessioni HTTP sottostanti. La creazione di un numero superiore di gestori rispetto a quelli necessari può determinare ritardi di connessione.</span><span class="sxs-lookup"><span data-stu-id="471c2-163">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="471c2-164">Alcuni gestori mantengono inoltre le connessioni aperte a tempo indefinito. Ciò può impedire al gestore di reagire alle modifiche DNS.</span><span class="sxs-lookup"><span data-stu-id="471c2-164">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="471c2-165">Gli oggetti `HttpMessageHandler` nel pool hanno una durata, che è l'intervallo di tempo in cui un'istanza di `HttpMessageHandler` nel pool può essere usata nuovamente.</span><span class="sxs-lookup"><span data-stu-id="471c2-165">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="471c2-166">Il valore predefinito è due minuti, ma può essere sostituito in base al cliente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="471c2-166">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="471c2-167">Per eseguire l'override, chiamare `SetHandlerLifetime()` nell'elemento <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> restituito al momento della creazione del client, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="471c2-167">To override it, call `SetHandlerLifetime()` on the <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="471c2-168">Ogni client tipizzato o client denominato può avere un proprio valore configurato di durata del gestore.</span><span class="sxs-lookup"><span data-stu-id="471c2-168">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="471c2-169">Impostare la durata su `InfiniteTimeSpan` per disabilitare la scadenza del gestore.</span><span class="sxs-lookup"><span data-stu-id="471c2-169">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="471c2-170">Implementare le classi di client tipizzato che usano l'oggetto HttpClient inserito e configurato</span><span class="sxs-lookup"><span data-stu-id="471c2-170">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="471c2-171">Come passaggio precedente, è necessario avere le classi di Client tipizzato definite, ad esempio le classi nel codice di esempio, ad esempio 'BasketService', 'CatalogService', 'OrderingService' e così via: un client tipizzato è una classe che accetta un `HttpClient` oggetto (iniettato tramite il relativo costruttore) e lo utilizza per chiamare un servizio HTTP remoto.</span><span class="sxs-lookup"><span data-stu-id="471c2-171">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like 'BasketService', 'CatalogService', 'OrderingService', etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="471c2-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471c2-172">For example:</span></span>

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

<span data-ttu-id="471c2-173">Il Client tipizzato (nell'esempio)`CatalogService` viene attivato da DI (Dependency Injection), vale a dire `HttpClient`che può accettare qualsiasi servizio registrato nel relativo costruttore, oltre a .</span><span class="sxs-lookup"><span data-stu-id="471c2-173">The Typed Client (`CatalogService` in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to `HttpClient`.</span></span>

<span data-ttu-id="471c2-174">Un client tipizzato è di fatto un oggetto temporaneo, vale a dire che ne viene creata una nuova istanza ogni volta che è necessario e riceve una nuova istanza `HttpClient` ogni volta che viene costruito.</span><span class="sxs-lookup"><span data-stu-id="471c2-174">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="471c2-175">Tuttavia, `HttpMessageHandler` gli oggetti nel pool sono gli `HttpClient` oggetti che vengono riutilizzati da più istanze.</span><span class="sxs-lookup"><span data-stu-id="471c2-175">However, the `HttpMessageHandler` objects in the pool are the objects that are reused by multiple `HttpClient` instances.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="471c2-176">Uso di classi di client tipizzato</span><span class="sxs-lookup"><span data-stu-id="471c2-176">Use your Typed Client classes</span></span>

<span data-ttu-id="471c2-177">Infine, una volta implementate le classi tipizzate `AddHttpClient()`e registrate e configurate con , è possibile utilizzarle ovunque sia possibile avere servizi iniettati da DI.</span><span class="sxs-lookup"><span data-stu-id="471c2-177">Finally, once you have your typed classes implemented and have them registered and configured with `AddHttpClient()`, you can use them wherever you can have services injected by DI.</span></span> <span data-ttu-id="471c2-178">Ad esempio, in un codice di pagina Razor o controller di un'app Web MVC, come nel codice seguente da eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="471c2-178">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="471c2-179">Fino a questo punto, il codice illustrato è solo l'esecuzione di normali richieste Http, ma la 'magia' è disponibile nelle sezioni seguenti in `HttpClient` cui, semplicemente aggiungendo criteri e delegando i gestori ai client tipizzati registrati, tutte le richieste HTTP da eseguire si comporterà tenendo conto di criteri resilienti come tentativi con backoff esponenziale, interruttori di circuito o qualsiasi altro gestore di delega personalizzato per implementare funzionalità di sicurezza aggiuntive, come l'utilizzo di token di autenticazione o qualsiasi altra funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="471c2-179">Up to this point, the code shown is just performing regular Http requests, but the 'magic' comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="471c2-180">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="471c2-180">Additional resources</span></span>

- <span data-ttu-id="471c2-181">**Uso di HttpClientFactory in .NET Core**</span><span class="sxs-lookup"><span data-stu-id="471c2-181">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="471c2-182">**Codice sorgente HttpClientFactory `dotnet/extensions` nel repository GitHub**</span><span class="sxs-lookup"><span data-stu-id="471c2-182">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="471c2-183">**Polly (libreria .NET con funzionalità di resilienza e gestione degli errori temporanei)**</span><span class="sxs-lookup"><span data-stu-id="471c2-183">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="471c2-184">**Utilizzo di IHttpClientFactory senza inserimento delle dipendenze (problema di GitHub)Using IHttpClientFactory without dependency injection (GitHub issue)**</span><span class="sxs-lookup"><span data-stu-id="471c2-184">**Using IHttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="471c2-185">[Successivo](implement-resilient-entity-framework-core-sql-connections.md)
>[precedente](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="471c2-185">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
