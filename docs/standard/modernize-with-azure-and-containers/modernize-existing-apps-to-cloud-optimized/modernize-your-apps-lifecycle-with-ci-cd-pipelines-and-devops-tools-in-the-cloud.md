---
title: Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Modernizza il ciclo di vita dell'app con le pipeline di integrazione continua/recapito Continuo e strumenti DevOps nel cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: c4eeb5606d3ea93b76efee58ddfecae0abbbd743
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012180"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud

È necessario che le aziende moderne innovazione rapida per essere competitivi nel marketplace. Distribuzione di alta qualità, le applicazioni moderne richiede strumenti DevOps e i processi di importanza cruciale per implementare questo ciclo costante di innovazione. Con gli strumenti DevOps, gli sviluppatori possono semplificare la distribuzione continua e ottenere più rapidamente applicazioni innovative nelle mani degli utenti.

Anche se l'integrazione e distribuzione continue sono ben definite, l'introduzione di contenitori introduce nuove considerazioni, specialmente quando si lavora con le applicazioni multi-contenitore.

Servizi di Azure DevOps supporta l'integrazione continua e distribuzione di applicazioni multi-contenitore in un'ampia gamma di ambienti tramite le attività di distribuzione di servizi di Azure DevOps ufficiale:

- [Distribuire alla macchina virtuale Host Docker autonoma](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o versioni successive)

- [Distribuire in Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

- [Distribuire nel servizio contenitore di Azure – Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

Ma è anche possibile distribuire [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS tramite le attività di servizi di Azure DevOps basato su script.

Per continuare a favorire l'agilità della distribuzione, questi strumenti offrono esperienze eccellente dev da-test-a-distribuzione di produzione per carichi di lavoro contenitore con una gamma di soluzioni di integrazione continua/recapito Continuo e sviluppo.

Figura 4-12 illustra una pipeline di distribuzione continua che distribuisce un cluster Kubernetes nel servizio contenitore di Azure.

![Pipeline di distribuzione continua DevOps servizi Azure, la distribuzione in un cluster Kubernetes](./media/image12.png)

> **Figura 4-12.** Pipeline di distribuzione continua DevOps servizi Azure, la distribuzione in un cluster Kubernetes

>[!div class="step-by-step"]
>[Precedente](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Successivo](migrate-to-hybrid-cloud-scenarios.md)