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
# <a name="implementing-the-circuit-breaker-pattern"></a>Implementazione dello schema Circuit Breaker

Come notato in precedenza, è necessario gestire gli errori che potrebbero richiedere una quantità di tempo variabile per il ripristino, come accade quando si prova a connettersi a una risorsa o a un servizio remoto. La gestione di questo tipo di errore può migliorare la stabilità e la resilienza di un'applicazione.

In un ambiente distribuito, le chiamate a servizi e risorse remote può non riuscire a causa di errori temporanei, ad esempio connessioni di rete lente e timeout oppure se le risorse vengono rallentate o sono temporaneamente non disponibili. Questi errori in genere si correggono autonomamente dopo un breve periodo di tempo e un'applicazione cloud affidabile deve essere preparata a gestirli usando una strategia simile allo schema Retry.

Tuttavia, in alcune situazioni gli errori sono dovuti a eventi imprevisti, la cui risoluzione potrebbe richiedere molto più tempo. La gravità di questi errori può variare, da una perdita parziale di connettività a un errore generale di un servizio. In questi casi, è inutile continuare a ripetere in un'applicazione un'operazione che è improbabile venga eseguita. È consigliabile invece codificare l'applicazione in modo che accetti l'errore dell'operazione e lo gestisca di conseguenza.

Lo schema Circuit Breaker ha uno scopo diverso rispetto allo schema Retry. Lo schema Retry consente a un'applicazione di ripetere un'operazione che si prevede possa essere completata correttamente. Lo schema Circuit Breaker impedisce a un'applicazione di eseguire un'operazione che potrebbe non riuscire. Un'applicazione può combinare questi due schemi, usando lo schema Retry per richiamare un'operazione con un interruttore di circuito. Tuttavia, la logica di ripetizione deve essere sensibile alle eventuali eccezioni restituite dall'interruttore di circuito e deve sospendere i tentativi se l'interruttore di circuito indica che un errore non è temporaneo.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Implementazione dello schema Circuit Breaker con Polly

Come accade quando si implementano i tentativi, l'approccio consigliato per gli interruttori di circuito prevede l'uso di librerie .NET collaudate come Polly.

L'applicazione eShopOnContainers usa i criteri dell'interruttore di circuito di Polly quando si implementano tentativi HTTP. In realtà, l'applicazione applica entrambi i criteri alla classe di utilità ResilientHttpClient. Quando si usa un oggetto di tipo ResilientHttpClient per le richieste HTTP da eShopOnContainers, vengono applicati entrambi i criteri, ma è possibile aggiungerne anche altri.

In questo scenario, l'unica aggiunta al codice usato per i tentativi di chiamata HTTP è il codice in cui viene aggiunto il criterio dell'interruttore di circuito all'elenco di criteri da usare, come illustrato alla fine di codice riportato di seguito:

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

Il codice aggiunge un criterio al wrapper HTTP. Questi criteri definiscono un interruttore di circuito che viene aperto quando il codice rileva il numero indicato di eccezioni consecutive (eccezioni in una riga), specificato nel parametro exceptionsAllowedBeforeBreaking (in questo caso, 5). Quando il circuito è aperto, le richieste HTTP non funzionano, ma viene generata un'eccezione.

Gli interruttori di circuito devono essere usati anche per reindirizzare le richieste a un'infrastruttura di fallback nel caso di problemi in una determinata risorsa che viene distribuita in un ambiente diverso rispetto all'applicazione client o al servizio che esegue la chiamata HTTP. In questo modo, se si verifica un'interruzione nel centro dati che influisce solo sui microservizi back-end, ma non sulle applicazioni client, queste applicazioni possono essere reindirizzate ai servizi di fallback. È il corso la pianificazione di un nuovo criterio in Polly che consenta di automatizzare questo scenario per i [criteri di failover](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).

Naturalmente, tutte queste funzionalità riguardano casi in cui il failover viene gestito internamente nel codice .NET, e non automaticamente da Azure, con la trasparenza dei percorsi.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>Uso della classe di utilità ResilientHttpClient da eShopOnContainers

La classe di utilità ResilientHttpClient viene usata in modo analogo alla classe .NET HttpClient. Nell'esempio seguente relativo all'applicazione Web MVC in eShopOnContainers, ossia la classe dell'agente OrderingService usata da OrderController, l'oggetto ResilientHttpClient viene inserito con il parametro httpClient del costruttore. L'oggetto viene quindi usato per eseguire le richieste HTTP.

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

Quando viene usato l'oggetto membro \_apiClient, al suo interno viene usata la classe wrapper con criteri di Polly: criteri di ripetizione, criteri dell'interruttore di circuito e altri criteri applicabili disponibili nella raccolta di Polly.

## <a name="testing-retries-in-eshoponcontainers"></a>Tentativi di test in eShopOnContainers

Ogni volta che si avvia la soluzione eShopOnContainers in un host Docker, è necessario avviare più contenitori. Alcuni dei contenitori vengono avviati e inizializzati più lentamente, ad esempio il contenitore di SQL Server. Questo vale in particolare la prima volta che si distribuisce l'applicazione eShopOnContainers in Docker, perché è necessario configurare le immagini e il database. Il fatto che alcuni contenitori vengano avviati più lentamente rispetto ad altri può causare la generazione iniziale di eccezioni HTTP negli altri servizi, anche se si impostano dipendenze tra i contenitori al livello Docker Compose, come illustrato nelle sezioni precedenti. Le dipendenze Docker Compose tra i contenitori si trovano solo sul livello processo. Il processo del punto di ingresso del contenitore può essere avviato, ma SQL Server potrebbe non essere pronto per le query. Di conseguenza, possono essere visualizzati numerosi errori e può essere restituita un'eccezione all'applicazione quando prova a usare il contenitore specificato.

Questo tipo di errore può essere visualizzato anche all'avvio quando l'applicazione viene distribuita nel cloud. In questo caso, è possibile che gli agenti di orchestrazione stiano spostando i contenitori da un nodo o da una macchina virtuale a un'altra (ovvero, stanno avviando nuove istanze) durante il bilanciamento del numero di contenitori tra i nodi del cluster.

eShopOnContainers risolve il problema usando lo schema Retry illustrato in precedenza. Questo approccio viene seguito anche perché, quando si avvia la soluzione, potrebbero essere visualizzate tracce di log o avvisi simili al seguente:

> "**Tentativo 1 implementato con i criteri di ripetizione di Polly**, causato da: System.Net.Http.HttpRequestException: Si è verificato un errore durante l'invio della richiesta. ---&gt; System.Net.Http.CurlException: impossibile connettersi al server\\ in System.Net.Http.CurlHandler.ThrowIfCURLEError(errore CURLcode)\\ in \[...\].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Test dell'interruttore di circuito in eShopOnContainers

Esistono diversi modi per aprire il circuito ed eseguirne il test con eShopOnContainers.

Una possibilità consiste nel ridurre il numero consentito di tentativi a 1 nei criteri dell'interruttore di circuito e ridistribuire l'intera soluzione in Docker. Con un solo tentativo, è probabile che una richiesta HTTP non riuscirà durante la distribuzione, l'interruttore di circuito verrà aperto e verrà visualizzato un errore.

Un'altra opzione consiste nell'usare middleware personalizzato che viene implementato nel microservizio `Basket`. Quando il middleware è abilitato, intercetta tutte le richieste HTTP e restituisce il codice di stato 500. È possibile abilitare il middleware eseguendo una richiesta GET all'URI che ha generato l'errore, come riportato di seguito:

-   GET /failing

Questa richiesta restituisce lo stato corrente del middleware. Se il middleware è abilitato, la richiesta restituisce il codice di stato 500. Se il middleware è disabilitato, non viene ricevuta alcuna risposta.

-   GET /failing?enable

Questa richiesta abilita il middleware.

-   GET /failing?disable

Questa richiesta disabilita il middleware.

Ad esempio, quando l'applicazione è in esecuzione, è possibile abilitare il middleware eseguendo una richiesta usando l'URI seguente in qualsiasi browser. Il microservizio degli ordini usa la porta 5103.

http://localhost:5103/failing?enable

È quindi possibile controllare lo stato usando l'URI [http://localhost:5103/failing](http://localhost:5103/failing), come illustrato nella figura 10-4.

![](./media/image4.png)

**Figura 10-4**. Verifica dello stato di errore del middleware ASP.NET. In questo caso, è disabilitato. 

A questo punto, il microservizio Basket risponde con il codice di stato 500 ogni volta che viene chiamato.

Quando il middleware è in esecuzione, è possibile provare a effettuare un ordine dall'applicazione Web MVC. Le richieste non riescono, quindi il circuito viene aperto.

Nell'esempio seguente si vede che l'applicazione Web MVC ha un blocco catch nella logica per l'immissione di un ordine. Se il codice rileva un'eccezione di circuito aperto, verrà visualizzato un messaggio descrittivo che comunica all'utente di attendere.

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

Ecco un riepilogo. I criteri di ripetizione provano più volte a eseguire la richiesta HTTP e ottengono errori HTTP. Quando il numero di tentativi raggiunge il valore massimo impostato per i criteri dell'interruttore di circuito (in questo caso, 5), l'applicazione genera un'eccezione BrokenCircuitException. Il risultato è un messaggio descrittivo, come illustrato nella figura 10-5.

![](./media/image5.png)

**Figura 10-5**. Interruttore di circuito che restituisce un errore nell'interfaccia utente

È possibile implementare una logica diversa per specificare quando aprire il circuito. In alternativa, si può provare a eseguire una richiesta HTTP in un microservizio back-end diverso, se è presente un centro dati di fallback o un sistema back-end ridondante.

Infine, un'altra possibilità per i criteri dell'interruttore di circuito prevede l'uso di Isolate, che forza l'apertura e mantiene aperto il circuito, e di Reset, che lo chiude nuovamente. È possibile usarli per creare un endpoint HTTP di utilità che richiama Isolate e Reset direttamente nei criteri. Questo endpoint HTTP può essere anche usato, se adeguatamente protetto, nell'ambiente di produzione per isolare temporaneamente un sistema downstream, ad esempio quando si vuole eseguire l'aggiornamento di tale sistema. In alternativa, si può attivare il circuito manualmente per proteggere un sistema downstream che si sospetta essere in stato di errore.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Aggiunta di una strategia di instabilità ai criteri di ripetizione

I normali criteri di ripetizione possono influire sul sistema quando scalabilità e concorrenza sono elevate e sono presenti molti conflitti. Per risolvere i picchi di tentativi simili provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità all'algoritmo o ai criteri di ripetizione. Ciò può migliorare le prestazioni complessive del sistema end-to-end grazie all'aggiunta di casualità nel backoff esponenziale. Permette di diluire i picchi quando si verificano problemi. Quando si usa Polly, il codice per implementare l'instabilità potrebbe somigliare a quello nell'esempio seguente:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Schema Retry**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Resilienza della connessione** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (libreria .NET con funzionalità di resilienza e di gestione degli errori temporanei) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Schema Circuit Breaker**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker. Jitter: Making Things Better With Randomness (Instabilità: usare la casualità per ottimizzare le procedure)** https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Indietro] (implement-http-call-retries-exponential-backoff-polly.md) [Avanti] (monitor-app-health.md)
