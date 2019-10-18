---
title: Modelli di orchestrazione-app senza server
description: Richieste pull di funzioni durevoli di Azure
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522643"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="c9a1f-103">Modelli di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="c9a1f-103">Orchestration patterns</span></span>

<span data-ttu-id="c9a1f-104">Durable Functions semplifica la creazione di flussi di lavoro con stato costituiti da attività discrete e a esecuzione prolungata in un ambiente senza server.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="c9a1f-105">Poiché Durable Functions possibile tenere traccia dello stato di avanzamento dei flussi di lavoro e di eseguire periodicamente il checkpoint della cronologia di esecuzione, si presta all'implementazione di alcuni modelli interessanti.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="c9a1f-106">Concatenamento di funzioni</span><span class="sxs-lookup"><span data-stu-id="c9a1f-106">Function chaining</span></span>

<span data-ttu-id="c9a1f-107">In un processo sequenziale tipico, le attività devono essere eseguite una dopo l'altra in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="c9a1f-108">Facoltativamente, l'attività imminente potrebbe richiedere un output della funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="c9a1f-109">Questa dipendenza dall'ordinamento delle attività crea una catena di funzioni di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="c9a1f-110">Il vantaggio di usare Durable Functions per implementare questo modello di flusso di lavoro deriva dalla possibilità di eseguire il checkpoint.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="c9a1f-111">Se il server si arresta in modo anomalo, si verifica il timeout della rete o si verificano altri problemi, le funzioni permanenti possono riprendere dall'ultimo stato noto e continuare a eseguire il flusso di lavoro anche se si trova in un altro server.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="c9a1f-112">Nell'esempio di codice precedente, la funzione `CallActivityAsync` è responsabile dell'esecuzione di un'attività specifica in una macchina virtuale nel data center.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="c9a1f-113">Quando il restituisce await e l'attività sottostante viene completata, l'esecuzione verrà registrata nella tabella di cronologia.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="c9a1f-114">Il codice nella funzione dell'agente di orchestrazione può utilizzare qualsiasi costrutto familiare del Task Parallel Library e le parole chiave async/await.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="c9a1f-115">Il codice seguente è un esempio semplificato di come può essere il metodo `ProcessPayment`:</span><span class="sxs-lookup"><span data-stu-id="c9a1f-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="c9a1f-116">API HTTP asincrone</span><span class="sxs-lookup"><span data-stu-id="c9a1f-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="c9a1f-117">In alcuni casi, i flussi di lavoro possono contenere attività che importano un periodo di tempo relativamente lungo per il completamento.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="c9a1f-118">Immaginate un processo che avvia il backup dei file multimediali nell'archivio BLOB.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="c9a1f-119">A seconda delle dimensioni e della quantità dei file multimediali, il completamento di questo processo di backup potrebbe richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="c9a1f-120">In questo scenario, l'`DurableOrchestrationClient` la capacità di verificare lo stato di un flusso di lavoro in esecuzione risulta utile.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="c9a1f-121">Quando si utilizza un `HttpTrigger` per avviare un flusso di lavoro, è possibile utilizzare il metodo `CreateCheckStatusResponse` per restituire un'istanza di `HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="c9a1f-122">Questa risposta fornisce al client un URI nel payload che può essere usato per controllare lo stato del processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="c9a1f-123">Il risultato di esempio seguente mostra la struttura del payload della risposta.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="c9a1f-124">Usando il client HTTP preferito, le richieste GET possono essere apportate all'URI in statusQueryGetUri per controllare lo stato del flusso di lavoro in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="c9a1f-125">La risposta allo stato restituito dovrebbe essere simile al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="c9a1f-126">Quando il processo continua, la risposta allo stato cambierà in **failed** o **Completed**.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="c9a1f-127">Al termine, la proprietà **output** nel payload conterrà tutti i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="c9a1f-128">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="c9a1f-128">Monitoring</span></span>

<span data-ttu-id="c9a1f-129">Per le semplici attività ricorrenti, funzioni di Azure fornisce le `TimerTrigger` che possono essere pianificate in base a un'espressione CRON.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="c9a1f-130">Il timer funziona correttamente per le attività semplici e di breve durata, ma potrebbero esserci scenari in cui è necessaria una pianificazione più flessibile.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="c9a1f-131">Questo scenario si verifica quando il modello di monitoraggio e Durable Functions possono essere utili.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="c9a1f-132">Durable Functions consente intervalli di pianificazione flessibili, gestione della durata e la creazione di più processi di monitoraggio da una singola funzione di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="c9a1f-133">Un caso d'uso per questa funzionalità potrebbe consistere nel creare Watcher per le modifiche dei prezzi azionarie che vengono completate dopo che è stata soddisfatta una determinata soglia.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="c9a1f-134">il metodo `CreateTimer` di `DurableOrchestrationContext` imposta la pianificazione per la successiva chiamata del ciclo per verificare la presenza di modifiche al prezzo azionario.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="c9a1f-135">`DurableOrchestrationContext` dispone inoltre di una proprietà `CurrentUtcDateTime` per ottenere il valore DateTime corrente in formato UTC.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="c9a1f-136">È preferibile usare questa proprietà anziché `DateTime.UtcNow` perché è facile da simulare per il test.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="c9a1f-137">Risorse consigliate</span><span class="sxs-lookup"><span data-stu-id="c9a1f-137">Recommended resources</span></span>

- [<span data-ttu-id="c9a1f-138">Durable Functions di Azure</span><span class="sxs-lookup"><span data-stu-id="c9a1f-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="c9a1f-139">Testing unità in .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="c9a1f-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="c9a1f-140">[Precedente](durable-azure-functions.md)
>[Successivo](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="c9a1f-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
