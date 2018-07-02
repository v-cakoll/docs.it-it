---
title: Implementazione dello schema Circuit Breaker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dello schema Circuit Breaker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.openlocfilehash: 2c89992c4c60ca7f1085050e6fed4922ecd4d8cc
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106129"
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="9e7d4-103">Implementazione dello schema Circuit Breaker</span><span class="sxs-lookup"><span data-stu-id="9e7d4-103">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="9e7d4-104">Come notato in precedenza, è necessario gestire gli errori che potrebbero richiedere una quantità di tempo variabile per il ripristino, come accade quando si prova a connettersi a una risorsa o a un servizio remoto.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="9e7d4-105">La gestione di questo tipo di errore può migliorare la stabilità e la resilienza di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="9e7d4-106">In un ambiente distribuito, le chiamate a servizi e risorse remote può non riuscire a causa di errori temporanei, ad esempio connessioni di rete lente e timeout oppure se le risorse vengono rallentate o sono temporaneamente non disponibili.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="9e7d4-107">Questi errori in genere si correggono autonomamente dopo un breve periodo di tempo e un'applicazione cloud affidabile deve essere preparata a gestirli usando una strategia simile allo schema Retry.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="9e7d4-108">Tuttavia, in alcune situazioni gli errori sono dovuti a eventi imprevisti, la cui risoluzione potrebbe richiedere molto più tempo.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="9e7d4-109">La gravità di questi errori può variare, da una perdita parziale di connettività a un errore generale di un servizio.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="9e7d4-110">In questi casi, è inutile continuare a ripetere in un'applicazione un'operazione che è improbabile venga eseguita.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-110">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="9e7d4-111">È consigliabile invece codificare l'applicazione in modo che accetti l'errore dell'operazione e lo gestisca di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="9e7d4-112">Lo schema Circuit Breaker ha uno scopo diverso rispetto allo schema Retry.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-112">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="9e7d4-113">Lo schema Retry consente a un'applicazione di ripetere un'operazione che si prevede possa essere completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-113">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="9e7d4-114">Lo schema Circuit Breaker impedisce a un'applicazione di eseguire un'operazione che potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-114">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="9e7d4-115">Un'applicazione può combinare questi due schemi, usando lo schema Retry per richiamare un'operazione con un interruttore di circuito.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-115">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="9e7d4-116">Tuttavia, la logica di ripetizione deve essere sensibile alle eventuali eccezioni restituite dall'interruttore di circuito e deve sospendere i tentativi se l'interruttore di circuito indica che un errore non è temporaneo.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-116">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="9e7d4-117">Implementazione dello schema Circuit Breaker con Polly</span><span class="sxs-lookup"><span data-stu-id="9e7d4-117">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="9e7d4-118">Come accade quando si implementano i tentativi, l'approccio consigliato per gli interruttori di circuito prevede l'uso di librerie .NET collaudate come Polly.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-118">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="9e7d4-119">L'applicazione eShopOnContainers usa i criteri dell'interruttore di circuito di Polly quando si implementano tentativi HTTP.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-119">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="9e7d4-120">In realtà, l'applicazione applica entrambi i criteri alla classe di utilità ResilientHttpClient.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-120">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="9e7d4-121">Quando si usa un oggetto di tipo ResilientHttpClient per le richieste HTTP da eShopOnContainers, vengono applicati entrambi i criteri, ma è possibile aggiungerne anche altri.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-121">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="9e7d4-122">In questo scenario, l'unica aggiunta al codice usato per i tentativi di chiamata HTTP è il codice in cui viene aggiunto il criterio dell'interruttore di circuito all'elenco di criteri da usare, come illustrato alla fine di codice riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9e7d4-122">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="9e7d4-123">Il codice aggiunge un criterio al wrapper HTTP.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-123">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="9e7d4-124">Questi criteri definiscono un interruttore di circuito che viene aperto quando il codice rileva il numero indicato di eccezioni consecutive (eccezioni in una riga), specificato nel parametro exceptionsAllowedBeforeBreaking (in questo caso, 5).</span><span class="sxs-lookup"><span data-stu-id="9e7d4-124">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="9e7d4-125">Quando il circuito è aperto, le richieste HTTP non funzionano, ma viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-125">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="9e7d4-126">Gli interruttori di circuito devono essere usati anche per reindirizzare le richieste a un'infrastruttura di fallback nel caso di problemi in una determinata risorsa che viene distribuita in un ambiente diverso rispetto all'applicazione client o al servizio che esegue la chiamata HTTP.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-126">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="9e7d4-127">In questo modo, se si verifica un'interruzione nel centro dati che influisce solo sui microservizi back-end, ma non sulle applicazioni client, queste applicazioni possono essere reindirizzate ai servizi di fallback.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-127">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="9e7d4-128">È il corso la pianificazione di un nuovo criterio in Polly che consenta di automatizzare questo scenario per i [criteri di failover](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).</span><span class="sxs-lookup"><span data-stu-id="9e7d4-128">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="9e7d4-129">Naturalmente, tutte queste funzionalità riguardano casi in cui il failover viene gestito internamente nel codice .NET, e non automaticamente da Azure, con la trasparenza dei percorsi.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-129">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="9e7d4-130">Uso della classe di utilità ResilientHttpClient da eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="9e7d4-130">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="9e7d4-131">La classe di utilità ResilientHttpClient viene usata in modo analogo alla classe .NET HttpClient.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-131">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="9e7d4-132">Nell'esempio seguente relativo all'applicazione Web MVC in eShopOnContainers, ossia la classe dell'agente OrderingService usata da OrderController, l'oggetto ResilientHttpClient viene inserito con il parametro httpClient del costruttore.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-132">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="9e7d4-133">L'oggetto viene quindi usato per eseguire le richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-133">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="9e7d4-134">Quando viene usato l'oggetto membro \_apiClient, al suo interno viene usata la classe wrapper con criteri di Polly: criteri di ripetizione, criteri dell'interruttore di circuito e altri criteri applicabili disponibili nella raccolta di Polly.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-134">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="9e7d4-135">Tentativi di test in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="9e7d4-135">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="9e7d4-136">Ogni volta che si avvia la soluzione eShopOnContainers in un host Docker, è necessario avviare più contenitori.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-136">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="9e7d4-137">Alcuni dei contenitori vengono avviati e inizializzati più lentamente, ad esempio il contenitore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-137">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="9e7d4-138">Questo vale in particolare la prima volta che si distribuisce l'applicazione eShopOnContainers in Docker, perché è necessario configurare le immagini e il database.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-138">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="9e7d4-139">Il fatto che alcuni contenitori vengano avviati più lentamente rispetto ad altri può causare la generazione iniziale di eccezioni HTTP negli altri servizi, anche se si impostano dipendenze tra i contenitori al livello Docker Compose, come illustrato nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-139">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="9e7d4-140">Le dipendenze Docker Compose tra i contenitori si trovano solo sul livello processo.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-140">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="9e7d4-141">Il processo del punto di ingresso del contenitore può essere avviato, ma SQL Server potrebbe non essere pronto per le query.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-141">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="9e7d4-142">Di conseguenza, possono essere visualizzati numerosi errori e può essere restituita un'eccezione all'applicazione quando prova a usare il contenitore specificato.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-142">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="9e7d4-143">Questo tipo di errore può essere visualizzato anche all'avvio quando l'applicazione viene distribuita nel cloud.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-143">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="9e7d4-144">In questo caso, è possibile che gli agenti di orchestrazione stiano spostando i contenitori da un nodo o da una macchina virtuale a un'altra (ovvero, stanno avviando nuove istanze) durante il bilanciamento del numero di contenitori tra i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-144">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="9e7d4-145">eShopOnContainers risolve il problema usando lo schema Retry illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-145">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="9e7d4-146">Questo approccio viene seguito anche perché, quando si avvia la soluzione, potrebbero essere visualizzate tracce di log o avvisi simili al seguente:</span><span class="sxs-lookup"><span data-stu-id="9e7d4-146">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="9e7d4-147">"**Tentativo 1 implementato con i criteri di ripetizione di Polly**, causato da: System.Net.Http.HttpRequestException: Si è verificato un errore durante l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-147">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="9e7d4-148"> ---&gt; System.Net.Http.CurlException: impossibile connettersi al server\\ in System.Net.Http.CurlHandler.ThrowIfCURLEError(errore CURLcode)\\ in \[...\].</span><span class="sxs-lookup"><span data-stu-id="9e7d4-148"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="9e7d4-149">Test dell'interruttore di circuito in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="9e7d4-149">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="9e7d4-150">Esistono diversi modi per aprire il circuito ed eseguirne il test con eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-150">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="9e7d4-151">Una possibilità consiste nel ridurre il numero consentito di tentativi a 1 nei criteri dell'interruttore di circuito e ridistribuire l'intera soluzione in Docker.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-151">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="9e7d4-152">Con un solo tentativo, è probabile che una richiesta HTTP non riuscirà durante la distribuzione, l'interruttore di circuito verrà aperto e verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-152">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="9e7d4-153">Un'altra opzione consiste nell'usare middleware personalizzato che viene implementato nel microservizio `Basket`.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-153">Another option is to use custom middleware that is implemented in the `Basket` microservice.</span></span> <span data-ttu-id="9e7d4-154">Quando il middleware è abilitato, intercetta tutte le richieste HTTP e restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-154">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="9e7d4-155">È possibile abilitare il middleware eseguendo una richiesta GET all'URI che ha generato l'errore, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9e7d4-155">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="9e7d4-156">GET /failing</span><span class="sxs-lookup"><span data-stu-id="9e7d4-156">GET /failing</span></span>

<span data-ttu-id="9e7d4-157">Questa richiesta restituisce lo stato corrente del middleware.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-157">This request returns the current state of the middleware.</span></span> <span data-ttu-id="9e7d4-158">Se il middleware è abilitato, la richiesta restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-158">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="9e7d4-159">Se il middleware è disabilitato, non viene ricevuta alcuna risposta.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-159">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="9e7d4-160">GET /failing?enable</span><span class="sxs-lookup"><span data-stu-id="9e7d4-160">GET /failing?enable</span></span>

<span data-ttu-id="9e7d4-161">Questa richiesta abilita il middleware.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-161">This request enables the middleware.</span></span>

-   <span data-ttu-id="9e7d4-162">GET /failing?disable</span><span class="sxs-lookup"><span data-stu-id="9e7d4-162">GET /failing?disable</span></span>

<span data-ttu-id="9e7d4-163">Questa richiesta disabilita il middleware.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-163">This request disables the middleware.</span></span>

<span data-ttu-id="9e7d4-164">Ad esempio, quando l'applicazione è in esecuzione, è possibile abilitare il middleware eseguendo una richiesta usando l'URI seguente in qualsiasi browser.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-164">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="9e7d4-165">Il microservizio degli ordini usa la porta 5103.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-165">Note that the ordering microservice uses port 5103.</span></span>

http://localhost:5103/failing?enable

<span data-ttu-id="9e7d4-166">È quindi possibile controllare lo stato usando l'URI [http://localhost:5103/failing](http://localhost:5103/failing), come illustrato nella figura 10-4.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-166">You can then check the status using the URI [http://localhost:5103/failing](http://localhost:5103/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="9e7d4-167">**Figura 10-4**.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-167">**Figure 10-4**.</span></span> <span data-ttu-id="9e7d4-168">Verifica dello stato di errore del middleware ASP.NET. In questo caso, è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-168">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="9e7d4-169">A questo punto, il microservizio Basket risponde con il codice di stato 500 ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-169">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="9e7d4-170">Quando il middleware è in esecuzione, è possibile provare a effettuare un ordine dall'applicazione Web MVC.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-170">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="9e7d4-171">Le richieste non riescono, quindi il circuito viene aperto.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-171">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="9e7d4-172">Nell'esempio seguente si vede che l'applicazione Web MVC ha un blocco catch nella logica per l'immissione di un ordine.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-172">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="9e7d4-173">Se il codice rileva un'eccezione di circuito aperto, verrà visualizzato un messaggio descrittivo che comunica all'utente di attendere.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-173">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

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

<span data-ttu-id="9e7d4-174">Ecco un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-174">Here’s a summary.</span></span> <span data-ttu-id="9e7d4-175">I criteri di ripetizione provano più volte a eseguire la richiesta HTTP e ottengono errori HTTP.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-175">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="9e7d4-176">Quando il numero di tentativi raggiunge il valore massimo impostato per i criteri dell'interruttore di circuito (in questo caso, 5), l'applicazione genera un'eccezione BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-176">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="9e7d4-177">Il risultato è un messaggio descrittivo, come illustrato nella figura 10-5.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-177">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="9e7d4-178">**Figura 10-5**.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-178">**Figure 10-5**.</span></span> <span data-ttu-id="9e7d4-179">Interruttore di circuito che restituisce un errore nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="9e7d4-179">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="9e7d4-180">È possibile implementare una logica diversa per specificare quando aprire il circuito.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-180">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="9e7d4-181">In alternativa, si può provare a eseguire una richiesta HTTP in un microservizio back-end diverso, se è presente un centro dati di fallback o un sistema back-end ridondante.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-181">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="9e7d4-182">Infine, un'altra possibilità per i criteri dell'interruttore di circuito prevede l'uso di Isolate, che forza l'apertura e mantiene aperto il circuito, e di Reset, che lo chiude nuovamente.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-182">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="9e7d4-183">È possibile usarli per creare un endpoint HTTP di utilità che richiama Isolate e Reset direttamente nei criteri.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-183">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="9e7d4-184">Questo endpoint HTTP può essere anche usato, se adeguatamente protetto, nell'ambiente di produzione per isolare temporaneamente un sistema downstream, ad esempio quando si vuole eseguire l'aggiornamento di tale sistema.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-184">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="9e7d4-185">In alternativa, si può attivare il circuito manualmente per proteggere un sistema downstream che si sospetta essere in stato di errore.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-185">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="9e7d4-186">Aggiunta di una strategia di instabilità ai criteri di ripetizione</span><span class="sxs-lookup"><span data-stu-id="9e7d4-186">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="9e7d4-187">I normali criteri di ripetizione possono influire sul sistema quando scalabilità e concorrenza sono elevate e sono presenti molti conflitti.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-187">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="9e7d4-188">Per risolvere i picchi di tentativi simili provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità all'algoritmo o ai criteri di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-188">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="9e7d4-189">Ciò può migliorare le prestazioni complessive del sistema end-to-end grazie all'aggiunta di casualità nel backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-189">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="9e7d4-190">Permette di diluire i picchi quando si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="9e7d4-190">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="9e7d4-191">Quando si usa Polly, il codice per implementare l'instabilità potrebbe somigliare a quello nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9e7d4-191">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="9e7d4-192">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9e7d4-192">Additional resources</span></span>

-   <span data-ttu-id="9e7d4-193">**Retry pattern**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry) (Modello di ripetizione)</span><span class="sxs-lookup"><span data-stu-id="9e7d4-193">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="9e7d4-194">**Connection Resiliency** (Resilienza della connessione) (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="9e7d4-194">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="9e7d4-195">**Polly** (libreria .NET con funzionalità di resilienza e di gestione degli errori temporanei) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="9e7d4-195">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="9e7d4-196">**Schema Circuit Breaker**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="9e7d4-196">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="9e7d4-197">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html(Instabilità: eseguire operazioni meglio con la casualità)</span><span class="sxs-lookup"><span data-stu-id="9e7d4-197">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="9e7d4-198">[Precedente](implement-http-call-retries-exponential-backoff-polly.md)
[Successivo](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="9e7d4-198">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>
