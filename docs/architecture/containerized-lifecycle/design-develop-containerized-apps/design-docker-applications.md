---
title: Progettare applicazioni Docker
description: Riferimento a una guida dettagliata all'architettura dei microservizi, argomento non trattato nel dettaglio nella presente guida.
ms.date: 02/15/2019
ms.openlocfilehash: b9539ff4edf405ab890d83be59a248ffa2360c99
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674038"
---
# <a name="design-docker-applications"></a><span data-ttu-id="34786-103">Progettare applicazioni Docker</span><span class="sxs-lookup"><span data-stu-id="34786-103">Design Docker applications</span></span>

<span data-ttu-id="34786-104">Il capitolo 1 ha presentato i concetti fondamentali relativi ai contenitori e a Docker.</span><span class="sxs-lookup"><span data-stu-id="34786-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="34786-105">Le informazioni fornite rappresentano il livello di conoscenza di base necessario per iniziare.</span><span class="sxs-lookup"><span data-stu-id="34786-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="34786-106">Le applicazioni aziendali tuttavia possono essere complesse e composte da più servizi anziché da un singolo servizio o contenitore.</span><span class="sxs-lookup"><span data-stu-id="34786-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="34786-107">Per questi casi d'uso facoltativi, è necessario conoscere ulteriori approcci di programmazione, ad esempio SOA (Service-Oriented Architecture), e concetti più avanzati relativi ai microservizi e all'orchestrazione dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="34786-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="34786-108">Poiché in questo documento non sono descritti solamente i microservizi ma il ciclo di vita di qualsiasi applicazione Docker, l'architettura dei microservizi non è descritta nel dettaglio poiché è anche possibile usare i contenitori e Docker con una normale architettura SOA, attività o processi in background o persino con approcci di sviluppo di applicazioni monolitiche.</span><span class="sxs-lookup"><span data-stu-id="34786-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="34786-109">**Altre informazioni** Per altre informazioni sulle applicazioni aziendali e una descrizione dettagliata dell'architettura dei microservizi, leggere la guida [NET Microservices: Architecture for Containerized .NET Applications](../../microservices/index.md) (Microservizi NET: Architettura per le applicazioni .NET aggiunte a contenitori) che è possibile scaricare da <https://aka.ms/MicroservicesEbook>.</span><span class="sxs-lookup"><span data-stu-id="34786-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="34786-110">Tuttavia, prima di addentrarsi nel ciclo di vita delle applicazioni e in DevOps, è importante conoscere il modo in cui l'applicazione verrà progettata e costruita e le scelte di progettazione.</span><span class="sxs-lookup"><span data-stu-id="34786-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="34786-111">[Precedente](index.md)
>[Successivo](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="34786-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
