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
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="06298-103">Quando distribuire i contenitori di Windows nel servizio contenitore di Azure (Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="06298-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="06298-104">Il servizio contenitore di Azure ottimizza la configurazione dei più diffusi strumenti e tecnologie open source appositamente per Azure.</span><span class="sxs-lookup"><span data-stu-id="06298-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="06298-105">Si ottiene una soluzione aperta che offre la portabilità per i contenitori e per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="06298-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="06298-106">Selezionare le dimensioni, il numero di host e gli strumenti di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="06298-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="06298-107">Il servizio contenitore di Azure gestisce automaticamente l'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="06298-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="06298-108">Se si sta già lavorando con agenti di orchestrazione open source come Kubernetes, Docker Swarm o DC/OS, non è necessario modificare le procedure di gestione esistenti per spostare i carichi di lavoro dei contenitori nel cloud.</span><span class="sxs-lookup"><span data-stu-id="06298-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="06298-109">Usare gli strumenti di gestione delle applicazioni con cui si ha già familiarità e connettersi tramite gli endpoint API standard per l'agente di orchestrazione scelto.</span><span class="sxs-lookup"><span data-stu-id="06298-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="06298-110">Tutti questi agenti di orchestrazione sono ambienti maturi se si usano contenitori Docker Linux, ma possono essere solo in stato di anteprima per i contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="06298-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="06298-111">In Kubernetes, ad esempio, il supporto per i contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori di Windows in Kubernetes è efficace (in anteprima in ACS a partire dai primi 2018).</span><span class="sxs-lookup"><span data-stu-id="06298-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="06298-112">Nota importante: la versione evoluta e "più PaaS" di ACS (servizio contenitore di Azure) per Kubernetes è AKS (servizio Azure Kubernetes). Tuttavia, i contenitori di Windows non sono ancora supportati a partire da Q2 2018, ma saranno presto supportati.</span><span class="sxs-lookup"><span data-stu-id="06298-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06298-113">[Precedente](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Successivo](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="06298-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
