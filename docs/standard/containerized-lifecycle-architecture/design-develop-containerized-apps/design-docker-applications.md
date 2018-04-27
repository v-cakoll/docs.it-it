---
title: Progettazione di applicazioni di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 951169a6b7c458872f5c90a8845826b675671101
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="design-docker-applications"></a><span data-ttu-id="950e6-103">Progettazione di applicazioni di Docker</span><span class="sxs-lookup"><span data-stu-id="950e6-103">Design Docker applications</span></span>

<span data-ttu-id="950e6-104">Capitolo 1 introdotti i concetti fondamentali relativi contenitori e Docker.</span><span class="sxs-lookup"><span data-stu-id="950e6-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="950e6-105">Tali informazioni sono il livello di base di informazioni necessarie per iniziare.</span><span class="sxs-lookup"><span data-stu-id="950e6-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="950e6-106">Tuttavia, le applicazioni aziendali possono essere complessi e composti da più servizi anziché un singolo servizio o un contenitore.</span><span class="sxs-lookup"><span data-stu-id="950e6-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="950e6-107">Per i casi di utilizzo facoltativo, è necessario conoscere altri approcci per progettazione, ad esempio architettura orientata ai servizi (SOA) e i concetti di microservizi più avanzate e contenitore concetti di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="950e6-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="950e6-108">L'ambito di questo documento non è limitato a microservizi ma per qualsiasi ciclo di vita delle applicazioni di Docker, pertanto non esplorare architettura microservizi in profondità perché è anche possibile usare i contenitori e Docker con i processi, le attività in background o SAN regolare o anche con approcci alla distribuzione di qualsiasi applicazione.</span><span class="sxs-lookup"><span data-stu-id="950e6-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="950e6-109">Tuttavia, prima di passare all'applicazione ciclo di vita e DevOps, è importante sapere come si prevede di progettazione e creare l'applicazione e quali sono le scelte di progettazione.</span><span class="sxs-lookup"><span data-stu-id="950e6-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="950e6-110">[Precedente] [Avanti] (comuni contenitore-progettazione principles.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="950e6-110">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
