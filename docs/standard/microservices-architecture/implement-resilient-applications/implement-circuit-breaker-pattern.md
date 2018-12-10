---
title: Implementazione dello schema Circuit Breaker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dello schema Circuit Breaker come sistema complementare ai tentativi HTTP
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 07/03/2018
ms.openlocfilehash: 08467184f40611888a05c3aa1fa4783b73c6b8ee
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147262"
---
# <a name="implement-the-circuit-breaker-pattern"></a><span data-ttu-id="007dc-103">Implementazione dello schema Circuit Breaker</span><span class="sxs-lookup"><span data-stu-id="007dc-103">Implement the Circuit Breaker pattern</span></span>

<span data-ttu-id="007dc-104">Come notato in precedenza, è necessario gestire gli errori che potrebbero richiedere una quantità di tempo variabile per il ripristino, come accade quando si prova a connettersi a una risorsa o a un servizio remoto.</span><span class="sxs-lookup"><span data-stu-id="007dc-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="007dc-105">La gestione di questo tipo di errore può migliorare la stabilità e la resilienza di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="007dc-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="007dc-106">In un ambiente distribuito, le chiamate a servizi e risorse remote possono non riuscire a causa di errori temporanei, ad esempio connessioni di rete lente e timeout oppure se le risorse rispondono lentamente o sono temporaneamente non disponibili.</span><span class="sxs-lookup"><span data-stu-id="007dc-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are responding slowly or are temporarily unavailable.</span></span> <span data-ttu-id="007dc-107">Questi errori in genere si correggono autonomamente dopo un breve periodo di tempo e un'applicazione cloud affidabile deve essere preparata a gestirli usando una strategia simile allo "schema Retry".</span><span class="sxs-lookup"><span data-stu-id="007dc-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the "Retry pattern".</span></span> 

<span data-ttu-id="007dc-108">Tuttavia, in alcune situazioni gli errori sono dovuti a eventi imprevisti, la cui risoluzione potrebbe richiedere molto più tempo.</span><span class="sxs-lookup"><span data-stu-id="007dc-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="007dc-109">La gravità di questi errori può variare, da una perdita parziale di connettività a un errore generale di un servizio.</span><span class="sxs-lookup"><span data-stu-id="007dc-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="007dc-110">In questi casi, è inutile continuare a ripetere in un'applicazione un'operazione che è improbabile venga eseguita.</span><span class="sxs-lookup"><span data-stu-id="007dc-110">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> 

<span data-ttu-id="007dc-111">È consigliabile invece codificare l'applicazione in modo che accetti l'errore dell'operazione e lo gestisca di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="007dc-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="007dc-112">L'uso improprio di tentativi HTTP potrebbe causare la creazione un attacco Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) nel proprio software.</span><span class="sxs-lookup"><span data-stu-id="007dc-112">Using Http retries carelessly could result in creating a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack within your own software.</span></span> <span data-ttu-id="007dc-113">Quando un microservizio non funziona o è lento, più client potrebbero ripetere più volte le richieste non riuscite.</span><span class="sxs-lookup"><span data-stu-id="007dc-113">As a microservice fails or performs slowly, multiple clients might repeatedly retry failed requests.</span></span> <span data-ttu-id="007dc-114">Si crea così un rischio pericoloso di un aumento esponenziale del traffico destinato al servizio non funzionante.</span><span class="sxs-lookup"><span data-stu-id="007dc-114">That creates a dangerous risk of exponentially increasing traffic targeted at the failing service.</span></span>

<span data-ttu-id="007dc-115">È pertanto necessario un tipo di barriera di difesa in modo che le richieste eccessive vengano interrotte quando non vale la pena continuare a provare.</span><span class="sxs-lookup"><span data-stu-id="007dc-115">Therefore, you need some kind of defense barrier so that excessive requests stop when it is not worth keeping trying.</span></span> <span data-ttu-id="007dc-116">La barriera di difesa è proprio l'interruttore di circuito.</span><span class="sxs-lookup"><span data-stu-id="007dc-116">That defense barrier is precisely the circuit breaker.</span></span>

<span data-ttu-id="007dc-117">Lo schema Circuit Breaker ha uno scopo diverso rispetto allo "schema Retry".</span><span class="sxs-lookup"><span data-stu-id="007dc-117">The Circuit Breaker pattern has a different purpose than the "Retry pattern".</span></span> <span data-ttu-id="007dc-118">Lo "schema Retry" consente a un'applicazione di ripetere un'operazione che si prevede possa essere completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="007dc-118">The "Retry pattern" enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="007dc-119">Lo schema Circuit Breaker impedisce a un'applicazione di eseguire un'operazione che potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="007dc-119">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="007dc-120">Un'applicazione può combinare questi due modelli.</span><span class="sxs-lookup"><span data-stu-id="007dc-120">An application can combine these two patterns.</span></span> <span data-ttu-id="007dc-121">Tuttavia, la logica di ripetizione deve essere sensibile alle eventuali eccezioni restituite dall'interruttore di circuito e deve sospendere i tentativi se l'interruttore di circuito indica che un errore non è temporaneo.</span><span class="sxs-lookup"><span data-stu-id="007dc-121">However, the retry logic should be sensitive to any exception returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implement-circuit-breaker-pattern-with-httpclientfactory-and-polly"></a><span data-ttu-id="007dc-122">Implementare lo schema Circuit Breaker con HttpClientFactory e Polly</span><span class="sxs-lookup"><span data-stu-id="007dc-122">Implement Circuit Breaker pattern with HttpClientFactory and Polly</span></span>

<span data-ttu-id="007dc-123">Come accade quando si implementano i tentativi, l'approccio consigliato per gli interruttori di circuito prevede l'uso di librerie .NET collaudate come Polly e la sua integrazione nativa con HttpClientFactory.</span><span class="sxs-lookup"><span data-stu-id="007dc-123">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly and its native integration with HttpClientFactory.</span></span>

<span data-ttu-id="007dc-124">Aggiungere dei criteri dell'interruttore di circuito nella pipeline middleware in uscita HttpClientFactory è semplice come aggiungere un singolo segmento di codice incrementale a quello già presente quando si usa HttpClientFactory.</span><span class="sxs-lookup"><span data-stu-id="007dc-124">Adding a circuit breaker policy into your HttpClientFactory outgoing middleware pipeline is as simple as adding a single incremental piece of code to what you already have when using HttpClientFactory.</span></span>

<span data-ttu-id="007dc-125">In questo scenario l'unica aggiunta al codice usato per i tentativi di chiamata HTTP è il codice in cui viene aggiunto il criterio dell'interruttore di circuito all'elenco di criteri da usare, come illustrato nel codice incrementale seguente, parte del metodo ConfigureServices().</span><span class="sxs-lookup"><span data-stu-id="007dc-125">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown in the following incremental code, part of the ConfigureServices() method.</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to 5 minutes
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="007dc-126">Il metodo `AddPolicyHandler()` aggiunge i criteri agli oggetti HttpClient che verranno usati.</span><span class="sxs-lookup"><span data-stu-id="007dc-126">The `AddPolicyHandler()`method is what adds policies to the HttpClient objects you will use.</span></span> <span data-ttu-id="007dc-127">In questo caso vengono aggiunti dei criteri Polly, uno per ogni interruttore di circuito.</span><span class="sxs-lookup"><span data-stu-id="007dc-127">In this case, it is adding a Polly policy for a circuit breaker.</span></span>

<span data-ttu-id="007dc-128">Per avere un approccio più modulare, i criteri dell'interruttore di circuito vengono definiti in un metodo separato denominato GetCircuitBreakerPolicy(), come il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="007dc-128">In order to have a more modular approach, the Circuit Breaker Policy is defined in a separate method named GetCircuitBreakerPolicy(), as the following code.</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

<span data-ttu-id="007dc-129">Nell'esempio di codice precedente i criteri dell'interruttore di circuito sono configurati in modo da interrompere o aprire il circuito quando si verificano cinque errori consecutivi durante i nuovi tentativi di richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="007dc-129">In the code example above, the circuit breaker policy is configured so it breaks or opens the circuit when there have been five consecutive faults when retrying the Http requests.</span></span> <span data-ttu-id="007dc-130">In questo caso, il circuito verrà interrotto per 30 secondi: in questo intervallo di tempo, le chiamate verranno bloccate immediatamente dall'interruttore di circuito invece di essere effettivamente inserite.</span><span class="sxs-lookup"><span data-stu-id="007dc-130">When that happens, the circuit will break for 30 seconds: in that period, calls will be failed immediately by the circuit-breaker rather than actually be placed.</span></span>  <span data-ttu-id="007dc-131">Il criterio interpreta automaticamente le [eccezioni e i codici di stato HTTP rilevanti](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1#handle-transient-faults) come errori.</span><span class="sxs-lookup"><span data-stu-id="007dc-131">The policy automatically interprets [relevant exceptions and HTTP status codes](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1#handle-transient-faults) as faults.</span></span>  

<span data-ttu-id="007dc-132">Gli interruttori di circuito devono essere usati anche per reindirizzare le richieste a un'infrastruttura di fallback nel caso di problemi in una determinata risorsa che viene distribuita in un ambiente diverso rispetto all'applicazione client o al servizio che esegue la chiamata HTTP.</span><span class="sxs-lookup"><span data-stu-id="007dc-132">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you had issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="007dc-133">In questo modo, se si verifica un'interruzione nel centro dati che influisce solo sui microservizi back-end, ma non sulle applicazioni client, queste applicazioni possono essere reindirizzate ai servizi di fallback.</span><span class="sxs-lookup"><span data-stu-id="007dc-133">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="007dc-134">È il corso la pianificazione di un nuovo criterio in Polly che consenta di automatizzare questo scenario per i [criteri di failover](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).</span><span class="sxs-lookup"><span data-stu-id="007dc-134">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span> 

<span data-ttu-id="007dc-135">Tutte queste funzionalità riguardano casi in cui il failover viene gestito internamente nel codice .NET, e non automaticamente da Azure, con la trasparenza dei percorsi.</span><span class="sxs-lookup"><span data-stu-id="007dc-135">All those features are for cases where you're managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span> 

<span data-ttu-id="007dc-136">Dal punto di vista dell'utilizzo, quando si usa HttpClient non occorre aggiungere nulla di nuovo, perché il codice è lo stesso di quando si usa HttpClient con HttpClientFactory, come mostrato nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="007dc-136">From a usage point of view, when using HttpClient, there’s no need to add anything new here because the code is the same than when using HttpClient with HttpClientFactory, as shown in previous sections.</span></span> 

## <a name="testing-http-retries-and-circuit-breakers-in-eshoponcontainers"></a><span data-ttu-id="007dc-137">Test dei tentativi HTTP e degli interruttori di circuito in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="007dc-137">Testing Http retries and circuit breakers in eShopOnContainers</span></span>

<span data-ttu-id="007dc-138">Ogni volta che si avvia la soluzione eShopOnContainers in un host Docker, è necessario avviare più contenitori.</span><span class="sxs-lookup"><span data-stu-id="007dc-138">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="007dc-139">Alcuni dei contenitori vengono avviati e inizializzati più lentamente, ad esempio il contenitore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="007dc-139">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="007dc-140">Questo vale in particolare la prima volta che si distribuisce l'applicazione eShopOnContainers in Docker, perché è necessario configurare le immagini e il database.</span><span class="sxs-lookup"><span data-stu-id="007dc-140">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="007dc-141">Il fatto che alcuni contenitori vengano avviati più lentamente rispetto ad altri può causare la generazione iniziale di eccezioni HTTP negli altri servizi, anche se si impostano dipendenze tra i contenitori al livello Docker Compose, come illustrato nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="007dc-141">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="007dc-142">Le dipendenze Docker Compose tra i contenitori si trovano solo sul livello processo.</span><span class="sxs-lookup"><span data-stu-id="007dc-142">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="007dc-143">Il processo del punto di ingresso del contenitore può essere avviato, ma SQL Server potrebbe non essere pronto per le query.</span><span class="sxs-lookup"><span data-stu-id="007dc-143">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="007dc-144">Di conseguenza, possono essere visualizzati numerosi errori e può essere restituita un'eccezione all'applicazione quando prova a usare il contenitore specificato.</span><span class="sxs-lookup"><span data-stu-id="007dc-144">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span> 

<span data-ttu-id="007dc-145">Questo tipo di errore può essere visualizzato anche all'avvio quando l'applicazione viene distribuita nel cloud.</span><span class="sxs-lookup"><span data-stu-id="007dc-145">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="007dc-146">In questo caso, è possibile che gli agenti di orchestrazione stiano spostando i contenitori da un nodo o da una macchina virtuale a un'altra (ovvero, stanno avviando nuove istanze) durante il bilanciamento del numero di contenitori tra i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="007dc-146">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="007dc-147">Quando si avviano tutti i contenitori, "eShopOnContainers" risolve questi problemi usando lo schema Retry illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="007dc-147">The way 'eShopOnContainers' solves those issues when starting all the containers is by using the Retry pattern illustrated earlier.</span></span> 

### <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="007dc-148">Test dell'interruttore di circuito in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="007dc-148">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="007dc-149">Esistono diversi modi per interrompere/aprire il circuito ed eseguirne il test con eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="007dc-149">There are a few ways you can break/open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="007dc-150">Una possibilità consiste nel ridurre il numero consentito di tentativi a 1 nei criteri dell'interruttore di circuito e ridistribuire l'intera soluzione in Docker.</span><span class="sxs-lookup"><span data-stu-id="007dc-150">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="007dc-151">Con un solo tentativo, è probabile che una richiesta HTTP non riuscirà durante la distribuzione, l'interruttore di circuito verrà aperto e verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="007dc-151">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="007dc-152">Un'altra opzione consiste nell'usare middleware personalizzato che viene implementato nel microservizio Basket.</span><span class="sxs-lookup"><span data-stu-id="007dc-152">Another option is to use custom middleware that is implemented in the Basket microservice.</span></span> <span data-ttu-id="007dc-153">Quando il middleware è abilitato, intercetta tutte le richieste HTTP e restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="007dc-153">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="007dc-154">È possibile abilitare il middleware eseguendo una richiesta GET all'URI che ha generato l'errore, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="007dc-154">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

- `GET http://localhost:5103/failing`

<span data-ttu-id="007dc-155">Questa richiesta restituisce lo stato corrente del middleware.</span><span class="sxs-lookup"><span data-stu-id="007dc-155">This request returns the current state of the middleware.</span></span> <span data-ttu-id="007dc-156">Se il middleware è abilitato, la richiesta restituisce il codice di stato 500.</span><span class="sxs-lookup"><span data-stu-id="007dc-156">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="007dc-157">Se il middleware è disabilitato, non viene ricevuta alcuna risposta.</span><span class="sxs-lookup"><span data-stu-id="007dc-157">If the middleware is disabled, there is no response.</span></span> 

- `GET http://localhost:5103/failing?enable`

<span data-ttu-id="007dc-158">Questa richiesta abilita il middleware.</span><span class="sxs-lookup"><span data-stu-id="007dc-158">This request enables the middleware.</span></span> 

- `GET http://localhost:5103/failing?disable`

<span data-ttu-id="007dc-159">Questa richiesta disabilita il middleware.</span><span class="sxs-lookup"><span data-stu-id="007dc-159">This request disables the middleware.</span></span> 

<span data-ttu-id="007dc-160">Ad esempio, quando l'applicazione è in esecuzione, è possibile abilitare il middleware eseguendo una richiesta usando l'URI seguente in qualsiasi browser.</span><span class="sxs-lookup"><span data-stu-id="007dc-160">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="007dc-161">Il microservizio degli ordini usa la porta 5103.</span><span class="sxs-lookup"><span data-stu-id="007dc-161">Note that the ordering microservice uses port 5103.</span></span>

`http://localhost:5103/failing?enable` 

<span data-ttu-id="007dc-162">È quindi possibile controllare lo stato usando l'URI `http://localhost:5103/failing`, come illustrato nella figura 10-4.</span><span class="sxs-lookup"><span data-stu-id="007dc-162">You can then check the status using the URI `http://localhost:5103/failing`, as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="007dc-163">**Figura 10-4**.</span><span class="sxs-lookup"><span data-stu-id="007dc-163">**Figure 10-4**.</span></span> <span data-ttu-id="007dc-164">Verifica dello stato di errore del middleware ASP.NET. In questo caso, è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="007dc-164">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="007dc-165">A questo punto, il microservizio Basket risponde con il codice di stato 500 ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="007dc-165">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="007dc-166">Quando il middleware è in esecuzione, è possibile provare a effettuare un ordine dall'applicazione Web MVC.</span><span class="sxs-lookup"><span data-stu-id="007dc-166">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="007dc-167">Le richieste non riescono, quindi il circuito viene aperto.</span><span class="sxs-lookup"><span data-stu-id="007dc-167">Because the requests fail, the circuit will open.</span></span> 

<span data-ttu-id="007dc-168">Nell'esempio seguente si vede che l'applicazione Web MVC ha un blocco catch nella logica per l'immissione di un ordine.</span><span class="sxs-lookup"><span data-stu-id="007dc-168">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span>  <span data-ttu-id="007dc-169">Se il codice rileva un'eccezione di circuito aperto, verrà visualizzato un messaggio descrittivo che comunica all'utente di attendere.</span><span class="sxs-lookup"><span data-stu-id="007dc-169">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {          
            var user = _appUserParser.Parse(HttpContext.User);
            //Http requests using the Typed Client (Service Agent)
            var vm = await _basketSvc.GetBasket(user);
            return View(vm);
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

<span data-ttu-id="007dc-170">Ecco un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="007dc-170">Here’s a summary.</span></span> <span data-ttu-id="007dc-171">I criteri di ripetizione provano più volte a eseguire la richiesta HTTP e ottengono errori HTTP.</span><span class="sxs-lookup"><span data-stu-id="007dc-171">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="007dc-172">Quando il numero di tentativi raggiunge il valore massimo impostato per i criteri dell'interruttore di circuito (in questo caso, 5), l'applicazione genera un'eccezione BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="007dc-172">When the number of retries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="007dc-173">Il risultato è un messaggio descrittivo, come illustrato nella figura 10-5.</span><span class="sxs-lookup"><span data-stu-id="007dc-173">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="007dc-174">**Figura 10-5**.</span><span class="sxs-lookup"><span data-stu-id="007dc-174">**Figure 10-5**.</span></span> <span data-ttu-id="007dc-175">Interruttore di circuito che restituisce un errore nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="007dc-175">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="007dc-176">È possibile implementare una logica diversa per specificare quando aprire/interrompere il circuito.</span><span class="sxs-lookup"><span data-stu-id="007dc-176">You can implement different logic for when to open/break the circuit.</span></span> <span data-ttu-id="007dc-177">In alternativa, si può provare a eseguire una richiesta HTTP in un microservizio back-end diverso, se è presente un centro dati di fallback o un sistema back-end ridondante.</span><span class="sxs-lookup"><span data-stu-id="007dc-177">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span> 

<span data-ttu-id="007dc-178">Infine, un'altra possibilità per `CircuitBreakerPolicy` prevede l'uso di `Isolate`, che forza l'apertura e mantiene aperto il circuito, e di `Reset`, che lo chiude nuovamente.</span><span class="sxs-lookup"><span data-stu-id="007dc-178">Finally, another possibility for the `CircuitBreakerPolicy` is to use `Isolate` (which forces open and holds open the circuit) and `Reset` (which closes it again).</span></span> <span data-ttu-id="007dc-179">È possibile usarli per creare un endpoint HTTP di utilità che richiama Isolate e Reset direttamente nei criteri.</span><span class="sxs-lookup"><span data-stu-id="007dc-179">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span>  <span data-ttu-id="007dc-180">Questo endpoint HTTP può essere anche usato, se adeguatamente protetto, nell'ambiente di produzione per isolare temporaneamente un sistema downstream, ad esempio quando si vuole eseguire l'aggiornamento di tale sistema.</span><span class="sxs-lookup"><span data-stu-id="007dc-180">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="007dc-181">In alternativa, si può attivare il circuito manualmente per proteggere un sistema downstream che si sospetta essere in stato di errore.</span><span class="sxs-lookup"><span data-stu-id="007dc-181">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="007dc-182">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="007dc-182">Additional resources</span></span>

-   <span data-ttu-id="007dc-183">**Schema Circuit Breaker**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="007dc-183">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="007dc-184">[Precedente](implement-http-call-retries-exponential-backoff-polly.md)
>[Successivo](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="007dc-184">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>