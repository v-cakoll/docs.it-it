---
title: Modernizzare del ciclo di vita dell'app con le pipeline CI/CD-ROM e gli strumenti DevOps nel cloud
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Modernizzare del ciclo di vita dell'app con le pipeline CI/CD-ROM e gli strumenti DevOps nel cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 56dbd4a867e0f47d0f7e681d924584629d763f87
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernizzare del ciclo di vita dell'app con le pipeline CI/CD-ROM e gli strumenti DevOps nel cloud

Aziende necessario innovazione a un ritmo rapido per essere competitivi in marketplace. Recapito di alta qualità, le applicazioni moderne richiede gli strumenti DevOps e i processi di importanza cruciale per implementare questo ciclo costante dell'innovazione. Con gli strumenti DevOps appropriati, gli sviluppatori possono semplificare la distribuzione continua e ottenere più rapidamente applicazioni innovative disposizione degli utenti.

Sebbene procedure consigliate di integrazione e la distribuzione continua sono ben definite, l'introduzione di contenitori introduce nuove considerazioni, in particolare quando si lavora con le applicazioni multi-contenitore.

Visual Studio Team Services supporta l'integrazione continua e distribuzione di applicazioni multi-contenitore a un'ampia gamma di ambienti mediante le attività di distribuzione ufficiale del Team Services:

-   [Distribuire in una macchina virtuale Host Docker autonoma](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o versioni successive)

-   [Distribuire a Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [Distribuire il servizio di contenitore di Azure – Kubernetes](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

Ma è anche possibile distribuire [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o controller di dominio o del sistema operativo tramite le attività di Team Services basato su script.

Per continuare agevolare la flessibilità di distribuzione, questi strumenti offrono si verifica nella distribuzione di dev-a-a-produzione di prova eccellente per carichi di lavoro contenitore, con una gamma di sviluppo e le soluzioni CI/CD-ROM.

Figura 4-12 illustra una pipeline di distribuzione continua che distribuisce un cluster Kubernetes contenitore nel servizio di Azure.

![Pipeline distribuzione continua di Visual Studio Team Services, la distribuzione in un cluster Kubernetes](./media/image12.png)

> **Figura 4-12.** Pipeline distribuzione continua di Visual Studio Team Services, la distribuzione in un cluster Kubernetes

>[!div class="step-by-step"]
[Precedente](modernize-your-apps-with-monitoring-and-telemetry.md)
[Successivo](migrate-to-hybrid-cloud-scenarios.md)
