---
title: Modelli di orchestrazione-app senza server
description: Richieste pull di funzioni durevoli di Azure
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 18e13c5355490ef4a019ceda459114bdb6bfd539
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577404"
---
# <a name="orchestration-patterns"></a>Modelli di orchestrazione

Durable Functions semplifica la creazione di flussi di lavoro con stato costituiti da attività discrete e a esecuzione prolungata in un ambiente senza server. Poiché Durable Functions possibile tenere traccia dello stato di avanzamento dei flussi di lavoro e di eseguire periodicamente il checkpoint della cronologia di esecuzione, si presta all'implementazione di alcuni modelli interessanti.

## <a name="function-chaining"></a>Concatenamento di funzioni

In un processo sequenziale tipico, le attività devono essere eseguite una dopo l'altra in un ordine particolare. Facoltativamente, l'attività imminente potrebbe richiedere un output della funzione precedente. Questa dipendenza dall'ordinamento delle attività crea una catena di funzioni di esecuzione.

Il vantaggio di usare Durable Functions per implementare questo modello di flusso di lavoro deriva dalla possibilità di eseguire il checkpoint. Se il server si arresta in modo anomalo, si verifica il timeout della rete o si verificano altri problemi, le funzioni permanenti possono riprendere dall'ultimo stato noto e continuare a eseguire il flusso di lavoro anche se si trova in un altro server.

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

Nell'esempio di codice precedente, la `CallActivityAsync` funzione è responsabile dell'esecuzione di un'attività specifica in una macchina virtuale nell'Data Center. Quando il restituisce await e l'attività sottostante viene completata, l'esecuzione verrà registrata nella tabella di cronologia. Il codice nella funzione dell'agente di orchestrazione può utilizzare qualsiasi costrutto familiare del Task Parallel Library e le parole chiave async/await.

Il codice seguente è un esempio semplificato di come `ProcessPayment` può essere il metodo:

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

In alcuni casi, i flussi di lavoro possono contenere attività che importano un periodo di tempo relativamente lungo per il completamento. Immaginate un processo che avvia il backup dei file multimediali nell'archivio BLOB. A seconda delle dimensioni e della quantità dei file multimediali, il completamento di questo processo di backup potrebbe richiedere alcune ore.

In questo scenario, la `DurableOrchestrationClient`possibilità di controllare lo stato di un flusso di lavoro in esecuzione risulta utile. Quando si utilizza `HttpTrigger` un oggetto per avviare un flusso `CreateCheckStatusResponse` di lavoro, è possibile utilizzare il metodo per `HttpResponseMessage`restituire un'istanza di. Questa risposta fornisce al client un URI nel payload che può essere usato per controllare lo stato del processo in esecuzione.

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

Usando il client HTTP preferito, le richieste GET possono essere apportate all'URI in statusQueryGetUri per controllare lo stato del flusso di lavoro in esecuzione. La risposta allo stato restituito dovrebbe essere simile al codice seguente.

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

Quando il processo continua, la risposta allo stato cambierà in **failed** o **Completed**. Al termine, la proprietà **output** nel payload conterrà tutti i dati restituiti.

## <a name="monitoring"></a>Monitoraggio

Per le semplici attività ricorrenti, funzioni di Azure fornisce `TimerTrigger` l'oggetto che può essere pianificato in base a un'espressione cron. Il timer funziona correttamente per le attività semplici e di breve durata, ma potrebbero esserci scenari in cui è necessaria una pianificazione più flessibile. Questo scenario si verifica quando il modello di monitoraggio e Durable Functions possono essere utili.

Durable Functions consente intervalli di pianificazione flessibili, gestione della durata e la creazione di più processi di monitoraggio da una singola funzione di orchestrazione. Un caso d'uso per questa funzionalità potrebbe consistere nel creare Watcher per le modifiche dei prezzi azionarie che vengono completate dopo che è stata soddisfatta una determinata soglia.

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

`DurableOrchestrationContext`il `CreateTimer` metodo di imposta la pianificazione per la successiva chiamata del ciclo per verificare la presenza di modifiche al prezzo azionario. `DurableOrchestrationContext`dispone inoltre di `CurrentUtcDateTime` una proprietà per ottenere il valore DateTime corrente in formato UTC. È preferibile usare questa proprietà anziché `DateTime.UtcNow` perché è facile da simulare per il test.

## <a name="recommended-resources"></a>Risorse consigliate

* [Durable Functions di Azure](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Testing unità in .NET Core e .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Precedente](durable-azure-functions.md)
>[Successivo](serverless-business-scenarios.md)
