---
title: Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cccf78ef5b7683a2eefa3efab50a7bbe1bffda18
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="af30f-103">Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="af30f-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="af30f-104">Il servizio contenitore di Azure consente di ottimizzare la configurazione di strumenti open source più diffusi e tecnologie in modo specifico per Azure.</span><span class="sxs-lookup"><span data-stu-id="af30f-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="af30f-105">È possibile ottenere una soluzione aperta che offre la portabilità per i contenitori e per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="af30f-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="af30f-106">Selezionare le dimensioni, il numero di host e gli strumenti di orchestrator.</span><span class="sxs-lookup"><span data-stu-id="af30f-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="af30f-107">Il servizio contenitore di Azure gestisce l'infrastruttura per l'utente.</span><span class="sxs-lookup"><span data-stu-id="af30f-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="af30f-108">Se sta già lavorando con orchestrators open source come Kubernetes, Docker Swarm o controller di dominio o del sistema operativo, è necessario modificare le procedure di gestione esistente per spostare i carichi di lavoro contenitore nel cloud.</span><span class="sxs-lookup"><span data-stu-id="af30f-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="af30f-109">Utilizzare gli strumenti di gestione di applicazioni ha già familiarità con e di connettersi tramite l'endpoint dell'API standard per l'agente di orchestrazione di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="af30f-109">Use the application management tools that you're already familiar with, and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="af30f-110">Se si utilizza contenitori Linux Docker, ma anche il supporto di contenitori di Windows come di 2017 (alcune versioni precedenti, alcune più di recente, in base all'agente di orchestrazione), tutti questi orchestrators sono ambienti avanzati.</span><span class="sxs-lookup"><span data-stu-id="af30f-110">All these orchestrators are mature environments if you are using Linux Docker containers, but they also support Windows Containers as of 2017 (some earlier, some more recently, depending on the orchestrator).</span></span>

<span data-ttu-id="af30f-111">Ad esempio, in Kubernetes, il supporto per i contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori di Windows in Kubernetes è anche molto efficace e affidabile (in anteprima fino all'inizio rientrano 2017).</span><span class="sxs-lookup"><span data-stu-id="af30f-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also very effective and reliable (in preview until early fall 2017).</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="af30f-112">[Precedente](when-to-deploy-windows-containers-to-service-fabric.md)
[Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="af30f-112">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
