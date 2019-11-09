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
# <a name="telemetry-with-application-insights"></a>Telemetria con Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi in app Web, app per dispositivi mobili, app desktop e microservizi. È possibile attivare Application Insights per le app per le funzioni semplicemente capovolgendo un'opzione nel portale. Application Insights offre tutte queste funzionalità senza dover configurare un server o configurare il proprio database. Tutte le funzionalità di Application Insights sono fornite come un servizio che si integra automaticamente con le app.

![Logo Application Insights](./media/application-insights-logo.png)

L'aggiunta di Application Insights alle app esistenti è semplice come aggiungere una chiave di strumentazione alle impostazioni dell'applicazione. Con Application Insights è possibile:

- Creare grafici e avvisi personalizzati in base alle metriche, ad esempio il numero di chiamate di funzione, il tempo necessario per l'esecuzione di una funzione e le eccezioni
- Analizzare gli errori e le eccezioni del server
- Analizzare le prestazioni per operazione e misurare il tempo necessario per chiamare le dipendenze di terze parti
- Monitorare l'utilizzo della CPU, la memoria e le tariffe in tutti i server che ospitano le app per le funzioni
- Visualizzare un flusso live di metriche, tra cui il numero di richieste e la latenza per le app per le funzioni
- Usare [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) per eseguire ricerche, eseguire query e creare grafici personalizzati sui dati delle funzioni

![Esplora metriche](./media/metrics-explorer.png)

Oltre ai dati di telemetria incorporati, è anche possibile generare dati di telemetria personalizzati. Il frammento di codice seguente crea un client di telemetria personalizzato usando il set di chiavi di strumentazione per l'app per le funzioni:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Il codice seguente consente di misurare il tempo necessario per inserire una nuova riga in un'istanza di [archiviazione tabelle di Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) :

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Viene visualizzato il grafico delle prestazioni risultante:

![Telemetria personalizzata](./media/custom-telemetry.png)

La telemetria personalizzata rivela il tempo medio per l'inserimento di una nuova riga è pari a 32,6 millisecondi.

Application Insights offre un modo pratico e potente per registrare i dati di telemetria dettagliati sulle applicazioni senza server. Si ha il controllo completo sul livello di traccia e registrazione fornito. È possibile tenere traccia delle statistiche personalizzate, ad esempio eventi, dipendenze e visualizzazione pagina. Infine, la potente analisi consente di scrivere query che pongono domande importanti e generano grafici e informazioni dettagliate avanzate.

Per altre informazioni, vedere [monitorare funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Precedente](azure-functions.md)
>[Successivo](logic-apps.md)
