---
title: Eseguire la migrazione a scenari di cloud ibrido
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Eseguire la migrazione a scenari di cloud ibrido
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 3d6fc272854654d890559d5db032b05667627d94
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147346"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="a2805-103">Eseguire la migrazione a scenari di cloud ibrido</span><span class="sxs-lookup"><span data-stu-id="a2805-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="a2805-104">Non è possibile eseguire la migrazione di alcune organizzazioni e aziende alcune delle proprie applicazioni per cloud pubblici, ad esempio Microsoft Azure o qualsiasi altro cloud pubblico a causa delle normative o i propri criteri.</span><span class="sxs-lookup"><span data-stu-id="a2805-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="a2805-105">Tuttavia, è probabile che qualsiasi organizzazione potrebbe trarre vantaggio dalla disponibilità di alcune delle proprie applicazioni nel cloud pubblico e altre applicazioni in locale.</span><span class="sxs-lookup"><span data-stu-id="a2805-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="a2805-106">Ma può causare un ambiente misto complessità eccessiva negli ambienti a causa di diverse piattaforme e tecnologie utilizzate in cloud pubblici e ambienti locali.</span><span class="sxs-lookup"><span data-stu-id="a2805-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="a2805-107">Microsoft offre la migliore soluzione cloud ibrida, uno in cui è possibile ottimizzare le risorse esistenti in locale e nel cloud pubblico, mentre garantire la coerenza in un cloud ibrido di Azure.</span><span class="sxs-lookup"><span data-stu-id="a2805-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="a2805-108">È possibile ottimizzare le competenze esistenti e Ottieni un approccio flessibile e unificato alla creazione di App che è possibile eseguire nel cloud o in locale, grazie a Azure Stack (locale) e Azure (cloud pubblico).</span><span class="sxs-lookup"><span data-stu-id="a2805-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="a2805-109">Quando si parla di sicurezza, è possibile centralizzare sicurezza e gestione tra il cloud ibrido.</span><span class="sxs-lookup"><span data-stu-id="a2805-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="a2805-110">È possibile ottenere il controllo su tutti gli asset, dal Data Center nel cloud, fornendo l'accesso single sign-on in locale e le app cloud.</span><span class="sxs-lookup"><span data-stu-id="a2805-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="a2805-111">A tale scopo mediante l'estensione Active Directory per un cloud ibrido e usando la gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="a2805-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="a2805-112">Infine, è possibile distribuire e analizza con facilità i dati, usare gli stessi linguaggi di query per gli asset locali e cloud e applicare analitica e apprendimento avanzato in Azure per arricchire i dati, indipendentemente dalla relativa origine.</span><span class="sxs-lookup"><span data-stu-id="a2805-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="a2805-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a2805-113">Azure Stack</span></span>

<span data-ttu-id="a2805-114">Azure Stack è una piattaforma di cloud ibrido che ti permette di offrire servizi di Azure dal Data Center dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2805-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="a2805-115">Azure Stack è progettato per supportare le nuove opzioni per le applicazioni moderne in scenari chiave, ad esempio edge e gli ambienti non connessi o sicurezza e conformità di requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="a2805-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="a2805-116">Figura 4-13 mostra una panoramica della piattaforma di cloud ibrido davvero offerte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2805-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Piattaforma di cloud ibrido Microsoft con Azure Stack e Azure](./media/image13.jpg)

> <span data-ttu-id="a2805-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="a2805-118">**Figure 4-13.**</span></span> <span data-ttu-id="a2805-119">Piattaforma di cloud ibrido Microsoft con Azure Stack e Azure</span><span class="sxs-lookup"><span data-stu-id="a2805-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="a2805-120">Azure Stack è disponibile in due opzioni di distribuzione, in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="a2805-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

-   <span data-ttu-id="a2805-121">Sistemi integrati di Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a2805-121">Azure Stack integrated systems</span></span>

-   <span data-ttu-id="a2805-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="a2805-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="a2805-123">Sistemi integrati di Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a2805-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="a2805-124">Sistemi integrati di Stack di Azure sono disponibili tramite una collaborazione dei partner Microsoft e hardware.</span><span class="sxs-lookup"><span data-stu-id="a2805-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="a2805-125">La relazione viene creata una soluzione che offre l'innovazione paced cloud bilanciata con semplicità di gestione.</span><span class="sxs-lookup"><span data-stu-id="a2805-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="a2805-126">Perché Azure Stack è disponibile come sistema integrato di hardware e software, otterrai la giusta quantità di flessibilità e controllo, durante l'adozione comunque l'innovazione dal cloud.</span><span class="sxs-lookup"><span data-stu-id="a2805-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="a2805-127">Sistemi Azure Stack integrati dimensioni variano da 4 a 12 nodi e congiuntamente supportati dai partner hardware e Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2805-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="a2805-128">Usare i sistemi integrati di Azure Stack per implementare nuovi scenari per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="a2805-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="a2805-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="a2805-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="a2805-130">Microsoft Azure Stack Development Kit è una distribuzione a nodo singolo di Azure Stack, che è possibile usare per valutare e ottenere informazioni su Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="a2805-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="a2805-131">È anche possibile usare Azure Stack Development Kit come un ambiente di sviluppo, in cui è possibile sviluppare usando le API e strumenti che siano coerenti con Azure.</span><span class="sxs-lookup"><span data-stu-id="a2805-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="a2805-132">Azure Stack Development Kit non deve essere utilizzato come un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="a2805-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a2805-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a2805-133">Additional resources</span></span>

-   <span data-ttu-id="a2805-134">**Cloud ibrido di Azure**</span><span class="sxs-lookup"><span data-stu-id="a2805-134">**Azure hybrid cloud**</span></span>

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   <span data-ttu-id="a2805-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="a2805-135">**Azure Stack**</span></span>

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   <span data-ttu-id="a2805-136">**Account del servizio Active Directory per i contenitori Windows**</span><span class="sxs-lookup"><span data-stu-id="a2805-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   <span data-ttu-id="a2805-137">**Creare un contenitore con supporto di Active Directory**</span><span class="sxs-lookup"><span data-stu-id="a2805-137">**Create a container with Active Directory support**</span></span>

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   <span data-ttu-id="a2805-138">**Azure vantaggio Hybrid Use**</span><span class="sxs-lookup"><span data-stu-id="a2805-138">**Azure Hybrid Benefit licensing**</span></span>

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
><span data-ttu-id="a2805-139">[Precedente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Successivo](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a2805-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>