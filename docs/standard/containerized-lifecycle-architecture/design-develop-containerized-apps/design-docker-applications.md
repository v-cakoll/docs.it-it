---
title: Progettazione di applicazioni di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aeddd3a4b7ebd3c917fba46e048fbab5a77dda19
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="design-docker-applications"></a><span data-ttu-id="961b2-104">Progettazione di applicazioni di Docker</span><span class="sxs-lookup"><span data-stu-id="961b2-104">Design Docker applications</span></span>

<span data-ttu-id="961b2-105">Capitolo 1 introdotti i concetti fondamentali relativi contenitori e Docker.</span><span class="sxs-lookup"><span data-stu-id="961b2-105">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="961b2-106">Tali informazioni sono il livello di base di informazioni necessarie per iniziare.</span><span class="sxs-lookup"><span data-stu-id="961b2-106">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="961b2-107">Tuttavia, le applicazioni aziendali possono essere complessi e composti da più servizi anziché un singolo servizio o un contenitore.</span><span class="sxs-lookup"><span data-stu-id="961b2-107">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="961b2-108">Per i casi di utilizzo facoltativo, è necessario conoscere altri approcci per progettazione, ad esempio architettura orientata ai servizi (SOA) e i concetti di microservizi più avanzate e contenitore concetti di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="961b2-108">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="961b2-109">L'ambito di questo documento non è limitato a microservizi ma per qualsiasi ciclo di vita delle applicazioni di Docker, pertanto non esplorare architettura microservizi in profondità perché è anche possibile usare i contenitori e Docker con i processi, le attività in background o SAN regolare o anche con approcci alla distribuzione di qualsiasi applicazione.</span><span class="sxs-lookup"><span data-stu-id="961b2-109">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="961b2-110">Tuttavia, prima di passare all'applicazione ciclo di vita e DevOps, è importante sapere come si prevede di progettazione e creare l'applicazione e quali sono le scelte di progettazione.</span><span class="sxs-lookup"><span data-stu-id="961b2-110">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="961b2-111">[Precedente] [Avanti] (comuni contenitore-progettazione principles.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="961b2-111">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
