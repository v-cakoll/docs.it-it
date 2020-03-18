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
# <a name="telemetry-with-application-insights"></a>Telemetria con Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi nelle app Web, nelle app per dispositivi mobili, nelle app desktop e nei microservizi. È possibile attivare Application Insights per le app per le funzioni semplicemente disattivando un interruttore nel portale. Application Insights offre tutte queste funzionalità senza dover configurare un server o configurare un database personalizzato. Tutte le funzionalità di Application Insights vengono fornite come servizio che si integra automaticamente con le app.

![Logo di Application Insights](./media/application-insights-logo.png)

L'aggiunta di Application Insights alle app esistenti è semplice come aggiungere una chiave di strumentazione alle impostazioni dell'applicazione. Con Application Insights è possibile:

- Creare grafici e avvisi personalizzati in base a metriche quali il numero di chiamate di funzioni, il tempo necessario per eseguire una funzione e le eccezioni
- Analizzare gli errori e le eccezioni del serverAnalyze failures and server exceptions
- Approfondisci le prestazioni in base al funzionamento e misura il tempo necessario per chiamare dipendenze di terze parti
- Monitorare l'utilizzo della CPU, la memoria e le velocità in tutti i server che ospitano le app per le funzioniMonitor CPU usage, memory, and rates across all servers that host your function apps
- Visualizzare un flusso live delle metriche, inclusi il numero di richieste e la latenza per le app per le funzioni
- Utilizzare [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) per cercare, eseguire query e creare grafici personalizzati sui dati delle funzioni

![Esplora metriche](./media/metrics-explorer.png)

Oltre ai dati di telemetria incorporati, è anche possibile generare dati di telemetria personalizzati. Il frammento di codice seguente crea un client di telemetria personalizzato usando la chiave di strumentazione impostata per l'app per le funzioni:The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Il codice seguente misura il tempo necessario per inserire una nuova riga in un'istanza di Archiviazione tabelle di Azure:The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Viene visualizzato il grafico delle prestazioni risultante:The resulting performance graph is shown:

![Telemetria personalizzata](./media/custom-telemetry.png)

I dati di telemetria personalizzati rivelano il tempo medio per l'inserimento di una nuova riga è 32,6 millisecondi.

Application Insights offre un modo pratico e potente per registrare dati di telemetria dettagliati sulle applicazioni senza server. Si dispone del controllo completo sul livello di traccia e registrazione fornito. È possibile tenere traccia di statistiche personalizzate, ad esempio eventi, dipendenze e visualizzazione pagina. Infine, le potenti analisi consentono di scrivere query che pongono domande importanti e generare grafici e informazioni avanzate.

Per altre informazioni, vedere [Monitorare Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Successivo](azure-functions.md)
>[precedente](logic-apps.md)
