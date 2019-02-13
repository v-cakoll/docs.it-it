---
title: Monitorare i servizi delle applicazioni in contenitori
description: Informazioni su alcuni aspetti fondamentali del monitoraggio di architetture di contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: e1be3c36f17fc5f85c9deacaa29031cee45226cc
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221186"
---
# <a name="monitor-containerized-application-services"></a>Monitorare i servizi delle applicazioni in contenitori

È fondamentale per le applicazioni di suddividere in più contenitori e microservizi avere un modo per monitorare e analizzare il comportamento dell'applicazione.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) è un servizio di analitica estendibile che consente di monitorare l'applicazione in tempo reale. Consente di rilevare e diagnosticare i problemi di prestazioni e comprendere ciò che effettivamente eseguite dagli utenti all'app. È progettato per gli sviluppatori, con lo scopo di aiutarti a migliorare continuamente le prestazioni e usabilità del servizi o applicazioni. Application Insights funziona con web/servizi e autonoma delle App su una vasta gamma di piattaforme quali .NET, Java, Node. js e molte altre piattaforme, ospitate in locale o nel cloud.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Analizzare le app Docker in ambienti di controllo di qualità con Application Insights

Per quanto attiene a Docker, è possibile grafico gli eventi del ciclo di vita e i contatori delle prestazioni da contenitori Docker in Application Insights. È sufficiente eseguire la [immagine Docker di Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) come un contenitore nell'host che verrà visualizzati i contatori delle prestazioni per l'host e per le altre immagini di Docker. Questa immagine Docker di Application Insights (figura 6 - 1) consente di monitorare le applicazioni in contenitori, raccogliendo i dati di telemetria sulle prestazioni e l'attività dell'host Docker (vale a dire, le macchine virtuali Linux), i contenitori Docker e le applicazioni in esecuzione all'interno di essi.

![esempio](./media/image1.png)

Figura 6-1: Monitoraggio dei contenitori e host Docker di Application Insights

Quando si esegue la [immagine Docker di Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) nell'host Docker, trarre vantaggio da quanto segue:

-   Dati di telemetria su tutti i contenitori in esecuzione nell'host del ciclo di vita, avviare, arrestare e così via.

-   Contatori delle prestazioni per tutti i contenitori: CPU, memoria, utilizzo della rete e altro ancora.

-   Se è installato anche [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) nelle App in esecuzione nei contenitori, tutti i dati di telemetria di tali App avranno proprietà aggiuntive che identificano il contenitore e il computer host. Quindi, ad esempio, se si dispone di istanze di un'app in esecuzione in più di un host, facilmente sarà in grado di filtrare i dati di telemetria dell'app dall'host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Configurazione di Application Insights per monitorare applicazioni Docker e l'host Docker

Per creare una risorsa di Application Insights, seguire le istruzioni riportate negli articoli presentati nell'elenco che segue. Portale di Azure creerà lo script necessario per l'utente.

-   **Monitorare le applicazioni Docker in Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Immagine di Docker Insights dell'applicazione in Docker Hub e Github:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) E <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Configurare Application Insights per ASP.NET:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights per pagine web:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](https://microsoft.com/oms) è una soluzione di gestione IT semplificata che fornisce log analitica, automazione, backup e site recovery. In base [query](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite, è possibile generare [avvisi](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) e impostare monitoraggio e aggiornamento tramite [automazione di Azure](https://docs.microsoft.com/azure/automation/). Si integra inoltre perfettamente con le soluzioni di gestione esistenti per fornire una singola visualizzazione di Pannello di controllo. Operations Management Suite aiuta a gestire e proteggere on-premises e infrastruttura cloud.

### <a name="operations-management-suitehttpsmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](https://microsoft.com/oms) soluzione contenitori per Docker

Oltre a fornire importanti servizi autonomamente, la soluzione contenitori di Operations Management Suite possono gestire e monitorare host e contenitori Docker mostrando le informazioni sull'ubicazione di contenitori e host di contenitori, quali contenitori sono in esecuzione o di errore e i log di daemon e contenitori Docker inviati a *stdout* e *stderr*. La soluzione mostra anche le metriche di prestazioni, tra cui CPU, memoria, rete e archiviazione, per il contenitore e gli host per semplificare la risoluzione dei problemi e trovare i contenitori che possono influire negativamente sulle prestazioni nelle vicinanze.

![](./media/image2.png)

Figura 6-2: Informazioni sui contenitori di Docker illustrato da Operations Management Suite

Application Insights e Operations Management Suite si concentrano sul monitoraggio attività. Application Insights, tuttavia, maggiormente incentrata sul monitoraggio di applicazioni autonomamente grazie alle relative SDK in esecuzione all'interno dell'app. Tuttavia, Operations Management Suite è molto più incentrato sull'infrastruttura per gli host, oltre che offre analisi approfondite dei log su larga scala offrendo un sistema molto flessibile basato sui dati/query di ricerca.

Poiché Operations Management Suite viene implementata come un servizio basato sul cloud, è possibile che in esecuzione rapidamente con un investimento minimo nei servizi di infrastruttura. Nuove funzionalità sono disponibili automaticamente, risparmiando la fatica di manutenzione periodica e aggiornare i costi.

Usa Operations Management Suite contenitore soluzione, è possibile eseguire le operazioni seguenti:

-   Centralizzare e correlare milioni di log dai contenitori di Docker su vasta scala

-   Visualizzare informazioni su tutti gli host del contenitore in un'unica posizione

-   Sapere quali sono i contenitori in esecuzione, quale immagine sono in esecuzione e in cui sono in esecuzione

-   Diagnosticare rapidamente i contenitori di "noisy neighbor" che possono causare problemi in host del contenitore

-   Vedere un audit trail per le azioni sui contenitori

-   Risolvere i problemi visualizzando e cercando log centralizzati senza la comunicazione remota e gli host Docker

-   Trovare i contenitori che potrebbero essere "vicini fastidiosi" e dispendiosa in termini di quantità eccessiva di risorse in un host

-   Visualizzazione centralizzata della CPU, memoria, archiviazione e informazioni sull'utilizzo e prestazioni di rete per i contenitori

-   Generare i contenitori Docker con automazione di Azure di test

È possibile visualizzare informazioni sulle prestazioni tramite l'esecuzione di query come tipo = Perf, come illustrato nella figura 6-3.

![DockerPerfMetricsView](./media/image3.png){width="5.78625in" height="3.25in"}

Figura 6-3: Metriche delle prestazioni di host Docker illustrato da Operations Management Suite

Il salvataggio delle query è una funzionalità standard in Operations Management Suite e consentono di mantenere le query si utili e si individuano le tendenze nel sistema.

**Altre informazioni** per trovare informazioni sull'installazione e configurazione di Docker soluzione contenitori in [Operations Management Suite](https://microsoft.com/oms), andare a <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.

>[!div class="step-by-step"]
>[Precedente](manage-production-docker-environments.md)
>[Successivo](../key-takeaways/index.md)