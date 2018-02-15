---
title: Modernizzare le app con monitoraggio e telemetria
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Modernizzare le app con monitoraggio e telemetria
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1535951eb648deab17cf8c2fe64db6ddf7df4cb5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernizzare le app con monitoraggio e telemetria

Quando si esegue un'applicazione nell'ambiente di produzione, è fondamentale disporre di informazioni dettagliate delle prestazioni dell'applicazione. Sta eseguendo un livello elevato? Gli utenti ricevono errori o l'applicazione stabile e affidabile? È necessario il monitoraggio delle prestazioni avanzate, potente avvisi e i dashboard per garantire che l'applicazione sia disponibile e verrà eseguito come previsto. È inoltre necessario essere in grado di verificare rapidamente se esiste un problema, determinare il numero di clienti interessato ed esegue un'analisi causa radice per individuare e correggere il problema.

## <a name="monitor-your-application-with-application-insights"></a>Monitorare l'applicazione con Application Insights

Application Insights è un servizio di gestione delle prestazioni dell'applicazione (APM) estendibile per gli sviluppatori web che lavorano su più piattaforme. Utilizzarlo per monitorare l'applicazione web in tempo reale. Application Insights rileva automaticamente le anomalie delle prestazioni. Include inoltre strumenti potenti analitica per facilitare la diagnosi di problemi e per comprendere cosa gli utenti effettivamente eseguire con l'app. Application Insights è progettato per migliorare continuamente le prestazioni e usabilità. Funziona per le app su una vasta gamma di piattaforme, tra cui .NET, Node.js e J2EE, se ospitato in locale o nel cloud. Application Insights si integra con i processi di DevOps e dispone di punti di connessione a un'ampia gamma di strumenti di sviluppo.

Figura 4-10 è illustrato un esempio di come Application Insights consente di monitorare l'applicazione e come espone tali informazioni a un dashboard.

![Dashboard di monitoraggio di Application Insights](./media/image10.png)

> **Figura 4-10.** Dashboard di monitoraggio di Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Monitorare l'infrastruttura di Docker con Log Analitica e la soluzione di monitoraggio contenitore

[Azure Log Analitica](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) fa parte di [complessive nella soluzione di monitoraggio di Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). È anche un servizio [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analitica monitora cloud e in ambienti locali (OMS per on-premise) per preservare la disponibilità e prestazioni. Vengono raccolti i dati generati dalle risorse negli ambienti di cloud e locali e di altri strumenti di monitoraggio per fornire analisi in più origini.

In relazione i log dell'infrastruttura di Azure, Log Analitica, come un servizio di Azure, inserisce dati di metrica e di log da altri servizi di Azure (tramite [Monitor Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), macchine virtuali di Azure, contenitori di Docker e altre infrastrutture di cloud o locali. Log Analitica offre ricerca nei log flessibile e analitica out-predefinito all'inizio di questo tipo di dati. Fornisce strumenti avanzati che è possibile utilizzare per analizzare i dati tra origini e consente query complesse in tutti i log, mentre è possibile verificare in modo proattivo in base alle condizioni specificate. È anche possibile raccogliere dati personalizzati nel repository Log Analitica centrale, in cui è possibile eseguire una query e visualizzarla. È anche possibile sfruttare le soluzioni predefinite Analitica di Log per ottenere immediatamente informazioni dettagliate della sicurezza in e le funzionalità dell'infrastruttura.

È possibile accedere a Analitica Log tramite il portale di OMS o il portale di Azure, che vengono eseguite in qualsiasi browser, e fornire all'utente l'accesso alle impostazioni di configurazione e con più strumenti per analizzare e agire sui dati raccolti.

Il [soluzione di monitoraggio contenitore](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Analitica Log consente visualizzare e gestire gli host Docker e contenitore di Windows in un'unica posizione. La soluzione Mostra i contenitori sono in esecuzione, quali immagini contenitore vengono eseguiti e in cui vengono eseguiti i contenitori. È possibile visualizzare informazioni dettagliate di controllo, inclusi i comandi che vengono utilizzati con i contenitori. È anche possibile risolvere contenitori mediante la visualizzazione e la ricerca di log centralizzato, senza la necessità di visualizzare in remoto host Docker o di Windows. È possibile trovare i contenitori che potrebbero essere rumore e dispendiosa in termini di quantità eccessiva di risorse in un host. Inoltre, è possibile visualizzare centralizzata della CPU, memoria, archiviazione e utilizzo della rete e informazioni sulle prestazioni, per i contenitori. Nei computer che eseguono Windows, è possibile centralizzare e confrontare i registri di Windows Server, Hyper-V e i contenitori di Docker. La soluzione supporta orchestrators il contenitore seguente:

-   Sciame docker

-   DC/OS

-   Kubernetes

-   Service Fabric

-   Red Hat OpenShift

Figura 4-11 Mostra le relazioni tra vari host contenitore e gli agenti e OMS.

![Soluzione di monitoraggio di contenitore Analitica di log](./media/image11.png)

> **Figura 4-11.** Soluzione di monitoraggio di contenitore Analitica di log

È possibile utilizzare la soluzione di monitoraggio del Log Analitica contenitore per:

-   Visualizzare informazioni su tutti gli host contenitore in un'unica posizione.

-   I contenitori sono in esecuzione, quali immagini che siano in esecuzione e in cui vengono eseguiti.

-   Vedere un audit trail per le azioni sui contenitori.

-   Risoluzione dei problemi con la visualizzazione e la ricerca di log centralizzato senza account di accesso remoto agli host Docker.

-   Trovare i contenitori che potrebbero essere "rumore router adiacenti" e stia utilizzando una quantità eccessiva di risorse in un host.

-   Consente di visualizzare centralizzata della CPU, memoria, archiviazione e utilizzo della rete e informazioni sulle prestazioni, per i contenitori.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Panoramica di monitoraggio in Microsoft Azure**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   **Che cos'è Application Insights?**

[https://docs.microsoft.com/azure/application-insights/app-insights-overview](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   **Che cos'è Analitica Log?**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-overview](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   **Soluzione di monitoraggio di contenitore in Log Analitica**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-containers](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   **Panoramica di monitoraggio di Azure**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   **Che cos'è Operations Management Suite (OMS)?**

[https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   **Monitoraggio di contenitori di Windows Server nell'infrastruttura di servizio con OMS**

[https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
[Precedente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Successivo](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
