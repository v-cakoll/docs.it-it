---
title: Eseguire la migrazione a scenari di cloud ibrido
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Eseguire la migrazione a scenari basati su cloud ibrido
ms.date: 04/30/2018
ms.openlocfilehash: 313608c41427b3833bbc873398595ceb37bd7c7d
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373937"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="ea189-103">Eseguire la migrazione a scenari di cloud ibrido</span><span class="sxs-lookup"><span data-stu-id="ea189-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="ea189-104">Alcune organizzazioni e aziende non possono eseguire la migrazione di alcune applicazioni ai cloud pubblici, ad esempio Microsoft Azure o qualsiasi altro cloud pubblico a causa delle normative o dei propri criteri.</span><span class="sxs-lookup"><span data-stu-id="ea189-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="ea189-105">Tuttavia, è probabile che qualsiasi organizzazione possa trarre vantaggio dalla presenza di alcune delle proprie applicazioni nel cloud pubblico e in altre applicazioni locali.</span><span class="sxs-lookup"><span data-stu-id="ea189-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="ea189-106">Tuttavia, un ambiente misto può causare una complessità eccessiva negli ambienti grazie a piattaforme e tecnologie diverse usate in cloud pubblici e ambienti locali.</span><span class="sxs-lookup"><span data-stu-id="ea189-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="ea189-107">Microsoft offre la migliore soluzione cloud ibrida, una in cui è possibile ottimizzare le risorse esistenti in locale e nel cloud pubblico, garantendo la coerenza in un cloud ibrido di Azure.</span><span class="sxs-lookup"><span data-stu-id="ea189-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="ea189-108">Puoi ottimizzare le competenze esistenti e ottenere un approccio flessibile e unificato per la creazione di app che possono essere eseguite nel cloud o in locale, grazie alla Azure Stack (locale) e ad Azure (cloud pubblico).</span><span class="sxs-lookup"><span data-stu-id="ea189-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="ea189-109">Per quanto riguarda la sicurezza, è possibile centralizzare la gestione e la sicurezza nel cloud ibrido.</span><span class="sxs-lookup"><span data-stu-id="ea189-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="ea189-110">Puoi ottenere il controllo su tutti gli asset, dal tuo Data Center al cloud, fornendo Single Sign-On alle app locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="ea189-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="ea189-111">A tale scopo, estendere Active Directory a un cloud ibrido e usare la gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="ea189-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="ea189-112">Infine, è possibile distribuire e analizzare facilmente i dati, usare gli stessi linguaggi di query per le risorse cloud e locali e applicare analisi e apprendimento avanzato in Azure per arricchire i dati, indipendentemente dalla relativa origine.</span><span class="sxs-lookup"><span data-stu-id="ea189-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="ea189-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="ea189-113">Azure Stack</span></span>

<span data-ttu-id="ea189-114">Azure Stack è una piattaforma cloud ibrida che consente di distribuire i servizi di Azure dal Data Center dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea189-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="ea189-115">Azure Stack è progettato per supportare nuove opzioni per le applicazioni moderne in scenari principali, ad esempio gli ambienti perimetrali e non connessi, o soddisfare requisiti di sicurezza e conformità specifici.</span><span class="sxs-lookup"><span data-stu-id="ea189-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="ea189-116">La figura 4-13 Mostra una panoramica della vera e propria piattaforma cloud ibrida offerta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ea189-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Piattaforma cloud ibrida Microsoft con Azure Stack e Azure](./media/image13.jpg)

<span data-ttu-id="ea189-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="ea189-118">**Figure 4-13.**</span></span> <span data-ttu-id="ea189-119">Piattaforma cloud ibrida Microsoft con Azure Stack e Azure</span><span class="sxs-lookup"><span data-stu-id="ea189-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="ea189-120">Azure Stack è disponibile in due opzioni di distribuzione, per soddisfare le proprie esigenze:</span><span class="sxs-lookup"><span data-stu-id="ea189-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="ea189-121">Sistemi integrati di Azure Stack</span><span class="sxs-lookup"><span data-stu-id="ea189-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="ea189-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="ea189-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="ea189-123">Sistemi integrati di Azure Stack</span><span class="sxs-lookup"><span data-stu-id="ea189-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="ea189-124">Azure Stack sistemi integrati sono offerti attraverso una partnership di Microsoft e dei partner hardware.</span><span class="sxs-lookup"><span data-stu-id="ea189-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="ea189-125">La partnership crea una soluzione che offre un'innovazione basata sul cloud, bilanciata dalla semplicità di gestione.</span><span class="sxs-lookup"><span data-stu-id="ea189-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="ea189-126">Poiché Azure Stack viene offerto come sistema integrato di hardware e software, si ottiene la giusta quantità di flessibilità e controllo, pur continuando ad adottare l'innovazione dal cloud.</span><span class="sxs-lookup"><span data-stu-id="ea189-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="ea189-127">Azure Stack i sistemi integrati hanno una dimensione compresa tra 4 e 12 nodi e sono supportati congiuntamente dal partner hardware e da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ea189-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="ea189-128">Usare Azure Stack sistemi integrati per implementare nuovi scenari per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="ea189-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="ea189-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="ea189-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="ea189-130">Microsoft Azure Stack Development Kit è una distribuzione a nodo singolo di Azure Stack, che è possibile utilizzare per valutare e ottenere informazioni sulle Azure Stack di.</span><span class="sxs-lookup"><span data-stu-id="ea189-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="ea189-131">È anche possibile usare Azure Stack Development Kit come un ambiente di sviluppo, in cui è possibile sviluppare usando le API e gli strumenti coerenti con Azure.</span><span class="sxs-lookup"><span data-stu-id="ea189-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="ea189-132">Azure Stack Development Kit non è destinato a essere utilizzato come ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="ea189-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ea189-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ea189-133">Additional resources</span></span>

- <span data-ttu-id="ea189-134">**Cloud ibrido di Azure**</span><span class="sxs-lookup"><span data-stu-id="ea189-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="ea189-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="ea189-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="ea189-136">**Account del servizio Active Directory per i contenitori di Windows**</span><span class="sxs-lookup"><span data-stu-id="ea189-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="ea189-137">**Creare un contenitore con supporto Active Directory**</span><span class="sxs-lookup"><span data-stu-id="ea189-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="ea189-138">**Gestione licenze Vantaggio Azure Hybrid**</span><span class="sxs-lookup"><span data-stu-id="ea189-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="ea189-139">[Precedente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Successivo](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ea189-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
