---
title: Operatore &amp;&amp; - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 82442f50275f21e0a0748951dc50628a8d7e11bb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243588"
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp; Operatore (Riferimenti per C#)

L'operatore AND logico condizionale `&&`, chiamato anche operatore AND logico di "corto circuito", calcola l'AND logico dei relativi operandi [bool](../keywords/bool.md). Il risultato di `x && y` è `true` se `x` e `y` restituiscono `true`. In caso contrario, il risultato è `false`. Se il primo operando restituisce `false`, il secondo operando non viene valutato e il risultato dell'operazione è `false`. L'esempio seguente illustra questo comportamento:

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

L'[operatore AND logico](and-operator.md) `&` calcola anche l'AND logico dei relativi operandi `bool`, ma valuta sempre entrambi gli operandi.

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente non può eseguire l'overload dell'operatore AND logico condizionale. Tuttavia, se un tipo definito dall'utente esegue l'overload degli operatori [AND logico](and-operator.md), [true e false](../keywords/true-false-operators.md) in un determinato modo, l'operazione `&&` può essere valutata per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatore ||](conditional-or-operator.md)
- [Operatore \!](logical-negation-operator.md)
- [Operatore &](and-operator.md)
