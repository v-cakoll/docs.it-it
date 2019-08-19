---
title: Modernizzare le app con monitoraggio e telemetria
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Modernizza le tue app con monitoraggio e telemetria
ms.date: 04/30/2018
ms.openlocfilehash: 5bffb336234f63dca150acc9ef31f9efa2e3937b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578174"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernizzare le app con monitoraggio e telemetria

Quando si esegue un'applicazione nell'ambiente di produzione, è fondamentale avere informazioni approfondite sulle prestazioni dell'applicazione. Viene eseguita a un livello elevato? Gli utenti ricevono errori o l'applicazione è stabile e affidabile? Sono necessari funzionalità avanzate di monitoraggio delle prestazioni, avvisi avanzati e dashboard che consentono di garantire che l'applicazione sia disponibile e funzioni come previsto. È anche necessario essere in grado di verificare rapidamente se si è verificato un problema, determinare il numero di clienti interessati ed eseguire un'analisi della causa radice per individuare e risolvere il problema.

## <a name="monitor-your-application-with-application-insights"></a>Monitorare l'applicazione con Application Insights

Application Insights è un servizio estendibile di gestione delle prestazioni delle applicazioni (APM) per sviluppatori Web che lavorano su più piattaforme. che consente di monitorare un'applicazione Web live. Application Insights rileva automaticamente le anomalie delle prestazioni. Include potenti strumenti di analisi che consentono di diagnosticare i problemi e di comprendere le operazioni effettivamente eseguite dagli utenti con l'app. Application Insights è progettato per consentire un miglioramento continuo delle prestazioni e dell'usabilità. Funziona per le app in un'ampia gamma di piattaforme, tra cui .NET, node. js e J2EE, indipendentemente dal fatto che sia ospitato in locale o nel cloud. Application Insights si integra con i processi DevOps e offre punti di connessione a un'ampia gamma di strumenti di sviluppo.

La figura 4-10 illustra un esempio di come Application Insights monitora l'applicazione e il modo in cui le informazioni vengono riportate in un dashboard.

![Dashboard di monitoraggio Application Insights](./media/image10.png)

> **Figura 4-10.** Dashboard di monitoraggio Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Monitorare l'infrastruttura Docker con Log Analytics e la soluzione di monitoraggio dei contenitori

[Azure log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) fa parte della [soluzione di monitoraggio complessiva Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). È anche un servizio di [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analytics monitora gli ambienti cloud e locali (OMS per l'ambiente locale) per garantire la disponibilità e le prestazioni. Raccoglie i dati generati dalle risorse negli ambienti cloud e locali e da altri strumenti di monitoraggio per analizzare più origini.

In relazione ai log dell'infrastruttura di Azure, Log Analytics, come servizio di Azure, inserisce dati di log e metriche da altri servizi di Azure (tramite [monitoraggio di Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), macchine virtuali di Azure, contenitori Docker e infrastrutture locali o altre infrastrutture cloud. Log Analytics offre una ricerca dei log flessibile e un'analisi predefinita per i dati. Fornisce strumenti avanzati che è possibile usare per analizzare i dati tra origini, consente query complesse in tutti i log e può inviare avvisi in modo proattivo in base a condizioni specificate. È anche possibile raccogliere dati personalizzati nel repository Log Analytics centrale, in cui è possibile eseguire query e visualizzarli. Puoi anche sfruttare i vantaggi delle soluzioni Log Analytics predefinite per ottenere immediatamente informazioni dettagliate sulla sicurezza e sulle funzionalità dell'infrastruttura.

È possibile accedere a Log Analytics tramite il portale di OMS o i portale di Azure, eseguiti in qualsiasi browser, e fornire l'accesso alle impostazioni di configurazione e a più strumenti per analizzare e agire sui dati raccolti.

La [soluzione di monitoraggio dei contenitori](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in log Analytics consente di visualizzare e gestire gli host del contenitore Docker e Windows in un'unica posizione. La soluzione Mostra i contenitori in esecuzione, l'immagine del contenitore in esecuzione e i contenitori in esecuzione. È possibile visualizzare informazioni dettagliate sul controllo, inclusi i comandi usati con i contenitori. È anche possibile risolvere i problemi relativi ai contenitori visualizzando e cercando log centralizzati, senza la necessità di visualizzare in remoto gli host Docker o Windows. È possibile trovare i contenitori che potrebbero essere rumorosi e che utilizzano risorse in eccesso in un host. Inoltre, per i contenitori è possibile visualizzare informazioni centralizzate su CPU, memoria, archiviazione e utilizzo della rete e sulle prestazioni. Nei computer che eseguono Windows, è possibile centralizzare e confrontare i log dai contenitori Windows Server, Hyper-V e Docker. La soluzione supporta gli agenti di orchestrazione dei contenitori seguenti:

- Docker Swarm

- Controller di dominio/sistema operativo

- kubernetes

- Red Hat OpenShift

La figura 4-11 Mostra le relazioni tra vari host e agenti del contenitore e OMS.

![Soluzione di monitoraggio del contenitore Log Analytics](./media/image11.png)

> **Figura 4-11.** Soluzione di monitoraggio del contenitore Log Analytics

È possibile usare la soluzione di monitoraggio dei contenitori Log Analytics per:

- Vedere le informazioni su tutti gli host del contenitore in un'unica posizione.

- Conoscere i contenitori in esecuzione, l'immagine in esecuzione e la posizione in cui sono in esecuzione.

- Vedere un audit trail per le azioni sui contenitori.

- Risolvere i problemi visualizzando e cercando log centralizzati senza account di accesso remoto per gli host docker.

- Individuare i contenitori che potrebbero essere "adiacenti rumorosi" e consumare risorse in eccesso in un host.

- Visualizzazione di CPU, memoria, archiviazione e utilizzo della rete centralizzata e informazioni sulle prestazioni per i contenitori.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Panoramica del monitoraggio in Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Informazioni su Azure Application Insights**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Che cos'è Log Analytics?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Soluzione di monitoraggio del contenitore in monitoraggio di Azure**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Panoramica di monitoraggio di Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Che cos'è Operations Management Suite (OMS)?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[Precedente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Successivo](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
