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
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="3087f-103">Quando distribuire i contenitori di Windows per il servizio contenitore di Azure (vale a dire Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="3087f-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="3087f-104">Il servizio contenitore di Azure consente di ottimizzare la configurazione di strumenti open source più diffusi e tecnologie in modo specifico per Azure.</span><span class="sxs-lookup"><span data-stu-id="3087f-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="3087f-105">È possibile ottenere una soluzione aperta che offre la portabilità per i contenitori e per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3087f-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="3087f-106">Selezionare le dimensioni, il numero di host e gli strumenti di orchestrator.</span><span class="sxs-lookup"><span data-stu-id="3087f-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="3087f-107">Il servizio contenitore di Azure gestisce l'infrastruttura per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3087f-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="3087f-108">Se sta già lavorando con orchestrators open source come Kubernetes, Docker Swarm o controller di dominio o del sistema operativo, è necessario modificare le procedure di gestione esistente per spostare i carichi di lavoro contenitore nel cloud.</span><span class="sxs-lookup"><span data-stu-id="3087f-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="3087f-109">Utilizzare gli strumenti di gestione di applicazioni che si ha già familiarità con e connettersi tramite l'endpoint API standard per l'agente di orchestrazione di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="3087f-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="3087f-110">Tutti questi orchestrators sono gli ambienti maturi se si usano i contenitori di Linux Docker, ma potrebbe essere solo in stato di anteprima per i contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="3087f-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="3087f-111">Ad esempio, in Kubernetes, il supporto per i contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori di Windows in Kubernetes è inoltre efficace (in anteprima in ACS a partire da 2018 anticipata).</span><span class="sxs-lookup"><span data-stu-id="3087f-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="3087f-112">Nota importante: l'evoluti e "PaaS ulteriori" versione di ACS (servizio contenitore di Azure) per Kubernetes è AKS (servizio di Azure Kubernetes), tuttavia, i contenitori di Windows non sono ancora supportati a partire da 2018 Q2, ma sarà supportato a breve.</span><span class="sxs-lookup"><span data-stu-id="3087f-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="3087f-113">[Precedente](when-to-deploy-windows-containers-to-service-fabric.md)
[Successivo](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="3087f-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
