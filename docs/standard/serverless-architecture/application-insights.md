---
title: Application Insights - App senza server
description: Application Insights è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi in App web, App per dispositivi mobili, App desktop e i microservizi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 1f5b99fba448c2c1c12139524ffdcd3708b3c956
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643371"
---
# <a name="telemetry-with-application-insights"></a>Dati di telemetria con Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) è una piattaforma di diagnostica senza server che consente agli sviluppatori di rilevare, valutare e diagnosticare i problemi in App web, App per dispositivi mobili, App desktop e i microservizi. È possibile attivare Application Insights per App per le funzioni semplicemente girando l'un interruttore nel portale. Application Insights offre tutte queste funzionalità senza dover configurare un server o configurare il proprio database. Tutte le funzionalità di Application Insights vengono fornite come un servizio che integra automaticamente con le app.

![Logo di Application Insights](./media/application-insights-logo.png)

L'aggiunta di Application Insights per le app esistenti è facile come aggiungere una chiave di strumentazione alle impostazioni dell'applicazione. Con Application Insights è possibile:

* Creare grafici personalizzati e gli avvisi basati sulle metriche, ad esempio numero di chiamate di funzione, il tempo che necessario per eseguire una funzione ed eccezioni
* Analizzare gli errori ed eccezioni del server
* Eseguire il drill-in prestazioni dall'operazione e misurare il tempo che necessario per chiamare le dipendenze di terze parti
* Monitorare l'utilizzo della CPU, memoria e frequenze tra tutti i server che ospitano le app di funzione
* Visualizzare un flusso in tempo reale di metriche, ad esempio numero di richieste e la latenza per le App (funzione)
* Uso [Analitica](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) per cercare, eseguire una query e creare grafici personalizzati sui dati (funzione)

![Esplora metriche](./media/metrics-explorer.png)

Oltre ai dati di telemetria predefiniti, è anche possibile generare dati di telemetria personalizzati. Il frammento di codice seguente crea un client di telemetria personalizzata usando la chiave di strumentazione impostato per l'app per le funzioni:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Il codice seguente misura il tempo necessario per inserire una nuova riga in un [archiviazione tabelle di Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) istanza:

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Viene visualizzato il grafico delle prestazioni risultante:

![Dati di telemetria personalizzati](./media/custom-telemetry.png)

I dati di telemetria personalizzati vengono visualizzati il tempo medio per inserire una nuova riga è 32.6 millisecondi.

Application Insights offre un modo efficace e conveniente per registrare dati di telemetria dettagliati sulle tue applicazioni senza server. Si ha il controllo completo sul livello di traccia e registrazione, che è disponibile. È possibile tenere traccia di statistiche personalizzate, ad esempio eventi, dipendenze e visualizzazione di pagina. Infine, il potente analitica consentono di scrivere le query che domande importanti e generano grafici e informazioni dettagliate avanzate.

Per altre informazioni, vedere [monitorare funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Precedente](azure-functions.md)
>[Successivo](logic-apps.md)
