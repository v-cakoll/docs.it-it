---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitori
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "73737014"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="74508-103">Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore</span><span class="sxs-lookup"><span data-stu-id="74508-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="74508-104">Come si è notato dopo aver letto le sezioni precedenti, Azure è un cloud aperto che offre più opzioni.</span><span class="sxs-lookup"><span data-stu-id="74508-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="74508-105">È tuttavia possibile usare la soluzione più adatta alle proprie esigenze, ma anche le domande sul prodotto/tecnologia da usare per le applicazioni in contenitori.</span><span class="sxs-lookup"><span data-stu-id="74508-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="74508-106">Come raccomandazione *per impostazione predefinita* , di seguito sono riportati i criteri principali consigliati in questa guida:</span><span class="sxs-lookup"><span data-stu-id="74508-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="74508-107">**Singola app monolitica:** Scegliere app Azure servizio</span><span class="sxs-lookup"><span data-stu-id="74508-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="74508-108">**App a più livelli:** Scegliere gli agenti di orchestrazione, ad esempio Azure Kubernetes Service (AKS) o il servizio app, se si dispone di un singolo o di pochi servizi back-end</span><span class="sxs-lookup"><span data-stu-id="74508-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="74508-109">**Microservizi:** Scegliere AKS o app Web di Azure per contenitori</span><span class="sxs-lookup"><span data-stu-id="74508-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="74508-110">**Funzioni senza server & gestori eventi:** Scegliere funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="74508-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="74508-111">**Batch su larga scala:** Scegliere Azure Batch</span><span class="sxs-lookup"><span data-stu-id="74508-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="74508-112">Questa raccomandazione, tuttavia, deve essere eseguita con un pizzico di Salt, in quanto la selezione del prodotto dipende dalle esigenze e dalle caratteristiche specifiche dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74508-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="74508-113">Non tutte le applicazioni sono le stesse anche quando inizialmente potrebbero sembrare tipi simili.</span><span class="sxs-lookup"><span data-stu-id="74508-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="74508-114">Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="74508-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="74508-115">Tuttavia, come punto di partenza, è opportuno disporre di indicazioni iniziali da cui è possibile iniziare a valutare e testare in base a una determinata priorità.</span><span class="sxs-lookup"><span data-stu-id="74508-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="74508-116">Nella figura 1 è possibile visualizzare una suddivisione dei diversi tipi di app e i relativi scenari di hosting di Azure ideali.</span><span class="sxs-lookup"><span data-stu-id="74508-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![Tabella di cui gli scenari di hosting di Azure sono migliori per le diverse app.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="74508-118">[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="74508-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
