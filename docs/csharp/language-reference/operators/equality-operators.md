---
title: Operatori di uguaglianza - Riferimenti per C#
description: Informazioni sugli operatori di confronto uguaglianze C#.
ms.date: 03/28/2019
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
ms.openlocfilehash: b4d3f3c0c6195fef22a33c47ad0b8c498f512f6a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753492"
---
# <a name="equality-operators-c-reference"></a>Operatori di uguaglianza (Riferimenti per C#)

Gli operatori [`==` (uguaglianza)](#equality-operator-) e [`!=` (disuguaglianza)](#inequality-operator-) controllano se i relativi operandi sono uguali oppure no.

## <a name="equality-operator-"></a>Operatore di uguaglianza ==

L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.

### <a name="value-types-equality"></a>Uguaglianza dei tipi valore

Gli operandi dei [tipi valore predefiniti](../keywords/value-types-table.md) sono uguali se i relativi valori sono uguali:

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> Per gli operatori `==`, [`<`, `>`, `<=` e `>=`](comparison-operators.md) se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`. Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`. Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Due operandi dello stesso tipo [enum](../keywords/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.

I tipi [struct](../keywords/struct.md) definiti dall'utente non supportano l'operatore `==` per impostazione predefinita. Per supportare l'operatore `==`, un tipo struct definito dall'utente deve eseguirne l'[overload](#operator-overloadability).

A partire da C# 7.3, gli operatori `==` e `!=` sono supportati dalle [tuple](../../tuples.md) C#. Per altre informazioni, vedere la sezione [Uguaglianza e tuple](../../tuples.md#equality-and-tuples) nell'articolo [Tipi tupla in C#](../../tuples.md).

### <a name="string-equality"></a>Uguaglianza di stringhe

Due operandi [stringa](../keywords/string.md) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

Questo è un confronto ordinale senza distinzione tra maiuscole e minuscole. Per altre informazioni sul confronto di stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).

### <a name="reference-types-equality"></a>Uguaglianza dei tipi riferimento

Due operandi di tipo riferimento diversi da `string` sono uguali quando fanno riferimento allo stesso oggetto:

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

Come illustrato nell'esempio, i tipi riferimento definiti dall'utente supportano l'operatore `==` per impostazione predefinita. Tuttavia, un tipo riferimento definito dall'utente può eseguire l'overload dell'operatore `==`. Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.

## <a name="inequality-operator-"></a>Operatore di disuguaglianza !=

L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario. Per gli operandi dei [tipi predefiniti](../keywords/built-in-types-table.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`. Per altre informazioni sull'uguaglianza dei tipi, vedere la sezione [Operatore di uguaglianza](#equality-operator-).

Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `==` e `!=`. Se un tipo esegue l'overload di uno dei due operatori, deve eseguire l'overload anche di un altro operatore.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [Confronti di uguaglianza](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [Operatori di confronto](comparison-operators.md)
