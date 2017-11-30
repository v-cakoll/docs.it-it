---
title: Implementazione di tentativi con backoff esponenziale
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di tentativi con backoff esponenziale
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8ad8c6363ddff59915efc076161fe6b76074bbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="2c4c5-104">Implementazione di tentativi con backoff esponenziale</span><span class="sxs-lookup"><span data-stu-id="2c4c5-104">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="2c4c5-105">[*Tentativi con backoff esponenziale* ](https://docs.microsoft.com/azure/architecture/patterns/retry) è una tecnica che tenta di ripetere un'operazione, con un tempo di attesa aumenta in modo esponenziale, fino a quando non è stato raggiunto un numero massimo di tentativi (il [backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="2c4c5-105">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="2c4c5-106">Questa tecnica basata sul modello il fatto che le risorse cloud in modo intermittente siano disponibili per più di pochi secondi per qualsiasi motivo.</span><span class="sxs-lookup"><span data-stu-id="2c4c5-106">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="2c4c5-107">Ad esempio, agente di orchestrazione potrebbe essere lo spostamento di un contenitore a un altro nodo in un cluster di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="2c4c5-107">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="2c4c5-108">Durante questo periodo, alcune richieste potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="2c4c5-108">During that time, some requests might fail.</span></span> <span data-ttu-id="2c4c5-109">Un altro esempio potrebbe essere un database come SQL Azure, in cui un database può essere spostato in un altro server per il carico di bilanciamento del carico, causando il database deve essere disponibile per alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="2c4c5-109">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="2c4c5-110">Esistono molti approcci per implementare la logica di tentativi con backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="2c4c5-110">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2c4c5-111">[Precedente] (parziale-errore-strategies.md) [Avanti] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="2c4c5-111">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
