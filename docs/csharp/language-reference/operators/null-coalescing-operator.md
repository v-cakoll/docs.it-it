---
title: ?? - operatore - Riferimenti per C#
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

L'operatore null-coalescing `??` restituisce il valore dell'operando a sinistra, in caso contrario `null`; in caso contrario, valuta l'operando destro e restituisce il risultato. Il `??` operatore non valuta operando a destra se l'operando sinistro restituisce un valore non null.

L'operatore null-coalescing è associativa a destra, vale a dire, un'espressione del form

```csharp
a ?? b ?? c
```

viene valutata come

```csharp
a ?? (b ?? c)
```

Il `??` operatore può essere utile negli scenari seguenti:

- Nelle espressioni con la [operatori condizionali null?. e?] ](member-access-operators.md#null-conditional-operators--and-), è possibile usare l'operatore null-coalescing per fornire un'espressione da valutare nel caso in cui il risultato dell'espressione con le operazioni condizionali null alternativa `null`:

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- Quando si lavora [tipi di valore nullable](../../programming-guide/nullable-types/index.md) ed è necessario fornire un valore di un tipo di valore sottostante, utilizzare l'operatore null-coalescing per specificare il valore da specificare nel caso in cui un valore di tipo nullable è `null`:

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  Usare la <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> metodo se il valore da utilizzare quando un valore di tipo nullable è `null` deve essere il valore predefinito del tipo di valore sottostante.

- A partire da C# 7.0, è possibile usare una [ `throw` espressione](../keywords/throw.md#the-throw-expression) come operando destro dell'operatore null-coalescing per rendere il codice il controllo degli argomenti più conciso:

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  Nell'esempio precedente viene inoltre illustrato come utilizzare [membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) per definire una proprietà.

## <a name="operator-overloadability"></a>Overload degli operatori

Non possa essere sottoposti a overload l'operatore null-coalescing.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [l'operatore null-coalescing](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) sezione il [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Operatore ?:](conditional-operator.md)
