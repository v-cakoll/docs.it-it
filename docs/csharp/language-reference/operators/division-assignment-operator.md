---
title: Operatore /= - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286520"
---
# <a name="-operator-c-reference"></a>Operatore /= (Riferimenti per C#)

Operatore di assegnazione di divisione.

Un'espressione che usa l'operatore `/=`, ad esempio

```csharp
x /= y
```

equivale a

```csharp
x = x / y
```

con la differenza che `x` viene valutato una sola volta.

L'[operatore di divisione](division-operator.md) `/` divide il primo operando per il secondo operando. È supportato da tutti i tipi numerici.

Nell'esempio seguente viene illustrato l'uso dell'operatore `/=`:

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a>Overload degli operatori

Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore di divisione](division-operator.md) `/`, viene eseguito l'overload in modo implicito dell'operatore di assegnazione di divisione `/=`. Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di divisione.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
