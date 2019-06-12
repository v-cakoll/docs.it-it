---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Scegliere le piattaforme di calcolo di Azure per le applicazioni basate su contenitore
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833846"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="4de0e-103">Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore</span><span class="sxs-lookup"><span data-stu-id="4de0e-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="4de0e-104">Come è stato certamente notato dopo la lettura delle sezioni precedenti, Azure è un cloud aperta che offre più opzioni.</span><span class="sxs-lookup"><span data-stu-id="4de0e-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="4de0e-105">È possibile usare la soluzione ottimale per le proprie esigenze, tuttavia, lo segnala anche domande su quale prodotto/tecnologia deve usare per le applicazioni in contenitori.</span><span class="sxs-lookup"><span data-stu-id="4de0e-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="4de0e-106">Come un *per impostazione predefinita* raccomandazione, di seguito è riportato il criterio principale consigliato in questa guida:</span><span class="sxs-lookup"><span data-stu-id="4de0e-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="4de0e-107">**Singola app monolitica, occorre:** Scegliere servizio App di Azure</span><span class="sxs-lookup"><span data-stu-id="4de0e-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="4de0e-108">**App a più livelli:** Scegliere gli agenti di orchestrazione, ad esempio Azure Kubernetes Service (AKS) o servizio App se si dispone di uno o alcuni servizi di back-end</span><span class="sxs-lookup"><span data-stu-id="4de0e-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="4de0e-109">**Microservizi:** Scegliere servizio contenitore di AZURE o App Web di Azure per contenitori</span><span class="sxs-lookup"><span data-stu-id="4de0e-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="4de0e-110">**Le funzioni senza server e i gestori eventi:** Scegliere le funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="4de0e-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="4de0e-111">**Batch su vasta scala:** Scegli Azure Batch</span><span class="sxs-lookup"><span data-stu-id="4de0e-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="4de0e-112">Tuttavia, questa raccomandazione attenzione con un con avvicinamento delle dita di salt, come selezione del prodotto varia in base alle esigenze e le caratteristiche dell'applicazione specifico.</span><span class="sxs-lookup"><span data-stu-id="4de0e-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="4de0e-113">Non tutte le applicazioni sono gli stessi, anche se inizialmente risultino tipi simili.</span><span class="sxs-lookup"><span data-stu-id="4de0e-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="4de0e-114">Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="4de0e-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="4de0e-115">Ma, come punto di partenza, è buona norma disporre le indicazioni iniziali da dove iniziare la valutazione e test di base di determinate priorità.</span><span class="sxs-lookup"><span data-stu-id="4de0e-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="4de0e-116">Nella figura che segue, è possibile visualizzare un riepilogo dei diversi tipi di App e i relativi scenari di hosting di Azure ideale.</span><span class="sxs-lookup"><span data-stu-id="4de0e-116">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="4de0e-117">[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="4de0e-117">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
