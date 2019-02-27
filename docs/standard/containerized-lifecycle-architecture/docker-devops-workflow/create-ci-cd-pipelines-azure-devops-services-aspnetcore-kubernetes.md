---
title: Passaggi nel flusso di lavoro DevOps ciclo esterno per un'applicazione Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 2cd769ce9013a8521c53f36b44ea260ceccd48b7
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "56834966"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="f7cbc-103">Creazione di pipeline CI/CD in servizi di DevOps di Azure per un'applicazione .NET Core 2.0 in contenitori e la distribuzione in un cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f7cbc-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="f7cbc-104">Nella figura 5-12 è possibile consultare lo scenario di DevOps end-to-end che coprono la gestione del codice, la compilazione del codice, compilazione di immagini Docker, eseguire il push delle immagini Docker in un registro Docker e infine la distribuzione in un cluster Kubernetes in Azure.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Flusso di lavoro: Viene avviata nel computer di sviluppo.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="f7cbc-107">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-107">**Figure 5-12**.</span></span> <span data-ttu-id="f7cbc-108">Scenario di integrazione continua/recapito Continuo, la creazione di immagini Docker e la distribuzione in un cluster Kubernetes in Azure</span><span class="sxs-lookup"><span data-stu-id="f7cbc-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="f7cbc-109">È importante evidenziare che le due pipeline compilazione/integrazione continua e rilascio/distribuzione continua, sono connessi tramite il registro Docker (ad esempio Hub Docker o registro contenitori di Azure).</span><span class="sxs-lookup"><span data-stu-id="f7cbc-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="f7cbc-110">Il Registro di Docker è una delle principali differenze rispetto a un processo CI/CD tradizionali senza Docker.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="f7cbc-111">Come illustrato nella figura 5-13, la prima fase è la pipeline di compilazione/integrazione continua.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="f7cbc-112">In servizi di Azure DevOps è possibile creare pipeline di compilazione/distribuzione continua che compila il codice, creare le immagini Docker, eseguirne il push in un registro Docker, ad esempio Hub Docker o registro contenitori di Azure.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-112">In Azure DevOps Services you can create build/CD pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Visualizzazione di esplorazione di Azure DevOps, definizione di attività di processo di compilazione.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="f7cbc-114">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-114">**Figure 5-13**.</span></span> <span data-ttu-id="f7cbc-115">Pipeline di compilazione/integrazione continua in DevOps di Azure creano immagini Docker e il push di immagini in un registro Docker</span><span class="sxs-lookup"><span data-stu-id="f7cbc-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="f7cbc-116">La seconda fase consiste nel creare una pipeline di distribuzione/rilascio.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="f7cbc-117">In servizi di Azure DevOps, è possibile creare facilmente una pipeline di distribuzione come destinazione un cluster Kubernetes tramite le attività di Kubernetes per i servizi di Azure DevOps, come illustrato nella figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Visualizzazione di esplorazione di DevOps di Azure, distribuire la definizione di attività Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="f7cbc-119">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="f7cbc-119">**Figure 5-14**.</span></span> <span data-ttu-id="f7cbc-120">Pipeline di rilascio/distribuzione continua nella distribuzione di servizi di Azure DevOps a un cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f7cbc-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [! Procedura dettagliata]<span data-ttu-id="f7cbc-121"> distribuzione eShopModernized per Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="f7cbc-121"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="f7cbc-122">Per una procedura dettagliata della pipeline CI/CD DevOps di Azure, la distribuzione in Kubernetes, vedere questo post di: \\</span><span class="sxs-lookup"><span data-stu-id="f7cbc-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: \\</span></span>
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="f7cbc-123">[Precedente](docker-application-outer-loop-devops-workflow.md)
>[Successivo](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="f7cbc-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
