---
title: Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)

Il servizio contenitore di Azure consente di ottimizzare la configurazione di strumenti open source più diffusi e tecnologie in modo specifico per Azure. È possibile ottenere una soluzione aperta che offre la portabilità per i contenitori e per la configurazione dell'applicazione. Selezionare le dimensioni, il numero di host e gli strumenti di orchestrator. Il servizio contenitore di Azure gestisce l'infrastruttura per l'utente.

Se sta già lavorando con orchestrators open source come Kubernetes, Docker Swarm o controller di dominio o del sistema operativo, è necessario modificare le procedure di gestione esistente per spostare i carichi di lavoro contenitore nel cloud. Utilizzare gli strumenti di gestione di applicazioni che si ha già familiarità con e connettersi tramite l'endpoint API standard per l'agente di orchestrazione di propria scelta.

Tutti questi orchestrators sono gli ambienti maturi se si usano i contenitori di Linux Docker, ma potrebbe essere solo in stato di anteprima per i contenitori di Windows.

Ad esempio, in Kubernetes, il supporto per i contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori di Windows in Kubernetes è inoltre efficace (in anteprima in ACS a partire da 2018 anticipata).

Nota importante: l'evoluti e "PaaS ulteriori" versione di ACS (servizio contenitore di Azure) per Kubernetes è AKS (servizio di Azure Kubernetes), tuttavia, i contenitori di Windows non sono ancora supportati a partire da 2018 Q2, ma sarà supportato a breve.

>[!div class="step-by-step"]
[Precedente](when-to-deploy-windows-containers-to-service-fabric.md)
[Successivo](choosing-azure-compute-options-for-container-based-applications.md)
