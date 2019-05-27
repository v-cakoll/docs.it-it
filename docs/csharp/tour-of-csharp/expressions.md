---
title: Espressioni C# - Panoramica del linguaggio C#
description: Espressioni, operandi e operatori sono blocchi predefiniti del linguaggio C#
ms.date: 04/25/2019
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: ffe800304a9125e11e20d96a84919936f1fee2c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753641"
---
# <a name="expressions"></a>Espressioni

Le *espressioni* sono costituite da *operandi* e *operatori*. Gli operatori di un'espressione indicano le operazioni che devono essere eseguite sugli operandi. Alcuni esempi di operatori sono `+`, `-`, `*`, `/` e `new`, mentre i valori effettivi, i campi, le variabili locali e le espressioni sono esempi di operandi.

Se un'espressione contiene più operatori, la *precedenza* degli operatori determina l'ordine in cui vengono valutati i singoli operatori. L'espressione `x + y * z`, ad esempio, viene valutata come `x + (y * z)` poiché l'operatore `*` ha la precedenza sull'operatore `+`.

Quando un operando si trova tra due operatori con la stessa precedenza, l'ordine di esecuzione delle operazioni viene determinato dall'*associatività* degli operatori:

* Ad eccezione degli operatori di assegnazione, tutti gli operatori binari *prevedono l'associazione all'operando a sinistra*. In altri termini, le operazioni vengono eseguite da sinistra a destra. L'espressione `x + y + z` viene ad esempio valutata come `(x + y) + z`.
* Gli operatori di assegnazione e gli operatori condizionali (`?:`) *prevedono l'associazione all'operando a destra*. In altri termini, le operazioni vengono eseguite da destra a sinistra. L'espressione `x = y = z` viene ad esempio valutata come `x = (y = z)`.

È possibile controllare la precedenza e l'associatività usando le parentesi. Ad esempio, `x + y * z` prima moltiplica `y` per `z` e quindi somma il risultato a `x`, ma `(x + y) * z` prima somma `x` e `y` e quindi moltiplica il risultato per `z`.

La maggior parte degli operatori può essere [*sottoposta a overload*](../language-reference/keywords/operator.md). L'overload degli operatori consente di specificare implementazioni di operatori definite dall'utente per le operazioni in cui uno o entrambi gli operandi appartengono a un tipo struct o a una classe definita dall'utente.

C# offre diversi operatori per eseguire operazioni [aritmetiche](../language-reference/operators/arithmetic-operators.md), [logiche](../language-reference/operators/boolean-logical-operators.md), [di spostamento e bit per bit](../language-reference/operators/bitwise-and-shift-operators.md), nonché confronti di [uguaglianza](../language-reference/operators/equality-operators.md) e [ordinamento](../language-reference/operators/comparison-operators.md).

Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere [Operatori C#](../language-reference/operators/index.md).

> [!div class="step-by-step"]
> [Precedente](types-and-variables.md)
> [Successivo](statements.md)
