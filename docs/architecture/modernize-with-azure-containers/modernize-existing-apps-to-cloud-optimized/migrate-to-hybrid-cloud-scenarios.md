---
title: Eseguire la migrazione a scenari di cloud ibrido
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Eseguire la migrazione a scenari di cloud ibridoMigrate to hybrid cloud scenarios
ms.date: 04/30/2018
ms.openlocfilehash: dcbb799a45609f8bb811866c4041951abf1fda8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937371"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="92f2c-103">Eseguire la migrazione a scenari di cloud ibrido</span><span class="sxs-lookup"><span data-stu-id="92f2c-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="92f2c-104">Alcune organizzazioni e aziende non possono eseguire la migrazione di alcune delle applicazioni a cloud pubblici come Microsoft Azure o qualsiasi altro cloud pubblico a causa di normative o dei propri criteri.</span><span class="sxs-lookup"><span data-stu-id="92f2c-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="92f2c-105">Tuttavia, è probabile che qualsiasi organizzazione potrebbe trarre vantaggio dalla presenza di alcune delle applicazioni nel cloud pubblico e altre applicazioni in locale.</span><span class="sxs-lookup"><span data-stu-id="92f2c-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="92f2c-106">Tuttavia, un ambiente misto può causare un'eccessiva complessità negli ambienti a causa di diverse piattaforme e tecnologie utilizzate nei cloud pubblici rispetto agli ambienti locali.</span><span class="sxs-lookup"><span data-stu-id="92f2c-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="92f2c-107">Microsoft offre la migliore soluzione cloud ibrida, in cui è possibile ottimizzare gli asset esistenti in locale e nel cloud pubblico, assicurando la coerenza in un cloud ibrido di Azure.Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span><span class="sxs-lookup"><span data-stu-id="92f2c-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="92f2c-108">È possibile ottimizzare le competenze esistenti e ottenere un approccio flessibile e unificato alla creazione di app che possono essere eseguite nel cloud o in locale, grazie ad Azure Stack (locale) e Azure (cloud pubblico).</span><span class="sxs-lookup"><span data-stu-id="92f2c-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="92f2c-109">Quando si tratta di sicurezza, è possibile centralizzare la gestione e la sicurezza nel cloud ibrido.</span><span class="sxs-lookup"><span data-stu-id="92f2c-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="92f2c-110">È possibile ottenere il controllo su tutti gli asset, dal data center al cloud, fornendo l'accesso Single Sign-On alle app locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="92f2c-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="92f2c-111">A tale scopo, estendere Active Directory a un cloud ibrido e utilizzando la gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="92f2c-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="92f2c-112">Infine, è possibile distribuire e analizzare i dati senza problemi, usare gli stessi linguaggi di query per gli asset cloud e locali e applicare analisi e deep learning in Azure per arricchire i dati, indipendentemente dalla relativa origine.</span><span class="sxs-lookup"><span data-stu-id="92f2c-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="92f2c-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="92f2c-113">Azure Stack</span></span>

<span data-ttu-id="92f2c-114">Azure Stack è una piattaforma cloud ibrida che consente di fornire servizi di Azure dal data center dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="92f2c-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="92f2c-115">Azure Stack è progettato per supportare nuove opzioni per le applicazioni moderne in scenari chiave, ad esempio ambienti perimetrali e non connessi o per soddisfare requisiti di sicurezza e conformità specifici.</span><span class="sxs-lookup"><span data-stu-id="92f2c-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="92f2c-116">Nella figura 4-13 viene illustrata una panoramica della vera piattaforma cloud ibrida offerta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92f2c-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Diagramma della piattaforma cloud ibrida Microsoft con Azure Stack e Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="92f2c-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="92f2c-118">**Figure 4-13.**</span></span> <span data-ttu-id="92f2c-119">Piattaforma cloud ibrida Microsoft con Azure Stack e Azure</span><span class="sxs-lookup"><span data-stu-id="92f2c-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="92f2c-120">Lo stack di Azure è disponibile in due opzioni di distribuzione per soddisfare le esigenze:Azure Stack is offered in two deployment options, to meet your needs:</span><span class="sxs-lookup"><span data-stu-id="92f2c-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="92f2c-121">Sistemi integrati di Azure StackAzure Stack integrated systems</span><span class="sxs-lookup"><span data-stu-id="92f2c-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="92f2c-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="92f2c-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="92f2c-123">Sistemi integrati di Azure StackAzure Stack integrated systems</span><span class="sxs-lookup"><span data-stu-id="92f2c-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="92f2c-124">I sistemi integrati di Azure Stack sono offerti tramite una partnership di Microsoft e dei partner hardware.</span><span class="sxs-lookup"><span data-stu-id="92f2c-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="92f2c-125">La partnership crea una soluzione che offre innovazione basata sul cloud, bilanciata con semplicità di gestione.</span><span class="sxs-lookup"><span data-stu-id="92f2c-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="92f2c-126">Dato che Azure Stack è disponibile come sistema integrato di hardware e software, si ottiene il giusto livello di flessibilità e controllo, pur adottando l'innovazione dal cloud.</span><span class="sxs-lookup"><span data-stu-id="92f2c-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="92f2c-127">Le dimensioni dei sistemi integrati di Azure Stack variano da 4 a 12 nodi e sono supportati congiuntamente dal partner hardware e da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92f2c-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="92f2c-128">Usare i sistemi integrati di Azure Stack per implementare nuovi scenari per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="92f2c-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="92f2c-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="92f2c-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="92f2c-130">Microsoft Azure Stack Development Kit è una distribuzione a nodo singolo di Azure Stack, che è possibile usare per valutare e imparare a conoscere Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="92f2c-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="92f2c-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span><span class="sxs-lookup"><span data-stu-id="92f2c-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="92f2c-132">Azure Stack Development Kit non è destinato all'uso in ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="92f2c-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="92f2c-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="92f2c-133">Additional resources</span></span>

- <span data-ttu-id="92f2c-134">**Cloud ibrido di AzureAzure hybrid cloud**</span><span class="sxs-lookup"><span data-stu-id="92f2c-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="92f2c-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="92f2c-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="92f2c-136">**Account del servizio Active Directory per i contenitori di Windows**</span><span class="sxs-lookup"><span data-stu-id="92f2c-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="92f2c-137">**Creare un contenitore con supporto active DirectoryCreate a container with Active Directory support**</span><span class="sxs-lookup"><span data-stu-id="92f2c-137">**Create a container with Active Directory support**</span></span>

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- <span data-ttu-id="92f2c-138">**Licenze per i vantaggi ibridi di AzureAzure Hybrid Benefit licensing**</span><span class="sxs-lookup"><span data-stu-id="92f2c-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="92f2c-139">[Successivo](life-cycle-ci-cd-pipelines-devops-tools.md)
>[precedente](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="92f2c-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
