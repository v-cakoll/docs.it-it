---
title: Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Modernizza il ciclo di vita dell'app con pipeline CI/CD e strumenti DevOps nel cloud
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578164"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud

Le aziende odierne devono innovare a ritmo rapido per essere competitive nel Marketplace. La distribuzione di applicazioni moderne di alta qualità richiede strumenti e processi DevOps cruciali per implementare questo ciclo costante di innovazione. Con gli strumenti DevOps corretti, gli sviluppatori possono semplificare la distribuzione continua e ottenere applicazioni innovative in modo più rapido dagli utenti.

Sebbene le procedure di integrazione e distribuzione continue siano ben stabilite, l'introduzione dei contenitori introduce nuove considerazioni, soprattutto quando si lavora con applicazioni a più contenitori.

Azure DevOps Services supporta l'integrazione e la distribuzione continue di applicazioni multicontenitore in diversi ambienti tramite le attività di distribuzione Azure DevOps Services ufficiali:

- [Eseguire la distribuzione in un app Web per contenitori di Azure](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [Eseguire la distribuzione nel servizio contenitore di Azure-Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

È anche possibile eseguire la distribuzione a [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS usando Azure DevOps Services attività basate su script.

Per continuare a facilitare l'agilità della distribuzione, questi strumenti offrono ottime esperienze di distribuzione da sviluppo a test per la produzione per i carichi di lavoro dei contenitori, con una scelta di sviluppo e soluzioni di integrazione continua/distribuzione continua.

La figura 4-12 Mostra una pipeline di distribuzione continua che distribuisce in un cluster Kubernetes nel servizio contenitore di Azure.

![Azure DevOps Services pipeline di distribuzione continua, distribuzione in un cluster Kubernetes](./media/image12.png)

> **Figura 4-12.** Azure DevOps Services pipeline di distribuzione continua, distribuzione in un cluster Kubernetes

>[!div class="step-by-step"]
>[Precedente](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Successivo](migrate-to-hybrid-cloud-scenarios.md)
