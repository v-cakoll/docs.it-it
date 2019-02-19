---
title: Operatore <<= - Riferimenti per C#
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219451"
---
# <a name="-operator-c-reference"></a>Operatore \<\<= (Riferimenti per C#)

Operatore di assegnazione di spostamento a sinistra.

Un'espressione che usa l'operatore `<<=`, ad esempio

```csharp
x <<= y
```

equivale a

```csharp
x = x << y
```

con la differenza che `x` viene valutato una sola volta.

L'[operatore `<<`](left-shift-operator.md) scorre verso sinistra il primo operando del numero di bit specificato dal secondo operando.

Nell'esempio seguente viene illustrato l'uso dell'operatore `<<=`:

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a>Overload degli operatori

Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore `<<`](left-shift-operator.md), viene eseguito l'overload in modo implicito dell'operatore di assegnazione di scorrimento a sinistra `<<=`. Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di scorrimento a sinistra.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
