---
title: ?? E?? Operatori - Riferimenti per C
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
ms.openlocfilehash: 69294f0fb706868b48b8d7fe8b95fa345af169b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847313"
---
# <a name="-and--operators-c-reference"></a>?? E?? Operatori (riferimenti per C

L'operatore null-coalescing `??` restituisce il valore dell'operando a sinistra se è `null`; in caso contrario, valuta l'operando a destra e ne restituisce il risultato. L'operatore `??` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.

Disponibile in C, 8.0 e versioni successive, l'operatore `??=` di assegnazione null-coalescing assegna il valore del relativo operando di `null`destra al relativo operando di sinistra solo se l'operando di sinistra restituisce . L'operatore `??=` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.

[!code-csharp[null-coalescing assignment](snippets/NullCoalescingOperator.cs#Assignment)]

L'operando di sinistra `??=` dell'operatore deve essere una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md)o un elemento [dell'indicizzatore.](../../programming-guide/indexers/index.md)

Nelle versioni precedenti e 7.3 del linguaggio C, il `??` tipo dell'operando a sinistra dell'operatore deve essere un tipo di [riferimento](../keywords/reference-types.md) o un tipo di [valore nullable.](../builtin-types/nullable-value-types.md) A partire dalla versione 8.0 di C, tale requisito viene sostituito con `??` `??=` il seguente: il tipo dell'operando di sinistra degli operatori e non può essere un tipo di valore non nullable. In particolare, a partire dalla versione 8.0 di C, è possibile usare gli operatori di null-coalescing con parametri di tipo non vincolati:In particular, beginning with C'è 8.0, you can use the null-coalescing operators with unconstrained type parameters:

[!code-csharp[unconstrained type parameter](snippets/NullCoalescingOperator.cs#UnconstrainedType)]

Gli operatori null-coalescing sono associativi a destra. Ovvero, le espressioni della forma

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

Gli `??` `??=` operatori e possono essere utili negli scenari seguenti:The and operators can be useful in the following scenarios:

- Nelle espressioni con gli [operatori null-conditional ?. e ?[]](member-access-operators.md#null-conditional-operators--and-), è possibile utilizzare l'operatore `??` per fornire `null`un'espressione alternativa da valutare nel caso in cui il risultato dell'espressione con operazioni null-conditional sia :

  [!code-csharp-interactive[with null-conditional](snippets/NullCoalescingOperator.cs#WithNullConditional)]

- Quando si utilizzano [tipi di valore nullable](../builtin-types/nullable-value-types.md) ed è necessario `??` fornire un valore di un tipo di valore `null`sottostante, utilizzare l'operatore per specificare il valore da fornire nel caso in cui un valore di tipo nullable sia :

  [!code-csharp-interactive[with nullable types](snippets/NullCoalescingOperator.cs#WithNullableTypes)]

  Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è `null` deve essere il valore predefinito del tipo valore sottostante.

- A partire dalla versione 7.0 di C, è possibile usare `??` [ `throw` un'espressione](../keywords/throw.md#the-throw-expression) come operando di destra dell'operatore per rendere più conciso il codice di controllo degli argomenti:At beginning with C' 7.0, you can use a expression as the right-hand operand of the operator to make the argument-checking code more concise:

  [!code-csharp[with throw expression](snippets/NullCoalescingOperator.cs#WithThrowExpression)]

  L'esempio precedente dimostra anche come usare [membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) per definire una proprietà.

- A partire dalla versione 8.0 `??=` di C, è possibile utilizzare l'operatore per sostituire il codice del modulo

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

Gli `??` operatori `??=` e non può essere sottoposto a overload.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni `??` sull'operatore, vedere [sezione relativa all'operatore coalescing null](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)

Per ulteriori informazioni `??=` sull'operatore, vedere la [nota](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md)della proposta di funzionalità .

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [?. E? [] operatori](member-access-operators.md#null-conditional-operators--and-)
- [?: operatore](conditional-operator.md)
