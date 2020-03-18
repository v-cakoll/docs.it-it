---
title: 'Operatore ?: - Riferimenti per C#'
ms.date: 03/06/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 1a17ba092d4228ba909c8774a2f7e15c2c50cfdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399518"
---
# <a name="-operator-c-reference"></a>Operatore ?: (Riferimenti per C#)

L'operatore `?:`condizionale , noto anche come operatore condizionale ternario, valuta un'espressione booleana e restituisce `true` `false`il risultato di una delle due espressioni, a seconda che l'espressione booleana restituisca o .

La sintassi dell'operatore condizionale è la seguente:

```csharp
condition ? consequent : alternative
```

L'espressione `condition` deve restituire `true` o `false`. Se `condition` restituisce `true`, viene valutata l'espressione `consequent` e il suo risultato diventa il risultato dell'operazione. Se `condition` restituisce `false`, viene valutata l'espressione `alternative` e il suo risultato diventa il risultato dell'operazione. Viene valutata solo `consequent` o solo `alternative`.

Il tipo di `consequent` e `alternative` deve corrispondere oppure deve essere presente una conversione implicita da un tipo all'altro.

L'operatore condizionale si associa all'operando a destra, che significa che un'espressione nel formato

```csharp
a ? b : c ? d : e
```

viene valutata come

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> Un modo per ricordarsi che cosa restituisce questo operatore è il seguente:
>
> ```text
> is this condition true ? yes : no
> ```

L'esempio seguente illustra l'uso dell'operatore condizionale:

[!code-csharp-interactive[non ref conditional](snippets/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Espressione condizionale ref

A partire dalla versione 7.2, una variabile locale [ref](../keywords/ref.md#ref-locals) o [ref readonly](../keywords/ref.md#ref-readonly-locals) può essere assegnata in modo condizionale con l'espressione di riferimento condizionale. È inoltre possibile utilizzare l'espressione di riferimento condizionale come [valore restituito](../keywords/ref.md#reference-return-values) di riferimento o come argomento del [ `ref` metodo](../keywords/ref.md#passing-an-argument-by-reference).

La sintassi dell'espressione condizionale ref è la seguente:

```csharp
condition ? ref consequent : ref alternative
```

Come l'operatore condizionale originale, l'espressione condizionale ref valuta solo una delle due espressioni: `consequent` o `alternative`.

Nel caso dell'espressione condizionale ref, il tipo di `consequent` e `alternative` deve coincidere.

L'esempio seguente illustra l'uso dell'espressione condizionale ref:

[!code-csharp-interactive[conditional ref](snippets/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Operatore condizionale e istruzione `if..else`

L'uso dell'operatore condizionale invece di un'istruzione [if-else](../keywords/if-else.md) potrebbe comportare codice più conciso nei casi in cui è necessario in modo condizionale calcolare un valore. L'esempio seguente illustra due modi di classificare un intero come negativo o non negativo:

[!code-csharp[conditional and if-else](snippets/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente non può eseguire l'overload dell'operatore condizionale.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatore condizionale](~/_csharplang/spec/expressions.md#conditional-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Per ulteriori informazioni sull'espressione di riferimento condizionale, vedere la [nota](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)della proposta di feature .

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Istruzione if-else](../keywords/if-else.md)
- [?. E? [] operatori](member-access-operators.md#null-conditional-operators--and-)
- [?? E?? Operatori di operatore](null-coalescing-operator.md)
- [ref (parola chiave)](../keywords/ref.md)
