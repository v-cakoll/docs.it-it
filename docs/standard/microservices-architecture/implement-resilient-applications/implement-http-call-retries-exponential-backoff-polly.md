---
title: Implementazione della ripetizione dei tentativi per le chiamate HTTP con backoff esponenziale con Polly
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione della ripetizione dei tentativi per le chiamate HTTP con backoff esponenziale con Polly
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 122f617874188d3bffe689d6b3cf7d7249c59c3b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a><span data-ttu-id="55f28-104">Implementazione della ripetizione dei tentativi per le chiamate HTTP con backoff esponenziale con Polly</span><span class="sxs-lookup"><span data-stu-id="55f28-104">Implementing HTTP call retries with exponential backoff with Polly</span></span>

<span data-ttu-id="55f28-105">L'approccio consigliato per la ripetizione dei tentativi con backoff esponenziale prevede l'uso di librerie .NET più avanzate, ad esempio la libreria open source [Polly](https://github.com/App-vNext/Polly).</span><span class="sxs-lookup"><span data-stu-id="55f28-105">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open source [Polly](https://github.com/App-vNext/Polly) library.</span></span>

<span data-ttu-id="55f28-106">Polly è una libreria .NET che fornisce funzionalità di resilienza e di gestione degli errori temporanei.</span><span class="sxs-lookup"><span data-stu-id="55f28-106">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="55f28-107">È possibile implementare facilmente queste funzionalità applicando i criteri di Polly, ad esempio Retry, Circuit Breaker, Bulkhead Isolation, Timeout e Fallback.</span><span class="sxs-lookup"><span data-stu-id="55f28-107">You can implement those capabilities easily by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="55f28-108">La libreria Polly è compatibile con .NET 4.x e .NET Standard versione 1.0, che supporta .NET Core.</span><span class="sxs-lookup"><span data-stu-id="55f28-108">Polly targets .NET 4.x and the .NET Standard version 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="55f28-109">I criteri di ripetizione (Retry) in Polly costituiscono l'approccio usato nell'app eShopOnContainers per l'implementazione dei tentativi HTTP.</span><span class="sxs-lookup"><span data-stu-id="55f28-109">The Retry policy in Polly is the approach used in eShopOnContainers when implementing HTTP retries.</span></span> <span data-ttu-id="55f28-110">È possibile implementare un'interfaccia per inserire la funzionalità HttpClient standard o una versione resiliente di HttpClient tramite Polly, a seconda della configurazione dei criteri di ripetizione che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="55f28-110">You can implement an interface so you can inject either standard HttpClient functionality or a resilient version of HttpClient using Polly, depending on what retry policy configuration you want to use.</span></span>

<span data-ttu-id="55f28-111">L'esempio seguente mostra l'interfaccia implementata in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="55f28-111">The following example shows the interface implemented in eShopOnContainers.</span></span>

```csharp
public interface IHttpClient
{
    Task<string> GetStringAsync(string uri, string authorizationToken = null,
        string authorizationMethod = "Bearer");
        Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    Task<HttpResponseMessage> DeleteAsync(string uri,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    // Other methods ...
}
```

<span data-ttu-id="55f28-112">È possibile usare l'implementazione standard se non si vuole usare un meccanismo resiliente, in particolare per lo sviluppo o il test di approcci più semplici.</span><span class="sxs-lookup"><span data-stu-id="55f28-112">You can use the standard implementation if you do not want to use a resilient mechanism, as when you are developing or testing simpler approaches.</span></span> <span data-ttu-id="55f28-113">Il codice seguente mostra l'implementazione della funzionalità HttpClient standard che consente le richieste con token di autenticazione come scenario facoltativo.</span><span class="sxs-lookup"><span data-stu-id="55f28-113">The following code shows the standard HttpClient implementation allowing requests with authentication tokens as an optional case.</span></span>

```csharp
public class StandardHttpClient : IHttpClient
{
    private HttpClient _client;
    private ILogger<StandardHttpClient> _logger;

    public StandardHttpClient(ILogger<StandardHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
    }

    public async Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
        if (authorizationToken != null)
        {
            requestMessage.Headers.Authorization =
                new AuthenticationHeaderValue(authorizationMethod, authorizationToken);
        }
        var response = await _client.SendAsync(requestMessage);
        return await response.Content.ReadAsStringAsync();
    }

    public async Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer")
    {
        // Rest of the code and other Http methods ...
```

<span data-ttu-id="55f28-114">L'aspetto interessante consiste nella scrittura di codice di un'altra classe simile usando Polly per implementare i meccanismi di resilienza desiderati, nell'esempio seguente i tentativi con backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="55f28-114">The interesting implementation is to code another, similar class, but using Polly to implement the resilient mechanisms you want to use—in the following example, retries with exponential backoff.</span></span>

```csharp
public class ResilientHttpClient : IHttpClient
{
    private HttpClient _client;
    private PolicyWrap _policyWrapper;
    private ILogger<ResilientHttpClient> _logger;

    public ResilientHttpClient(Policy[] policies,
        ILogger<ResilientHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
        // Add Policies to be applied
        _policyWrapper = Policy.WrapAsync(policies);
    }

    private Task<T> HttpInvoker<T>(Func<Task<T>> action)
    {
        // Executes the action applying all
        // the policies defined in the wrapper
        return _policyWrapper.ExecuteAsync(() => action());
    }

    public Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        return HttpInvoker(async () =>
        {
            var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
            // The Token's related code eliminated for clarity in code snippet
            var response = await _client.SendAsync(requestMessage);
            return await response.Content.ReadAsStringAsync();
        });
    }
    // Other Http methods executed through HttpInvoker so it applies Polly policies
    // ...
}
```

<span data-ttu-id="55f28-115">Con Polly, si definiscono criteri di ripetizione con il numero di tentativi, la configurazione del backoff esponenziale e le azioni da eseguire quando si verifica un'eccezione HTTP, ad esempio la registrazione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="55f28-115">With Polly, you define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="55f28-116">In questo caso, i criteri sono configurati, quindi verrà eseguito il numero di tentativi specificato durante la registrazione dei tipi nel contenitore IoC.</span><span class="sxs-lookup"><span data-stu-id="55f28-116">In this case, the policy is configured so it will try the number of times specified when registering the types in the IoC container.</span></span> <span data-ttu-id="55f28-117">Poiché è presente una configurazione di backoff esponenziale, ogni volta che il codice rileva un'eccezione HttpRequest, effettua un nuovo tentativo di richiesta HTTP dopo aver atteso un periodo di tempo che aumenta esponenzialmente a seconda di come sono stati configurati i criteri.</span><span class="sxs-lookup"><span data-stu-id="55f28-117">Because of the exponential backoff configuration, whenever the code detects an HttpRequest exception, it retries the Http request after waiting an amount of time that increases exponentially depending on how the policy was configured.</span></span>

<span data-ttu-id="55f28-118">Il metodo importante in questo scenario è HttpInvoker, che elabora le richieste tramite questa classe di utilità.</span><span class="sxs-lookup"><span data-stu-id="55f28-118">The important method is HttpInvoker, which is what makes HTTP requests throughout this utility class.</span></span> <span data-ttu-id="55f28-119">Questo metodo esegue internamente la richiesta HTTP con \_policyWrapper.ExecuteAsync, che tiene conto dei criteri di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="55f28-119">That method internally executes the HTTP request with \_policyWrapper.ExecuteAsync, which takes into account the retry policy.</span></span>

<span data-ttu-id="55f28-120">In eShopOnContainers si specificano i criteri di Polly durante la registrazione dei tipi nel contenitore IoC, come nel codice seguente della [classe startup.cs dell'app Web MVC](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs).</span><span class="sxs-lookup"><span data-stu-id="55f28-120">In eShopOnContainers you specify Polly policies when registering the types at the IoC container, as in the following code from the [MVC web app at the startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) class.</span></span>

```csharp
// Startup.cs class
if (Configuration.GetValue<string>("UseResilientHttp") == bool.TrueString)
{
    services.AddTransient<IResilientHttpClientFactory,
        ResilientHttpClientFactory>();
    services.AddSingleton<IHttpClient,
        ResilientHttpClient>(sp =>
            sp.GetService<IResilientHttpClientFactory>().
            CreateResilientHttpClient());
}
else
{
    services.AddSingleton<IHttpClient, StandardHttpClient>();
}
```

<span data-ttu-id="55f28-121">Si noti che per gli oggetti IHttpClient le istanze vengono create come singleton anziché come temporanee per garantire l'uso efficiente delle connessioni TCP da parte del servizio ed evitare che si verifichino [problemi con i socket](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="55f28-121">Note that the IHttpClient objects are instantiated as singleton instead of as transient so that TCP connections are used efficiently by the service and [an issue with sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) will not occur.</span></span>

<span data-ttu-id="55f28-122">Il punto importante circa la resilienza sta nel fatto che si applicano i criteri di Polly WaitAndRetryAsync in ResilientHttpClientFactory nel metodo CreateResilientHttpClient, come mostrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="55f28-122">But the important point about resiliency is that you apply the Polly WaitAndRetryAsync policy within ResilientHttpClientFactory in the CreateResilientHttpClient method, as shown in the following code:</span></span>

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

// Other code
private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
        // number of retries
        6,
        // exponential backoff
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
        // on retry
        (exception, timeSpan, retryCount, context) =>
        {
            var msg = $"Retry {retryCount} implemented with Pollys RetryPolicy " +
            $"of {context.PolicyKey} " +
            $"at {context.ExecutionKey}, " +
            $"due to: {exception}.";
            _logger.LogWarning(msg);
            _logger.LogDebug(msg);
        }),
    }
```


>[!div class="step-by-step"]
<span data-ttu-id="55f28-123">[Indietro] (implement-custom-http-call-retries-exponential-backoff.md) [Avanti] (implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="55f28-123">[Previous] (implement-custom-http-call-retries-exponential-backoff.md) [Next] (implement-circuit-breaker-pattern.md)</span></span>
