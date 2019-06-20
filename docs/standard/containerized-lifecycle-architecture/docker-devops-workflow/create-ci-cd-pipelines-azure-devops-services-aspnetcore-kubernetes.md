---
title: Passaggi nel flusso di lavoro DevOps del ciclo esterno per un'applicazione Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.date: 02/15/2019
ms.openlocfilehash: 9fdc5acfd375e4f2266859f061ef1c854286b914
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644977"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="63df9-103">Creazione di pipeline CI/CD in Azure DevOps Services per un'applicazione .NET Core 2.0 in contenitori e distribuzione in un cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="63df9-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="63df9-104">Nella figura 5-12 è possibile vedere lo scenario DevOps end-to-end relativo alla gestione e alla compilazione del codice, alla compilazione delle immagini Docker, al push delle immagini Docker in un registro Docker e infine alla distribuzione in un cluster Kubernetes in Azure.</span><span class="sxs-lookup"><span data-stu-id="63df9-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Flusso di lavoro: Inizia nel computer di sviluppo.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="63df9-107">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="63df9-107">**Figure 5-12**.</span></span> <span data-ttu-id="63df9-108">Scenario di integrazione continua/distribuzione continua che crea immagini Docker e le distribuisce in un cluster Kubernetes in Azure</span><span class="sxs-lookup"><span data-stu-id="63df9-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="63df9-109">È importante sottolineare che le due pipeline (compilazione/integrazione continua e rilascio/distribuzione continua) sono connesse tramite il registro Docker (ad esempio Docker Hub o Registro Azure Container).</span><span class="sxs-lookup"><span data-stu-id="63df9-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="63df9-110">Il registro Docker è una delle principali differenze rispetto a un processo di integrazione continua/distribuzione continua tradizionale senza Docker.</span><span class="sxs-lookup"><span data-stu-id="63df9-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="63df9-111">Come illustrato nella figura 5-13, la prima fase è costituita dalla pipeline di compilazione/integrazione continua.</span><span class="sxs-lookup"><span data-stu-id="63df9-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="63df9-112">In Azure DevOps Services è possibile creare pipeline di compilazione/integrazione continua che compilano il codice, creano le immagini Docker e ne eseguono il push in un registro Docker, ad esempio Docker Hub o Registro Azure Container.</span><span class="sxs-lookup"><span data-stu-id="63df9-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Visualizzazione nel browser di Azure DevOps, definizione dell'attività del processo di compilazione.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="63df9-114">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="63df9-114">**Figure 5-13**.</span></span> <span data-ttu-id="63df9-115">Pipeline di compilazione/integrazione continua in Azure DevOps che crea immagini Docker e ne esegue il push in un registro Docker</span><span class="sxs-lookup"><span data-stu-id="63df9-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="63df9-116">La seconda fase consiste nella creazione di una pipeline di distribuzione/rilascio.</span><span class="sxs-lookup"><span data-stu-id="63df9-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="63df9-117">In Azure DevOps Services è possibile creare facilmente una pipeline di distribuzione destinata a un cluster Kubernetes tramite le attività di Kubernetes per Azure DevOps Services, come illustrato nella Figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="63df9-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Visualizzazione nel browser di Azure DevOps, definizione dell'attività di distribuzione Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="63df9-119">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="63df9-119">**Figure 5-14**.</span></span> <span data-ttu-id="63df9-120">Pipeline di rilascio/distribuzione continua in Azure DevOps che esegue la distribuzione in un cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="63df9-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [!Procedura dettagliata]<span data-ttu-id="63df9-121"> Distribuzione di eShopModernized in Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="63df9-121"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="63df9-122">Per una procedura dettagliata della pipeline di integrazione continua/distribuzione continua di Azure DevOps, vedere questo post: </span><span class="sxs-lookup"><span data-stu-id="63df9-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: </span></span>\
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="63df9-123">[Precedente](docker-application-outer-loop-devops-workflow.md)
>[Successivo](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="63df9-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
