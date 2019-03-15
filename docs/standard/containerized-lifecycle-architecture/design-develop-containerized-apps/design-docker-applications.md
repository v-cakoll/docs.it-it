---
title: Progettare applicazioni Docker
description: Fai clic qui per un riferimento a una guida approfondita su architettura di microservizi, perché questo è un argomento che non è descritta in dettaglio in questa Guida.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 1d49f7509c0a12edfe375486429147e8fd240b2d
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57846330"
---
# <a name="design-docker-applications"></a><span data-ttu-id="2b1c2-103">Progettare applicazioni Docker</span><span class="sxs-lookup"><span data-stu-id="2b1c2-103">Design Docker applications</span></span>

<span data-ttu-id="2b1c2-104">Capitolo 1 di sono stati introdotti i concetti fondamentali relative a contenitori e Docker.</span><span class="sxs-lookup"><span data-stu-id="2b1c2-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="2b1c2-105">Tali informazioni sono il livello di base di informazioni necessarie per iniziare.</span><span class="sxs-lookup"><span data-stu-id="2b1c2-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="2b1c2-106">Tuttavia, le applicazioni aziendali possono essere complessi e composte da più servizi anziché un singolo servizio o contenitore.</span><span class="sxs-lookup"><span data-stu-id="2b1c2-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="2b1c2-107">Per i casi di utilizzo facoltativo, è necessario conoscere altri approcci alla progettazione, ad esempio Service-Oriented Architecture (SOA) e i concetti di microservizi più avanzati e un contenitore ai concetti di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="2b1c2-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="2b1c2-108">L'ambito di questo documento non è limitato ai microservizi, ma per qualsiasi ciclo di vita delle applicazioni di Docker, pertanto, non esplori architettura di microservizi in modo approfondito perché è anche possibile usare i contenitori e Docker con regolare SOA, le attività in background o processi o persino con gli approcci di distribuzione applicazione monolitica.</span><span class="sxs-lookup"><span data-stu-id="2b1c2-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="2b1c2-109">**Altre informazioni** per altre informazioni sulle applicazioni aziendali e architettura di microservizi in profondità, leggere la Guida [NET Microservizi: Architettura per applicazioni .NET in contenitori](../../microservices-architecture/index.md) che è anche possibile scaricare da <https://aka.ms/MicroservicesEbook>.</span><span class="sxs-lookup"><span data-stu-id="2b1c2-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices-architecture/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="2b1c2-110">Tuttavia, prima di addentrarsi il ciclo di vita dell'applicazione e DevOps, è importante conoscere come verrà orchestrata per progettare e costrutto dell'applicazione e quali sono le scelte di progettazione.</span><span class="sxs-lookup"><span data-stu-id="2b1c2-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2b1c2-111">[Precedente](index.md)
>[Successivo](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="2b1c2-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>