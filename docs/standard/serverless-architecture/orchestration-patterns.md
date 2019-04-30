---
title: Modelli di orchestrazione - App senza server
description: Le funzioni di Azure durevole delle richieste pull
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 8be499a24e2c5a94132ce07241e17f675e8a1274
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940959"
---
# <a name="orchestration-patterns"></a>Modelli di orchestrazione

Funzioni permanenti rende più semplice creare flussi di lavoro con stati che sono composte da attività discrete, esecuzione prolungata in un ambiente senza server. Poiché funzioni durevoli può tenere traccia dell'avanzamento dei flussi di lavoro e periodicamente checkpoint la cronologia di esecuzione, presta all'implementazione di alcuni modelli interessanti.

## <a name="function-chaining"></a>Concatenamento di funzioni

In un tipico processo sequenza, è necessario che le attività eseguite una dopo l'altra in un ordine particolare. Facoltativamente, la prossima attività potrebbe richiedere alcuni output dalla funzione precedente. Questa dipendenza per l'ordinamento delle attività crea una serie di funzioni di esecuzione.

Il vantaggio dell'uso di funzioni permanenti per implementare questo modello di flusso di lavoro provenienza dalla possibilità di eseguire operazioni di checkpoint. Se il server si blocca, timeout di rete o un altro problema si verifica, funzioni permanenti è possono riprendere dall'ultimo stato conosciuto e continuare l'esecuzione del flusso di lavoro, anche se è in un altro server.

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

Nell'esempio di codice precedente, il `CallActivityAsync` funzione è responsabile per l'esecuzione di una determinata attività in una macchina virtuale nel data center. Quando viene completata l'attività sottostante e la restituisce await, l'esecuzione verrà registrato nella tabella di cronologia. Il codice nella funzione dell'agente di orchestrazione può rendere utilizzare uno dei costrutti di familiarità di Task Parallel Library e le parole chiave async/await.

Il codice seguente è un esempio semplificato di ciò che il `ProcessPayment` metodo sarà simile a:

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

In alcuni casi, i flussi di lavoro può contenere le attività che hanno un periodo di tempo necessario per completare relativamente lungo. Si immagini un processo che viene avviato il backup dei supporti i file nell'archiviazione blob. A seconda della dimensione e quantità dei file multimediali, questo processo di backup potrebbe richiedere ore per il completamento.

In questo scenario il `DurableOrchestrationClient`della possibilità di controllare lo stato di un flusso di lavoro in esecuzione diventa utile. Quando si usa un' `HttpTrigger` per avviare un flusso di lavoro, il `CreateCheckStatusResponse` metodo può essere utilizzato per restituire un'istanza di `HttpResponseMessage`. Questa risposta fornisce al client con un URI nel payload che può essere utilizzato per controllare lo stato del processo in esecuzione.

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

Il risultato di esempio riportato di seguito viene illustrata la struttura del payload della risposta.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Usa il proprio client HTTP preferito, GET è possibile effettuare richieste all'URI nel statusQueryGetUri per verificare lo stato del flusso di lavoro in esecuzione. La risposta di stato restituito deve assomigliare al codice seguente.

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

Il processo continua e la risposta di stato verrà modificato in uno **Failed** oppure **Completed**. Al termine, il **output** proprietà nel payload conterrà tutti i dati restituiti.

## <a name="monitoring"></a>Monitoraggio

Per semplici attività ricorrenti, funzioni di Azure fornisce il `TimerTrigger` che possono essere programmate in base a un'espressione CRON. Il timer funziona bene per operazioni semplici e di breve durate, ma potrebbero essere presenti scenari in cui è necessaria una pianificazione più flessibile. Questo scenario è quando il modello di monitoraggio e funzioni durevoli può aiutare.

Consente di funzioni permanenti per gli intervalli di pianificazione flessibile, gestione della durata e la creazione di più processi di monitoraggio da una funzione unica orchestrazione. Un caso d'uso per questa funzionalità può essere la creazione di controlli per le modifiche di prezzo delle azioni che vengono completate quando viene soddisfatta una determinata soglia.

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

`DurableOrchestrationContext`del `CreateTimer` metodo imposta la pianificazione per la chiamata successiva del ciclo per controllare le modifiche di prezzo azionario. `DurableOrchestrationContext` ha anche un `CurrentUtcDateTime` proprietà da ottenere il valore di data/ora corrente in formato UTC. È preferibile usare questa proprietà anziché `DateTime.UtcNow` perché si è facilmente fittizie per il test.

## <a name="recommended-resources"></a>Risorse consigliate

* [Funzioni durevoli di Azure](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Testing unità in .NET Core e .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Precedente](durable-azure-functions.md)
>[Successivo](serverless-business-scenarios.md)