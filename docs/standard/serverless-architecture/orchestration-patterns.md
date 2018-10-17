---
title: Modelli di orchestrazione - App senza server
description: Le funzioni di Azure durevole delle richieste pull
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 241eff4f30e63b2bb34664d6f783f854a000e7fd
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370056"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="a0253-103">Modelli di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="a0253-103">Orchestration patterns</span></span>

<span data-ttu-id="a0253-104">Funzioni permanenti rende più semplice creare flussi di lavoro con stati che sono composte da attività discrete, esecuzione prolungata in un ambiente senza server.</span><span class="sxs-lookup"><span data-stu-id="a0253-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="a0253-105">Poiché funzioni durevoli può tenere traccia dell'avanzamento dei flussi di lavoro e periodicamente checkpoint la cronologia di esecuzione, presta all'implementazione di alcuni modelli interessanti.</span><span class="sxs-lookup"><span data-stu-id="a0253-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="a0253-106">Concatenamento di funzioni</span><span class="sxs-lookup"><span data-stu-id="a0253-106">Function chaining</span></span>

<span data-ttu-id="a0253-107">In un tipico processo sequenza, è necessario che le attività eseguite una dopo l'altra in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="a0253-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="a0253-108">Facoltativamente, la prossima attività potrebbe richiedere alcuni output dalla funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="a0253-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="a0253-109">Questa dipendenza per l'ordinamento delle attività crea una serie di funzioni di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0253-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="a0253-110">Il vantaggio dell'uso di funzioni permanenti per implementare questo modello di flusso di lavoro provenienza dalla possibilità di eseguire operazioni di checkpoint.</span><span class="sxs-lookup"><span data-stu-id="a0253-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="a0253-111">Se il server si blocca, timeout di rete o un altro problema si verifica, funzioni permanenti è possono riprendere dall'ultimo stato conosciuto e continuare l'esecuzione del flusso di lavoro, anche se è in un altro server.</span><span class="sxs-lookup"><span data-stu-id="a0253-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="a0253-112">Nell'esempio di codice precedente, il `CallActivityAsync` funzione è responsabile per l'esecuzione di una determinata attività in una macchina virtuale nel data center.</span><span class="sxs-lookup"><span data-stu-id="a0253-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="a0253-113">Quando viene completata l'attività sottostante e la restituisce await, l'esecuzione verrà registrato nella tabella di cronologia.</span><span class="sxs-lookup"><span data-stu-id="a0253-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="a0253-114">Il codice nella funzione dell'agente di orchestrazione può rendere utilizzare uno dei costrutti di familiarità di Task Parallel Library e le parole chiave async/await.</span><span class="sxs-lookup"><span data-stu-id="a0253-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="a0253-115">Il codice seguente è un esempio semplificato di ciò che il `ProcessPayment` metodo sarà simile a:</span><span class="sxs-lookup"><span data-stu-id="a0253-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="a0253-116">API HTTP asincrone</span><span class="sxs-lookup"><span data-stu-id="a0253-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="a0253-117">In alcuni casi, i flussi di lavoro può contenere le attività che hanno un periodo di tempo necessario per completare relativamente lungo.</span><span class="sxs-lookup"><span data-stu-id="a0253-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="a0253-118">Si immagini un processo che viene avviato il backup dei supporti i file nell'archiviazione blob.</span><span class="sxs-lookup"><span data-stu-id="a0253-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="a0253-119">A seconda della dimensione e quantità dei file multimediali, questo processo di backup potrebbe richiedere ore per il completamento.</span><span class="sxs-lookup"><span data-stu-id="a0253-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="a0253-120">In questo scenario il `DurableOrchestrationClient`della possibilità di controllare lo stato di un flusso di lavoro in esecuzione diventa utile.</span><span class="sxs-lookup"><span data-stu-id="a0253-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="a0253-121">Quando si usa un' `HttpTrigger` per avviare un flusso di lavoro, il `CreateCheckStatusResponse` metodo può essere utilizzato per restituire un'istanza di `HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="a0253-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="a0253-122">Questa risposta fornisce al client con un URI nel payload che può essere utilizzato per controllare lo stato del processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0253-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="a0253-123">Il risultato di esempio riportato di seguito viene illustrata la struttura del payload della risposta.</span><span class="sxs-lookup"><span data-stu-id="a0253-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="a0253-124">Usa il proprio client HTTP preferito, GET è possibile effettuare richieste all'URI nel statusQueryGetUri per verificare lo stato del flusso di lavoro in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0253-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="a0253-125">La risposta di stato restituito deve assomigliare al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a0253-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="a0253-126">Il processo continua e la risposta di stato verrà modificato in uno **Failed** oppure **Completed**.</span><span class="sxs-lookup"><span data-stu-id="a0253-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="a0253-127">Al termine, il **output** proprietà nel payload conterrà tutti i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="a0253-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="a0253-128">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="a0253-128">Monitoring</span></span>

<span data-ttu-id="a0253-129">Per semplici attività ricorrenti, funzioni di Azure fornisce il `TimerTrigger` che possono essere programmate in base a un'espressione CRON.</span><span class="sxs-lookup"><span data-stu-id="a0253-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="a0253-130">Il timer funziona bene per operazioni semplici e di breve durate, ma potrebbero essere presenti scenari in cui è necessaria una pianificazione più flessibile.</span><span class="sxs-lookup"><span data-stu-id="a0253-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="a0253-131">Questo scenario è quando il modello di monitoraggio e funzioni durevoli può aiutare.</span><span class="sxs-lookup"><span data-stu-id="a0253-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="a0253-132">Consente di funzioni permanenti per gli intervalli di pianificazione flessibile, gestione della durata e la creazione di più processi di monitoraggio da una funzione unica orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="a0253-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="a0253-133">Un caso d'uso per questa funzionalità può essere la creazione di controlli per le modifiche di prezzo delle azioni che vengono completate quando viene soddisfatta una determinata soglia.</span><span class="sxs-lookup"><span data-stu-id="a0253-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="a0253-134">`DurableOrchestrationContext`del `CreateTimer` metodo imposta la pianificazione per la chiamata successiva del ciclo per controllare le modifiche di prezzo azionario.</span><span class="sxs-lookup"><span data-stu-id="a0253-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="a0253-135">`DurableOrchestrationContext` ha anche un `CurrentUtcDateTime` proprietà da ottenere il valore di data/ora corrente in formato UTC.</span><span class="sxs-lookup"><span data-stu-id="a0253-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="a0253-136">È preferibile usare questa proprietà anziché `DateTime.UtcNow` perché si è facilmente fittizie per il test.</span><span class="sxs-lookup"><span data-stu-id="a0253-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="a0253-137">Risorse consigliate</span><span class="sxs-lookup"><span data-stu-id="a0253-137">Recommended resources</span></span>

* [<span data-ttu-id="a0253-138">Funzioni durevoli di Azure</span><span class="sxs-lookup"><span data-stu-id="a0253-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="a0253-139">Testing unità in .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="a0253-139">Unit Testing in .NET Core and .NET Standard</span></span>](https://docs.microsoft.com/dotnet/core/testing/)

>[!div class="step-by-step"]
<span data-ttu-id="a0253-140">[Precedente](durable-azure-functions.md)
[Successivo](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="a0253-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
