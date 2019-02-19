---
title: '! - operatore - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/14/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 464bd658c9bf430191d84d3d5ad8d57173ab87c5
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303712"
---
# <a name="-operator-c-reference"></a>! operator (Riferimenti per C#)

L'operatore di negazione logico `!` è un operatore unario che calcola la negazione logica del relativo operando [bool](../keywords/bool.md). Vale a dire, produce `true`, se l'operando è `false` e `false` se l'operando è `true`:

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalNegationExamples.cs#Example)]

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `!`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatore di negazione logico](~/_csharplang/spec/expressions.md#logical-negation-operator) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)