---
title: ?? e? = Operators C# -riferimento
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 1e94038a41a6a6cc19be6c67bff2891397793fb3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924687"
---
# <a name="-and--operators-c-reference"></a>?? e? = OperatorsC# (riferimento)

L'operatore null-coalescing `??` restituisce il valore dell'operando a sinistra se non è `null`; in caso contrario, valuta l'operando a destra e ne restituisce il risultato. L'operatore `??` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.

Disponibile in C# 8,0 e versioni successive, l'operatore `??=` di assegnazione di Unione null assegna il valore dell'operando destro all'operando sinistro solo se l' `null`operando sinistro restituisce. L'operatore `??=` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.

[!code-csharp[null-coalescing assignment](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#Assignment)]

L'operando sinistro dell' `??=` operatore deve essere una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md)o un elemento [indicizzatore](../../programming-guide/indexers/index.md) . Per ulteriori informazioni sull'assegnazione di Unione null, vedere la [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).

In C# 7,3 e versioni precedenti, il tipo dell'operando sinistro dell' `??` operatore deve essere un tipo di riferimento o un tipo di [valore Nullable](../../programming-guide/nullable-types/index.md). A partire C# da 8,0, il requisito viene sostituito con quanto segue: il tipo dell'operando sinistro degli `??` operatori e `??=` non può essere un tipo di valore non nullable. In particolare, è possibile usare gli operatori di Unione null con parametri di tipo non vincolati in C# 8,0 e versioni successive:

[!code-csharp[unconstrained type parameter](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#UnconstrainedType)]

Gli operatori che uniscono i valori null sono associativi a destra. Ovvero espressioni nel formato

```csharp
a ?? b ?? c
d ??= e ??= f
```

vengono valutati come

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a>Esempi

Gli operatori `??=` e possono essere utili negli scenari seguenti: `??`

- Nelle espressioni con gli [operatori condizionali null ?. e ?[]](member-access-operators.md#null-conditional-operators--and-), è possibile usare l'operatore null-coalescing per creare un'espressione alternativa da valutare nel caso in cui il risultato dell'operazione con operazioni condizionali Null sia `null`:

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- Se si usano [tipi di valori nullable](../../programming-guide/nullable-types/index.md) e si deve specificare un valore di un tipo sottostante, usare l'operatore null-coalescing per specificare il valore da fornire nel caso in cui un valore di tipo nullable sia `null`:

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è `null` deve essere il valore predefinito del tipo valore sottostante.

- A partire da C# 7.0, è possibile usare un'[espressione `throw`](../keywords/throw.md#the-throw-expression) come operando destro dell'operatore null-coalescing per rendere più conciso il codice il controllo degli argomenti:

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  L'esempio precedente dimostra anche come usare [membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) per definire una proprietà.

- A partire C# da 8,0, è possibile usare `??=` l'operatore per sostituire il codice del modulo

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  con il codice seguente:

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a>Overload degli operatori

Non è `??` possibile `??=` eseguire l'overload degli operatori e.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni sull' `??` operatore, vedere la sezione relativa all'operatore di Unione [null](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) nella [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Operatore ?:](conditional-operator.md)
