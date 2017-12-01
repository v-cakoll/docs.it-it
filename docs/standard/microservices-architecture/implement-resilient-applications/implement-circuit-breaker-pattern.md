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
# <a name="implementing-the-circuit-breaker-pattern"></a>Implementazione del modello di interruttore

Come notato in precedenza, è necessario gestire gli errori che potrebbero richiedere una quantità di tempo per il recupero, come può verificarsi quando si tenta di connettersi a una risorsa o un servizio remoto variabile. La gestione di questo tipo di errore, è possibile migliorare la stabilità e la flessibilità di un'applicazione.

In un ambiente distribuito, le chiamate alle risorse remote e ai servizi può non riuscire a causa di errori temporanei, ad esempio connessioni di rete lente e i timeout, o se le risorse vengono rallentare o sono temporaneamente non disponibile. Questi errori in genere correggere autonomamente dopo un breve periodo di tempo e un'applicazione cloud affidabile deve essere preparata per gestirli utilizzando una strategia simile il criterio di ripetizione.

Tuttavia, può anche essere situazioni in cui a causa di eventi imprevisti che potrebbero richiedere molto più tempo per risolvere gli errori. Questi errori possono variare in base alla gravità da una perdita parziale di connettività per l'errore completo di un servizio. In questi casi, potrebbe essere inutile per un'applicazione continuamente ripetere un'operazione che è improbabile che venga eseguita correttamente. Al contrario, l'applicazione deve essere codificato per accettare che l'operazione non è riuscita e gestire l'errore, di conseguenza.

Il modello di interruttore ha uno scopo diverso del modello di tentativi. Il criterio di ripetizione consente a un'applicazione ripetere un'operazione nella previsione che l'operazione verrà infine completata. Il modello di interruttore impedisce un'applicazione eseguendo un'operazione che potrebbe non riuscire. Un'applicazione è possibile combinare questi due modelli utilizzando il modello di tentativi per richiamare un'operazione tramite un interruttore. Tuttavia, la logica di tentativi deve essere sensibile alle eventuali eccezioni restituite dall'interruttore e deve essere abbandonato tentativi se l'interruttore indica che un errore non è temporaneo.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Implementazione di un modello di interruttore con Polly

Come quando si implementa tentativi, l'approccio consigliato per gli interruttori di sfruttare le librerie .NET si basa sulla collaudata come Polly.

L'applicazione eShopOnContainers utilizza i criteri di Polly interruttore quando si implementa tentativi HTTP. In realtà, l'applicazione applica entrambi i criteri per la classe di utilità ResilientHttpClient. Quando si usa un oggetto di tipo ResilientHttpClient per le richieste HTTP (da eShopOnContainers), si applicano entrambe tali criteri, ma è possibile aggiungere altri criteri, troppo.

L'aggiunta sola per il codice utilizzato per i tentativi di chiamata HTTP è il codice aggiungere il criterio interruttore all'elenco di criteri da usare, come illustrato alla fine di codice riportato di seguito:

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

Il codice aggiunge un criterio per il wrapper HTTP. Che criteri definiscono un interruttore che viene visualizzata quando il codice rileva il numero di eccezioni consecutivi (eccezioni in una riga), specificato come passato nel parametro exceptionsAllowedBeforeBreaking (in questo caso, 5). Una volta aperto il circuito, le richieste HTTP non funzionano, ma viene generata un'eccezione.

Circuito va inoltre usata per reindirizzare le richieste a un'infrastruttura di fallback, se si potrebbe presentare problemi in una determinata risorsa che viene distribuito in un ambiente diverso rispetto all'applicazione client o servizio che esegue la chiamata HTTP. In questo modo, se si verifica un'interruzione nel Data Center che influisce solo il microservizi back-end, ma non le applicazioni client, le applicazioni client possono reindirizzare a servizi di fallback. Un nuovo criterio per automatizzare questa operazione prevede Polly [criteri di failover](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.

Naturalmente, tutte queste funzionalità sono casi in cui si sta gestendo il failover da all'interno del codice .NET, anziché viene gestita automaticamente da Azure, con la trasparenza dei percorsi.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>Utilizzo della classe di utilità ResilientHttpClient da eShopOnContainers

Utilizzare la classe di utilità ResilientHttpClient in modo analogo a come si utilizza la classe .NET HttpClient. Nell'esempio seguente dall'applicazione web MVC eShopOnContainers (OrderingService classe agent utilizzata da OrderController), viene inserito l'oggetto ResilientHttpClient tramite il parametro httpClient del costruttore. L'oggetto viene quindi utilizzato per eseguire richieste HTTP.

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

Ogni volta che il \_viene utilizzato l'oggetto membro apiClient, utilizza internamente la classe wrapper con Polly policiesؙ: i criteri di ripetizione, il criterio interruttore e altri criteri che è possibile applicare dalla raccolta di criteri Polly.

## <a name="testing-retries-in-eshoponcontainers"></a>Test di nuovi tentativi in eShopOnContainers

Ogni volta che si avvia la soluzione eShopOnContainers in un host Docker, è necessario avviare più contenitori. Alcuni dei contenitori sono più lenti per l'avvio e l'inizializzazione, ad esempio il contenitore di SQL Server. Questo vale in particolare la prima volta che si distribuisce l'applicazione eShopOnContainers in Docker, perché è necessario impostare le immagini e il database. Il fatto che alcuni contenitori di avviare più lenta rispetto ad altri utenti può causare il resto dei servizi inizialmente generare eccezioni HTTP, anche se si impostano le dipendenze tra i contenitori nella composizione docker livello, come illustrato nelle sezioni precedenti. Quelli docker-creare dipendenze tra i contenitori sono solo a livello di processo. Processo del punto di ingresso del contenitore potrebbe essere avviato, ma SQL Server potrebbe non essere pronto per le query. Il risultato può essere una catena di errori e l'applicazione può ottenere un'eccezione durante il tentativo di utilizzare tale contenitore specifico.

Quando l'applicazione viene distribuita nel cloud, è possibile visualizzare questo tipo di errore all'avvio. In tal caso, orchestrators potrebbe essere spostamento contenitori da un nodo o da macchina virtuale a un altro (che è, avvio di nuove istanze) quando il numero di contenitori di bilanciamento tra i nodi del cluster.

Il modo eShopOnContainers per risolvere questo problema è utilizzando il modello di tentativi che è illustrati in precedenza. È inoltre perché, quando si avvia la soluzione, è possibile ottenere le tracce di log o avvisi simile al seguente:

> "**Tentativo 1 implementato con RetryPolicy di Polly**, a causa di: System.Net.Http.HttpRequestException: si è verificato un errore durante l'invio della richiesta. ---&gt;System.Net.Http.CurlException: Impossibile connettersi al server\\n in System.Net.Http.CurlHandler.ThrowIfCURLEError (errore CURLcode)\\n in \[... \].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Test dell'interruttore in eShopOnContainers

Esistono diversi modi, è possibile aprire il circuito ed eseguirne il test con eShopOnContainers.

È possibile ridurre il numero consentito di tentativi su 1 nei criteri di interruttore e ridistribuire l'intera soluzione in Docker. Con un nuovo tentativo singolo, è probabile che una richiesta HTTP avrà esito negativo durante la distribuzione, verrà aperto l'interruttore e si verifica un errore.

Un'altra opzione consiste nell'utilizzare middleware personalizzato che viene implementato in microservizio l'ordinamento. Quando è abilitato questo middleware, intercetta tutte le richieste HTTP e lo restituisce il codice di stato 500. È possibile abilitare il middleware tramite una richiesta GET ha generato l'errore URI, simile al seguente:

-   OTTENERE/non superati

Questa richiesta restituisce lo stato corrente del middleware. Se il middleware è abilitato, la richiesta restituisce il codice di stato 500. Se il middleware è disabilitato, non è stata ricevuta alcuna risposta.

-   OTTENERE/non superati? abilitare

Questa richiesta consente il middleware.

-   OTTENERE/non superati? disabilitare

Questa richiesta disabilita il middleware.

Ad esempio, dopo l'applicazione è in esecuzione, è possibile abilitare il middleware tramite una richiesta utilizzando il seguente URI in qualsiasi browser. Si noti che l'ordinamento microservizio utilizza la porta 5102.

http://localhost:5102 / non superati? abilitare

È quindi possibile controllare lo stato usando l'URI [http://localhost:5102 / non superati](http://localhost:5100/failing), come illustrato nella figura 10-4.

![](./media/image4.png)

**Nella figura 10-4**. Simulazione di un errore con il middleware ASP.NET

A questo punto, risponde microservizio ordinamento con codice di stato 500 ogni volta che chiamano richiamano.

Quando il middleware è in esecuzione, è possibile provare a effettuare un ordine dall'applicazione web MVC. Poiché le richieste non riesce, verrà aperto il circuito.

Nell'esempio seguente, è possibile visualizzare l'applicazione web MVC di un blocco catch bloccare nella logica dell'immissione di un ordine. Se il codice rileva un'eccezione di open circuito, verrà visualizzato all'utente un messaggio descrittivo informa di attesa.

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

Di seguito è riportato un riepilogo. I criteri di ripetizione tenta più volte per la richiesta HTTP e ottiene gli errori HTTP. Quando il numero di tentativi raggiunge il massimo valore impostato per il criterio interruttore (in questo caso, 5), l'applicazione genera un BrokenCircuitException. Il risultato è un messaggio descrittivo, come illustrato nella figura 10-5.

![](./media/image5.png)

**Nella figura 10-5**. Interruttore restituendo un errore nell'interfaccia utente

È possibile implementare una logica diversa per i casi in cui aprire il circuito. O se è presente un Data Center di fallback o ridondante sistema back-end, è possibile provare una richiesta HTTP in un diverso microservizio back-end.

Infine, un'altra possibilità per il CircuitBreakerPolicy consiste nell'utilizzare isolano (che forza aperto e mantiene aperta del circuito) e la reimpostazione (che chiude nuovamente). È possibile utilizzarli per creare un endpoint HTTP di utilità che richiama isolano e reimpostare direttamente al criterio. Tale endpoint HTTP può essere utilizzato anche adeguatamente protetto, nell'ambiente di produzione per isolare temporaneamente un sistema a valle, ad esempio quando si desidera eseguire l'aggiornamento. O Impossibile attivarsi il circuito manualmente per proteggere un sistema a valle che sospetti è possibile generare un errore.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Aggiunta di una strategia di instabilità per i criteri di ripetizione

Criteri di ripetizione regolari possono influire su sistema nel caso di scalabilità e concorrenza elevata e con elevata contesa. Per risolvere i picchi di tentativi simile provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità per l'algoritmo/criteri di ripetizione. Ciò può migliorare le prestazioni complessive del sistema end-to-end mediante l'aggiunta di casualità di backoff esponenziale. Consistenti i picchi di problemi. Quando si utilizza Polly, codice per implementare l'instabilità potrebbe essere simile al seguente:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Ripetere modello**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Resilienza di connessione** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (resilienza .NET e la gestione di errori temporanei libreria) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Modello di interruttore**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker. Instabilità: Eseguire operazioni meglio con casualità** https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Precedente] [Avanti] (app-monitor-health.md) (implement-http-call-retries-exponential-backoff-polly.md)
