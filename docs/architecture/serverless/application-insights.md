---
title: Application Insights - App senza server
description: Application Insights è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi nelle app Web, nelle app per dispositivi mobili, nelle app desktop e nei microservizi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522741"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="e7333-103">Telemetria con Application Insights</span><span class="sxs-lookup"><span data-stu-id="e7333-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="e7333-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi nelle app Web, nelle app per dispositivi mobili, nelle app desktop e nei microservizi.</span><span class="sxs-lookup"><span data-stu-id="e7333-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="e7333-105">È possibile attivare Application Insights per le app per le funzioni semplicemente disattivando un interruttore nel portale.</span><span class="sxs-lookup"><span data-stu-id="e7333-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="e7333-106">Application Insights offre tutte queste funzionalità senza dover configurare un server o configurare un database personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e7333-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="e7333-107">Tutte le funzionalità di Application Insights vengono fornite come servizio che si integra automaticamente con le app.</span><span class="sxs-lookup"><span data-stu-id="e7333-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Logo di Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="e7333-109">L'aggiunta di Application Insights alle app esistenti è semplice come aggiungere una chiave di strumentazione alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e7333-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="e7333-110">Con Application Insights è possibile:</span><span class="sxs-lookup"><span data-stu-id="e7333-110">With Application Insights you can:</span></span>

- <span data-ttu-id="e7333-111">Creare grafici e avvisi personalizzati in base a metriche quali il numero di chiamate di funzioni, il tempo necessario per eseguire una funzione e le eccezioni</span><span class="sxs-lookup"><span data-stu-id="e7333-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="e7333-112">Analizzare gli errori e le eccezioni del serverAnalyze failures and server exceptions</span><span class="sxs-lookup"><span data-stu-id="e7333-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="e7333-113">Approfondisci le prestazioni in base al funzionamento e misura il tempo necessario per chiamare dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="e7333-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="e7333-114">Monitorare l'utilizzo della CPU, la memoria e le velocità in tutti i server che ospitano le app per le funzioniMonitor CPU usage, memory, and rates across all servers that host your function apps</span><span class="sxs-lookup"><span data-stu-id="e7333-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="e7333-115">Visualizzare un flusso live delle metriche, inclusi il numero di richieste e la latenza per le app per le funzioni</span><span class="sxs-lookup"><span data-stu-id="e7333-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="e7333-116">Utilizzare [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) per cercare, eseguire query e creare grafici personalizzati sui dati delle funzioni</span><span class="sxs-lookup"><span data-stu-id="e7333-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Esplora metriche](./media/metrics-explorer.png)

<span data-ttu-id="e7333-118">Oltre ai dati di telemetria incorporati, è anche possibile generare dati di telemetria personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e7333-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="e7333-119">Il frammento di codice seguente crea un client di telemetria personalizzato usando la chiave di strumentazione impostata per l'app per le funzioni:The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span><span class="sxs-lookup"><span data-stu-id="e7333-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="e7333-120">Il codice seguente misura il tempo necessario per inserire una nuova riga in un'istanza di Archiviazione tabelle di Azure:The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span><span class="sxs-lookup"><span data-stu-id="e7333-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="e7333-121">Viene visualizzato il grafico delle prestazioni risultante:The resulting performance graph is shown:</span><span class="sxs-lookup"><span data-stu-id="e7333-121">The resulting performance graph is shown:</span></span>

![Telemetria personalizzata](./media/custom-telemetry.png)

<span data-ttu-id="e7333-123">I dati di telemetria personalizzati rivelano il tempo medio per l'inserimento di una nuova riga è 32,6 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="e7333-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="e7333-124">Application Insights offre un modo pratico e potente per registrare dati di telemetria dettagliati sulle applicazioni senza server.</span><span class="sxs-lookup"><span data-stu-id="e7333-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="e7333-125">Si dispone del controllo completo sul livello di traccia e registrazione fornito.</span><span class="sxs-lookup"><span data-stu-id="e7333-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="e7333-126">È possibile tenere traccia di statistiche personalizzate, ad esempio eventi, dipendenze e visualizzazione pagina.</span><span class="sxs-lookup"><span data-stu-id="e7333-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="e7333-127">Infine, le potenti analisi consentono di scrivere query che pongono domande importanti e generare grafici e informazioni avanzate.</span><span class="sxs-lookup"><span data-stu-id="e7333-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="e7333-128">Per altre informazioni, vedere [Monitorare Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="e7333-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e7333-129">[Successivo](azure-functions.md)
>[precedente](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="e7333-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
