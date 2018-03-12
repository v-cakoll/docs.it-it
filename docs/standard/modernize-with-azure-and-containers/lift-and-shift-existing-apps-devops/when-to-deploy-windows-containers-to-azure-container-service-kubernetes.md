---
title: Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f0a096712e14e506403961f0b9283ca4b707cbda
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)

Il servizio contenitore di Azure consente di ottimizzare la configurazione di strumenti open source più diffusi e tecnologie in modo specifico per Azure. È possibile ottenere una soluzione aperta che offre la portabilità per i contenitori e per la configurazione dell'applicazione. Selezionare le dimensioni, il numero di host e gli strumenti di orchestrator. Il servizio contenitore di Azure gestisce l'infrastruttura per l'utente.

Se sta già lavorando con orchestrators open source come Kubernetes, Docker Swarm o controller di dominio o del sistema operativo, è necessario modificare le procedure di gestione esistente per spostare i carichi di lavoro contenitore nel cloud. Utilizzare gli strumenti di gestione di applicazioni ha già familiarità con e di connettersi tramite l'endpoint dell'API standard per l'agente di orchestrazione di propria scelta.

Se si utilizza contenitori Linux Docker, ma anche il supporto di contenitori di Windows come di 2017 (alcune versioni precedenti, alcune più di recente, in base all'agente di orchestrazione), tutti questi orchestrators sono ambienti avanzati.

Ad esempio, in Kubernetes, il supporto per i contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori di Windows in Kubernetes è anche molto efficace e affidabile (in anteprima fino all'inizio rientrano 2017).

>[!div class="step-by-step"]
[Precedente](when-to-deploy-windows-containers-to-service-fabric.md)
[Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
