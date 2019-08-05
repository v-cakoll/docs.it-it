---
title: Implementazione dei tentativi con backoff esponenziale
description: Informazioni su come implementare i tentativi con backoff esponenziale.
ms.date: 10/16/2018
ms.openlocfilehash: 1b948e399495eeb12016006442ac08d2b04f2e69
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674538"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="bdb98-103">Implementazione dei tentativi con backoff esponenziale</span><span class="sxs-lookup"><span data-stu-id="bdb98-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="bdb98-104">I [*tentativi con backoff esponenziale*](/azure/architecture/patterns/retry) sono una tecnica che ripete un'operazione con un tempo di attesa che aumenta in modo esponenziale, fino al raggiungimento del numero massimo di tentativi ([backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="bdb98-104">[*Retries with exponential backoff*](/azure/architecture/patterns/retry) is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="bdb98-105">Questa tecnica si basa sul presupposto che le risorse cloud potrebbero essere non disponibili in modo intermittente per più di alcuni secondi, per qualsiasi motivo.</span><span class="sxs-lookup"><span data-stu-id="bdb98-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="bdb98-106">Ad esempio, quando un agente di orchestrazione sposta un contenitore in un altro nodo in un cluster per il bilanciamento del carico,</span><span class="sxs-lookup"><span data-stu-id="bdb98-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="bdb98-107">durante l'operazione, alcune richieste potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="bdb98-107">During that time, some requests might fail.</span></span> <span data-ttu-id="bdb98-108">Oppure, in SQL Azure, dove un database può essere spostato in un altro server per il bilanciamento del carico, il database non sarà disponibile per alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="bdb98-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="bdb98-109">Esistono molti approcci all'implementazione della logica per i tentativi con backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="bdb98-109">There are many approaches to implement retries logic with exponential backoff.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bdb98-110">[Precedente](partial-failure-strategies.md)
>[Successivo](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="bdb98-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>
