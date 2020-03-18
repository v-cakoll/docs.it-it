---
title: Monitorare i servizi delle applicazioni nei contenitori
description: Informazioni su alcuni aspetti fondamentali del monitoraggio delle architetture dei contenitori
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673458"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="59028-103">Monitorare i servizi delle applicazioni nei contenitori</span><span class="sxs-lookup"><span data-stu-id="59028-103">Monitor containerized application services</span></span>

<span data-ttu-id="59028-104">È fondamentale per le applicazioni suddivise in più contenitori e microservizi avere un modo per monitorare e analizzare il comportamento dell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="59028-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="59028-105">Monitoraggio di Azure</span><span class="sxs-lookup"><span data-stu-id="59028-105">Azure Monitor</span></span>

<span data-ttu-id="59028-106">[Monitoraggio di Azure](https://azure.microsoft.com/services/monitor/) è un servizio di analisi estendibile che consente di monitorare un'applicazione attiva.</span><span class="sxs-lookup"><span data-stu-id="59028-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="59028-107">Il servizio consente di rilevare e diagnosticare problemi di prestazioni e individuare le operazioni effettivamente eseguite dagli utenti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59028-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="59028-108">Il servizio è progettato per gli sviluppatori con lo scopo di favorire un continuo miglioramento delle prestazioni e dell'usabilità dei servizi o delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="59028-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="59028-109">Monitoraggio di Azure può essere usato sia con app Web o servizi che con app autonome in numerose piattaforme come .NET, Java, Node.js e molte altre piattaforme, ospitate in locale o nel cloud.</span><span class="sxs-lookup"><span data-stu-id="59028-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="59028-110">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="59028-110">Additional resources</span></span>

- <span data-ttu-id="59028-111">**Panoramica di Monitoraggio di AzureOverview of Azure Monitor** </span><span class="sxs-lookup"><span data-stu-id="59028-111">**Overview of Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="59028-112">**Che cos'è Application Insights?**</span><span class="sxs-lookup"><span data-stu-id="59028-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="59028-113">**Cosa sono le metriche di Monitoraggio di Azure?**</span><span class="sxs-lookup"><span data-stu-id="59028-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="59028-114">**Soluzione di monitoraggio dei contenitori in Monitoraggio di AzureContainer Monitoring solution in Azure Monitor** </span><span class="sxs-lookup"><span data-stu-id="59028-114">**Container Monitoring solution in Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="59028-115">Servizi di sicurezza e backup</span><span class="sxs-lookup"><span data-stu-id="59028-115">Security and backup services</span></span>

<span data-ttu-id="59028-116">Poiché esistono molte operazioni di supporto con numerosi dettagli che è necessario gestire per garantire che le applicazioni e l'infrastruttura siano nelle condizioni ottimali per rispondere alle esigenze aziendali e la situazione diventa più complessa per i microservizi, è necessario avere a disposizione viste d'insieme e viste dettagliate per eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="59028-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="59028-117">Azure include gli strumenti per gestire e offrire una vista unificata dei quattro aspetti critici delle risorse del cloud e locali:</span><span class="sxs-lookup"><span data-stu-id="59028-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="59028-118">**Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="59028-118">**Security**.</span></span> <span data-ttu-id="59028-119">Con [Centro sicurezza di Azure](https://azure.microsoft.com/services/security-center/).</span><span class="sxs-lookup"><span data-stu-id="59028-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="59028-120">Ottenere visibilità completa e controllo della sicurezza di macchine virtuali, app e carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="59028-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="59028-121">Centralizzare la gestione dei criteri di sicurezza e integrare i processi e gli strumenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="59028-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="59028-122">Rilevare le minacce effettive con analisi avanzata.</span><span class="sxs-lookup"><span data-stu-id="59028-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="59028-123">**Backup**.</span><span class="sxs-lookup"><span data-stu-id="59028-123">**Backup**.</span></span> <span data-ttu-id="59028-124">Con [Backup di Azure](https://azure.microsoft.com/services/backup/).</span><span class="sxs-lookup"><span data-stu-id="59028-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="59028-125">Evitare costose interruzioni dell'attività aziendale, raggiungere gli obiettivi di conformità e proteggere i dati da ransomware ed errori umani.</span><span class="sxs-lookup"><span data-stu-id="59028-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="59028-126">Mantenere crittografati i dati di backup in transito o inattivi.</span><span class="sxs-lookup"><span data-stu-id="59028-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="59028-127">Garantire un accesso basato sull'autenticazione a più fattori per impedire l'uso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="59028-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="59028-128">**Risorse locali**.</span><span class="sxs-lookup"><span data-stu-id="59028-128">**On-premises resources**.</span></span> <span data-ttu-id="59028-129">Con un [cloud ibrido coerente](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span><span class="sxs-lookup"><span data-stu-id="59028-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="59028-130">[Successivo](manage-production-docker-environments.md)
>[precedente](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="59028-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
