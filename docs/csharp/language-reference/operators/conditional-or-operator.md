---
title: Operatore || (Riferimenti per C#)
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: a391078372e4ec0a3882bed4515733adedffb547
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "42925540"
---
# <a name="-operator-c-reference"></a>Operatore || (Riferimenti per C#)

L'operatore OR logico condizionale `||`, chiamato anche operatore OR logico di "corto circuito", calcola l'OR logico dei relativi operandi [bool](../keywords/bool.md). Il risultato di `x || y` è `true` se `x` o `y` restituisce `true`. In caso contrario, il risultato è `false`. Se il primo operando restituisce `true`, il secondo operando non viene valutato e il risultato dell'operazione è `true`. L'esempio seguente illustra questo comportamento:

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

L'[operatore OR logico](or-operator.md) `|` calcola anche l'OR logico dei relativi operandi `bool`, ma valuta sempre entrambi gli operandi.

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente non può eseguire l'overload dell'operatore OR logico condizionale. Tuttavia, se un tipo definito dall'utente esegue l'overload degli operatori [OR logico](or-operator.md), [true](../keywords/true-operator.md) e [false](../keywords/false-operator.md) in un determinato modo, l'operazione `||` può essere valutata per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatore &&](conditional-and-operator.md)
- [Operatore !](logical-negation-operator.md)
- [Operatore |](or-operator.md)
