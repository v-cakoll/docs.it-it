---
title: Implementazione dei tentativi con backoff esponenziale
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dei tentativi con backoff esponenziale
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ee5dd711484ba7861eedbd9613fda1209736d5b6
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106918"
---
# <a name="implementing-retries-with-exponential-backoff"></a>Implementazione dei tentativi con backoff esponenziale

I [*tentativi con backoff esponenziale*](https://docs.microsoft.com/azure/architecture/patterns/retry) sono una tecnica che tenta di ripetere un'operazione con un tempo di attesa che aumenta esponenzialmente, fino a quando non viene raggiunto il numero massimo di tentativi ([backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)). Questa tecnica si basa sul presupposto che le risorse cloud potrebbero essere non disponibili in modo intermittente per più di alcuni secondi, per qualsiasi motivo. Ad esempio, quando un agente di orchestrazione sposta un contenitore in un altro nodo in un cluster per il bilanciamento del carico, durante l'operazione, alcune richieste potrebbero non riuscire. Oppure, in SQL Azure, dove un database può essere spostato in un altro server per il bilanciamento del carico, il database non sarà disponibile per alcuni secondi.

Esistono molti approcci all'implementazione della logica per i tentativi con backoff esponenziale.


>[!div class="step-by-step"]
[Precedente](partial-failure-strategies.md)
[Successivo](implement-resilient-entity-framework-core-sql-connections.md)
