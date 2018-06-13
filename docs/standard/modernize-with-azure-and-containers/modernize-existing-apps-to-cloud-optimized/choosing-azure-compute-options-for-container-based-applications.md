---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate sul contenitore
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Scelta delle piattaforme di calcolo di Azure per le applicazioni basate sul contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958011"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="ff494-103">Scelta delle piattaforme di calcolo di Azure per le applicazioni basate sul contenitore</span><span class="sxs-lookup"><span data-stu-id="ff494-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="ff494-104">Come si notare dopo la lettura delle sezioni precedenti, Azure è un cloud aperto che offre più opzioni.</span><span class="sxs-lookup"><span data-stu-id="ff494-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="ff494-105">È possibile usare la scelta migliore per le proprie esigenze, tuttavia, anche superfici domande sul prodotto o tecnologia deve usare per le applicazioni nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="ff494-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="ff494-106">Come un *per impostazione predefinita* , quanto segue si consiglia di principali criteri consigliati in questa guida:</span><span class="sxs-lookup"><span data-stu-id="ff494-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="ff494-107">**Singola app monolitico:** scegliere servizio App di Azure</span><span class="sxs-lookup"><span data-stu-id="ff494-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="ff494-108">**App a più livelli:** scegliere orchestrators quali Azure Kubernetes servizio (AKS), Service Fabric (SF) o il servizio App se si dispone di un singolo o alcuni servizi back-end</span><span class="sxs-lookup"><span data-stu-id="ff494-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="ff494-109">**Linux microservizi:** scegliere AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="ff494-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="ff494-110">**Windows microservizi:** scegliere Service Fabric</span><span class="sxs-lookup"><span data-stu-id="ff494-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="ff494-111">**Funzioni senza server & gestori di eventi:** scegliere le funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="ff494-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="ff494-112">**Batch su vasta scala:** scegliere Azure Batch</span><span class="sxs-lookup"><span data-stu-id="ff494-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="ff494-113">Tuttavia, questa indicazione è opportuno tenere con un zoom indietro del salt, come selezione del prodotto varia in base alle esigenze e le caratteristiche dell'applicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="ff494-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="ff494-114">Non tutte le applicazioni sono gli stessi anche quando inizialmente sembrano tipi simili.</span><span class="sxs-lookup"><span data-stu-id="ff494-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="ff494-115">Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="ff494-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="ff494-116">Ma, come un punto di partenza, è opportuno usare le istruzioni iniziali da dove è possibile avviare la valutazione e il test in base a determinati la priorità.</span><span class="sxs-lookup"><span data-stu-id="ff494-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="ff494-117">Nella figura che segue, è possibile analizzare più globale durante la tabella decisioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="ff494-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="ff494-118">Si noti il modo in cui sottostante del sistema operativo (Windows Visual Studio. Linux) può anche rappresentare un fattore di decisione come alcuni orchestrators sono più maturo sui contenitori di Linux e altri in contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="ff494-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="ff494-119">Ad esempio, i contenitori di Linux sono molto maturi in Kubernetes (AKS in Azure), ma meno avanzata nell'infrastruttura del servizio.</span><span class="sxs-lookup"><span data-stu-id="ff494-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="ff494-120">D'altro canto, i contenitori di Windows sono più maturo in Service Fabric (rilasciato nel maggio 2017) e meno avanzata in AKS.</span><span class="sxs-lookup"><span data-stu-id="ff494-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="ff494-121">Tuttavia, queste differenze in scadenza del sistema operativo gradualmente in futuro e più piattaforme avrà confrontabili maturità del sistema operativo e la decisione si troveranno altre preferenze in base alle funzionalità specifiche dell'applicazione potrebbe essere necessario o in base a ecosistema di ciascuna piattaforma motivi.</span><span class="sxs-lookup"><span data-stu-id="ff494-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ff494-122">[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="ff494-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
