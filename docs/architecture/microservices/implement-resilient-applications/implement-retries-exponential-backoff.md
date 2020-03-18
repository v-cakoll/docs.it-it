---
title: Implementazione dei tentativi con backoff esponenziale
description: Informazioni su come implementare i tentativi con backoff esponenziale.
ms.date: 10/16/2018
ms.openlocfilehash: 1b948e399495eeb12016006442ac08d2b04f2e69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674538"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="3e63a-103">Implementazione dei tentativi con backoff esponenziale</span><span class="sxs-lookup"><span data-stu-id="3e63a-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="3e63a-104">I [*tentativi con backoff esponenziale*](/azure/architecture/patterns/retry) sono una tecnica che ripete un'operazione con un tempo di attesa che aumenta in modo esponenziale, fino al raggiungimento del numero massimo di tentativi ([backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="3e63a-104">[*Retries with exponential backoff*](/azure/architecture/patterns/retry) is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="3e63a-105">Questa tecnica si basa sul presupposto che le risorse cloud potrebbero essere non disponibili in modo intermittente per più di alcuni secondi, per qualsiasi motivo.</span><span class="sxs-lookup"><span data-stu-id="3e63a-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="3e63a-106">Ad esempio, quando un agente di orchestrazione sposta un contenitore in un altro nodo in un cluster per il bilanciamento del carico,</span><span class="sxs-lookup"><span data-stu-id="3e63a-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="3e63a-107">durante l'operazione, alcune richieste potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="3e63a-107">During that time, some requests might fail.</span></span> <span data-ttu-id="3e63a-108">Oppure, in SQL Azure, dove un database può essere spostato in un altro server per il bilanciamento del carico, il database non sarà disponibile per alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="3e63a-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="3e63a-109">Esistono molti approcci all'implementazione della logica per i tentativi con backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="3e63a-109">There are many approaches to implement retries logic with exponential backoff.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3e63a-110">[Successivo](partial-failure-strategies.md)
>[precedente](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="3e63a-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>
