---
title: Passaggi nel flusso di lavoro DevOps del ciclo esterno per un'applicazione Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.date: 02/15/2019
ms.openlocfilehash: 9fdc5acfd375e4f2266859f061ef1c854286b914
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673778"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Creazione di pipeline CI/CD in Azure DevOps Services per un'applicazione .NET Core 2.0 in contenitori e distribuzione in un cluster Kubernetes

Nella figura 5-12 è possibile vedere lo scenario DevOps end-to-end relativo alla gestione e alla compilazione del codice, alla compilazione delle immagini Docker, al push delle immagini Docker in un registro Docker e infine alla distribuzione in un cluster Kubernetes in Azure.

![Flusso di lavoro: avvia nel computer di sviluppo. Il push in un repository inizia l'attività di compilazione/integrazione continua tramite un'immagine personalizzata che viene inserita in un registro Docker e quindi usata dall'attività di distribuzione/distribuzione continua per eseguire infine il push al servizio Azure Kubernetes.](media/docker-workflow-ci-cd-aks.png)

**Figura 5-12**. Scenario di integrazione continua/distribuzione continua che crea immagini Docker e le distribuisce in un cluster Kubernetes in Azure

È importante sottolineare che le due pipeline (compilazione/integrazione continua e rilascio/distribuzione continua) sono connesse tramite il registro Docker (ad esempio Docker Hub o Registro Azure Container). Il registro Docker è una delle principali differenze rispetto a un processo di integrazione continua/distribuzione continua tradizionale senza Docker.

Come illustrato nella figura 5-13, la prima fase è costituita dalla pipeline di compilazione/integrazione continua. In Azure DevOps Services è possibile creare pipeline di compilazione/integrazione continua che compilano il codice, creano le immagini Docker e ne eseguono il push in un registro Docker, ad esempio Docker Hub o Registro Azure Container.

![Visualizzazione nel browser di Azure DevOps, definizione dell'attività del processo di compilazione.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Figura 5-13**. Pipeline di compilazione/integrazione continua in Azure DevOps che crea immagini Docker e ne esegue il push in un registro Docker

La seconda fase consiste nella creazione di una pipeline di distribuzione/rilascio. In Azure DevOps Services è possibile creare facilmente una pipeline di distribuzione destinata a un cluster Kubernetes tramite le attività di Kubernetes per Azure DevOps Services, come illustrato nella Figura 5-14.

![Visualizzazione nel browser di Azure DevOps, definizione dell'attività di distribuzione Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Figura 5-14**. Pipeline di rilascio/distribuzione continua in Azure DevOps che esegue la distribuzione in un cluster Kubernetes

> [!Procedura dettagliata] Distribuzione di eShopModernized in Kubernetes:
>
> Per una procedura dettagliata della pipeline di integrazione continua/distribuzione continua di Azure DevOps, vedere questo post: \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[Successivo](docker-application-outer-loop-devops-workflow.md)
>[precedente](../run-manage-monitor-docker-environments/index.md)
