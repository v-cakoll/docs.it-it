---
title: Implementazione dello schema Circuit Breaker
description: Informazioni su come implementare lo schema Circuit Breaker come sistema complementare per i tentativi HTTP.
ms.date: 03/03/2020
ms.openlocfilehash: a79c6fcca1e29f3c30d697cb369060d59a72c121
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847245"
---
# <a name="implement-the-circuit-breaker-pattern"></a>Implementazione dello schema Circuit Breaker

Come notato in precedenza, è necessario gestire gli errori che potrebbero richiedere una quantità di tempo variabile per il ripristino, come accade quando si prova a connettersi a una risorsa o a un servizio remoto. La gestione di questo tipo di errore può migliorare la stabilità e la resilienza di un'applicazione.

In un ambiente distribuito, le chiamate a servizi e risorse remote possono non riuscire a causa di errori temporanei, ad esempio connessioni di rete lente e timeout oppure se le risorse rispondono lentamente o sono temporaneamente non disponibili. Questi errori in genere si correggono autonomamente dopo un breve periodo di tempo e un'applicazione cloud affidabile deve essere preparata a gestirli usando una strategia simile allo "schema Retry".

Tuttavia, in alcune situazioni gli errori sono dovuti a eventi imprevisti, la cui risoluzione potrebbe richiedere molto più tempo. Questi errori possono variare, in base alla gravità, dalla perdita parziale della connettività alla totale interruzione di un servizio. In questi casi è inutile continuare a ripetere in un'applicazione un'operazione che difficilmente avrà esito positivo.

È consigliabile invece codificare l'applicazione in modo che accetti l'errore dell'operazione e lo gestisca di conseguenza.

L'uso improprio di tentativi HTTP potrebbe causare la creazione un attacco Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) nel proprio software. Quando un microservizio non funziona o è lento, più client potrebbero ripetere più volte le richieste non riuscite. Si crea così un rischio pericoloso di un aumento esponenziale del traffico destinato al servizio non funzionante.

È pertanto necessaria una barriera di difesa, in modo che le richieste in eccesso vengano interrotte quando non vale la pena continuare a provare. La barriera di difesa è proprio l'interruttore di circuito.

Lo schema Circuit Breaker ha uno scopo diverso rispetto allo "schema Retry". Lo "schema Retry" consente a un'applicazione di ripetere un'operazione che si prevede possa essere completata correttamente. Lo schema Circuit Breaker impedisce a un'applicazione di eseguire un'operazione che ha probabilità minime di riuscire. Un'applicazione può combinare questi due modelli. Tuttavia, la logica di ripetizione deve essere sensibile alle eventuali eccezioni restituite dall'interruttore di circuito e deve sospendere i tentativi se l'interruttore di circuito indica che un errore non è temporaneo.

## <a name="implement-circuit-breaker-pattern-with-ihttpclientfactory-and-polly"></a>Implementare il `IHttpClientFactory` modello Circuit Breaker con e Polly

Come quando si implementano i tentativi, l'approccio consigliato per gli interruttori di `IHttpClientFactory`circuito consiste nell'utilizzare le librerie .NET collaudate come Polly e la relativa integrazione nativa con .

L'aggiunta di un `IHttpClientFactory` criterio di interruttore nella pipeline middleware in uscita è semplice `IHttpClientFactory`come aggiungere una singola parte di codice incrementale a ciò che si dispone già quando si utilizza .

In questo scenario l'unica aggiunta al codice usato per i tentativi di chiamata HTTP è il codice in cui viene aggiunto il criterio dell'interruttore di circuito all'elenco di criteri da usare, come illustrato nel codice incrementale seguente, parte del metodo ConfigureServices().

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Sample. Default lifetime is 2 minutes
        .AddHttpMessageHandler<HttpClientAuthorizationDelegatingHandler>()
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

Il metodo `AddPolicyHandler()` aggiunge i criteri agli oggetti `HttpClient` che verranno usati. In questo caso aggiunge criteri Polly per un interruttore di circuito.

Per un approccio più modulare, i criteri dell'interruttore di circuito sono definiti in un metodo separato denominato `GetCircuitBreakerPolicy()`, come illustrato nel codice seguente:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

Nell'esempio di codice precedente i criteri dell'interruttore di circuito sono configurati in modo da interrompere o aprire il circuito quando si verificano cinque errori consecutivi durante i nuovi tentativi di richieste HTTP. In questo caso, il circuito verrà interrotto per 30 secondi: in questo intervallo di tempo, le chiamate verranno bloccate immediatamente dall'interruttore di circuito invece di essere effettivamente inserite.  Il criterio interpreta automaticamente le [eccezioni e i codici di stato HTTP rilevanti](/aspnet/core/fundamentals/http-requests#handle-transient-faults) come errori.  

Gli interruttori di circuito devono essere usati anche per reindirizzare le richieste a un'infrastruttura di fallback nel caso di problemi in una determinata risorsa che viene distribuita in un ambiente diverso rispetto all'applicazione client o al servizio che esegue la chiamata HTTP. In questo modo, se si verifica un'interruzione nel centro dati che ha effetto solo sui microservizi back-end ma non sulle applicazioni client, queste applicazioni possono essere reindirizzate ai servizi di fallback. È il corso la pianificazione di un nuovo criterio in Polly che consenta di automatizzare questo scenario per i [criteri di failover](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).

Tutte queste funzionalità riguardano casi in cui il failover viene gestito internamente nel codice .NET, e non automaticamente da Azure, con la trasparenza dei percorsi.

Dal punto di vista dell'utilizzo, quando si utilizza HttpClient, non è necessario aggiungere `HttpClient` qui `IHttpClientFactory`nulla di nuovo perché il codice è lo stesso di quando si utilizza con , come illustrato nelle sezioni precedenti.

## <a name="test-http-retries-and-circuit-breakers-in-eshoponcontainers"></a>Eseguire test per i tentativi HTTP e gli interruttori di circuito in eShopOnContainers

Ogni volta che si avvia la soluzione eShopOnContainers in un host Docker, è necessario avviare più contenitori. Alcuni dei contenitori vengono avviati e inizializzati più lentamente, ad esempio il contenitore di SQL Server. Questo vale in particolare la prima volta che si distribuisce l'applicazione eShopOnContainers in Docker, perché è necessario configurare le immagini e il database. Il fatto che alcuni contenitori vengano avviati più lentamente rispetto ad altri può causare la generazione iniziale di eccezioni HTTP negli altri servizi, anche se si impostano dipendenze tra i contenitori al livello Docker Compose, come illustrato nelle sezioni precedenti. Le dipendenze Docker Compose tra i contenitori si trovano solo sul livello processo. Il processo del punto di ingresso del contenitore può essere avviato, ma SQL Server potrebbe non essere pronto per le query. Di conseguenza, possono essere visualizzati numerosi errori e può essere restituita un'eccezione all'applicazione quando prova a usare il contenitore specificato.

Questo tipo di errore può essere visualizzato anche all'avvio quando l'applicazione viene distribuita nel cloud. In questo caso, è possibile che gli agenti di orchestrazione stiano spostando i contenitori da un nodo o da una macchina virtuale a un'altra (ovvero, stanno avviando nuove istanze) durante il bilanciamento del numero di contenitori tra i nodi del cluster.

Quando si avviano tutti i contenitori, "eShopOnContainers" risolve questi problemi usando lo schema Retry illustrato in precedenza.

### <a name="test-the-circuit-breaker-in-eshoponcontainers"></a>Eseguire il test dell'interruttore di circuito in eShopOnContainers

Esistono diversi modi per interrompere/aprire il circuito ed eseguirne il test con eShopOnContainers.

Una possibilità consiste nel ridurre il numero consentito di tentativi a 1 nei criteri dell'interruttore di circuito e ridistribuire l'intera soluzione in Docker. Con un solo tentativo extra, è probabile che una richiesta HTTP non riuscirà durante la distribuzione, l'interruttore di circuito verrà aperto e verrà visualizzato un errore.

Un'altra opzione è l'uso del middleware personalizzato che viene implementato nel microservizio **Basket**. Quando il middleware è abilitato, intercetta tutte le richieste HTTP e restituisce il codice di stato 500. È possibile abilitare il middleware eseguendo una richiesta GET all'URI che ha generato l'errore, come riportato di seguito:

- `GET http://localhost:5103/failing`\
  Questa richiesta restituisce lo stato corrente del middleware. Se il middleware è abilitato, la richiesta restituisce il codice di stato 500. Se il middleware è disabilitato non viene ricevuta alcuna risposta.

- `GET http://localhost:5103/failing?enable`\
  Questa richiesta abilita il middleware.

- `GET http://localhost:5103/failing?disable`\
  Questa richiesta disabilita il middleware.

Ad esempio, quando l'applicazione è in esecuzione, è possibile abilitare il middleware eseguendo una richiesta usando l'URI seguente in qualsiasi browser. Il microservizio degli ordini usa la porta 5103.

`http://localhost:5103/failing?enable`

È quindi possibile controllare lo stato usando l'URI `http://localhost:5103/failing`, come illustrato nella figura 8-5.

![Screenshot del controllo dello stato della simulazione middleware non riuscita.](./media/implement-circuit-breaker-pattern/failing-middleware-simulation.png)

**Figura 8-5**. Verifica dello stato di errore del middleware ASP.NET. In questo caso, è disabilitato.

A questo punto, il microservizio Basket risponde con il codice di stato 500 ogni volta che viene chiamato.

Quando il middleware è in esecuzione, è possibile provare a effettuare un ordine dall'applicazione Web MVC. Le richieste non riescono, quindi il circuito viene aperto.

Nell'esempio seguente si vede che l'applicazione Web MVC ha un blocco catch nella logica per l'immissione di un ordine.  Se il codice rileva un'eccezione di circuito aperto, verrà visualizzato un messaggio descrittivo che comunica all'utente di attendere.

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

Ecco un riepilogo. I criteri di ripetizione provano più volte a eseguire la richiesta HTTP e ottengono errori HTTP. Quando il numero di tentativi raggiunge il valore massimo impostato per i criteri dell'interruttore di circuito (in questo caso, 5), l'applicazione genera un'eccezione BrokenCircuitException. Il risultato è un messaggio descrittivo, come illustrato nella figura 8-6.

![Screenshot dell'app Web MVC con errore di inoperativi del servizio di basket.](./media/implement-circuit-breaker-pattern/basket-service-inoperative.png)

**Figura 8-6**. Interruttore di circuito che restituisce un errore nell'interfaccia utente

È possibile implementare una logica diversa per specificare quando aprire/interrompere il circuito. In alternativa si può provare a eseguire una richiesta HTTP in un microservizio back-end diverso, se è presente un centro dati di fallback o un sistema back-end ridondante.

Infine, un'altra possibilità per `CircuitBreakerPolicy` prevede l'uso di `Isolate`, che forza l'apertura e mantiene aperto il circuito, e di `Reset`, che lo chiude nuovamente. È possibile usarli per creare un endpoint HTTP di utilità che richiama Isolate e Reset direttamente nei criteri.  Questo endpoint HTTP può essere anche usato, se adeguatamente protetto, nell'ambiente di produzione per isolare temporaneamente un sistema downstream, ad esempio quando si vuole eseguire l'aggiornamento di tale sistema. In alternativa, si può attivare il circuito manualmente per proteggere un sistema downstream che si sospetta essere in stato di errore.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Modello Interruttore circuito**\
  [https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker](/azure/architecture/patterns/circuit-breaker)

>[!div class="step-by-step"]
>[Successivo](implement-http-call-retries-exponential-backoff-polly.md)
>[precedente](monitor-app-health.md)
