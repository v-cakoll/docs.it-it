---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Scegliere le piattaforme di calcolo di Azure per le applicazioni basate su contenitore
ms.date: 05/04/2018
ms.openlocfilehash: 28e103c67f47d63582384c9ab468a5f631b5ce9e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638985"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="0cbfa-103">Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore</span><span class="sxs-lookup"><span data-stu-id="0cbfa-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="0cbfa-104">Come è stato certamente notato dopo la lettura delle sezioni precedenti, Azure è un cloud aperta che offre più opzioni.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="0cbfa-105">È possibile usare la soluzione ottimale per le proprie esigenze, tuttavia, lo segnala anche domande su quale prodotto/tecnologia deve usare per le applicazioni in contenitori.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="0cbfa-106">Come un *per impostazione predefinita* raccomandazione, di seguito è riportato il criterio principale consigliato in questa guida:</span><span class="sxs-lookup"><span data-stu-id="0cbfa-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="0cbfa-107">**Singola app monolitica, occorre:** Scegliere servizio App di Azure</span><span class="sxs-lookup"><span data-stu-id="0cbfa-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="0cbfa-108">**App a più livelli:** Scegliere gli agenti di orchestrazione, ad esempio servizio App, Service Fabric (SF) o Azure Kubernetes Service (AKS) se si dispone di uno o alcuni servizi di back-end</span><span class="sxs-lookup"><span data-stu-id="0cbfa-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="0cbfa-109">**Microservizi di Linux:** Scegliere servizio contenitore di AZURE/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="0cbfa-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="0cbfa-110">**Microservizi di Windows:** Scegliere Service Fabric</span><span class="sxs-lookup"><span data-stu-id="0cbfa-110">**Windows microservices:** Choose Service Fabric</span></span>
- <span data-ttu-id="0cbfa-111">**Le funzioni senza server e i gestori eventi:** Scegliere le funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="0cbfa-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="0cbfa-112">**Batch su vasta scala:** Scegli Azure Batch</span><span class="sxs-lookup"><span data-stu-id="0cbfa-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="0cbfa-113">Tuttavia, questa raccomandazione attenzione con un con avvicinamento delle dita di salt, come selezione del prodotto varia in base alle esigenze e le caratteristiche dell'applicazione specifico.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="0cbfa-114">Non tutte le applicazioni sono gli stessi, anche se inizialmente risultino tipi simili.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="0cbfa-115">Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="0cbfa-116">Ma, come punto di partenza, è buona norma disporre le indicazioni iniziali da dove iniziare la valutazione e test di base di determinate priorità.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="0cbfa-117">Nella figura che segue, è possibile analizzare più globale durante la tabella decisioni dettagliati.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="0cbfa-118">Si noti come il sottostante del sistema operativo (Windows Visual Studio. Linux) può anche rappresentare un fattore di decisione perché alcuni agenti di orchestrazione sono più maturo in contenitori Linux e altre sui contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="0cbfa-119">Ad esempio, i contenitori Linux sono molto maturi in Kubernetes (servizio contenitore di AZURE in Azure) ma meno maturo in Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="0cbfa-120">D'altra parte, i contenitori Windows sono più "maturo" Service Fabric (rilasciato a maggio 2017) e meno maturo in AKS.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="0cbfa-121">Tuttavia, tali differenze nel livello di maturità del sistema operativo verranno dissolvenza in entrata in futuro e più piattaforme abbiano confrontabili maturità del sistema operativo e la decisione si troveranno altre preferenze basata su funzionalità specifiche dell'applicazione potrebbe essere necessario o base ecosistema di ciascuna piattaforma motivi.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="0cbfa-122">[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="0cbfa-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
