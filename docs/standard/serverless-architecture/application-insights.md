---
title: Application Insights - App senza server
description: Application Insights è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi in App web, App per dispositivi mobili, App desktop e i microservizi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4884d483de07c1c2077f7280b6b77c6059572c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051236"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="f3e67-103">Dati di telemetria con Application Insights</span><span class="sxs-lookup"><span data-stu-id="f3e67-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="f3e67-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi in App web, App per dispositivi mobili, App desktop e i microservizi.</span><span class="sxs-lookup"><span data-stu-id="f3e67-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="f3e67-105">È possibile attivare Application Insights per App per le funzioni semplicemente girando l'un interruttore nel portale.</span><span class="sxs-lookup"><span data-stu-id="f3e67-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="f3e67-106">Application Insights offre tutte queste funzionalità senza dover configurare un server o configurare il proprio database.</span><span class="sxs-lookup"><span data-stu-id="f3e67-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="f3e67-107">Tutte le funzionalità di Application Insights vengono fornite come un servizio che integra automaticamente con le app.</span><span class="sxs-lookup"><span data-stu-id="f3e67-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Logo di Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="f3e67-109">L'aggiunta di Application Insights per le app esistenti è facile come aggiungere una chiave di strumentazione alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3e67-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="f3e67-110">Con Application Insights è possibile:</span><span class="sxs-lookup"><span data-stu-id="f3e67-110">With Application Insights you can:</span></span>

* <span data-ttu-id="f3e67-111">Creare grafici personalizzati e gli avvisi basati sulle metriche, ad esempio numero di chiamate di funzione, il tempo che necessario per eseguire una funzione ed eccezioni</span><span class="sxs-lookup"><span data-stu-id="f3e67-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="f3e67-112">Analizzare gli errori ed eccezioni del server</span><span class="sxs-lookup"><span data-stu-id="f3e67-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="f3e67-113">Eseguire il drill-in prestazioni dall'operazione e misurare il tempo che necessario per chiamare le dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="f3e67-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="f3e67-114">Monitorare l'utilizzo della CPU, memoria e frequenze tra tutti i server che ospitano le app di funzione</span><span class="sxs-lookup"><span data-stu-id="f3e67-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="f3e67-115">Visualizzare un flusso in tempo reale di metriche, ad esempio numero di richieste e la latenza per le App (funzione)</span><span class="sxs-lookup"><span data-stu-id="f3e67-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="f3e67-116">Uso [Analitica](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) per cercare, eseguire una query e creare grafici personalizzati sui dati (funzione)</span><span class="sxs-lookup"><span data-stu-id="f3e67-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Esplora metriche](./media/metrics-explorer.png)

<span data-ttu-id="f3e67-118">Oltre ai dati di telemetria predefiniti, è anche possibile generare dati di telemetria personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f3e67-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="f3e67-119">Il frammento di codice seguente crea un client di telemetria personalizzata usando la chiave di strumentazione impostato per l'app per le funzioni:</span><span class="sxs-lookup"><span data-stu-id="f3e67-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="f3e67-120">Il codice seguente misura il tempo necessario per inserire una nuova riga in un [archiviazione tabelle di Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) istanza:</span><span class="sxs-lookup"><span data-stu-id="f3e67-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="f3e67-121">Viene visualizzato il grafico delle prestazioni risultante:</span><span class="sxs-lookup"><span data-stu-id="f3e67-121">The resulting performance graph is shown:</span></span>

![Dati di telemetria personalizzati](./media/custom-telemetry.png)

<span data-ttu-id="f3e67-123">I dati di telemetria personalizzati vengono visualizzati il tempo medio per inserire una nuova riga è 32.6 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="f3e67-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="f3e67-124">Application Insights offre un modo efficace e conveniente per registrare dati di telemetria dettagliati sulle tue applicazioni senza server.</span><span class="sxs-lookup"><span data-stu-id="f3e67-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="f3e67-125">Si ha il controllo completo sul livello di traccia e registrazione, che è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f3e67-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="f3e67-126">È possibile tenere traccia di statistiche personalizzate, ad esempio eventi, dipendenze e visualizzazione di pagina.</span><span class="sxs-lookup"><span data-stu-id="f3e67-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="f3e67-127">Infine, il potente analitica consentono di scrivere le query che domande importanti e generano grafici e informazioni dettagliate avanzate.</span><span class="sxs-lookup"><span data-stu-id="f3e67-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="f3e67-128">Per altre informazioni, vedere [monitorare funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="f3e67-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f3e67-129">[Precedente](azure-functions.md)
>[Successivo](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="f3e67-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>