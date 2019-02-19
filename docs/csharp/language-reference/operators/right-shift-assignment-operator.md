---
title: '>>Operatore = - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220913"
---
# <a name="-operator-c-reference"></a>Operatore >>= (Riferimenti per C#)

Operatore di assegnazione di spostamento a destra.

Un'espressione che usa l'operatore `>>=`, ad esempio

```csharp
x >>= y
```

equivale a

```csharp
x = x >> y
```

con la differenza che `x` viene valutato una sola volta.

L'[operatore `>>`](right-shift-operator.md) scorre verso destra il primo operando del numero di bit definito dal secondo operando.

Nell'esempio seguente viene illustrato l'uso dell'operatore `>>=`:

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a>Overload degli operatori

Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore `>>`](right-shift-operator.md), viene eseguito l'overload in modo implicito dell'operatore di assegnazione di scorrimento a destra `>>=`. Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di scorrimento a destra.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)