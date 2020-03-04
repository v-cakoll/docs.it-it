---
title: Espressioni C# - Panoramica del linguaggio C#
description: Espressioni, operandi e operatori sono blocchi predefiniti del linguaggio C#
ms.date: 02/27/2020
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 209b5da01cd7539f2bd97023f40fd149910b6f1d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159156"
---
# <a name="expressions"></a>Espressioni

Le *espressioni* sono costituite da *operandi* e *operatori* Gli operatori di un'espressione indicano le operazioni che devono essere eseguite sugli operandi. Alcuni esempi di operatori sono `+`, `-`, `*`, `/` e `new`, mentre i valori effettivi, i campi, le variabili locali e le espressioni sono esempi di operandi.

Se un'espressione contiene più operatori, la *precedenza* degli operatori determina l'ordine in cui vengono valutati i singoli operatori. L'espressione `x + y * z`, ad esempio, viene valutata come `x + (y * z)` poiché l'operatore `*` ha la precedenza sull'operatore `+`.

Quando un operando si trova tra due operatori con la stessa precedenza, l'ordine di esecuzione delle operazioni viene determinato dall'*associatività* degli operatori:

* Ad eccezione degli operatori di assegnazione e di Unione null, tutti gli operatori binari sono *associativi a sinistra*, ovvero le operazioni vengono eseguite da sinistra a destra. L'espressione `x + y + z` viene ad esempio valutata come `(x + y) + z`.
* Gli operatori di assegnazione, gli operatori di `??` e di `??=` di valori null e l'operatore condizionale `?:` sono *associativi a destra*, ovvero le operazioni vengono eseguite da destra a sinistra. L'espressione `x = y = z` viene ad esempio valutata come `x = (y = z)`.

È possibile controllare la precedenza e l'associatività usando le parentesi. Ad esempio, `x + y * z` prima moltiplica `y` per `z` e quindi somma il risultato a `x`, ma `(x + y) * z` prima somma `x` e `y` e quindi moltiplica il risultato per `z`.

La maggior parte degli operatori può essere [*sottoposta a overload*](../language-reference/operators/operator-overloading.md). L'overload degli operatori consente di specificare implementazioni di operatori definite dall'utente per le operazioni in cui uno o entrambi gli operandi appartengono a un tipo struct o a una classe definita dall'utente.

C# offre diversi operatori per eseguire operazioni [aritmetiche](../language-reference/operators/arithmetic-operators.md), [logiche](../language-reference/operators/boolean-logical-operators.md), [di spostamento e bit per bit](../language-reference/operators/bitwise-and-shift-operators.md), nonché confronti di [uguaglianza](../language-reference/operators/equality-operators.md) e [ordinamento](../language-reference/operators/comparison-operators.md).

Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere [Operatori C#](../language-reference/operators/index.md).

> [!div class="step-by-step"]
> [Precedente](types-and-variables.md)
> [Successivo](statements.md)
