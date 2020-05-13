---
title: Operatori di confronto - Riferimenti per C#
description: Informazioni sugli operatori di confronto C# che è possibile usare per controllare l'ordine dei valori numerici.
ms.date: 05/11/2020
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: eda039d950e4be13d9c041c8bb95b6ea773b83f6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207221"
---
# <a name="comparison-operators-c-reference"></a>Operatori di confronto (Riferimenti per C#)

Gli operatori [ `<` (minore di)](#less-than-operator-), [ `>` (maggiore di)](#greater-than-operator-), [ `<=` (minore o uguale)](#less-than-or-equal-operator-)e [ `>=` (maggiore o uguale)](#greater-than-or-equal-operator-) , noti anche come relazionali, comparano gli operandi. Questi operatori sono supportati da tutti i tipi numerici [integrali](../builtin-types/integral-numeric-types.md) e a [virgola mobile](../builtin-types/floating-point-numeric-types.md) .

> [!NOTE]
> Per gli operatori `==`, `<`, `>`, `<=` e `>=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`. Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`. Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Il tipo [char](../builtin-types/char.md) supporta anche gli operatori di confronto. Nel caso degli `char` operandi, vengono confrontati i codici carattere corrispondenti.

Anche i tipi di enumerazione supportano gli operatori di confronto. Per gli operandi dello stesso tipo [enum](../builtin-types/enum.md), i valori corrispondenti del tipo integrale sottostante vengono confrontati.

Gli [ `==` `!=` operatori e](equality-operators.md) controllano se gli operandi sono uguali o meno.

## <a name="less-than-operator-"></a>Operatore "minore di" \<

L'operatore `<` restituisce `true` se l'operando di sinistra è minore dell'operando di destra, `false` in caso contrario:

[!code-csharp-interactive[less than example](snippets/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a>Operatore "maggiore di" >

L'operatore `>` restituisce `true` se l'operando di sinistra è maggiore dell'operando di destra, `false` in caso contrario:

[!code-csharp-interactive[greater than example](snippets/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>Operatore "minore o uguale a" \<=

L'operatore `<=` restituisce `true` se l'operando di sinistra è minore o uguale all'operatore di destra, `false` in caso contrario:

[!code-csharp-interactive[less than or equal example](snippets/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>Operatore "maggiore o uguale a" >=

L'operatore `>=` restituisce `true` se l'operando di sinistra è maggiore o uguale all'operatore di destra, `false` in caso contrario:

[!code-csharp-interactive[greater than or equal example](snippets/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l' [Overload](operator-overloading.md) degli `<` operatori, `>` , `<=` e `>=` .

Se un tipo esegue l'overload di uno degli operatori `<` o `>`, deve eseguire l'overload sia di `<` che di `>`. Se un tipo esegue l'overload di uno degli operatori `<=` o `>=`, deve eseguire l'overload sia di `<=` che di `>=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Operatori di uguaglianza](equality-operators.md)
