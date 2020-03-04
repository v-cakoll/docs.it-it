---
title: 'Operatore ?: - Riferimenti per C#'
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 6e8fde8c210b2c33cc514167be7face657cbb618
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239379"
---
# <a name="-operator-c-reference"></a>Operatore ?: (Riferimenti per C#)

L'operatore condizionale `?:`, noto anche come operatore condizionale ternario, valuta un'espressione booleana e restituisce il risultato di una delle due espressioni, a seconda che l'espressione booleana restituisca `true` o `false`. A partire da C# 7.2, l'[espressione condizionale ref](#conditional-ref-expression) restituisce il riferimento al risultato di una delle due espressioni.

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

[!code-csharp-interactive[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Espressione condizionale ref

A partire da C# 7.2, è possibile usare l'espressione condizionale ref per restituire il riferimento al risultato di una delle due espressioni. È possibile assegnare tale riferimento a una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals) oppure usarlo come [valore restituito di riferimento](../keywords/ref.md#reference-return-values) o come [parametro del metodo `ref`](../keywords/ref.md#passing-an-argument-by-reference).

La sintassi dell'espressione condizionale ref è la seguente:

```csharp
condition ? ref consequent : ref alternative
```

Come l'operatore condizionale originale, l'espressione condizionale ref valuta solo una delle due espressioni: `consequent` o `alternative`.

Nel caso dell'espressione condizionale ref, il tipo di `consequent` e `alternative` deve coincidere.

L'esempio seguente illustra l'uso dell'espressione condizionale ref:

[!code-csharp-interactive[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Operatore condizionale e istruzione `if..else`

L'uso dell'operatore condizionale anziché di un'istruzione [if-else](../keywords/if-else.md) potrebbe produrre codice più conciso nei casi in cui è necessario calcolare un valore in modo condizionale. L'esempio seguente illustra due modi di classificare un intero come negativo o non negativo:

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente non può eseguire l'overload dell'operatore condizionale.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatore condizionale](~/_csharplang/spec/expressions.md#conditional-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Per ulteriori informazioni sull'espressione di riferimento condizionale, vedere la [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Istruzione if-else](../keywords/if-else.md)
- [Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)
- [?? e? = operatori](null-coalescing-operator.md)
- [ref (parola chiave)](../keywords/ref.md)
