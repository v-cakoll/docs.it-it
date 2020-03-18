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
# <a name="orchestration-patterns"></a><span data-ttu-id="d3984-103">Modelli di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="d3984-103">Orchestration patterns</span></span>

<span data-ttu-id="d3984-104">Funzioni durevoli semplifica la creazione di flussi di lavoro con stato composti da attività discrete a esecuzione prolungata in un ambiente serverless.</span><span class="sxs-lookup"><span data-stu-id="d3984-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="d3984-105">Poiché funzioni durevoli è in grado di tenere traccia dello stato di avanzamento dei flussi di lavoro e periodicamente controlla la cronologia di esecuzione, si presta all'implementazione di alcuni modelli interessanti.</span><span class="sxs-lookup"><span data-stu-id="d3984-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="d3984-106">Concatenamento di funzioni</span><span class="sxs-lookup"><span data-stu-id="d3984-106">Function chaining</span></span>

<span data-ttu-id="d3984-107">In un tipico processo sequenziale, le attività devono essere eseguite una dopo l'altra in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="d3984-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="d3984-108">Facoltativamente, l'attività imminente potrebbe richiedere un output della funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="d3984-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="d3984-109">Questa dipendenza dall'ordine delle attività crea una catena di esecuzione delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="d3984-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="d3984-110">Il vantaggio dell'utilizzo di funzioni durevoli per implementare questo modello di flusso di lavoro deriva dalla capacità di eseguire checkpoint.</span><span class="sxs-lookup"><span data-stu-id="d3984-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="d3984-111">Se il server si blocca, si verifica il timeout della rete o si verifica un altro problema, le funzioni durevoli possono riprendere dall'ultimo stato noto e continuare l'esecuzione del flusso di lavoro anche se si trova su un altro server.</span><span class="sxs-lookup"><span data-stu-id="d3984-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="d3984-112">Nell'esempio di codice `CallActivityAsync` precedente, la funzione è responsabile dell'esecuzione di una determinata attività in una macchina virtuale nel data center.</span><span class="sxs-lookup"><span data-stu-id="d3984-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="d3984-113">Quando l'attesa viene restituita e l'attività sottostante viene completata, l'esecuzione verrà registrata nella tabella di cronologia.</span><span class="sxs-lookup"><span data-stu-id="d3984-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="d3984-114">Il codice nella funzione dell'agente di orchestrazione può utilizzare uno qualsiasi dei costrutti familiari della libreria Task Parallel Library e le parole chiave async/await.</span><span class="sxs-lookup"><span data-stu-id="d3984-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="d3984-115">Il codice seguente è un `ProcessPayment` esempio semplificato di come potrebbe apparire il metodo:The following code is a simplified example of what the method may look like:</span><span class="sxs-lookup"><span data-stu-id="d3984-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="d3984-116">API HTTP asincrone</span><span class="sxs-lookup"><span data-stu-id="d3984-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="d3984-117">In alcuni casi, i flussi di lavoro possono contenere attività che richiedono un periodo di tempo relativamente lungo.</span><span class="sxs-lookup"><span data-stu-id="d3984-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="d3984-118">Immagina un processo che avvia il backup dei file multimediali nell'archiviazione BLOB.</span><span class="sxs-lookup"><span data-stu-id="d3984-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="d3984-119">A seconda delle dimensioni e della quantità dei file multimediali, il completamento di questo processo di backup potrebbe richiedere ore.</span><span class="sxs-lookup"><span data-stu-id="d3984-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="d3984-120">In questo scenario, la `DurableOrchestrationClient`capacità di controllare lo stato di un flusso di lavoro in esecuzione diventa utile.</span><span class="sxs-lookup"><span data-stu-id="d3984-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="d3984-121">Quando si `HttpTrigger` utilizza un oggetto `CreateCheckStatusResponse` per avviare un flusso `HttpResponseMessage`di lavoro, il metodo può essere utilizzato per restituire un'istanza di .</span><span class="sxs-lookup"><span data-stu-id="d3984-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="d3984-122">Questa risposta fornisce al client un URI nel payload che può essere utilizzato per controllare lo stato del processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d3984-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="d3984-123">Il risultato di esempio seguente mostra la struttura del payload della risposta.</span><span class="sxs-lookup"><span data-stu-id="d3984-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="d3984-124">Utilizzando il client HTTP preferito, è possibile effettuare richieste GET all'URI in statusQueryGetUri per controllare lo stato del flusso di lavoro in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d3984-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="d3984-125">La risposta di stato restituita dovrebbe essere simile al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d3984-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="d3984-126">Mentre il processo continua, la risposta allo stato cambierà in **Non riuscito** o **Completato**.</span><span class="sxs-lookup"><span data-stu-id="d3984-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="d3984-127">Al completamento, la proprietà **di output** nel payload conterrà tutti i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="d3984-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="d3984-128">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="d3984-128">Monitoring</span></span>

<span data-ttu-id="d3984-129">Per le semplici attività ricorrenti, Funzioni di Azure fornisce l'oggetto `TimerTrigger` che può essere pianificato in base a un'espressione CRON.</span><span class="sxs-lookup"><span data-stu-id="d3984-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="d3984-130">Il timer funziona bene per attività semplici e di breve durata, ma potrebbero esserci scenari in cui è necessaria una pianificazione più flessibile.</span><span class="sxs-lookup"><span data-stu-id="d3984-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="d3984-131">Questo scenario è quando il modello di monitoraggio e funzioni durevoli può aiutare.</span><span class="sxs-lookup"><span data-stu-id="d3984-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="d3984-132">Funzioni durevoli consente intervalli di pianificazione flessibili, gestione della durata e la creazione di più processi di monitoraggio da una singola funzione di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="d3984-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="d3984-133">Un caso d'uso per questa funzionalità potrebbe essere quello di creare osservatori per le modifiche dei prezzi delle azioni che vengono completate una volta raggiunta una determinata soglia.</span><span class="sxs-lookup"><span data-stu-id="d3984-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="d3984-134">`DurableOrchestrationContext`'s `CreateTimer` metodo imposta la pianificazione per la successiva chiamata del ciclo per verificare le variazioni di prezzo delle azioni.</span><span class="sxs-lookup"><span data-stu-id="d3984-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="d3984-135">`DurableOrchestrationContext`ha anche `CurrentUtcDateTime` una proprietà per ottenere il valore DateTime corrente in UTC.</span><span class="sxs-lookup"><span data-stu-id="d3984-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="d3984-136">È preferibile utilizzare questa proprietà `DateTime.UtcNow` anziché perché è facilmente deriso per il test.</span><span class="sxs-lookup"><span data-stu-id="d3984-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="d3984-137">Risorse consigliate</span><span class="sxs-lookup"><span data-stu-id="d3984-137">Recommended resources</span></span>

- [<span data-ttu-id="d3984-138">Durable Functions di Azure</span><span class="sxs-lookup"><span data-stu-id="d3984-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="d3984-139">Testing unità in .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="d3984-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="d3984-140">[Successivo](durable-azure-functions.md)
>[precedente](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="d3984-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
