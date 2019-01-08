---
title: Operatore == - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655959"
---
# <a name="-operator-c-reference"></a>Operatore == (Riferimenti per C#)

L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.

## <a name="value-types-equality"></a>Uguaglianza dei tipi valore

Gli operandi dei [tipi valore predefiniti](../keywords/value-types-table.md) sono uguali se i relativi valori sono uguali:

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> Per gli operatori relazionali `==`, `>`, `<` `>=`, e `<=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`. Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`). Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Due operandi dello stesso tipo [enum](../keywords/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.

Per impostazione predefinita, l'operatore `==` non è definito per un tipo [struct](../keywords/struct.md) definito dall'utente. Un tipo definito dall'utente può eseguire l'[overload](#operator-overloadability) dell'operatore `==`.

A partire da C# 7.3, gli operatori `==` e [`!=`](not-equal-operator.md) sono supportati da [tuple](../../tuples.md) C#. Per altre informazioni, vedere la sezione [Uguaglianza e tuple](../../tuples.md#equality-and-tuples) nell'articolo [Tipi tupla in C#](../../tuples.md).

## <a name="string-equality"></a>Uguaglianza di stringhe

Due operandi [stringa](../keywords/string.md) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

Questo è un confronto ordinale senza distinzione tra maiuscole e minuscole. Per altre informazioni su come confrontare le stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).

## <a name="reference-types-equality"></a>Uguaglianza dei tipi riferimento

Due operandi di tipo riferimento diversi da `string` sono uguali quando fanno riferimento allo stesso oggetto:

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

L'esempio mostra che l'operatore `==` è supportato dai tipi riferimento definiti dall'utente. Tuttavia, un tipo riferimento definito dall'utente può eseguire l'overload dell'operatore `==`. Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `==`. Se un tipo esegue l'overload dell'operatore di uguaglianza `==`, deve anche eseguire l'overload dell'[operatore di disuguaglianza](not-equal-operator.md) `!=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Confronti di uguaglianza](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
