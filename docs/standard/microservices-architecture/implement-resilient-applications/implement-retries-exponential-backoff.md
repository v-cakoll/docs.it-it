---
title: Implementazione dei tentativi con backoff esponenziale
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dei tentativi con backoff esponenziale
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: a5ab15299ecb501691c26bbc6d377e22a38ee51e
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874364"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="afa9c-103">Implementazione dei tentativi con backoff esponenziale</span><span class="sxs-lookup"><span data-stu-id="afa9c-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="afa9c-104">I [*tentativi con backoff esponenziale*](https://docs.microsoft.com/azure/architecture/patterns/retry) sono una tecnica che tenta di ripetere un'operazione con un tempo di attesa che aumenta esponenzialmente, fino a quando non viene raggiunto il numero massimo di tentativi ([backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="afa9c-104">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="afa9c-105">Questa tecnica si basa sul presupposto che le risorse cloud potrebbero essere non disponibili in modo intermittente per più di alcuni secondi, per qualsiasi motivo.</span><span class="sxs-lookup"><span data-stu-id="afa9c-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="afa9c-106">Ad esempio, quando un agente di orchestrazione sposta un contenitore in un altro nodo in un cluster per il bilanciamento del carico,</span><span class="sxs-lookup"><span data-stu-id="afa9c-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="afa9c-107">durante l'operazione, alcune richieste potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="afa9c-107">During that time, some requests might fail.</span></span> <span data-ttu-id="afa9c-108">Oppure, in SQL Azure, dove un database può essere spostato in un altro server per il bilanciamento del carico, il database non sarà disponibile per alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="afa9c-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="afa9c-109">Esistono molti approcci all'implementazione della logica per i tentativi con backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="afa9c-109">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="afa9c-110">[Precedente](partial-failure-strategies.md)
[Successivo](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="afa9c-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>
