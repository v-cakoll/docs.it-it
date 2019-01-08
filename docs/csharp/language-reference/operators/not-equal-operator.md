---
title: Operatore != - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 939b5664dba4345e62a43fb2f8d4d5379659d6aa
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610177"
---
# <a name="-operator-c-reference"></a>Operatore != (Riferimenti per C#)

L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario. Per gli operandi dei [tipi predefiniti](../keywords/built-in-types-table.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`. Per altre informazioni, vedere l'articolo [Operatore ==](equality-comparison-operator.md).

Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `!=`. Se un tipo esegue l'overload dell'operatore di disuguaglianza `!=`, deve anche eseguire l'overload dell'[operatore di uguaglianza](equality-comparison-operator.md) `==`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Confronti di uguaglianza](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
