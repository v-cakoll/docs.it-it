---
title: Passaggi nel flusso di lavoro DevOps del ciclo esterno per un'applicazione Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e11c9ec61ea7d5131595f01ce76b5bb810bb70c0
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063306"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Creazione di pipeline CI/CD in Azure DevOps Services per un'applicazione .NET Core 2.0 in contenitori e distribuzione in un cluster Kubernetes

Nella figura 5-12 è possibile consultare lo scenario di DevOps end-to-end che coprono la gestione del codice, la compilazione del codice, compilazione di immagini Docker, eseguire il push delle immagini Docker in un registro Docker e infine la distribuzione in un cluster Kubernetes in Azure.

![Flusso di lavoro: Viene avviata nel computer di sviluppo. Il push in un repository inizia l'attività di compilazione/integrazione continua usando un'immagine personalizzata che viene inserita in un registro Docker e quindi viene usata dall'attività di distribuzione/recapito Continuo, infine, eseguire il push al servizio contenitore di AZURE.](media/docker-workflow-ci-cd-aks.png)

**Figura 5-12**. Scenario di integrazione continua/recapito Continuo, la creazione di immagini Docker e la distribuzione in un cluster Kubernetes in Azure

È importante evidenziare che le due pipeline compilazione/integrazione continua e rilascio/distribuzione continua, sono connessi tramite il registro Docker (ad esempio Hub Docker o registro contenitori di Azure). Il Registro di Docker è una delle principali differenze rispetto a un processo CI/CD tradizionali senza Docker.

Come illustrato nella figura 5-13, la prima fase è la pipeline di compilazione/integrazione continua. In servizi di Azure DevOps è possibile creare pipeline di compilazione/CI che compila il codice, creare le immagini Docker, eseguirne il push in un registro Docker, ad esempio Hub Docker o registro contenitori di Azure.

![Visualizzazione di esplorazione di Azure DevOps, definizione di attività di processo di compilazione.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Figura 5-13**. Pipeline di compilazione/integrazione continua in DevOps di Azure creano immagini Docker e il push di immagini in un registro Docker

La seconda fase consiste nel creare una pipeline di distribuzione/rilascio. In servizi di Azure DevOps, è possibile creare facilmente una pipeline di distribuzione come destinazione un cluster Kubernetes tramite le attività di Kubernetes per i servizi di Azure DevOps, come illustrato nella figura 5-14.

![Visualizzazione di esplorazione di DevOps di Azure, distribuire la definizione di attività Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Figura 5-14**. Pipeline di rilascio/distribuzione continua nella distribuzione di servizi di Azure DevOps a un cluster Kubernetes

> [! Procedura dettagliata] distribuzione eShopModernized per Kubernetes:
>
> Per una procedura dettagliata della pipeline CI/CD DevOps di Azure, la distribuzione in Kubernetes, vedere questo post di: \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[Precedente](docker-application-outer-loop-devops-workflow.md)
>[Successivo](../run-manage-monitor-docker-environments/index.md)
