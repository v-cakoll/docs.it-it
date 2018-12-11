---
title: Modernizza il ciclo di vita dell'app con le pipeline di integrazione continua/recapito Continuo e strumenti DevOps nel cloud
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Modernizza il ciclo di vita dell'app con le pipeline di integrazione continua/recapito Continuo e strumenti DevOps nel cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: c4eeb5606d3ea93b76efee58ddfecae0abbbd743
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128180"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="b3a80-103">Modernizza il ciclo di vita dell'app con le pipeline di integrazione continua/recapito Continuo e strumenti DevOps nel cloud</span><span class="sxs-lookup"><span data-stu-id="b3a80-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="b3a80-104">È necessario che le aziende moderne innovazione rapida per essere competitivi nel marketplace.</span><span class="sxs-lookup"><span data-stu-id="b3a80-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="b3a80-105">Distribuzione di alta qualità, le applicazioni moderne richiede strumenti DevOps e i processi di importanza cruciale per implementare questo ciclo costante di innovazione.</span><span class="sxs-lookup"><span data-stu-id="b3a80-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="b3a80-106">Con gli strumenti DevOps, gli sviluppatori possono semplificare la distribuzione continua e ottenere più rapidamente applicazioni innovative nelle mani degli utenti.</span><span class="sxs-lookup"><span data-stu-id="b3a80-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="b3a80-107">Anche se l'integrazione e distribuzione continue sono ben definite, l'introduzione di contenitori introduce nuove considerazioni, specialmente quando si lavora con le applicazioni multi-contenitore.</span><span class="sxs-lookup"><span data-stu-id="b3a80-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="b3a80-108">Servizi di Azure DevOps supporta l'integrazione continua e distribuzione di applicazioni multi-contenitore in un'ampia gamma di ambienti tramite le attività di distribuzione di servizi di Azure DevOps ufficiale:</span><span class="sxs-lookup"><span data-stu-id="b3a80-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

-   <span data-ttu-id="b3a80-109">[Distribuire alla macchina virtuale Host Docker autonoma](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="b3a80-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="b3a80-110">Distribuire in Service Fabric</span><span class="sxs-lookup"><span data-stu-id="b3a80-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="b3a80-111">Distribuire nel servizio contenitore di Azure – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="b3a80-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="b3a80-112">Ma è anche possibile distribuire [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS tramite le attività di servizi di Azure DevOps basato su script.</span><span class="sxs-lookup"><span data-stu-id="b3a80-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="b3a80-113">Per continuare a favorire l'agilità della distribuzione, questi strumenti offrono esperienze eccellente dev da-test-a-distribuzione di produzione per carichi di lavoro contenitore con una gamma di soluzioni di integrazione continua/recapito Continuo e sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b3a80-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="b3a80-114">Figura 4-12 illustra una pipeline di distribuzione continua che distribuisce un cluster Kubernetes nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="b3a80-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Pipeline di distribuzione continua DevOps servizi Azure, la distribuzione in un cluster Kubernetes](./media/image12.png)

> <span data-ttu-id="b3a80-116">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="b3a80-116">**Figure 4-12.**</span></span> <span data-ttu-id="b3a80-117">Pipeline di distribuzione continua DevOps servizi Azure, la distribuzione in un cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="b3a80-117">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b3a80-118">[Precedente](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Successivo](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="b3a80-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>