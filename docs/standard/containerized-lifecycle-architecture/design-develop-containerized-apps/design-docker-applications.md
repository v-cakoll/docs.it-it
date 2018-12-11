---
title: Progettare applicazioni Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: d02cec0595024eb7bd7c0ac46df093359680da74
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155379"
---
# <a name="design-docker-applications"></a><span data-ttu-id="10c92-103">Progettare applicazioni Docker</span><span class="sxs-lookup"><span data-stu-id="10c92-103">Design Docker applications</span></span>

<span data-ttu-id="10c92-104">Capitolo 1 di sono stati introdotti i concetti fondamentali relative a contenitori e Docker.</span><span class="sxs-lookup"><span data-stu-id="10c92-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="10c92-105">Tali informazioni sono il livello di base di informazioni necessarie per iniziare.</span><span class="sxs-lookup"><span data-stu-id="10c92-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="10c92-106">Tuttavia, le applicazioni aziendali possono essere complessi e composte da più servizi anziché un singolo servizio o contenitore.</span><span class="sxs-lookup"><span data-stu-id="10c92-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="10c92-107">Per i casi di utilizzo facoltativo, è necessario conoscere altri approcci alla progettazione, ad esempio Service-Oriented Architecture (SOA) e i concetti di microservizi più avanzati e un contenitore ai concetti di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="10c92-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="10c92-108">L'ambito di questo documento non è limitato ai microservizi, ma per qualsiasi ciclo di vita delle applicazioni di Docker, pertanto, non esplori architettura di microservizi in modo approfondito perché è anche possibile usare i contenitori e Docker con processi, attività in background o SAO regolare o anche con gli approcci di distribuzione applicazione monolitica.</span><span class="sxs-lookup"><span data-stu-id="10c92-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="10c92-109">Tuttavia, prima di addentrarsi il ciclo di vita dell'applicazione e DevOps, è importante sapere come intende progettazione e costruire l'applicazione e quali sono le scelte di progettazione.</span><span class="sxs-lookup"><span data-stu-id="10c92-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="10c92-110">[Precedente](index.md)
>[Successivo](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="10c92-110">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>