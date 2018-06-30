---
title: Monitorare i servizi delle applicazioni nei contenitori
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 368d99e92f80cf37965139cb67fc5f22b44f40cd
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106130"
---
# <a name="monitor-containerized-application-services"></a>Monitorare i servizi delle applicazioni nei contenitori

È fondamentale per le applicazioni suddiviso in più contenitori e microservizi disporre di un modo per monitorare e analizzare il comportamento dell'applicazione.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) è un servizio analitica estendibile che consente di monitorare l'applicazione in tempo reale. Consente di rilevare e diagnosticare i problemi di prestazioni e per comprendere cosa gli utenti effettivamente fare con l'app. È progettato per gli sviluppatori, con lo scopo di consentono di migliorare continuamente le prestazioni e usabilità dei propri servizi o applicazioni. Application Insights funziona con/servizi web e da autonome App su una vasta gamma di piattaforme, ad esempio .NET, Java, Node. js e molte altre piattaforme, ospitato in locale o nel cloud.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Analisi delle app di Docker in ambienti QA con Application Insights

Quanto fa riferimento a Docker, è possibile grafico gli eventi del ciclo di vita e i contatori delle prestazioni dai contenitori di Docker in Application Insights. È sufficiente eseguire la [immagine di Application Insights Docker](https://hub.docker.com/r/microsoft/applicationinsights/) come un contenitore nell'host che verrà visualizzati i contatori delle prestazioni per l'host e per le altre immagini Docker. Questa immagine di Application Insights Docker (figura 6 - 1) consente di monitorare le applicazioni nei contenitori mediante la raccolta dei dati di telemetria sulle prestazioni e attività dell'host Docker (vale a dire, le macchine virtuali Linux), i contenitori di Docker e le applicazioni in esecuzione all'interno di essi.

![esempio](./media/image1.png)

Figura 6-1: monitoraggio host Docker e i contenitori di Application Insights

Quando si esegue il [immagine di Application Insights Docker](https://hub.docker.com/r/microsoft/applicationinsights/) sull'host Docker, vantaggioso quanto segue:

-   Dati di telemetria su tutti i contenitori in esecuzione nell'host del ciclo di vita, avviare, arrestare e così via.

-   I contatori delle prestazioni per tutti i contenitori: CPU, memoria, utilizzo della rete e altro ancora.

-   Se è installato anche [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in applicazioni in esecuzione nei contenitori, tutti i dati di telemetria di tali App hanno proprietà aggiuntive che identifica il computer host e contenitore. In tal caso, ad esempio, se si dispone di istanze di un'app in esecuzione in più di un host, facilmente sarà in grado di filtrare i dati di telemetria app dall'host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Configurazione di Application Insights per monitorare le applicazioni di Docker e gli host Docker

Per creare una risorsa di Application Insights, seguire le istruzioni negli articoli presentati nell'elenco che segue. Portale di Azure verrà creato lo script necessario per l'utente.

-   **Monitoraggio delle applicazioni di Docker in Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Application Insights Docker immagine Hub Docker e Github:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) e <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Configurare Application Insights per ASP.NET:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights per le pagine web:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](http://microsoft.com/oms) è una soluzione di gestione IT semplificata che fornisce log analitica, automazione, backup e ripristino del sito. In base alle [query](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite, è possibile generare [avvisi](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) e impostare monitoraggio e aggiornamento tramite [automazione di Azure](https://docs.microsoft.com/azure/automation/). Si integra anche con facilità con le soluzioni di gestione esistenti che offrono un singolo pannello di controllo. Operations Management Suite consente di gestire e proteggere in locale e l'infrastruttura cloud.

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](http://microsoft.com/oms) soluzione contenitore Docker

Oltre a fornire importanti servizi autonomamente, la soluzione di contenitore di Operations Management Suite può gestire e monitorare gli host Docker e contenitori tramite la visualizzazione di informazioni in cui i contenitori e gli host contenitore, i contenitori in esecuzione o non riusciti, Docker daemon contenitore nei registri eventi e inviato a *stdout* e *stderr*. La soluzione mostra anche le metriche di prestazioni, tra cui CPU, memoria, rete e archiviazione, per il contenitore e gli host per semplificare la risoluzione dei problemi e trovare i contenitori che possono influire negativamente sulle prestazioni nelle vicinanze.

![](./media/image2.png)

Figura 6-2: informazioni sui contenitori di Docker illustrato da Operations Management Suite

Application Insights e Operations Management Suite concentrarsi sulle attività di monitoraggio Tuttavia, Application Insights si concentra più sul monitoraggio le app autonomamente grazie ai relativi SDK in esecuzione all'interno dell'app. Tuttavia, Operations Management Suite è molto più incentrato sull'infrastruttura per gli host e offre un'analisi approfondita sui registri su larga scala, offrendo un sistema molto flessibili basati sui dati/query di ricerca.

Poiché Operations Management Suite viene implementata come un servizio basato su cloud, è possibile che in esecuzione rapidamente con un investimento minimo nei servizi di infrastruttura. Nuove funzionalità sono rese disponibili automaticamente, senza la manutenzione ordinaria e aggiornare i costi.

Utilizza soluzione contenitore di Operations Management Suite, è possibile eseguire le operazioni seguenti:

-   Centralizzare e correlare milioni di log dai contenitori di Docker su larga scala

-   Visualizzare informazioni su tutti gli host contenitore in un'unica posizione

-   I contenitori sono in esecuzione, quali immagini che siano in esecuzione e in cui vengono eseguiti

-   Diagnosticare rapidamente contenitori "fastidioso" che possono causare problemi negli host contenitore

-   Vedere un audit trail per le azioni sui contenitori

-   Risolvere i problemi mediante la visualizzazione e la ricerca di log centralizzato senza la comunicazione remota per gli host Docker

-   Trovare i contenitori che potrebbero essere "disturbate router adiacenti" e dispendiosa in termini di quantità eccessiva di risorse in un host

-   Visualizzare centralizzata della CPU, memoria, archiviazione e informazioni sull'utilizzo e sulle prestazioni di rete per i contenitori

-   Generare test container Docker con automazione di Azure

Per visualizzare informazioni sulle prestazioni, l'esecuzione di query come tipo = Perf, come illustrato nella figura 6-3.

![DockerPerfMetricsView](./media/image3.png){larghezza = altezza "5.78625 in" = "3.25 in"}

Figura 6-3: le metriche delle prestazioni di host Docker illustrato da Operations Management Suite

Salvataggio di query è anche una funzionalità standard di Operations Management Suite e consentono di mantenere le query è stato individuato utili e individuare le tendenze nel sistema.

**Altre informazioni** per trovare informazioni sull'installazione e configurazione di Docker soluzione contenitore [Operations Management Suite](http://microsoft.com/oms), andare a <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.

>[!div class="step-by-step"]
[Precedente](manage-production-docker-environments.md)
[Successivo](../key-takeaways/index.md)
