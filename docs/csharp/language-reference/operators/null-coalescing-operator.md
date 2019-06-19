---
title: ?? \- operatore - Riferimenti per C#
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816016"
---
# <a name="-operator-c-reference"></a>?? operator (Riferimenti per C#)

L'operatore null-coalescing `??` restituisce il valore dell'operando a sinistra se è `null`; in caso contrario, valuta l'operando a destra e ne restituisce il risultato. L'operatore `??` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.

L'operatore null-coalescing si associa all'operando a destra, che significa che un'espressione nel formato

```csharp
a ?? b ?? c
```

viene valutata come

```csharp
a ?? (b ?? c)
```

L'operatore `??` può essere utile negli scenari seguenti:

- Nelle espressioni con gli [operatori condizionali null ?. e ?[]](member-access-operators.md#null-conditional-operators--and-), è possibile usare l'operatore null-coalescing per creare un'espressione alternativa da valutare nel caso in cui il risultato dell'operazione con operazioni condizionali Null sia `null`:

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- Se si usano [tipi di valori nullable](../../programming-guide/nullable-types/index.md) e si deve specificare un valore di un tipo sottostante, usare l'operatore null-coalescing per specificare il valore da fornire nel caso in cui un valore di tipo nullable sia `null`:

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è `null` deve essere il valore predefinito del tipo valore sottostante.

- A partire da C# 7.0, è possibile usare un'[espressione `throw`](../keywords/throw.md#the-throw-expression) come operando destro dell'operatore null-coalescing per rendere più conciso il codice il controllo degli argomenti:

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  L'esempio precedente dimostra anche come usare [membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) per definire una proprietà.

## <a name="operator-overloadability"></a>Overload degli operatori

Non è possibile sottoporre a overload l'operatore null-coalescing.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [ null coalescing](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Operatore ?:](conditional-operator.md)
