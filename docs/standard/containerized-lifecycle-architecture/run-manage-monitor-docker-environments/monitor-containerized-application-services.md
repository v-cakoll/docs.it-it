---
title: Monitorare i servizi delle applicazioni nei contenitori
description: Informazioni su alcuni aspetti fondamentali del monitoraggio di architetture di contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4553a35c8db6cfc46187525ef2ffc65cb3ba07c9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922746"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="62485-103">Monitorare i servizi delle applicazioni nei contenitori</span><span class="sxs-lookup"><span data-stu-id="62485-103">Monitor containerized application services</span></span>

<span data-ttu-id="62485-104">È fondamentale per le applicazioni di suddividere in più contenitori e microservizi avere un modo per monitorare e analizzare il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62485-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="62485-105">Monitoraggio di Azure</span><span class="sxs-lookup"><span data-stu-id="62485-105">Azure Monitor</span></span>

<span data-ttu-id="62485-106">[Monitoraggio di Azure](https://azure.microsoft.com/services/monitor/) è un servizio di analitica estendibile che consente di monitorare l'applicazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="62485-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="62485-107">Consente di rilevare e diagnosticare i problemi di prestazioni e comprendere ciò che effettivamente eseguite dagli utenti all'app.</span><span class="sxs-lookup"><span data-stu-id="62485-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="62485-108">È progettato per gli sviluppatori, con lo scopo di aiutarti a migliorare continuamente le prestazioni e usabilità del servizi o applicazioni.</span><span class="sxs-lookup"><span data-stu-id="62485-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="62485-109">Monitoraggio di Azure funziona con web/servizi e autonoma delle App su una vasta gamma di piattaforme quali .NET, Java, Node. js e molte altre piattaforme, ospitate in locale o nel cloud.</span><span class="sxs-lookup"><span data-stu-id="62485-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="62485-110">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="62485-110">Additional resources</span></span>

- <span data-ttu-id="62485-111">**Panoramica del monitoraggio di Azure** \\</span><span class="sxs-lookup"><span data-stu-id="62485-111">**Overview of Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="62485-112">**Informazioni su Azure Application Insights**</span><span class="sxs-lookup"><span data-stu-id="62485-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="62485-113">**Che cos'è metriche di monitoraggio di Azure?**</span><span class="sxs-lookup"><span data-stu-id="62485-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="62485-114">**Soluzione monitoraggio contenitori in Monitoraggio di Azure** \\</span><span class="sxs-lookup"><span data-stu-id="62485-114">**Container Monitoring solution in Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="62485-115">Servizi di protezione e backup</span><span class="sxs-lookup"><span data-stu-id="62485-115">Security and backup services</span></span>

<span data-ttu-id="62485-116">Esistono molte attività di supporto con un numero elevato di dettagli che è necessario gestire per assicurarsi che l'infrastruttura e applicazioni siano in condizione di notch superiore per supportare le esigenze aziendali e la situazione diventa più complessa nell'area di autenticazione microservizi, pertanto è necessario un modo per avere visualizzazioni generali e dettagliate quando è necessario intervenire.</span><span class="sxs-lookup"><span data-stu-id="62485-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="62485-117">Azure offre gli strumenti per gestire e fornire una vista unificata dei quattro aspetti critici di risorse del cloud e locali:</span><span class="sxs-lookup"><span data-stu-id="62485-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="62485-118">**Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="62485-118">**Security**.</span></span> <span data-ttu-id="62485-119">Con [Centro sicurezza di Azure](https://azure.microsoft.com/services/security-center/).</span><span class="sxs-lookup"><span data-stu-id="62485-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="62485-120">Ottenere visibilità completa e il controllo della sicurezza delle macchine virtuali, App e carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="62485-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="62485-121">Centralizzare la gestione dei criteri di sicurezza e integra gli strumenti e processi esistenti.</span><span class="sxs-lookup"><span data-stu-id="62485-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="62485-122">Rilevare le minacce effettive con analitica avanzata.</span><span class="sxs-lookup"><span data-stu-id="62485-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="62485-123">**Backup**.</span><span class="sxs-lookup"><span data-stu-id="62485-123">**Backup**.</span></span> <span data-ttu-id="62485-124">Con [Backup di Azure](https://azure.microsoft.com/services/backup/).</span><span class="sxs-lookup"><span data-stu-id="62485-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="62485-125">Evitare interruzioni aziendali costose, soddisfano gli obiettivi di conformità e proteggere i dati da ransomware ed errori umani.</span><span class="sxs-lookup"><span data-stu-id="62485-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="62485-126">Mantenere i dati di backup crittografati in transito e inattivi.</span><span class="sxs-lookup"><span data-stu-id="62485-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="62485-127">Verificare l'accesso in base a multi-factor authentication per evitare l'uso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="62485-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="62485-128">**Le risorse locali**.</span><span class="sxs-lookup"><span data-stu-id="62485-128">**On-premises resources**.</span></span> <span data-ttu-id="62485-129">Con [un cloud ibrido davvero coerente](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span><span class="sxs-lookup"><span data-stu-id="62485-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="62485-130">[Precedente](manage-production-docker-environments.md)
>[Successivo](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="62485-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
