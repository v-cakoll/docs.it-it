---
title: Modernizzare le app con monitoraggio e telemetria
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Modernizza le tue app con monitoraggio e telemetria
ms.date: 04/30/2018
ms.openlocfilehash: 3d629e89a73c870d4b6396c6b1d0ecbe95b79ead
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393859"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernizzare le app con monitoraggio e telemetria

Quando si esegue un'applicazione nell'ambiente di produzione, è fondamentale disporre di informazioni dettagliate sulle prestazioni dell'applicazione. Si sta esibendo ad alto livello? Gli utenti ricevono errori o l'applicazione è stabile e affidabile? Per garantire che l'applicazione sia disponibile e funzioni come previsto, sono necessari un monitoraggio avanzato delle prestazioni, avvisi potenti e dashboard. È inoltre necessario essere in grado di vedere rapidamente se c'è un problema, determinare quanti clienti sono interessati ed eseguire un'analisi della causa principale per trovare e risolvere il problema.

## <a name="monitor-your-application-with-application-insights"></a>Monitorare l'applicazione con Application InsightsMonitor your application with Application Insights

Application Insights è un servizio APM (Application Performance Management) estensibile per gli sviluppatori Web che lavorano su più piattaforme. che consente di monitorare un'applicazione Web live. Application Insights rileva automaticamente le anomalie delle prestazioni. Include potenti strumenti di analisi che consentono di diagnosticare i problemi e di comprendere le operazioni effettivamente eseguite dagli utenti con l'app. Application Insights è progettato per supportare il miglioramento continuo delle prestazioni e dell'usabilità. Funziona per le app su un'ampia gamma di piattaforme, tra cui .NET, Node.js e J2EE, sia ospitate in locale o nel cloud. Application Insights si integra con i processi DevOps e dispone di punti di connessione a diversi strumenti di sviluppo.

Nella figura 4-10 viene illustrato un esempio di monitoraggio dell'applicazione in Application Insights e di come tali informazioni vengono visualizzate in un dashboard.

![Screenshot del dashboard di monitoraggio di Application Insights.](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

**Figura 4-10.** Dashboard di monitoraggio di Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Monitorare l'infrastruttura Docker con Log Analytics e la relativa soluzione di monitoraggio dei contenitoriMonitor your Docker infrastructure with Log Analytics and its Container Monitoring solution

[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) fa parte della soluzione di monitoraggio generale di [Microsoft Azure.](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview) È anche un servizio in [Operations Management Suite (OMS).](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview) Log Analytics monitora gli ambienti cloud e locali (OMS per locale) per mantenere la disponibilità e le prestazioni. Raccoglie i dati generati dalle risorse negli ambienti cloud e locali e da altri strumenti di monitoraggio per analizzare più origini.

In relazione ai log dell'infrastruttura di Azure, Log Analytics, come servizio di Azure, invii i dati di log e metriche da altri servizi di Azure (tramite Monitoraggio di [Azure),](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)macchine virtuali di Azure, contenitori Docker e infrastrutture cloud locali o di altro tipo. Log Analytics offre una ricerca flessibile nei log e l'analisi out-of-the-box su questi dati. Fornisce strumenti avanzati che è possibile utilizzare per analizzare i dati tra le origini, consente query complesse in tutti i log e può ricevere avvisi in modo proattivo in base alle condizioni specificate. È anche possibile raccogliere dati personalizzati nel repository centrale di Log Analytics, in cui è possibile eseguire query e visualizzarli. È inoltre possibile sfruttare le soluzioni integrate di Log Analytics per ottenere immediatamente informazioni dettagliate sulla sicurezza e le funzionalità dell'infrastruttura.

È possibile accedere a Log Analytics tramite il portale di OMS o il portale di Azure, che viene eseguito in qualsiasi browser e fornire l'accesso alle impostazioni di configurazione e a più strumenti per analizzare e agire sui dati raccolti.

La [soluzione di monitoraggio dei contenitori](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics consente di visualizzare e gestire gli host Docker e Windows Container in un'unica posizione. La soluzione mostra quali contenitori sono in esecuzione, quale immagine del contenitore sono in esecuzione e dove sono in esecuzione i contenitori. È possibile visualizzare informazioni di controllo dettagliate, inclusi i comandi utilizzati con i contenitori. È inoltre possibile risolvere i problemi relativi ai contenitori visualizzando e cercando i log centralizzati, senza dover visualizzare in remoto gli host Docker o Windows. È possibile trovare contenitori che potrebbero essere rumorosi e consumare risorse in eccesso in un host. Inoltre, è possibile visualizzare la CPU centralizzata, la memoria, l'archiviazione e l'utilizzo della rete e le informazioni sulle prestazioni, per i contenitori. Nei computer che eseguono Windows, è possibile centralizzare e confrontare i log dai contenitori Windows Server, Hyper-V e Docker. La soluzione supporta gli agenti di orchestrazione dei contenitori seguenti:

- Docker Swarm

- Controller di dominio/sistema operativo

- Kubernetes

- Red Hat OpenShift

Nella figura 4-11 sono illustrate le relazioni tra i vari host e agenti del contenitore e OMS.

![Screenshot della soluzione di monitoraggio del contenitore log Analytics.](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

**Figura 4-11.** Soluzione di monitoraggio del contenitore di Log AnalyticsLog Analytics Container Monitoring solution

È possibile usare la soluzione di monitoraggio del contenitore Log Analytics per:You can use the Log Analytics Container Monitoring solution to:

- Visualizzare informazioni su tutti gli host contenitore in un'unica posizione.

- Sapere quali contenitori sono in esecuzione, quale immagine sono in esecuzione e dove sono in esecuzione.

- Vedere un audit trail per le azioni sui contenitori.

- Risolvere i problemi visualizzando e cercando i log centralizzati senza accesso remoto agli host Docker.

- Trovare contenitori che potrebbero essere "vicini fastidiosi" e consumare risorse in eccesso in un host.

- Visualizzare informazioni centralizzate su CPU, memoria, archiviazione e utilizzo della rete e sulle prestazioni per i contenitori.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Panoramica del monitoraggio in Microsoft AzureOverview of monitoring in Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Che cos'è Application Insights?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Cos'è Log Analytics?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Soluzione di monitoraggio dei contenitori in Monitoraggio di Azure**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Panoramica di Monitoraggio di Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Informazioni su Operations Management Suite (OMS)**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[precedente](life-cycle-ci-cd-pipelines-devops-tools.md)
