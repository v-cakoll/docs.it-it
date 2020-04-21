---
title: Progettare applicazioni Docker
description: Riferimento a una guida dettagliata all'architettura dei microservizi, argomento non trattato nel dettaglio nella presente guida.
ms.date: 02/15/2019
ms.openlocfilehash: b8a08658ec6c3df3e1aed596a0240223768dd647
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738469"
---
# <a name="design-docker-applications"></a><span data-ttu-id="bb0e4-103">Progettare applicazioni Docker</span><span class="sxs-lookup"><span data-stu-id="bb0e4-103">Design Docker applications</span></span>

<span data-ttu-id="bb0e4-104">Il capitolo 1 ha presentato i concetti fondamentali relativi ai contenitori e a Docker.</span><span class="sxs-lookup"><span data-stu-id="bb0e4-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="bb0e4-105">Le informazioni fornite rappresentano il livello di conoscenza di base necessario per iniziare.</span><span class="sxs-lookup"><span data-stu-id="bb0e4-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="bb0e4-106">Le applicazioni aziendali tuttavia possono essere complesse e composte da più servizi anziché da un singolo servizio o contenitore.</span><span class="sxs-lookup"><span data-stu-id="bb0e4-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="bb0e4-107">Per questi casi d'uso facoltativi, è necessario conoscere ulteriori approcci di programmazione, ad esempio SOA (Service-Oriented Architecture), e concetti più avanzati relativi ai microservizi e all'orchestrazione dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="bb0e4-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="bb0e4-108">L'ambito di questo documento non è limitato ai microservizi, ma a qualsiasi ciclo di vita dell'applicazione Docker, pertanto non esplora l'architettura dei microservizi in modo approfondito perché è anche possibile utilizzare contenitori e Docker con SOA regolari, attività o processi in background o anche con approcci di distribuzione monolitici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb0e4-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you can also use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="bb0e4-109">**Maggiori informazioni** Per altre informazioni sulle applicazioni aziendali e sull'architettura dei microservizi approfondita, leggere la guida <https://aka.ms/MicroservicesEbook> [Net Microservices: Architecture for Containerized Applications](../../microservices/index.md) che è anche possibile scaricare da .</span><span class="sxs-lookup"><span data-stu-id="bb0e4-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="bb0e4-110">Tuttavia, prima di addentrarsi nel ciclo di vita delle applicazioni e in DevOps, è importante conoscere il modo in cui l'applicazione verrà progettata e costruita e le scelte di progettazione.</span><span class="sxs-lookup"><span data-stu-id="bb0e4-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bb0e4-111">[Successivo](index.md)
>[precedente](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="bb0e4-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
