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
# <a name="implementing-retries-with-exponential-backoff"></a>Implementazione di tentativi con backoff esponenziale

[*Tentativi con backoff esponenziale* ](https://docs.microsoft.com/azure/architecture/patterns/retry) è una tecnica che tenta di ripetere un'operazione, con un tempo di attesa aumenta in modo esponenziale, fino a quando non è stato raggiunto un numero massimo di tentativi (il [backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)). Questa tecnica basata sul modello il fatto che le risorse cloud in modo intermittente siano disponibili per più di pochi secondi per qualsiasi motivo. Ad esempio, agente di orchestrazione potrebbe essere lo spostamento di un contenitore a un altro nodo in un cluster di bilanciamento del carico. Durante questo periodo, alcune richieste potrebbero non riuscire. Un altro esempio potrebbe essere un database come SQL Azure, in cui un database può essere spostato in un altro server per il carico di bilanciamento del carico, causando il database deve essere disponibile per alcuni secondi.

Esistono molti approcci per implementare la logica di tentativi con backoff esponenziale.


>[!div class="step-by-step"]
[Precedente] (parziale-errore-strategies.md) [Avanti] (implement-resilient-entity-framework-core-sql-connections.md)
