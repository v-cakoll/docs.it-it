---
title: Quando distribuire i contenitori di Windows nel servizio contenitore di Azure (Kubernetes)
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Quando distribuire i contenitori di Windows nel servizio contenitore di Azure (Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577944"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Quando distribuire i contenitori di Windows nel servizio contenitore di Azure (Kubernetes)

Il servizio contenitore di Azure ottimizza la configurazione dei più diffusi strumenti e tecnologie open source appositamente per Azure. Si ottiene una soluzione aperta che offre la portabilità per i contenitori e per la configurazione dell'applicazione. Selezionare le dimensioni, il numero di host e gli strumenti di orchestrazione. Il servizio contenitore di Azure gestisce automaticamente l'infrastruttura.

Se si sta già lavorando con agenti di orchestrazione open source come Kubernetes, Docker Swarm o DC/OS, non è necessario modificare le procedure di gestione esistenti per spostare i carichi di lavoro dei contenitori nel cloud. Usare gli strumenti di gestione delle applicazioni con cui si ha già familiarità e connettersi tramite gli endpoint API standard per l'agente di orchestrazione scelto.

Tutti questi agenti di orchestrazione sono ambienti maturi se si usano contenitori Docker Linux, ma possono essere solo in stato di anteprima per i contenitori di Windows.

In Kubernetes, ad esempio, il supporto per i contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori di Windows in Kubernetes è efficace (in anteprima in ACS a partire dai primi 2018).

Nota importante: la versione evoluta e "più PaaS" di ACS (servizio contenitore di Azure) per Kubernetes è AKS (servizio Azure Kubernetes). Tuttavia, i contenitori di Windows non sono ancora supportati a partire da Q2 2018, ma saranno presto supportati.

>[!div class="step-by-step"]
>[Precedente](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Successivo](choosing-azure-compute-options-for-container-based-applications.md)
