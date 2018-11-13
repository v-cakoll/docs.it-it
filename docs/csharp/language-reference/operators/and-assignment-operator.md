---
title: Operatore &amp;= (Riferimenti per C#)
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 8ce27c999cf21a9059ba23ee3c86b8fa024c7341
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980609"
---
# <a name="amp-operator-c-reference"></a>Operatore &amp;= (Riferimenti per C#)

Operatore di assegnazione AND.

Un'espressione che usa l'operatore `&=`, ad esempio

```csharp
x &= y
```

equivale a

```csharp
x = x & y
```

con la differenza che `x` viene valutato una sola volta.

Per gli operandi di numeri interi, l'[operatore `&`](and-operator.md) calcola l'AND logico bit per bit dei relativi operandi; per gli operandi [bool](../keywords/bool.md), calcola l'AND logico dei relativi operandi.

Nell'esempio seguente viene illustrato l'uso dell'operatore `&=`:

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a>Overload degli operatori

Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore `&`](and-operator.md), viene eseguito l'overload in modo implicito dell'operatore di assegnazione `&=`. Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione AND.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
