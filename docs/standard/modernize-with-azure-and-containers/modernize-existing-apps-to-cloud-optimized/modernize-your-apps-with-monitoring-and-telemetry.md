---
title: Modernizzare le app con monitoraggio e telemetria
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Modernizza le tue App con monitoraggio e telemetria
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: cd54861600127191b852e0a966baae6e0fe7914e
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613876"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernizzare le app con monitoraggio e telemetria

Quando si esegue un'applicazione nell'ambiente di produzione, è fondamentale che sono disponibili informazioni dettagliate sulle prestazioni dell'applicazione. Sta eseguendo un alto livello? Gli utenti ricevono errori o è l'applicazione né stabile né affidabile? È necessario il monitoraggio avanzato delle prestazioni, potenti avvisi e i dashboard al fine di garantire che l'applicazione sia disponibile e che funzioni come previsto. È anche necessario essere in grado di visualizzare rapidamente se si è verificato un problema, determinare quanti clienti sono interessati ed eseguono un'analisi causa radice per trovare e correggere il problema.

## <a name="monitor-your-application-with-application-insights"></a>Monitorare l'applicazione con Application Insights

Application Insights è un servizio estendibile di Application Performance Management (APM) per gli sviluppatori web che funzionano su più piattaforme. Usarlo per monitorare l'applicazione web live. Application Insights rileva automaticamente le anomalie nelle prestazioni. Include strumenti di analitica potenti che consentono di diagnosticare i problemi e per comprendere ciò che effettivamente eseguite dagli utenti all'app. Application Insights è progettato per supportare il miglioramento continuo delle prestazioni e usabilità. Funziona per le App in un'ampia gamma di piattaforme, tra cui .NET, Node. js e J2EE, se ospitato in locale o nel cloud. Application Insights si integra con i processi DevOps e offre punti di connessione a un'ampia gamma di strumenti di sviluppo.

Figura 4-10 illustra un esempio di come Application Insights monitora l'applicazione e come rileva questi approfondimenti a un dashboard.

![Dashboard di monitoraggio di Application Insights](./media/image10.png)

> **Figura 4-10.** Dashboard di monitoraggio di Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Monitorare l'infrastruttura di Docker con Log Analitica e la relativa soluzione monitoraggio contenitori

[Azure Log Analitica](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) fa parte il [complessiva soluzione di monitoraggio di Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). È anche un servizio in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analitica monitora cloud e negli ambienti locali (per risorse locali, OMS) per garantire disponibilità e prestazioni. Raccoglie i dati generati dalle risorse negli ambienti cloud e locali e da altri strumenti di monitoraggio per analizzare più origini.

In relazione i log dell'infrastruttura di Azure, Log Analitica, come un servizio di Azure, inserisce i dati di metrica e log da altri servizi di Azure (tramite [monitoraggio di Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), macchine virtuali di Azure, i contenitori Docker e in locale o altre infrastrutture cloud. Log Analitica offre ricerca flessibile nei log e analitica out-pronte dei dati. Fornisce strumenti avanzati che è possibile usare per analizzare i dati tra origini, consente query complesse su tutti i log e può generare avvisi proattivi in base alle condizioni specificate. È anche possibile raccogliere dati personalizzati nel repository di Log Analitica centrale, in cui è possibile eseguire una query e la visualizzazione. È anche possibile richiedere i vantaggi delle soluzioni Log Analitica incorporate per ottenere immediatamente informazioni sulla sicurezza e le funzionalità dell'infrastruttura.

È possibile accedere ai Log Analitica tramite il portale OMS o il portale di Azure, che vengono eseguite in qualsiasi browser, e fornire all'utente l'accesso alle impostazioni di configurazione e a diversi strumenti per analizzare e agire sui dati raccolti.

Il [soluzione monitoraggio contenitori](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) nel Log Analitica consente di visualizzare e gestire gli host Docker e un contenitore Windows in un'unica posizione. La soluzione indica quali contenitori sono in esecuzione, quale immagine del contenitore eseguono e in cui vengono eseguiti i contenitori. È possibile visualizzare informazioni dettagliate di controllo, inclusi i comandi che vengono usati con i contenitori. È anche possibile risolvere i contenitori visualizzando e cercando log centralizzati, senza la necessità di visualizzare in remoto gli host Docker o Windows. È possibile trovare contenitori che potrebbero essere consumano risorse in eccesso in un host. Inoltre, è possibile visualizzare centralizzata della CPU, memoria, archiviazione e utilizzo della rete e informazioni sulle prestazioni, per i contenitori. Nei computer che eseguono Windows, è possibile centralizzare e confrontare i log da Windows Server, Hyper-V e contenitori Docker. La soluzione supporta gli agenti di orchestrazione di contenitori seguenti:

-   Docker Swarm

-   DC/OS

-   Kubernetes

-   Service Fabric

-   Red Hat OpenShift

Figura 4-11 vengono mostrate le relazioni tra vari host del contenitore e gli agenti e OMS.

![Soluzione monitoraggio contenitori Analitica log](./media/image11.png)

> **Figura 4-11.** Soluzione monitoraggio contenitori Analitica log

È possibile usare la soluzione monitoraggio contenitori Log Analitica per:

-   Visualizzare informazioni su tutti gli host del contenitore in un'unica posizione.

-   Sapere quali sono i contenitori in esecuzione, quale immagine sono in esecuzione e in cui sono in esecuzione.

-   Vedere un audit trail per le azioni sui contenitori.

-   Risolvere i problemi visualizzando e cercando log centralizzati senza account di accesso remoto per gli host Docker.

-   Trovare i contenitori che potrebbero essere "vicini fastidiosi" e utilizza una quantità eccessiva delle risorse in eccesso in un host.

-   Visualizzazione centralizzata della CPU, memoria, archiviazione e utilizzo della rete e informazioni sulle prestazioni, per i contenitori.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Panoramica sul monitoraggio in Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

-   **Informazioni su Azure Application Insights**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

-   **Che cos'è Log Analitica?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

-   **Soluzione monitoraggio contenitori in Monitoraggio di Azure**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

-   **Panoramica del monitoraggio di Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

-   **Novità di Operations Management Suite (OMS)?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

-   **Monitoraggio dei contenitori di Windows Server in Service Fabric con OMS**

<https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver>

>[!div class="step-by-step"]
>[Precedente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Successivo](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
