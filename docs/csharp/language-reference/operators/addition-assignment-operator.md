---
title: Operatore += - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: 5d48f2fe53a9bb6f781f8d35f1e0983bcaa30f88
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240931"
---
# <a name="-operator-c-reference"></a>Operatore += (Riferimenti per C#)

Operatore di assegnazione di addizione.

Un'espressione che usa l'operatore `+=`, ad esempio

```csharp
x += y
```

equivale a

```csharp
x = x + y
```

con la differenza che `x` viene valutato una sola volta.
  
Per i tipi numerici, l'[operatore addizione](addition-operator.md) `+` calcola la somma dei due operandi. Quando uno o entrambi gli operandi sono di tipo [stringa](../keywords/string.md), concatena le rappresentazioni di stringa dei due operandi. Per i tipi delegati, l'operatore `+` restituisce una nuova istanza di delegato che è una combinazione dei due operandi.

È anche possibile usare l'operatore `+=` per specificare un metodo del gestore eventi quando si sottoscrive un [evento](../keywords/event.md). Per altre informazioni, vedere [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

Nell'esempio seguente viene illustrato l'uso dell'operatore `+=`:

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a>Overload degli operatori

Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore addizione](addition-operator.md) `+`, viene eseguito l'overload in modo implicito dell'operatore di assegnazione di addizione `+=`. Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di addizione.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) e [Assegnazione di eventi](~/_csharplang/spec/expressions.md#event-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Eventi](../../programming-guide/events/index.md)
- [Delegati](../../programming-guide/delegates/index.md)
