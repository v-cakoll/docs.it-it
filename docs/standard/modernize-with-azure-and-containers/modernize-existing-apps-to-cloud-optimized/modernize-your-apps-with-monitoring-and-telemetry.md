---
title: Modernizzare le app con monitoraggio e telemetria
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Modernizza le tue App con monitoraggio e telemetria
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: a8135031d2879ff377881d246c532573a2149fe7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611653"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="43ed8-103">Modernizzare le app con monitoraggio e telemetria</span><span class="sxs-lookup"><span data-stu-id="43ed8-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="43ed8-104">Quando si esegue un'applicazione nell'ambiente di produzione, è fondamentale che sono disponibili informazioni dettagliate sulle prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43ed8-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="43ed8-105">Sta eseguendo un alto livello?</span><span class="sxs-lookup"><span data-stu-id="43ed8-105">Is it performing at a high level?</span></span> <span data-ttu-id="43ed8-106">Gli utenti ricevono errori o è l'applicazione né stabile né affidabile?</span><span class="sxs-lookup"><span data-stu-id="43ed8-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="43ed8-107">È necessario il monitoraggio avanzato delle prestazioni, potenti avvisi e i dashboard al fine di garantire che l'applicazione sia disponibile e che funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="43ed8-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="43ed8-108">È anche necessario essere in grado di visualizzare rapidamente se si è verificato un problema, determinare quanti clienti sono interessati ed eseguono un'analisi causa radice per trovare e correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="43ed8-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="43ed8-109">Monitorare l'applicazione con Application Insights</span><span class="sxs-lookup"><span data-stu-id="43ed8-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="43ed8-110">Application Insights è un servizio estendibile di Application Performance Management (APM) per gli sviluppatori web che funzionano su più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="43ed8-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="43ed8-111">Usarlo per monitorare l'applicazione web live.</span><span class="sxs-lookup"><span data-stu-id="43ed8-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="43ed8-112">Application Insights rileva automaticamente le anomalie nelle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="43ed8-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="43ed8-113">Include strumenti di analitica potenti che consentono di diagnosticare i problemi e per comprendere ciò che effettivamente eseguite dagli utenti all'app.</span><span class="sxs-lookup"><span data-stu-id="43ed8-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="43ed8-114">Application Insights è progettato per supportare il miglioramento continuo delle prestazioni e usabilità.</span><span class="sxs-lookup"><span data-stu-id="43ed8-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="43ed8-115">Funziona per le App in un'ampia gamma di piattaforme, tra cui .NET, Node. js e J2EE, se ospitato in locale o nel cloud.</span><span class="sxs-lookup"><span data-stu-id="43ed8-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="43ed8-116">Application Insights si integra con i processi DevOps e offre punti di connessione a un'ampia gamma di strumenti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="43ed8-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="43ed8-117">Figura 4-10 illustra un esempio di come Application Insights monitora l'applicazione e come rileva questi approfondimenti a un dashboard.</span><span class="sxs-lookup"><span data-stu-id="43ed8-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Dashboard di monitoraggio di Application Insights](./media/image10.png)

> <span data-ttu-id="43ed8-119">**Figura 4-10.**</span><span class="sxs-lookup"><span data-stu-id="43ed8-119">**Figure 4-10.**</span></span> <span data-ttu-id="43ed8-120">Dashboard di monitoraggio di Application Insights</span><span class="sxs-lookup"><span data-stu-id="43ed8-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="43ed8-121">Monitorare l'infrastruttura di Docker con Log Analitica e la relativa soluzione monitoraggio contenitori</span><span class="sxs-lookup"><span data-stu-id="43ed8-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="43ed8-122">[Azure Log Analitica](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) fa parte il [complessiva soluzione di monitoraggio di Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span><span class="sxs-lookup"><span data-stu-id="43ed8-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="43ed8-123">È anche un servizio in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="43ed8-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="43ed8-124">Log Analitica monitora cloud e negli ambienti locali (per risorse locali, OMS) per garantire disponibilità e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="43ed8-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="43ed8-125">Raccoglie i dati generati dalle risorse negli ambienti cloud e locali e da altri strumenti di monitoraggio per analizzare più origini.</span><span class="sxs-lookup"><span data-stu-id="43ed8-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="43ed8-126">In relazione i log dell'infrastruttura di Azure, Log Analitica, come un servizio di Azure, inserisce i dati di metrica e log da altri servizi di Azure (tramite [monitoraggio di Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), macchine virtuali di Azure, i contenitori Docker e in locale o altre infrastrutture cloud.</span><span class="sxs-lookup"><span data-stu-id="43ed8-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="43ed8-127">Log Analitica offre ricerca flessibile nei log e analitica out-pronte dei dati.</span><span class="sxs-lookup"><span data-stu-id="43ed8-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="43ed8-128">Fornisce strumenti avanzati che è possibile usare per analizzare i dati tra origini, consente query complesse su tutti i log e può generare avvisi proattivi in base alle condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="43ed8-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="43ed8-129">È anche possibile raccogliere dati personalizzati nel repository di Log Analitica centrale, in cui è possibile eseguire una query e la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="43ed8-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="43ed8-130">È anche possibile richiedere i vantaggi delle soluzioni Log Analitica incorporate per ottenere immediatamente informazioni sulla sicurezza e le funzionalità dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="43ed8-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="43ed8-131">È possibile accedere ai Log Analitica tramite il portale OMS o il portale di Azure, che vengono eseguite in qualsiasi browser, e fornire all'utente l'accesso alle impostazioni di configurazione e a diversi strumenti per analizzare e agire sui dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="43ed8-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="43ed8-132">Il [soluzione monitoraggio contenitori](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) nel Log Analitica consente di visualizzare e gestire gli host Docker e un contenitore Windows in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="43ed8-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="43ed8-133">La soluzione indica quali contenitori sono in esecuzione, quale immagine del contenitore eseguono e in cui vengono eseguiti i contenitori.</span><span class="sxs-lookup"><span data-stu-id="43ed8-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="43ed8-134">È possibile visualizzare informazioni dettagliate di controllo, inclusi i comandi che vengono usati con i contenitori.</span><span class="sxs-lookup"><span data-stu-id="43ed8-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="43ed8-135">È anche possibile risolvere i contenitori visualizzando e cercando log centralizzati, senza la necessità di visualizzare in remoto gli host Docker o Windows.</span><span class="sxs-lookup"><span data-stu-id="43ed8-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="43ed8-136">È possibile trovare contenitori che potrebbero essere consumano risorse in eccesso in un host.</span><span class="sxs-lookup"><span data-stu-id="43ed8-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="43ed8-137">Inoltre, è possibile visualizzare centralizzata della CPU, memoria, archiviazione e utilizzo della rete e informazioni sulle prestazioni, per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="43ed8-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="43ed8-138">Nei computer che eseguono Windows, è possibile centralizzare e confrontare i log da Windows Server, Hyper-V e contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="43ed8-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="43ed8-139">La soluzione supporta gli agenti di orchestrazione di contenitori seguenti:</span><span class="sxs-lookup"><span data-stu-id="43ed8-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="43ed8-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="43ed8-140">Docker Swarm</span></span>

- <span data-ttu-id="43ed8-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="43ed8-141">DC/OS</span></span>

- <span data-ttu-id="43ed8-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="43ed8-142">Kubernetes</span></span>

- <span data-ttu-id="43ed8-143">Service Fabric</span><span class="sxs-lookup"><span data-stu-id="43ed8-143">Service Fabric</span></span>

- <span data-ttu-id="43ed8-144">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="43ed8-144">Red Hat OpenShift</span></span>

<span data-ttu-id="43ed8-145">Figura 4-11 vengono mostrate le relazioni tra vari host del contenitore e gli agenti e OMS.</span><span class="sxs-lookup"><span data-stu-id="43ed8-145">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Soluzione monitoraggio contenitori Analitica log](./media/image11.png)

> <span data-ttu-id="43ed8-147">**Figura 4-11.**</span><span class="sxs-lookup"><span data-stu-id="43ed8-147">**Figure 4-11.**</span></span> <span data-ttu-id="43ed8-148">Soluzione monitoraggio contenitori Analitica log</span><span class="sxs-lookup"><span data-stu-id="43ed8-148">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="43ed8-149">È possibile usare la soluzione monitoraggio contenitori Log Analitica per:</span><span class="sxs-lookup"><span data-stu-id="43ed8-149">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="43ed8-150">Visualizzare informazioni su tutti gli host del contenitore in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="43ed8-150">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="43ed8-151">Sapere quali sono i contenitori in esecuzione, quale immagine sono in esecuzione e in cui sono in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="43ed8-151">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="43ed8-152">Vedere un audit trail per le azioni sui contenitori.</span><span class="sxs-lookup"><span data-stu-id="43ed8-152">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="43ed8-153">Risolvere i problemi visualizzando e cercando log centralizzati senza account di accesso remoto per gli host Docker.</span><span class="sxs-lookup"><span data-stu-id="43ed8-153">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="43ed8-154">Trovare i contenitori che potrebbero essere "vicini fastidiosi" e utilizza una quantità eccessiva delle risorse in eccesso in un host.</span><span class="sxs-lookup"><span data-stu-id="43ed8-154">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="43ed8-155">Visualizzazione centralizzata della CPU, memoria, archiviazione e utilizzo della rete e informazioni sulle prestazioni, per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="43ed8-155">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="43ed8-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="43ed8-156">Additional resources</span></span>

- <span data-ttu-id="43ed8-157">**Panoramica sul monitoraggio in Microsoft Azure**</span><span class="sxs-lookup"><span data-stu-id="43ed8-157">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="43ed8-158">**Informazioni su Azure Application Insights**</span><span class="sxs-lookup"><span data-stu-id="43ed8-158">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="43ed8-159">**Che cos'è Log Analitica?**</span><span class="sxs-lookup"><span data-stu-id="43ed8-159">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="43ed8-160">**Soluzione monitoraggio contenitori in Monitoraggio di Azure**</span><span class="sxs-lookup"><span data-stu-id="43ed8-160">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="43ed8-161">**Panoramica del monitoraggio di Azure**</span><span class="sxs-lookup"><span data-stu-id="43ed8-161">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="43ed8-162">**Novità di Operations Management Suite (OMS)?**</span><span class="sxs-lookup"><span data-stu-id="43ed8-162">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

- <span data-ttu-id="43ed8-163">**Monitoraggio dei contenitori di Windows Server in Service Fabric con OMS**</span><span class="sxs-lookup"><span data-stu-id="43ed8-163">**Monitoring Windows Server containers in Service Fabric with OMS**</span></span>

<https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver>

>[!div class="step-by-step"]
><span data-ttu-id="43ed8-164">[Precedente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Successivo](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="43ed8-164">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
