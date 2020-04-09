---
title: Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Modernizza il ciclo di vita della tua app con pipeline CI/CD e strumenti DevOps nel cloud
ms.date: 04/30/2018
ms.openlocfilehash: ac2d9a1e9ab432cf69cb3da670fc91c681f802c2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987855"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="4bec1-103">Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud</span><span class="sxs-lookup"><span data-stu-id="4bec1-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="4bec1-104">Le aziende di oggi devono innovare a un ritmo rapido per essere competitive sul mercato.</span><span class="sxs-lookup"><span data-stu-id="4bec1-104">Today's businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="4bec1-105">La fornitura di applicazioni moderne e di alta qualità richiede strumenti e processi DevOps fondamentali per implementare questo ciclo costante di innovazione.</span><span class="sxs-lookup"><span data-stu-id="4bec1-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="4bec1-106">Con i giusti strumenti DevOps, gli sviluppatori possono semplificare la distribuzione continua e ottenere applicazioni innovative nelle mani degli utenti più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="4bec1-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="4bec1-107">Sebbene le procedure di integrazione e distribuzione continue siano ben consolidate, l'introduzione di contenitori introduce nuove considerazioni, in particolare quando si lavora con applicazioni multi-contenitore.</span><span class="sxs-lookup"><span data-stu-id="4bec1-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="4bec1-108">I servizi DevOps di Azure supportano l'integrazione e la distribuzione continua di applicazioni multi-contenitore in un'ampia gamma di ambienti tramite le attività di distribuzione ufficiali di Servizi DevOps di Azure:Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span><span class="sxs-lookup"><span data-stu-id="4bec1-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="4bec1-109">Eseguire la distribuzione in un'app Web di Azure per i contenitoriDeploy to an Azure Web App for Containers</span><span class="sxs-lookup"><span data-stu-id="4bec1-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [<span data-ttu-id="4bec1-110">Eseguire la distribuzione nel servizio Azure KubernetesDeploy to Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="4bec1-110">Deploy to Azure Kubernetes Service</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

<span data-ttu-id="4bec1-111">Ma è anche possibile distribuire a Docker Swarm o DC/OS usando le attività basate su script di Servizi DevOps di Azure.But you can also deploy to [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) or DC/OS by using Azure DevOps Services script-based tasks.</span><span class="sxs-lookup"><span data-stu-id="4bec1-111">But you also can deploy to [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="4bec1-112">Per continuare a facilitare l'agilità di distribuzione, questi strumenti offrono eccellenti esperienze di distribuzione da sviluppo a test per i carichi di lavoro dei contenitori, con una scelta di soluzioni di sviluppo e CI/CD.</span><span class="sxs-lookup"><span data-stu-id="4bec1-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="4bec1-113">Nella figura 4-12 è illustrata una pipeline di distribuzione continua che viene distribuita in un cluster Kubernetes nel servizio contenitore di Azure.Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="4bec1-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Screenshot della distribuzione dei servizi DevOps di Azure in un cluster Kubernetes.Screenshot of Azure DevOps Services deploying to a Kubernetes cluster.](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

<span data-ttu-id="4bec1-115">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="4bec1-115">**Figure 4-12.**</span></span> <span data-ttu-id="4bec1-116">Pipeline di distribuzione continua di Azure DevOps Services, distribuzione in un cluster KubernetesAzure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span><span class="sxs-lookup"><span data-stu-id="4bec1-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4bec1-117">[Successivo](modernize-your-apps-with-monitoring-and-telemetry.md)
>[precedente](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="4bec1-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
