---
title: + (operatore) - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 92e20dad8ae6358f71137e955bb80e3641a66a54
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237753"
---
# <a name="-operator-c-reference"></a>Operatore + (Riferimenti per C#)

L'operatore `+` è supportato in due forme: un operatore + unario o un operatore addizione binario.

## <a name="unary-plus-operator"></a>Operatore più unario

L'operatore `+` unario restituisce il valore del proprio operando. È supportato da tutti i tipi numerici.

## <a name="numeric-addition"></a>Addizione numerica

Per i tipi numerici, l'operatore `+` calcola la somma dei due operandi:

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a>Concatenazione stringhe

Quando uno o entrambi gli operandi sono di tipo [stringa](../keywords/string.md), l'operatore `+` concatena le rappresentazioni di stringa dei due operandi:

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

A partire da C# 6, l'[interpolazione di stringhe](../tokens/interpolated.md) offre un pratico strumento per formattare le stringhe:

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Combinazione di delegati

Per i tipi [delegate](../keywords/delegate.md), l'operatore `+` restituisce una nuova istanza di delegato che, quando viene richiamata, richiama il primo operando e quindi il secondo. Se uno degli operandi è `null`, l'operatore `+` restituisce il valore di un altro operando, che può essere anch'esso `null`. L'esempio seguente mostra in che modo è possibile combinare delegati con l'operatore `+`:

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) degli operatori `+` unario e binario. Quando viene eseguito l'overload di un operatore `+`, viene anche aggiunto l'[operatore di assegnazione di addizione](addition-assignment-operator.md) `+=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Operatore + unario](~/_csharplang/spec/expressions.md#unary-plus-operator) e [Operatore addizione](~/_csharplang/spec/expressions.md#addition-operator) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Interpolazione di stringhe](../tokens/interpolated.md)
- [Procedura: Concatenare più stringhe](../../how-to/concatenate-multiple-strings.md)
- [Delegati](../../programming-guide/delegates/index.md)
- [Checked e Unchecked](../keywords/checked-and-unchecked.md)
