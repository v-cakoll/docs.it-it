---
title: Modernizzare del ciclo di vita dell'app con le pipeline CI/CD-ROM e gli strumenti DevOps nel cloud
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Modernizzare del ciclo di vita dell'app con le pipeline CI/CD e gli strumenti DevOps nel cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 63907a1911b4c95f0dbecb2af33964225cf3e7b1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
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
