---
title: Casi in cui distribuire i contenitori di Windows al servizio contenitore di Azure (ovvero Kubernetes)
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Casi in cui distribuire i contenitori di Windows al servizio contenitore di Azure (ovvero Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 921767b52f2b0d80f2d31d972b65ac7551d2f7c5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643565"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="2d18f-103">Casi in cui distribuire i contenitori di Windows al servizio contenitore di Azure (ovvero Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="2d18f-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="2d18f-104">Servizio contenitore di Azure ottimizza la configurazione di diffusi strumenti open source e tecnologie in modo specifico per Azure.</span><span class="sxs-lookup"><span data-stu-id="2d18f-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="2d18f-105">Si ottiene una soluzione che offre la portabilità per i contenitori sia per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d18f-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="2d18f-106">Si seleziona la dimensione, il numero di host e gli strumenti di orchestrator.</span><span class="sxs-lookup"><span data-stu-id="2d18f-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="2d18f-107">Servizio contenitore di Azure gestisce l'infrastruttura per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2d18f-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="2d18f-108">Se sta già lavorando con gli agenti di orchestrazione open source come Kubernetes, Docker Swarm o DC/OS, non devi modificare le procedure di gestione esistenti per spostare i carichi di lavoro di contenitore nel cloud.</span><span class="sxs-lookup"><span data-stu-id="2d18f-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="2d18f-109">Usare gli strumenti di gestione di applicazioni che ha già familiarità e connettersi tramite l'endpoint API standard per l'agente di orchestrazione di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="2d18f-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="2d18f-110">Tutti questi agenti di orchestrazione sono ambienti maturi se si usano contenitori Docker di Linux, ma potrebbe essere solo stavu anteprima per i contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="2d18f-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="2d18f-111">Ad esempio, in Kubernetes, il supporto per contenitori è nativo (cittadino di prima classe), quindi l'uso di contenitori Windows in Kubernetes è inoltre efficace (in anteprima nel servizio contenitore di AZURE a partire dall'inizio del 2018).</span><span class="sxs-lookup"><span data-stu-id="2d18f-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="2d18f-112">Nota importante: L'evoluto e "PaaS più" versione di ACS (servizio contenitore di Azure) per Kubernetes è servizio contenitore di AZURE (Azure Kubernetes Service), tuttavia, i contenitori di Windows non sono ancora supportati a partire da 2018 (domanda 2), ma sarà supportata a breve.</span><span class="sxs-lookup"><span data-stu-id="2d18f-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2d18f-113">[Precedente](when-to-deploy-windows-containers-to-service-fabric.md)
>[Successivo](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="2d18f-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
