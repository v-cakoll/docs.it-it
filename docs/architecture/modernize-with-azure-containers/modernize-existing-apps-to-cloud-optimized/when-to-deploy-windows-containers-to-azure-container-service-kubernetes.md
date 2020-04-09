---
title: Quando distribuire i contenitori di Windows nel servizio contenitore di Azure, ovvero KubernetesWhen to deploy Windows Containers to Azure Container Service (ovvero Kubernetes)
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Quando distribuire i contenitori di Windows nel servizio contenitore di Azure, ovvero KubernetesWhen to deploy Windows Containers to Azure Container Service (ovvero Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 3ff51a70d4e158b831155ab4992ec32f5d98cedb
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987764"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Quando distribuire i contenitori di Windows nel servizio contenitore di Azure, ovvero KubernetesWhen to deploy Windows Containers to Azure Container Service (ovvero Kubernetes)

Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure. Si ottiene una soluzione aperta che offre portabilità sia per i contenitori che per la configurazione dell'applicazione. Selezionare la dimensione, il numero di host e gli strumenti dell'agente di orchestrazione. Il servizio contenitore di Azure gestisce automaticamente l'infrastruttura.

Se si sta già lavorando con orchestratori open source come Kubernetes, Docker Swarm o DC/OS, non è necessario modificare le procedure di gestione esistenti per spostare i carichi di lavoro dei contenitori nel cloud. Usare gli strumenti di gestione delle applicazioni che già conosci e connetterti tramite gli endpoint API standard per l'agente di orchestrazione di tua scelta.

Tutti questi orchestratori sono ambienti maturi se si utilizzano contenitori Docker Linux, ma potrebbe essere solo nello stato di anteprima per i contenitori di Windows.All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.

Ad esempio, in Kubernetes, il supporto per i contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori di Windows su Kubernetes è efficace (in anteprima in ACS all'inizio del 2018).

Nota importante: la versione evoluta e "più PaaS" di ACS (Azure Container Service) per Kubernetes è AKS (Azure Kubernetes Service), tuttavia, i contenitori di Windows non sono ancora supportati a partire dal secondo trimestre 2018, ma sarà presto supportato.

>[!div class="step-by-step"]
>[Successivo](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[precedente](choosing-azure-compute-options-for-container-based-applications.md)
