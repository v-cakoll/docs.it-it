---
title: Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Modernizza il ciclo di vita della tua app con pipeline CI/CD e strumenti DevOps nel cloud
ms.date: 04/30/2018
ms.openlocfilehash: 17a78c108bfc61471128a34191ec7a5d7cc28289
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503854"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud

Le aziende di oggi devono innovare a un ritmo rapido per essere competitive sul mercato. La fornitura di applicazioni moderne e di alta qualità richiede strumenti e processi DevOps fondamentali per implementare questo ciclo costante di innovazione. Con i giusti strumenti DevOps, gli sviluppatori possono semplificare la distribuzione continua e ottenere applicazioni innovative nelle mani degli utenti più rapidamente.

Sebbene le procedure di integrazione e distribuzione continue siano ben consolidate, l'introduzione di contenitori introduce nuove considerazioni, in particolare quando si lavora con applicazioni multi-contenitore.

I servizi DevOps di Azure supportano l'integrazione e la distribuzione continua di applicazioni multi-contenitore in un'ampia gamma di ambienti tramite le attività di distribuzione ufficiali di Servizi DevOps di Azure:Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:

- [Eseguire la distribuzione in un'app Web di Azure per i contenitoriDeploy to an Azure Web App for Containers](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [Eseguire la distribuzione nel servizio Azure KubernetesDeploy to Azure Kubernetes Service](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

Ma è anche possibile distribuire a Docker Swarm o DC/OS usando le attività basate su script di Servizi DevOps di Azure.But you can also deploy to [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) or DC/OS by using Azure DevOps Services script-based tasks.

Per continuare a facilitare l'agilità di distribuzione, questi strumenti offrono eccellenti esperienze di distribuzione da sviluppo a test per i carichi di lavoro dei contenitori, con una scelta di soluzioni di sviluppo e CI/CD.

Nella figura 4-12 è illustrata una pipeline di distribuzione continua che viene distribuita in un cluster Kubernetes nel servizio contenitore di Azure.Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.

![Screenshot della distribuzione dei servizi DevOps di Azure in un cluster Kubernetes.Screenshot of Azure DevOps Services deploying to a Kubernetes cluster.](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

**Figura 4-12.** Pipeline di distribuzione continua di Azure DevOps Services, distribuzione in un cluster KubernetesAzure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster

>[!div class="step-by-step"]
>[Successivo](modernize-your-apps-with-monitoring-and-telemetry.md)
>[precedente](migrate-to-hybrid-cloud-scenarios.md)
