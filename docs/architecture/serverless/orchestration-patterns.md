---
title: Modelli di orchestrazione - App senza serverOrchestration patterns - Serverless apps
description: Funzioni di Azure durevoli prAzure Durable functions pr
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522643"
---
# <a name="orchestration-patterns"></a>Modelli di orchestrazione

Funzioni durevoli semplifica la creazione di flussi di lavoro con stato composti da attività discrete a esecuzione prolungata in un ambiente serverless. Poiché funzioni durevoli è in grado di tenere traccia dello stato di avanzamento dei flussi di lavoro e periodicamente controlla la cronologia di esecuzione, si presta all'implementazione di alcuni modelli interessanti.

## <a name="function-chaining"></a>Concatenamento di funzioni

In un tipico processo sequenziale, le attività devono essere eseguite una dopo l'altra in un ordine particolare. Facoltativamente, l'attività imminente potrebbe richiedere un output della funzione precedente. Questa dipendenza dall'ordine delle attività crea una catena di esecuzione delle funzioni.

Il vantaggio dell'utilizzo di funzioni durevoli per implementare questo modello di flusso di lavoro deriva dalla capacità di eseguire checkpoint. Se il server si blocca, si verifica il timeout della rete o si verifica un altro problema, le funzioni durevoli possono riprendere dall'ultimo stato noto e continuare l'esecuzione del flusso di lavoro anche se si trova su un altro server.

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<bool>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

Nell'esempio di codice `CallActivityAsync` precedente, la funzione è responsabile dell'esecuzione di una determinata attività in una macchina virtuale nel data center. Quando l'attesa viene restituita e l'attività sottostante viene completata, l'esecuzione verrà registrata nella tabella di cronologia. Il codice nella funzione dell'agente di orchestrazione può utilizzare uno qualsiasi dei costrutti familiari della libreria Task Parallel Library e le parole chiave async/await.

Il codice seguente è un `ProcessPayment` esempio semplificato di come potrebbe apparire il metodo:The following code is a simplified example of what the method may look like:

```csharp
[FunctionName("ProcessPayment")]
public static bool ProcessPayment([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    ApplyCoupons(orderData);
    if(IssuePaymentRequest(orderData)) {
        return true;
    }

    return false;
}
```

## <a name="asynchronous-http-apis"></a>API HTTP asincrone

In alcuni casi, i flussi di lavoro possono contenere attività che richiedono un periodo di tempo relativamente lungo. Immagina un processo che avvia il backup dei file multimediali nell'archiviazione BLOB. A seconda delle dimensioni e della quantità dei file multimediali, il completamento di questo processo di backup potrebbe richiedere ore.

In questo scenario, la `DurableOrchestrationClient`capacità di controllare lo stato di un flusso di lavoro in esecuzione diventa utile. Quando si `HttpTrigger` utilizza un oggetto `CreateCheckStatusResponse` per avviare un flusso `HttpResponseMessage`di lavoro, il metodo può essere utilizzato per restituire un'istanza di . Questa risposta fornisce al client un URI nel payload che può essere utilizzato per controllare lo stato del processo in esecuzione.

```csharp
[FunctionName("OrderWorkflow")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient orchestrationClient)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

Il risultato di esempio seguente mostra la struttura del payload della risposta.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Utilizzando il client HTTP preferito, è possibile effettuare richieste GET all'URI in statusQueryGetUri per controllare lo stato del flusso di lavoro in esecuzione. La risposta di stato restituita dovrebbe essere simile al codice seguente.

```json
{
    "runtimeStatus": "Running",
    "input": {
        "$type": "DurableFunctionsDemos.OrderRequestData, DurableFunctionsDemos"
    },
    "output": null,
    "createdTime": "2018-01-01T00:22:05Z",
    "lastUpdatedTime": "2018-01-01T00:22:09Z"
}
```

Mentre il processo continua, la risposta allo stato cambierà in **Non riuscito** o **Completato**. Al completamento, la proprietà **di output** nel payload conterrà tutti i dati restituiti.

## <a name="monitoring"></a>Monitoraggio

Per le semplici attività ricorrenti, Funzioni di Azure fornisce l'oggetto `TimerTrigger` che può essere pianificato in base a un'espressione CRON. Il timer funziona bene per attività semplici e di breve durata, ma potrebbero esserci scenari in cui è necessaria una pianificazione più flessibile. Questo scenario è quando il modello di monitoraggio e funzioni durevoli può aiutare.

Funzioni durevoli consente intervalli di pianificazione flessibili, gestione della durata e la creazione di più processi di monitoraggio da una singola funzione di orchestrazione. Un caso d'uso per questa funzionalità potrebbe essere quello di creare osservatori per le modifiche dei prezzi delle azioni che vengono completate una volta raggiunta una determinata soglia.

```csharp
[FunctionName("CheckStockPrice")]
public static async Task CheckStockPrice([OrchestrationTrigger] DurableOrchestrationContext context)
{
    StockWatcherInfo stockInfo = context.GetInput<StockWatcherInfo>();
    const int checkIntervalSeconds = 120;
    StockPrice initialStockPrice = null;

    DateTime fireAt;
    DateTime exitTime = context.CurrentUtcDateTime.Add(stockInfo.TimeLimit);

    while (context.CurrentUtcDateTime < exitTime)
    {
        StockPrice currentStockPrice = await context.CallActivityAsync<StockPrice>("GetStockPrice", stockInfo);

        if (initialStockPrice == null)
        {
            initialStockPrice = currentStockPrice;
            fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
            await context.CreateTimer(fireAt, CancellationToken.None);
            continue;
        }

        decimal percentageChange = (initialStockPrice.Price - currentStockPrice.Price) /
                               ((initialStockPrice.Price + currentStockPrice.Price) / 2);

        if (Math.Abs(percentageChange) >= stockInfo.PercentageChange)
        {
            // Change threshold detected
            await context.CallActivityAsync("NotifyStockPercentageChange", currentStockPrice);
            break;
        }

        // Sleep til next polling interval
        fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
        await context.CreateTimer(fireAt, CancellationToken.None);
    }
}
```

`DurableOrchestrationContext`'s `CreateTimer` metodo imposta la pianificazione per la successiva chiamata del ciclo per verificare le variazioni di prezzo delle azioni. `DurableOrchestrationContext`ha anche `CurrentUtcDateTime` una proprietà per ottenere il valore DateTime corrente in UTC. È preferibile utilizzare questa proprietà `DateTime.UtcNow` anziché perché è facilmente deriso per il test.

## <a name="recommended-resources"></a>Risorse consigliate

- [Durable Functions di Azure](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Testing unità in .NET Core e .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Successivo](durable-azure-functions.md)
>[precedente](serverless-business-scenarios.md)
