---
title: Eseguire la migrazione a scenari di cloud ibrido
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Eseguire la migrazione a scenari di cloud ibrido
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/2/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a2fc5a2118736d3491a5a0731e47c697edd674f1
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="30daa-103">Eseguire la migrazione a scenari di cloud ibrido</span><span class="sxs-lookup"><span data-stu-id="30daa-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="30daa-104">Non è possibile eseguire la migrazione di alcune organizzazioni e aziende alcune delle proprie applicazioni per cloud pubblici, come Microsoft Azure o qualsiasi altro cloud pubblico a causa di normative o ai propri criteri.</span><span class="sxs-lookup"><span data-stu-id="30daa-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="30daa-105">Tuttavia, è probabile che un'organizzazione potrebbe traggono profitto dalla presenza di alcune delle proprie applicazioni nel cloud pubblico e altre applicazioni in locale.</span><span class="sxs-lookup"><span data-stu-id="30daa-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="30daa-106">Ma può provocare un ambiente misto complessità eccessiva in ambienti a causa di diverse piattaforme e tecnologie utilizzate in cloud pubblici e ambienti locali.</span><span class="sxs-lookup"><span data-stu-id="30daa-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="30daa-107">Microsoft offre la migliore soluzione di cloud ibrido, uno in cui è possibile ottimizzare le risorse esistenti in locale e nel cloud pubblico, mentre garantire la coerenza in un cloud ibrido di Azure.</span><span class="sxs-lookup"><span data-stu-id="30daa-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="30daa-108">È possibile ottimizzare le competenze esistenti e ottenere un approccio flessibile e unificato per la compilazione di App eseguiti nel cloud o locale, grazie a Azure Stack (locale) e Azure (cloud pubblici).</span><span class="sxs-lookup"><span data-stu-id="30daa-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="30daa-109">Quando si tratta di sicurezza, è possibile centralizzare la gestione e sicurezza tra il cloud ibrido.</span><span class="sxs-lookup"><span data-stu-id="30daa-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="30daa-110">È possibile ottenere controllo su tutti gli asset, dal Data Center nel cloud, fornendo single sign-on per on-premise e App cloud.</span><span class="sxs-lookup"><span data-stu-id="30daa-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="30daa-111">A tale scopo estendendo Active Directory in un cloud ibrido e, utilizzando la gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="30daa-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="30daa-112">Infine, è possibile distribuire e analizzare facilmente i dati, utilizzare linguaggi di query per le risorse cloud e locali e applicare analitica e completo di apprendimento in Azure per arricchire i dati, indipendentemente dalla relativa origine.</span><span class="sxs-lookup"><span data-stu-id="30daa-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="30daa-113">Stack di Azure</span><span class="sxs-lookup"><span data-stu-id="30daa-113">Azure Stack</span></span>

<span data-ttu-id="30daa-114">Stack di Azure è una piattaforma di cloud ibrido che consente di fornire servizi di Azure dal Data Center dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30daa-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="30daa-115">Stack di Azure è progettato per supportare nuove opzioni per le moderne applicazioni negli scenari chiave, ad esempio il bordo e ambienti non connessi o sicurezza e conformità requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="30daa-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="30daa-116">Figura 4-13 mostra una panoramica della piattaforma di cloud ibrido true che Microsoft offre.</span><span class="sxs-lookup"><span data-stu-id="30daa-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Piattaforma di cloud ibrido di Microsoft con Stack di Azure e Azure](./media/image13.jpg)

> <span data-ttu-id="30daa-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="30daa-118">**Figure 4-13.**</span></span> <span data-ttu-id="30daa-119">Piattaforma di cloud ibrido di Microsoft con Stack di Azure e Azure</span><span class="sxs-lookup"><span data-stu-id="30daa-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="30daa-120">Stack di Azure viene offerto con due opzioni di distribuzione, in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="30daa-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

-   <span data-ttu-id="30daa-121">Sistemi Stack integrate di Azure</span><span class="sxs-lookup"><span data-stu-id="30daa-121">Azure Stack integrated systems</span></span>

-   <span data-ttu-id="30daa-122">Kit di sviluppo di Azure Stack</span><span class="sxs-lookup"><span data-stu-id="30daa-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="30daa-123">Sistemi Stack integrate di Azure</span><span class="sxs-lookup"><span data-stu-id="30daa-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="30daa-124">Sistemi di Stack integrato Azure sono disponibili tramite una relazione di partner Microsoft e hardware.</span><span class="sxs-lookup"><span data-stu-id="30daa-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="30daa-125">La relazione viene creata una soluzione che offre l'innovazione paced cloud viene bilanciato con semplicità di gestione.</span><span class="sxs-lookup"><span data-stu-id="30daa-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="30daa-126">Perché lo Stack di Azure viene presentato come un sistema integrato di hardware e software, si verifica la giusta quantità di flessibilità e controllo, quando ancora adozione innovazione dal cloud.</span><span class="sxs-lookup"><span data-stu-id="30daa-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="30daa-127">Sistemi di Stack integrato Azure intervallo dimensioni da 4 a 12 nodi e congiuntamente sono supportati dal partner hardware Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30daa-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="30daa-128">Utilizzare sistemi Azure Stack integrato per implementare nuovi scenari per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="30daa-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="30daa-129">Kit di sviluppo di Azure Stack</span><span class="sxs-lookup"><span data-stu-id="30daa-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="30daa-130">Kit di sviluppo di Microsoft Azure Stack è una distribuzione a nodo singolo dello Stack di Azure, è possibile utilizzare per valutare e informazioni sullo Stack di Azure.</span><span class="sxs-lookup"><span data-stu-id="30daa-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="30daa-131">È anche possibile utilizzare Azure Stack Development Kit come un ambiente di sviluppo in cui è possibile sviluppare usando le API e strumenti che sono coerenti con Azure.</span><span class="sxs-lookup"><span data-stu-id="30daa-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="30daa-132">Azure Kit di sviluppo dello Stack non deve essere utilizzato come un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="30daa-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="30daa-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="30daa-133">Additional resources</span></span>

-   <span data-ttu-id="30daa-134">**Cloud ibridi di Azure**</span><span class="sxs-lookup"><span data-stu-id="30daa-134">**Azure hybrid cloud**</span></span>

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   <span data-ttu-id="30daa-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="30daa-135">**Azure Stack**</span></span>

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   <span data-ttu-id="30daa-136">**Account del servizio Active Directory per i contenitori di Windows**</span><span class="sxs-lookup"><span data-stu-id="30daa-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   <span data-ttu-id="30daa-137">**Creare un contenitore con supporto di Active Directory**</span><span class="sxs-lookup"><span data-stu-id="30daa-137">**Create a container with Active Directory support**</span></span>

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   <span data-ttu-id="30daa-138">**Licenze vantaggio ibrida di Azure**</span><span class="sxs-lookup"><span data-stu-id="30daa-138">**Azure Hybrid Benefit licensing**</span></span>

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
<span data-ttu-id="30daa-139">[Precedente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Successivo](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="30daa-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
