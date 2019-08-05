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
# <a name="implement-retries-with-exponential-backoff"></a>Implementazione dei tentativi con backoff esponenziale

I [*tentativi con backoff esponenziale*](/azure/architecture/patterns/retry) sono una tecnica che ripete un'operazione con un tempo di attesa che aumenta in modo esponenziale, fino al raggiungimento del numero massimo di tentativi ([backoff esponenziale](https://en.wikipedia.org/wiki/Exponential_backoff)). Questa tecnica si basa sul presupposto che le risorse cloud potrebbero essere non disponibili in modo intermittente per più di alcuni secondi, per qualsiasi motivo. Ad esempio, quando un agente di orchestrazione sposta un contenitore in un altro nodo in un cluster per il bilanciamento del carico, durante l'operazione, alcune richieste potrebbero non riuscire. Oppure, in SQL Azure, dove un database può essere spostato in un altro server per il bilanciamento del carico, il database non sarà disponibile per alcuni secondi.

Esistono molti approcci all'implementazione della logica per i tentativi con backoff esponenziale.

>[!div class="step-by-step"]
>[Precedente](partial-failure-strategies.md)
>[Successivo](implement-resilient-entity-framework-core-sql-connections.md)
