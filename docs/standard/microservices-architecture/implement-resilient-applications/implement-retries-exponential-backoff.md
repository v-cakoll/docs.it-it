---
title: Implementazione dei tentativi con backoff esponenziale
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dei tentativi con backoff esponenziale
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: e0758ee8fe28cb45ecd35ad07ddc738c12614973
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148769"
---
# <a name="implement-retries-with-exponential-backoff"></a>Implementazione dei tentativi con backoff esponenziale

I [*tentativi con backoff esponenziale*](https://docs.microsoft.com/azure/architecture/patterns/retry) sono una tecnica che tenta di ripetere un'operazione con un tempo di attesa che aumenta esponenzialmente, fino a quando non viene raggiunto il numero massimo di tentativi ([backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)). Questa tecnica si basa sul presupposto che le risorse cloud potrebbero essere non disponibili in modo intermittente per più di alcuni secondi, per qualsiasi motivo. Ad esempio, quando un agente di orchestrazione sposta un contenitore in un altro nodo in un cluster per il bilanciamento del carico, durante l'operazione, alcune richieste potrebbero non riuscire. Oppure, in SQL Azure, dove un database può essere spostato in un altro server per il bilanciamento del carico, il database non sarà disponibile per alcuni secondi.

Esistono molti approcci all'implementazione della logica per i tentativi con backoff esponenziale.

>[!div class="step-by-step"]
>[Precedente](partial-failure-strategies.md)
>[Successivo](implement-resilient-entity-framework-core-sql-connections.md)