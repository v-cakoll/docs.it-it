---
title: Operatori di uguaglianza - Riferimenti per C#
description: Informazioni sugli operatori di confronto delle uguaglianze C# e sull'uguaglianza dei tipi C#.
ms.date: 06/26/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 079522b18afdf86a942d502672174516d45d37fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399567"
---
# <a name="equality-operators-c-reference"></a>Operatori di uguaglianza (Riferimenti per C#)

Gli [ `==` operatori (uguaglianza)](#equality-operator-) e [ `!=` (disuguaglianza)](#inequality-operator-) controllano se i relativi operandi sono uguali o meno.

## <a name="equality-operator-"></a>Operatore di uguaglianza ==

L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.

### <a name="value-types-equality"></a>Uguaglianza dei tipi valore

Gli operandi dei [tipi valore predefiniti](../builtin-types/value-types.md#built-in-value-types) sono uguali se i relativi valori sono uguali:

[!code-csharp-interactive[value types equality](snippets/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> Per `==`gli operatori , [ `<` `>`, , `<=`e `>=` ](comparison-operators.md) , se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), il risultato dell'operazione è `false`. Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`. Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Due operandi dello stesso tipo [enum](../builtin-types/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.

I tipi [struct](../builtin-types/struct.md) definiti dall'utente non supportano l'operatore `==` per impostazione predefinita. Per supportare l'operatore `==`, un tipo struct definito dall'utente deve eseguirne l'[overload](operator-overloading.md).

A partire da C# 7.3, gli operatori `==` e `!=` sono supportati da [tuple](../../tuples.md) C#. Per altre informazioni, vedere la sezione [Uguaglianza e tuple](../../tuples.md#equality-and-tuples) nell'articolo [Tipi tupla in C#](../../tuples.md).

### <a name="reference-types-equality"></a>Uguaglianza dei tipi riferimento

Per impostazione predefinita, due operandi di tipo riferimento sono uguali se fanno riferimento allo stesso oggetto:

[!code-csharp[reference type equality](snippets/EqualityOperators.cs#ReferenceTypesEquality)]

Come illustrato nell'esempio, i tipi riferimento definiti dall'utente supportano l'operatore `==` per impostazione predefinita. Tuttavia, un tipo riferimento può eseguire l'overload dell'operatore `==`. Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.

### <a name="string-equality"></a>Uguaglianza di stringhe

Due operandi [stringa](../builtin-types/reference-types.md#the-string-type) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:

[!code-csharp-interactive[string equality](snippets/EqualityOperators.cs#StringEquality)]

Si tratta di un confronto ordinale con distinzione tra maiuscole e minuscole. Per altre informazioni sul confronto di stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).

### <a name="delegate-equality"></a>Delegare l'uguaglianza

Due operandi [delegati](../../programming-guide/delegates/index.md) dello stesso tipo di runtime sono uguali quando entrambi sono `null` o i relativi elenchi di chiamate hanno la stessa lunghezza e voci uguali in ogni posizione:

[!code-csharp-interactive[delegate equality](snippets/EqualityOperators.cs#DelegateEquality)]

Per altre informazioni, vedere la sezione [Delegare gli operatori di uguaglianza](~/_csharplang/spec/expressions.md#delegate-equality-operators) dell'articolo [Specifiche del linguaggio C#](~/_csharplang/spec/introduction.md).

I delegati prodotti dalla valutazione di [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) semanticamente identiche non sono uguali, come mostra l'esempio seguente:

[!code-csharp-interactive[from identical lambdas](snippets/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a>Operatore di disuguaglianza !=

L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario. Per gli operandi dei [tipi predefiniti](../builtin-types/built-in-types.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`. Per altre informazioni sull'uguaglianza dei tipi, vedere la sezione [Operatore di uguaglianza](#equality-operator-).

Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:

[!code-csharp-interactive[non-equality examples](snippets/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l'[overload](operator-overloading.md) degli operatori `==` e `!=`. Se un tipo esegue l'overload di uno dei due operatori, deve eseguire l'overload anche di un altro operatore.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [Confronti di uguaglianza](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [Operatori di confronto](comparison-operators.md)
