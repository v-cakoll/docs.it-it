---
title: Implementazione dello schema Circuit Breaker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dello schema Circuit Breaker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5d7db6899068f84f9165022cfbf17767a75e7db9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="e4f83-104">Implementazione dello schema Circuit Breaker</span><span class="sxs-lookup"><span data-stu-id="e4f83-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="e4f83-105">Come notato in precedenza, è necessario gestire gli errori che potrebbero richiedere una quantità di tempo variabile per il ripristino, come accade quando si prova a connettersi a una risorsa o a un servizio remoto.</span><span class="sxs-lookup"><span data-stu-id="e4f83-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="e4f83-106">La gestione di questo tipo di errore può migliorare la stabilità e la resilienza di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4f83-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="e4f83-107">In un ambiente distribuito, le chiamate a servizi e risorse remote può non riuscire a causa di errori temporanei, ad esempio connessioni di rete lente e timeout oppure se le risorse vengono rallentate o sono temporaneamente non disponibili.</span><span class="sxs-lookup"><span data-stu-id="e4f83-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="e4f83-108">Questi errori in genere si correggono autonomamente dopo un breve periodo di tempo e un'applicazione cloud affidabile deve essere preparata a gestirli usando una strategia simile allo schema Retry.</span><span class="sxs-lookup"><span data-stu-id="e4f83-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="e4f83-109">Tuttavia, in alcune situazioni gli errori sono dovuti a eventi imprevisti, la cui risoluzione potrebbe richiedere molto più tempo.</span><span class="sxs-lookup"><span data-stu-id="e4f83-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="e4f83-110">La gravità di questi errori può variare, da una perdita parziale di connettività a un errore generale di un servizio.</span><span class="sxs-lookup"><span data-stu-id="e4f83-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="e4f83-111">In questi casi, è inutile continuare a ripetere in un'applicazione un'operazione che è improbabile venga eseguita.</span><span class="sxs-lookup"><span data-stu-id="e4f83-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="e4f83-112">È consigliabile invece codificare l'applicazione in modo che accetti l'errore dell'operazione e lo gestisca di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="e4f83-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="e4f83-113">Lo schema Circuit Breaker ha uno scopo diverso rispetto allo schema Retry.</span><span class="sxs-lookup"><span data-stu-id="e4f83-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="e4f83-114">Lo schema Retry consente a un'applicazione di ripetere un'operazione che si prevede possa essere completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e4f83-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="e4f83-115">Lo schema Circuit Breaker impedisce a un'applicazione di eseguire un'operazione che potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="e4f83-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="e4f83-116">Un'applicazione può combinare questi due schemi, usando lo schema Retry per richiamare un'operazione con un interruttore di circuito.</span><span class="sxs-lookup"><span data-stu-id="e4f83-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="e4f83-117">Tuttavia, la logica di ripetizione deve essere sensibile alle eventuali eccezioni restituite dall'interruttore di circuito e deve sospendere i tentativi se l'interruttore di circuito indica che un errore non è temporaneo.</span><span class="sxs-lookup"><span data-stu-id="e4f83-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="e4f83-118">Implementazione dello schema Circuit Breaker con Polly</span><span class="sxs-lookup"><span data-stu-id="e4f83-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="e4f83-119">Come accade quando si implementano i tentativi, l'approccio consigliato per gli interruttori di circuito prevede l'uso di librerie .NET collaudate come Polly.</span><span class="sxs-lookup"><span data-stu-id="e4f83-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="e4f83-120">L'applicazione eShopOnContainers usa i criteri dell'interruttore di circuito di Polly quando si implementano tentativi HTTP.</span><span class="sxs-lookup"><span data-stu-id="e4f83-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="e4f83-121">In realtà, l'applicazione applica entrambi i criteri alla classe di utilità ResilientHttpClient.</span><span class="sxs-lookup"><span data-stu-id="e4f83-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="e4f83-122">Quando si usa un oggetto di tipo ResilientHttpClient per le richieste HTTP da eShopOnContainers, vengono applicati entrambi i criteri, ma è possibile aggiungerne anche altri.</span><span class="sxs-lookup"><span data-stu-id="e4f83-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="e4f83-123">In questo scenario, l'unica aggiunta al codice usato per i tentativi di chiamata HTTP è il codice in cui viene aggiunto il criterio dell'interruttore di circuito all'elenco di criteri da usare, come illustrato alla fine di codice riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e4f83-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
            // number of retries
            6,
            // exponential backofff
            retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
            // on retry
            (exception, timeSpan, retryCount, context) =>
            {
                var msg = $"Retry {retryCount} implemented with Polly RetryPolicy " +
                    $"of {context.PolicyKey} " +
                    $"at {context.ExecutionKey}, " +
                    $"due to: {exception}.";
                _logger.LogWarning(msg);
                _logger.LogDebug(msg);
            }),
            Policy.Handle<HttpRequestException>()
                .CircuitBreakerAsync(
                    // number of exceptions before breaking circuit
                    5,
                    // time circuit opened before retry
                    TimeSpan.FromMinutes(1),
                    (exception, duration) =>
                    {
                        // on circuit opened
                        _logger.LogTrace("Circuit breaker opened");
                    },
                    () =>
                    {
                        // on circuit closed
                        _logger.LogTrace("Circuit breaker reset");
                    })
    };
}
```

<span data-ttu-id="e4f83-124">Il codice aggiunge un criterio al wrapper HTTP.</span><span class="sxs-lookup"><span data-stu-id="e4f83-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="e4f83-125">Questi criteri definiscono un interruttore di circuito che viene aperto quando il codice rileva il numero indicato di eccezioni consecutive (eccezioni in una riga), specificato nel parametro exceptionsAllowedBeforeBreaking (in questo caso, 5).</span><span class="sxs-lookup"><span data-stu-id="e4f83-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="e4f83-126">Quando il circuito è aperto, le richieste HTTP non funzionano, ma viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e4f83-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="e4f83-127">Gli interruttori di circuito devono essere usati anche per reindirizzare le richieste a un'infrastruttura di fallback nel caso di problemi in una determinata risorsa che viene distribuita in un ambiente diverso rispetto all'applicazione client o al servizio che esegue la chiamata HTTP.</span><span class="sxs-lookup"><span data-stu-id="e4f83-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="e4f83-128">In questo modo, se si verifica un'interruzione nel centro dati che influisce solo sui microservizi back-end, ma non sulle applicazioni client, queste applicazioni possono essere reindirizzate ai servizi di fallback.</span><span class="sxs-lookup"><span data-stu-id="e4f83-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="e4f83-129">È il corso la pianificazione di un nuovo criterio in Polly che consenta di automatizzare questo scenario per i [criteri di failover](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).</span><span class="sxs-lookup"><span data-stu-id="e4f83-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="e4f83-130">Naturalmente, tutte queste funzionalità riguardano casi in cui il failover viene gestito internamente nel codice .NET, e non automaticamente da Azure, con la trasparenza dei percorsi.</span><span class="sxs-lookup"><span data-stu-id="e4f83-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="e4f83-131">Uso della classe di utilità ResilientHttpClient da eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="e4f83-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="e4f83-132">La classe di utilità ResilientHttpClient viene usata in modo analogo alla classe .NET HttpClient.</span><span class="sxs-lookup"><span data-stu-id="e4f83-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="e4f83-133">Nell'esempio seguente relativo all'applicazione Web MVC in eShopOnContainers, ossia la classe dell'agente OrderingService usata da OrderController, l'oggetto ResilientHttpClient viene inserito con il parametro httpClient del costruttore.</span><span class="sxs-lookup"><span data-stu-id="e4f83-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="e4f83-134">L'oggetto viene quindi usato per eseguire le richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="e4f83-134">Then the object is used to perform HTTP requests.</span></span>

```csharp
public class OrderingService : IOrderingService
{
    private IHttpClient _apiClient;
    private readonly string _remoteServiceBaseUrl;
    private readonly IOptionsSnapshot<AppSettings> _settings;
    private readonly IHttpContextAccessor _httpContextAccesor;

    public OrderingService(IOptionsSnapshot<AppSettings> settings,
        IHttpContextAccessor httpContextAccesor,
        IHttpClient httpClient)
    {
        _remoteServiceBaseUrl = $"{settings.Value.OrderingUrl}/api/v1/orders";
        _settings = settings;
        _httpContextAccesor = httpContextAccesor;
        _apiClient = httpClient;
    }

    async public Task<List<Order>> GetMyOrders(ApplicationUser user)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        var ordersUrl = _remoteServiceBaseUrl;
        var dataString = await _apiClient.GetStringAsync(ordersUrl);
        var response = JsonConvert.DeserializeObject<List<Order>>(dataString);
        return response;
    }

    // Other methods ...
    async public Task CreateOrder(Order order)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        _apiClient.Inst.DefaultRequestHeaders.Add("x-requestid",
            order.RequestId.ToString());
        var ordersUrl = $"{_remoteServiceBaseUrl}/new";
        order.CardTypeId = 1;
        order.CardExpirationApiFormat();
        SetFakeIdToProducts(order);
        var response = await _apiClient.PostAsync(ordersUrl, order);
        response.EnsureSuccessStatusCode();
    }
}
```

<span data-ttu-id="e4f83-135">Quando viene usato l'oggetto membro \_apiClient, al suo interno viene usata la classe wrapper con criteri di Polly: criteri di ripetizione, criteri dell'interruttore di circuito e altri criteri applicabili disponibili nella raccolta di Polly.</span><span class="sxs-lookup"><span data-stu-id="e4f83-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="e4f83-136">Tentativi di test in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="e4f83-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="e4f83-137">Ogni volta che si avvia la soluzione eShopOnContainers in un host Docker, è necessario avviare più contenitori.</span><span class="sxs-lookup"><span data-stu-id="e4f83-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="e4f83-138">Alcuni dei contenitori vengono avviati e inizializzati più lentamente, ad esempio il contenitore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4f83-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="e4f83-139">Questo vale in particolare la prima volta che si distribuisce l'applicazione eShopOnContainers in Docker, perché è necessario configurare le immagini e il database.</span><span class="sxs-lookup"><span data-stu-id="e4f83-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="e4f83-140">Il fatto che alcuni contenitori vengano avviati più lentamente rispetto ad altri può causare la generazione iniziale di eccezioni HTTP negli altri servizi, anche se si impostano dipendenze tra i contenitori al livello Docker Compose, come illustrato nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e4f83-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="e4f83-141">Le dipendenze Docker Compose tra i contenitori si trovano solo sul livello processo.</span><span class="sxs-lookup"><span data-stu-id="e4f83-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="e4f83-142">Il processo del punto di ingresso del contenitore può essere avviato, ma SQL Server potrebbe non essere pronto per le query.</span><span class="sxs-lookup"><span data-stu-id="e4f83-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="e4f83-143">Di conseguenza, possono essere visualizzati numerosi errori e può essere restituita un'eccezione all'applicazione quando prova a usare il contenitore specificato.</span><span class="sxs-lookup"><span data-stu-id="e4f83-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="e4f83-144">Questo tipo di errore può essere visualizzato anche all'avvio quando l'applicazione viene distribuita nel cloud.</span><span class="sxs-lookup"><span data-stu-id="e4f83-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="e4f83-145">In questo caso, è possibile che gli agenti di orchestrazione stiano spostando i contenitori da un nodo o da una macchina virtuale a un'altra (ovvero, stanno avviando nuove istanze) durante il bilanciamento del numero di contenitori tra i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="e4f83-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="e4f83-146">eShopOnContainers risolve il problema usando lo schema Retry illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e4f83-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="e4f83-147">Questo approccio viene seguito anche perché, quando si avvia la soluzione, potrebbero essere visualizzate tracce di log o avvisi simili al seguente:</span><span class="sxs-lookup"><span data-stu-id="e4f83-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="e4f83-148">"**Tentativo 1 implementato con i criteri di ripetizione di Polly**, causato da: System.Net.Http.HttpRequestException: Si è verificato un errore durante l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e4f83-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="e4f83-149"> ---&gt; System.Net.Http.CurlException: impossibile connettersi al server\\ in System.Net.Http.CurlHandler.ThrowIfCURLEError(errore CURLcode)\\ in \[...\].</span><span class="sxs-lookup"><span data-stu-id="e4f83-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="e4f83-150">Test dell'interruttore di circuito in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="e4f83-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="e4f83-151">Esistono diversi modi per aprire il circuito ed eseguirne il test con eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="e4f83-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="e4f83-152">Una possibilità consiste nel ridurre il numero consentito di tentativi a 1 nei criteri dell'interruttore di circuito e ridistribuire l'intera soluzione in Docker.</span><span class="sxs-lookup"><span data-stu-id="e4f83-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="e4f83-153">Con un solo tentativo, è probabile che una richiesta HTTP non riuscirà durante la distribuzione, l'interruttore di circuito verrà aperto e verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="e4f83-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="e4f83-154">Un'altra opzione consiste nell'usare middleware personalizzato che viene implementato nel microservizio `Basket`.</span><span class="sxs-lookup"><span data-stu-id="e4f83-154">Another option is to use custom middleware that is implemented in the `Basket` microservice.</span></span> <span data-ttu-id="e4f83-155">Quando il middleware è abilitato, intercetta tutte le richieste HTTP e restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="e4f83-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="e4f83-156">È possibile abilitare il middleware eseguendo una richiesta GET all'URI che ha generato l'errore, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e4f83-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="e4f83-157">GET /failing</span><span class="sxs-lookup"><span data-stu-id="e4f83-157">GET /failing</span></span>

<span data-ttu-id="e4f83-158">Questa richiesta restituisce lo stato corrente del middleware.</span><span class="sxs-lookup"><span data-stu-id="e4f83-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="e4f83-159">Se il middleware è abilitato, la richiesta restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="e4f83-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="e4f83-160">Se il middleware è disabilitato, non viene ricevuta alcuna risposta.</span><span class="sxs-lookup"><span data-stu-id="e4f83-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="e4f83-161">GET /failing?enable</span><span class="sxs-lookup"><span data-stu-id="e4f83-161">GET /failing?enable</span></span>

<span data-ttu-id="e4f83-162">Questa richiesta abilita il middleware.</span><span class="sxs-lookup"><span data-stu-id="e4f83-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="e4f83-163">GET /failing?disable</span><span class="sxs-lookup"><span data-stu-id="e4f83-163">GET /failing?disable</span></span>

<span data-ttu-id="e4f83-164">Questa richiesta disabilita il middleware.</span><span class="sxs-lookup"><span data-stu-id="e4f83-164">This request disables the middleware.</span></span>

<span data-ttu-id="e4f83-165">Ad esempio, quando l'applicazione è in esecuzione, è possibile abilitare il middleware eseguendo una richiesta usando l'URI seguente in qualsiasi browser.</span><span class="sxs-lookup"><span data-stu-id="e4f83-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="e4f83-166">Il microservizio degli ordini usa la porta 5103.</span><span class="sxs-lookup"><span data-stu-id="e4f83-166">Note that the ordering microservice uses port 5103.</span></span>

<span data-ttu-id="e4f83-167">http://localhost:5103/failing?enable</span><span class="sxs-lookup"><span data-stu-id="e4f83-167">http://localhost:5103/failing?enable</span></span>

<span data-ttu-id="e4f83-168">È quindi possibile controllare lo stato usando l'URI [http://localhost:5103/failing](http://localhost:5103/failing), come illustrato nella figura 10-4.</span><span class="sxs-lookup"><span data-stu-id="e4f83-168">You can then check the status using the URI [http://localhost:5103/failing](http://localhost:5103/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="e4f83-169">**Figura 10-4**.</span><span class="sxs-lookup"><span data-stu-id="e4f83-169">**Figure 10-4**.</span></span> <span data-ttu-id="e4f83-170">Verifica dello stato di errore del middleware ASP.NET. In questo caso, è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="e4f83-170">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="e4f83-171">A questo punto, il microservizio Basket risponde con il codice di stato 500 ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="e4f83-171">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="e4f83-172">Quando il middleware è in esecuzione, è possibile provare a effettuare un ordine dall'applicazione Web MVC.</span><span class="sxs-lookup"><span data-stu-id="e4f83-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="e4f83-173">Le richieste non riescono, quindi il circuito viene aperto.</span><span class="sxs-lookup"><span data-stu-id="e4f83-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="e4f83-174">Nell'esempio seguente si vede che l'applicazione Web MVC ha un blocco catch nella logica per l'immissione di un ordine.</span><span class="sxs-lookup"><span data-stu-id="e4f83-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="e4f83-175">Se il codice rileva un'eccezione di circuito aperto, verrà visualizzato un messaggio descrittivo che comunica all'utente di attendere.</span><span class="sxs-lookup"><span data-stu-id="e4f83-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            //… Other code
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode                 
            HandleBrokenCircuitException();
        }
        return View();
    }       

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

<span data-ttu-id="e4f83-176">Ecco un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="e4f83-176">Here’s a summary.</span></span> <span data-ttu-id="e4f83-177">I criteri di ripetizione provano più volte a eseguire la richiesta HTTP e ottengono errori HTTP.</span><span class="sxs-lookup"><span data-stu-id="e4f83-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="e4f83-178">Quando il numero di tentativi raggiunge il valore massimo impostato per i criteri dell'interruttore di circuito (in questo caso, 5), l'applicazione genera un'eccezione BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="e4f83-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="e4f83-179">Il risultato è un messaggio descrittivo, come illustrato nella figura 10-5.</span><span class="sxs-lookup"><span data-stu-id="e4f83-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="e4f83-180">**Figura 10-5**.</span><span class="sxs-lookup"><span data-stu-id="e4f83-180">**Figure 10-5**.</span></span> <span data-ttu-id="e4f83-181">Interruttore di circuito che restituisce un errore nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="e4f83-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="e4f83-182">È possibile implementare una logica diversa per specificare quando aprire il circuito.</span><span class="sxs-lookup"><span data-stu-id="e4f83-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="e4f83-183">In alternativa, si può provare a eseguire una richiesta HTTP in un microservizio back-end diverso, se è presente un centro dati di fallback o un sistema back-end ridondante.</span><span class="sxs-lookup"><span data-stu-id="e4f83-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="e4f83-184">Infine, un'altra possibilità per i criteri dell'interruttore di circuito prevede l'uso di Isolate, che forza l'apertura e mantiene aperto il circuito, e di Reset, che lo chiude nuovamente.</span><span class="sxs-lookup"><span data-stu-id="e4f83-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="e4f83-185">È possibile usarli per creare un endpoint HTTP di utilità che richiama Isolate e Reset direttamente nei criteri.</span><span class="sxs-lookup"><span data-stu-id="e4f83-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="e4f83-186">Questo endpoint HTTP può essere anche usato, se adeguatamente protetto, nell'ambiente di produzione per isolare temporaneamente un sistema downstream, ad esempio quando si vuole eseguire l'aggiornamento di tale sistema.</span><span class="sxs-lookup"><span data-stu-id="e4f83-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="e4f83-187">In alternativa, si può attivare il circuito manualmente per proteggere un sistema downstream che si sospetta essere in stato di errore.</span><span class="sxs-lookup"><span data-stu-id="e4f83-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="e4f83-188">Aggiunta di una strategia di instabilità ai criteri di ripetizione</span><span class="sxs-lookup"><span data-stu-id="e4f83-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="e4f83-189">I normali criteri di ripetizione possono influire sul sistema quando scalabilità e concorrenza sono elevate e sono presenti molti conflitti.</span><span class="sxs-lookup"><span data-stu-id="e4f83-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="e4f83-190">Per risolvere i picchi di tentativi simili provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità all'algoritmo o ai criteri di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="e4f83-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="e4f83-191">Ciò può migliorare le prestazioni complessive del sistema end-to-end grazie all'aggiunta di casualità nel backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="e4f83-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="e4f83-192">Permette di diluire i picchi quando si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="e4f83-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="e4f83-193">Quando si usa Polly, il codice per implementare l'instabilità potrebbe somigliare a quello nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e4f83-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="e4f83-194">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e4f83-194">Additional resources</span></span>

-   <span data-ttu-id="e4f83-195">**Schema Retry**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="e4f83-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="e4f83-196">**Resilienza della connessione** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="e4f83-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="e4f83-197">**Polly** (libreria .NET con funzionalità di resilienza e di gestione degli errori temporanei) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="e4f83-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="e4f83-198">**Schema Circuit Breaker**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="e4f83-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="e4f83-199">**Marc Brooker. Jitter: Making Things Better With Randomness (Instabilità: usare la casualità per ottimizzare le procedure)** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="e4f83-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e4f83-200">[Indietro] (implement-http-call-retries-exponential-backoff-polly.md) [Avanti] (monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="e4f83-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
