---
title: Implementazione del modello di interruttore
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione del modello di interruttore
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2a629e25a7565aaba156f68cf06d9a24b6c2b8b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="c4a73-104">Implementazione del modello di interruttore</span><span class="sxs-lookup"><span data-stu-id="c4a73-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="c4a73-105">Come notato in precedenza, è necessario gestire gli errori che potrebbero richiedere una quantità di tempo per il recupero, come può verificarsi quando si tenta di connettersi a una risorsa o un servizio remoto variabile.</span><span class="sxs-lookup"><span data-stu-id="c4a73-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="c4a73-106">La gestione di questo tipo di errore, è possibile migliorare la stabilità e la flessibilità di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c4a73-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="c4a73-107">In un ambiente distribuito, le chiamate alle risorse remote e ai servizi può non riuscire a causa di errori temporanei, ad esempio connessioni di rete lente e i timeout, o se le risorse vengono rallentare o sono temporaneamente non disponibile.</span><span class="sxs-lookup"><span data-stu-id="c4a73-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="c4a73-108">Questi errori in genere correggere autonomamente dopo un breve periodo di tempo e un'applicazione cloud affidabile deve essere preparata per gestirli utilizzando una strategia simile il criterio di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="c4a73-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="c4a73-109">Tuttavia, può anche essere situazioni in cui a causa di eventi imprevisti che potrebbero richiedere molto più tempo per risolvere gli errori.</span><span class="sxs-lookup"><span data-stu-id="c4a73-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="c4a73-110">Questi errori possono variare in base alla gravità da una perdita parziale di connettività per l'errore completo di un servizio.</span><span class="sxs-lookup"><span data-stu-id="c4a73-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="c4a73-111">In questi casi, potrebbe essere inutile per un'applicazione continuamente ripetere un'operazione che è improbabile che venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="c4a73-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="c4a73-112">Al contrario, l'applicazione deve essere codificato per accettare che l'operazione non è riuscita e gestire l'errore, di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="c4a73-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="c4a73-113">Il modello di interruttore ha uno scopo diverso del modello di tentativi.</span><span class="sxs-lookup"><span data-stu-id="c4a73-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="c4a73-114">Il criterio di ripetizione consente a un'applicazione ripetere un'operazione nella previsione che l'operazione verrà infine completata.</span><span class="sxs-lookup"><span data-stu-id="c4a73-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="c4a73-115">Il modello di interruttore impedisce un'applicazione eseguendo un'operazione che potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="c4a73-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="c4a73-116">Un'applicazione è possibile combinare questi due modelli utilizzando il modello di tentativi per richiamare un'operazione tramite un interruttore.</span><span class="sxs-lookup"><span data-stu-id="c4a73-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="c4a73-117">Tuttavia, la logica di tentativi deve essere sensibile alle eventuali eccezioni restituite dall'interruttore e deve essere abbandonato tentativi se l'interruttore indica che un errore non è temporaneo.</span><span class="sxs-lookup"><span data-stu-id="c4a73-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="c4a73-118">Implementazione di un modello di interruttore con Polly</span><span class="sxs-lookup"><span data-stu-id="c4a73-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="c4a73-119">Come quando si implementa tentativi, l'approccio consigliato per gli interruttori di sfruttare le librerie .NET si basa sulla collaudata come Polly.</span><span class="sxs-lookup"><span data-stu-id="c4a73-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="c4a73-120">L'applicazione eShopOnContainers utilizza i criteri di Polly interruttore quando si implementa tentativi HTTP.</span><span class="sxs-lookup"><span data-stu-id="c4a73-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="c4a73-121">In realtà, l'applicazione applica entrambi i criteri per la classe di utilità ResilientHttpClient.</span><span class="sxs-lookup"><span data-stu-id="c4a73-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="c4a73-122">Quando si usa un oggetto di tipo ResilientHttpClient per le richieste HTTP (da eShopOnContainers), si applicano entrambe tali criteri, ma è possibile aggiungere altri criteri, troppo.</span><span class="sxs-lookup"><span data-stu-id="c4a73-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="c4a73-123">L'aggiunta sola per il codice utilizzato per i tentativi di chiamata HTTP è il codice aggiungere il criterio interruttore all'elenco di criteri da usare, come illustrato alla fine di codice riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c4a73-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="c4a73-124">Il codice aggiunge un criterio per il wrapper HTTP.</span><span class="sxs-lookup"><span data-stu-id="c4a73-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="c4a73-125">Che criteri definiscono un interruttore che viene visualizzata quando il codice rileva il numero di eccezioni consecutivi (eccezioni in una riga), specificato come passato nel parametro exceptionsAllowedBeforeBreaking (in questo caso, 5).</span><span class="sxs-lookup"><span data-stu-id="c4a73-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="c4a73-126">Una volta aperto il circuito, le richieste HTTP non funzionano, ma viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c4a73-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="c4a73-127">Circuito va inoltre usata per reindirizzare le richieste a un'infrastruttura di fallback, se si potrebbe presentare problemi in una determinata risorsa che viene distribuito in un ambiente diverso rispetto all'applicazione client o servizio che esegue la chiamata HTTP.</span><span class="sxs-lookup"><span data-stu-id="c4a73-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="c4a73-128">In questo modo, se si verifica un'interruzione nel Data Center che influisce solo il microservizi back-end, ma non le applicazioni client, le applicazioni client possono reindirizzare a servizi di fallback.</span><span class="sxs-lookup"><span data-stu-id="c4a73-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="c4a73-129">Un nuovo criterio per automatizzare questa operazione prevede Polly [criteri di failover](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span><span class="sxs-lookup"><span data-stu-id="c4a73-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="c4a73-130">Naturalmente, tutte queste funzionalità sono casi in cui si sta gestendo il failover da all'interno del codice .NET, anziché viene gestita automaticamente da Azure, con la trasparenza dei percorsi.</span><span class="sxs-lookup"><span data-stu-id="c4a73-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="c4a73-131">Utilizzo della classe di utilità ResilientHttpClient da eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="c4a73-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="c4a73-132">Utilizzare la classe di utilità ResilientHttpClient in modo analogo a come si utilizza la classe .NET HttpClient.</span><span class="sxs-lookup"><span data-stu-id="c4a73-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="c4a73-133">Nell'esempio seguente dall'applicazione web MVC eShopOnContainers (OrderingService classe agent utilizzata da OrderController), viene inserito l'oggetto ResilientHttpClient tramite il parametro httpClient del costruttore.</span><span class="sxs-lookup"><span data-stu-id="c4a73-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="c4a73-134">L'oggetto viene quindi utilizzato per eseguire richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="c4a73-134">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="c4a73-135">Ogni volta che il \_viene utilizzato l'oggetto membro apiClient, utilizza internamente la classe wrapper con Polly policiesؙ: i criteri di ripetizione, il criterio interruttore e altri criteri che è possibile applicare dalla raccolta di criteri Polly.</span><span class="sxs-lookup"><span data-stu-id="c4a73-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="c4a73-136">Test di nuovi tentativi in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="c4a73-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="c4a73-137">Ogni volta che si avvia la soluzione eShopOnContainers in un host Docker, è necessario avviare più contenitori.</span><span class="sxs-lookup"><span data-stu-id="c4a73-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="c4a73-138">Alcuni dei contenitori sono più lenti per l'avvio e l'inizializzazione, ad esempio il contenitore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c4a73-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="c4a73-139">Questo vale in particolare la prima volta che si distribuisce l'applicazione eShopOnContainers in Docker, perché è necessario impostare le immagini e il database.</span><span class="sxs-lookup"><span data-stu-id="c4a73-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="c4a73-140">Il fatto che alcuni contenitori di avviare più lenta rispetto ad altri utenti può causare il resto dei servizi inizialmente generare eccezioni HTTP, anche se si impostano le dipendenze tra i contenitori nella composizione docker livello, come illustrato nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="c4a73-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="c4a73-141">Quelli docker-creare dipendenze tra i contenitori sono solo a livello di processo.</span><span class="sxs-lookup"><span data-stu-id="c4a73-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="c4a73-142">Processo del punto di ingresso del contenitore potrebbe essere avviato, ma SQL Server potrebbe non essere pronto per le query.</span><span class="sxs-lookup"><span data-stu-id="c4a73-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="c4a73-143">Il risultato può essere una catena di errori e l'applicazione può ottenere un'eccezione durante il tentativo di utilizzare tale contenitore specifico.</span><span class="sxs-lookup"><span data-stu-id="c4a73-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="c4a73-144">Quando l'applicazione viene distribuita nel cloud, è possibile visualizzare questo tipo di errore all'avvio.</span><span class="sxs-lookup"><span data-stu-id="c4a73-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="c4a73-145">In tal caso, orchestrators potrebbe essere spostamento contenitori da un nodo o da macchina virtuale a un altro (che è, avvio di nuove istanze) quando il numero di contenitori di bilanciamento tra i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="c4a73-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="c4a73-146">Il modo eShopOnContainers per risolvere questo problema è utilizzando il modello di tentativi che è illustrati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c4a73-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="c4a73-147">È inoltre perché, quando si avvia la soluzione, è possibile ottenere le tracce di log o avvisi simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c4a73-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="c4a73-148">"**Tentativo 1 implementato con RetryPolicy di Polly**, a causa di: System.Net.Http.HttpRequestException: si è verificato un errore durante l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="c4a73-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="c4a73-149"> ---&gt;System.Net.Http.CurlException: Impossibile connettersi al server\\n in System.Net.Http.CurlHandler.ThrowIfCURLEError (errore CURLcode)\\n in \[... \].</span><span class="sxs-lookup"><span data-stu-id="c4a73-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="c4a73-150">Test dell'interruttore in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="c4a73-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="c4a73-151">Esistono diversi modi, è possibile aprire il circuito ed eseguirne il test con eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c4a73-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="c4a73-152">È possibile ridurre il numero consentito di tentativi su 1 nei criteri di interruttore e ridistribuire l'intera soluzione in Docker.</span><span class="sxs-lookup"><span data-stu-id="c4a73-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="c4a73-153">Con un nuovo tentativo singolo, è probabile che una richiesta HTTP avrà esito negativo durante la distribuzione, verrà aperto l'interruttore e si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="c4a73-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="c4a73-154">Un'altra opzione consiste nell'utilizzare middleware personalizzato che viene implementato in microservizio l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="c4a73-154">Another option is to use custom middleware that is implemented in the ordering microservice.</span></span> <span data-ttu-id="c4a73-155">Quando è abilitato questo middleware, intercetta tutte le richieste HTTP e lo restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="c4a73-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="c4a73-156">È possibile abilitare il middleware tramite una richiesta GET ha generato l'errore URI, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c4a73-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="c4a73-157">OTTENERE/non superati</span><span class="sxs-lookup"><span data-stu-id="c4a73-157">GET /failing</span></span>

<span data-ttu-id="c4a73-158">Questa richiesta restituisce lo stato corrente del middleware.</span><span class="sxs-lookup"><span data-stu-id="c4a73-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="c4a73-159">Se il middleware è abilitato, la richiesta restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="c4a73-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="c4a73-160">Se il middleware è disabilitato, non è stata ricevuta alcuna risposta.</span><span class="sxs-lookup"><span data-stu-id="c4a73-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="c4a73-161">OTTENERE/non superati? abilitare</span><span class="sxs-lookup"><span data-stu-id="c4a73-161">GET /failing?enable</span></span>

<span data-ttu-id="c4a73-162">Questa richiesta consente il middleware.</span><span class="sxs-lookup"><span data-stu-id="c4a73-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="c4a73-163">OTTENERE/non superati? disabilitare</span><span class="sxs-lookup"><span data-stu-id="c4a73-163">GET /failing?disable</span></span>

<span data-ttu-id="c4a73-164">Questa richiesta disabilita il middleware.</span><span class="sxs-lookup"><span data-stu-id="c4a73-164">This request disables the middleware.</span></span>

<span data-ttu-id="c4a73-165">Ad esempio, dopo l'applicazione è in esecuzione, è possibile abilitare il middleware tramite una richiesta utilizzando il seguente URI in qualsiasi browser.</span><span class="sxs-lookup"><span data-stu-id="c4a73-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="c4a73-166">Si noti che l'ordinamento microservizio utilizza la porta 5102.</span><span class="sxs-lookup"><span data-stu-id="c4a73-166">Note that the ordering microservice uses port 5102.</span></span>

<span data-ttu-id="c4a73-167">http://localhost:5102 / non superati? abilitare</span><span class="sxs-lookup"><span data-stu-id="c4a73-167">http://localhost:5102/failing?enable</span></span>

<span data-ttu-id="c4a73-168">È quindi possibile controllare lo stato usando l'URI [http://localhost:5102 / non superati](http://localhost:5100/failing), come illustrato nella figura 10-4.</span><span class="sxs-lookup"><span data-stu-id="c4a73-168">You can then check the status using the URI [http://localhost:5102/failing](http://localhost:5100/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="c4a73-169">**Nella figura 10-4**.</span><span class="sxs-lookup"><span data-stu-id="c4a73-169">**Figure 10-4**.</span></span> <span data-ttu-id="c4a73-170">Simulazione di un errore con il middleware ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c4a73-170">Simulating a failure with ASP.NET middleware</span></span>

<span data-ttu-id="c4a73-171">A questo punto, risponde microservizio ordinamento con codice di stato 500 ogni volta che chiamano richiamano.</span><span class="sxs-lookup"><span data-stu-id="c4a73-171">At this point, the ordering microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="c4a73-172">Quando il middleware è in esecuzione, è possibile provare a effettuare un ordine dall'applicazione web MVC.</span><span class="sxs-lookup"><span data-stu-id="c4a73-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="c4a73-173">Poiché le richieste non riesce, verrà aperto il circuito.</span><span class="sxs-lookup"><span data-stu-id="c4a73-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="c4a73-174">Nell'esempio seguente, è possibile visualizzare l'applicazione web MVC di un blocco catch bloccare nella logica dell'immissione di un ordine.</span><span class="sxs-lookup"><span data-stu-id="c4a73-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="c4a73-175">Se il codice rileva un'eccezione di open circuito, verrà visualizzato all'utente un messaggio descrittivo informa di attesa.</span><span class="sxs-lookup"><span data-stu-id="c4a73-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
[HttpPost]
public async Task<IActionResult> Create(Order model, string action)
{
    try
    {
        if (ModelState.IsValid)
        {
            var user = _appUserParser.Parse(HttpContext.User);
            await _orderSvc.CreateOrder(model);
            //Redirect to historic list.
            return RedirectToAction("Index");
        }
    }
    catch(BrokenCircuitException ex)
    {
        ModelState.AddModelError("Error",
            "It was not possible to create a new order, please try later on");
    }
    return View(model);
}
```

<span data-ttu-id="c4a73-176">Di seguito è riportato un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="c4a73-176">Here’s a summary.</span></span> <span data-ttu-id="c4a73-177">I criteri di ripetizione tenta più volte per la richiesta HTTP e ottiene gli errori HTTP.</span><span class="sxs-lookup"><span data-stu-id="c4a73-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="c4a73-178">Quando il numero di tentativi raggiunge il massimo valore impostato per il criterio interruttore (in questo caso, 5), l'applicazione genera un BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="c4a73-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="c4a73-179">Il risultato è un messaggio descrittivo, come illustrato nella figura 10-5.</span><span class="sxs-lookup"><span data-stu-id="c4a73-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="c4a73-180">**Nella figura 10-5**.</span><span class="sxs-lookup"><span data-stu-id="c4a73-180">**Figure 10-5**.</span></span> <span data-ttu-id="c4a73-181">Interruttore restituendo un errore nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c4a73-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="c4a73-182">È possibile implementare una logica diversa per i casi in cui aprire il circuito.</span><span class="sxs-lookup"><span data-stu-id="c4a73-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="c4a73-183">O se è presente un Data Center di fallback o ridondante sistema back-end, è possibile provare una richiesta HTTP in un diverso microservizio back-end.</span><span class="sxs-lookup"><span data-stu-id="c4a73-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="c4a73-184">Infine, un'altra possibilità per il CircuitBreakerPolicy consiste nell'utilizzare isolano (che forza aperto e mantiene aperta del circuito) e la reimpostazione (che chiude nuovamente).</span><span class="sxs-lookup"><span data-stu-id="c4a73-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="c4a73-185">È possibile utilizzarli per creare un endpoint HTTP di utilità che richiama isolano e reimpostare direttamente al criterio.</span><span class="sxs-lookup"><span data-stu-id="c4a73-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="c4a73-186">Tale endpoint HTTP può essere utilizzato anche adeguatamente protetto, nell'ambiente di produzione per isolare temporaneamente un sistema a valle, ad esempio quando si desidera eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c4a73-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="c4a73-187">O Impossibile attivarsi il circuito manualmente per proteggere un sistema a valle che sospetti è possibile generare un errore.</span><span class="sxs-lookup"><span data-stu-id="c4a73-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="c4a73-188">Aggiunta di una strategia di instabilità per i criteri di ripetizione</span><span class="sxs-lookup"><span data-stu-id="c4a73-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="c4a73-189">Criteri di ripetizione regolari possono influire su sistema nel caso di scalabilità e concorrenza elevata e con elevata contesa.</span><span class="sxs-lookup"><span data-stu-id="c4a73-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="c4a73-190">Per risolvere i picchi di tentativi simile provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità per l'algoritmo/criteri di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="c4a73-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="c4a73-191">Ciò può migliorare le prestazioni complessive del sistema end-to-end mediante l'aggiunta di casualità di backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="c4a73-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="c4a73-192">Consistenti i picchi di problemi.</span><span class="sxs-lookup"><span data-stu-id="c4a73-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="c4a73-193">Quando si utilizza Polly, codice per implementare l'instabilità potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c4a73-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="c4a73-194">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c4a73-194">Additional resources</span></span>

-   <span data-ttu-id="c4a73-195">**Ripetere modello**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="c4a73-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="c4a73-196">**Resilienza di connessione** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="c4a73-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="c4a73-197">**Polly** (resilienza .NET e la gestione di errori temporanei libreria) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="c4a73-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="c4a73-198">**Modello di interruttore**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="c4a73-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="c4a73-199">**Marc Brooker. Instabilità: Eseguire operazioni meglio con casualità** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="c4a73-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c4a73-200">[Precedente] [Avanti] (app-monitor-health.md) (implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="c4a73-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
