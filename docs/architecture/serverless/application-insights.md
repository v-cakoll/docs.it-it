---
title: App Application Insights senza server
description: Application Insights è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi in app Web, app per dispositivi mobili, app desktop e microservizi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522741"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="dd27b-103">Telemetria con Application Insights</span><span class="sxs-lookup"><span data-stu-id="dd27b-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="dd27b-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi in app Web, app per dispositivi mobili, app desktop e microservizi.</span><span class="sxs-lookup"><span data-stu-id="dd27b-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="dd27b-105">È possibile attivare Application Insights per le app per le funzioni semplicemente capovolgendo un'opzione nel portale.</span><span class="sxs-lookup"><span data-stu-id="dd27b-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="dd27b-106">Application Insights offre tutte queste funzionalità senza dover configurare un server o configurare il proprio database.</span><span class="sxs-lookup"><span data-stu-id="dd27b-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="dd27b-107">Tutte le funzionalità di Application Insights sono fornite come un servizio che si integra automaticamente con le app.</span><span class="sxs-lookup"><span data-stu-id="dd27b-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Logo Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="dd27b-109">L'aggiunta di Application Insights alle app esistenti è semplice come aggiungere una chiave di strumentazione alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd27b-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="dd27b-110">Con Application Insights è possibile:</span><span class="sxs-lookup"><span data-stu-id="dd27b-110">With Application Insights you can:</span></span>

- <span data-ttu-id="dd27b-111">Creare grafici e avvisi personalizzati in base alle metriche, ad esempio il numero di chiamate di funzione, il tempo necessario per l'esecuzione di una funzione e le eccezioni</span><span class="sxs-lookup"><span data-stu-id="dd27b-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="dd27b-112">Analizzare gli errori e le eccezioni del server</span><span class="sxs-lookup"><span data-stu-id="dd27b-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="dd27b-113">Analizzare le prestazioni per operazione e misurare il tempo necessario per chiamare le dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="dd27b-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="dd27b-114">Monitorare l'utilizzo della CPU, la memoria e le tariffe in tutti i server che ospitano le app per le funzioni</span><span class="sxs-lookup"><span data-stu-id="dd27b-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="dd27b-115">Visualizzare un flusso live di metriche, tra cui il numero di richieste e la latenza per le app per le funzioni</span><span class="sxs-lookup"><span data-stu-id="dd27b-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="dd27b-116">Usare [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) per eseguire ricerche, eseguire query e creare grafici personalizzati sui dati delle funzioni</span><span class="sxs-lookup"><span data-stu-id="dd27b-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Esplora metriche](./media/metrics-explorer.png)

<span data-ttu-id="dd27b-118">Oltre ai dati di telemetria incorporati, è anche possibile generare dati di telemetria personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dd27b-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="dd27b-119">Il frammento di codice seguente crea un client di telemetria personalizzato usando il set di chiavi di strumentazione per l'app per le funzioni:</span><span class="sxs-lookup"><span data-stu-id="dd27b-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="dd27b-120">Il codice seguente consente di misurare il tempo necessario per inserire una nuova riga in un'istanza di [archiviazione tabelle di Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) :</span><span class="sxs-lookup"><span data-stu-id="dd27b-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="dd27b-121">Viene visualizzato il grafico delle prestazioni risultante:</span><span class="sxs-lookup"><span data-stu-id="dd27b-121">The resulting performance graph is shown:</span></span>

![Telemetria personalizzata](./media/custom-telemetry.png)

<span data-ttu-id="dd27b-123">La telemetria personalizzata rivela il tempo medio per l'inserimento di una nuova riga è pari a 32,6 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="dd27b-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="dd27b-124">Application Insights offre un modo pratico e potente per registrare i dati di telemetria dettagliati sulle applicazioni senza server.</span><span class="sxs-lookup"><span data-stu-id="dd27b-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="dd27b-125">Si ha il controllo completo sul livello di traccia e registrazione fornito.</span><span class="sxs-lookup"><span data-stu-id="dd27b-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="dd27b-126">È possibile tenere traccia delle statistiche personalizzate, ad esempio eventi, dipendenze e visualizzazione pagina.</span><span class="sxs-lookup"><span data-stu-id="dd27b-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="dd27b-127">Infine, la potente analisi consente di scrivere query che pongono domande importanti e generano grafici e informazioni dettagliate avanzate.</span><span class="sxs-lookup"><span data-stu-id="dd27b-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="dd27b-128">Per altre informazioni, vedere [monitorare funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="dd27b-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dd27b-129">[Precedente](azure-functions.md)
>[Successivo](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="dd27b-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
