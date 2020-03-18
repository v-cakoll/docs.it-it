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
# <a name="implement-retries-with-exponential-backoff"></a>Implementazione dei tentativi con backoff esponenziale

I [*tentativi con backoff esponenziale*](/azure/architecture/patterns/retry) sono una tecnica che ripete un'operazione con un tempo di attesa che aumenta in modo esponenziale, fino al raggiungimento del numero massimo di tentativi ([backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)). Questa tecnica si basa sul presupposto che le risorse cloud potrebbero essere non disponibili in modo intermittente per più di alcuni secondi, per qualsiasi motivo. Ad esempio, quando un agente di orchestrazione sposta un contenitore in un altro nodo in un cluster per il bilanciamento del carico, durante l'operazione, alcune richieste potrebbero non riuscire. Oppure, in SQL Azure, dove un database può essere spostato in un altro server per il bilanciamento del carico, il database non sarà disponibile per alcuni secondi.

Esistono molti approcci all'implementazione della logica per i tentativi con backoff esponenziale.

>[!div class="step-by-step"]
>[Successivo](partial-failure-strategies.md)
>[precedente](implement-resilient-entity-framework-core-sql-connections.md)
