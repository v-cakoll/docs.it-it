---
title: + Operatori + e += (Riferimenti per C#)
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d03743bad47c60925462d027d18445047ebc0fc9
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300110"
---
# <a name="-and--operators-c-reference"></a>Operatori + e += (Riferimenti per C#)

L'operatore `+` è supportato dai tipi numerici predefiniti, dai tipi [stringa](../keywords/string.md) e dai tipi [delegato](../keywords/delegate.md).

Per informazioni sull'operatore aritmetico `+`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di addizione +](arithmetic-operators.md#addition-operator-) dell'articolo [Operatori aritmetici](arithmetic-operators.md).

## <a name="string-concatenation"></a>Concatenazione di stringhe

Quando uno o entrambi gli operandi sono di tipo [stringa](../keywords/string.md), l'operatore `+` concatena le rappresentazioni di stringa dei due operandi:

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

A partire da C# 6, l'[interpolazione di stringhe](../tokens/interpolated.md) offre un pratico strumento per formattare le stringhe:

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Combinazione di delegati

Per gli operandi con lo stesso tipo [delegato](../keywords/delegate.md), l'operatore `+` restituisce una nuova istanza di delegato che, quando viene richiamata, richiama il primo operando e quindi il secondo. Se uno degli operandi è `null`, l'operatore `+` restituisce il valore di un altro operando, che può essere anch'esso `null`. L'esempio seguente mostra in che modo è possibile combinare delegati con l'operatore `+`:

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).

## <a name="addition-assignment-operator-"></a>Operatore di assegnazione di addizione +=

Un'espressione che usa l'operatore `+=`, ad esempio

```csharp
x += y
```

equivale a

```csharp
x = x + y
```

con la differenza che `x` viene valutato una sola volta.
  
Nell'esempio seguente viene illustrato l'uso dell'operatore `+=`:

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

È anche possibile usare l'operatore `+=` per specificare un metodo del gestore eventi quando si sottoscrive un [evento](../keywords/event.md). Per altre informazioni, vedere [Procedura: Sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) dell'operatore `+`. Quando viene eseguito l'overload di un operatore `+` binario, viene eseguito in modo implicito anche l'overload dell'operatore `+=`. Un tipo definito dall'utente non può eseguire l'overload dell'operatore `+=` in modo esplicito.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Operatore + unario](~/_csharplang/spec/expressions.md#unary-plus-operator) e [Operatore addizione](~/_csharplang/spec/expressions.md#addition-operator) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Interpolazione di stringhe](../tokens/interpolated.md)
- [Procedura: Concatenare più stringhe](../../how-to/concatenate-multiple-strings.md)
- [Delegati](../../programming-guide/delegates/index.md)
- [Eventi](../../programming-guide/events/index.md)
- [Checked e Unchecked](../keywords/checked-and-unchecked.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Operatori - e -=](subtraction-operator.md)
