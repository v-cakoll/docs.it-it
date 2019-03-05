---
title: Operatore *= - Riferimenti per C#
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967386"
---
# <a name="-operator-c-reference"></a>Operatore \*= (Riferimenti per C#)

Operatore di assegnazione di moltiplicazione.

Un'espressione che usa l'operatore `*=`, ad esempio

```csharp
x *= y
```

equivale a

```csharp
x = x * y
```

con la differenza che `x` viene valutato una sola volta.

Per i tipi numerici, l'[operatore \*](multiplication-operator.md) calcola il prodotto dei due operandi.

Nell'esempio seguente viene illustrato l'uso dell'operatore `*=`:

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a>Overload degli operatori

Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore di moltiplicazione](multiplication-operator.md) `*`, viene eseguito l'overload in modo implicito dell'operatore di assegnazione di moltiplicazione `*=`. Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di moltiplicazione.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
