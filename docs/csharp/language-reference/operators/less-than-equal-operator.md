---
title: Operatore <= - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: 54c8300ad883e81cfb3d4886881984fd5a0ebdb3
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545377"
---
# <a name="-operator-c-reference"></a>Operatore \<= (Riferimenti per C#)

L'operatore relazionale "minore o uguale a" `<=` restituisce `true` se il primo operando è minore o uguale al secondo operando, `false` in caso contrario. Tutti i tipi numerici e di enumerazione supportano l'operatore `<=`. Per gli operandi dello stesso tipo [enum](../keywords/enum.md), i valori corrispondenti del tipo integrale sottostante vengono confrontati.

> [!NOTE]
> Per gli operatori relazionali `==`, `>`, `<` `>=`, e `<=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`. Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`). Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Nell'esempio seguente viene illustrato l'uso dell'operatore `<=`:

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `<=`. Se un tipo esegue l'overload dell'operatore "minore o uguale a" `<=`, deve anche eseguire l'overload dell'[operatore "maggiore o uguale a"](greater-than-equal-operator.md) `>=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatore <](less-than-operator.md)
- [Operatore ==](equality-operators.md#equality-operator-)
- <xref:System.IComparable%601?displayProperty=nameWithType>
