---
title: Operatore ~ - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 57e5baee423c0b5d9292d0ad4cbf909646eb3a38
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235719"
---
# <a name="-operator-c-reference"></a>Operatore ~ (Riferimenti per C#)

L'operatore di complemento bit per bit `~` è un operatore unario che produce un complemento bit per bit del suo operando invertendo ogni bit. Tutti i tipi integer supportano l'operatore `~`.

> [!NOTE]
> È possibile anche usare il simbolo `~` per dichiarare i finalizzatori. Per altre informazioni, vedere [Finalizzatori](../../programming-guide/classes-and-structs/destructors.md).

Nell'esempio seguente viene illustrato l'uso dell'operatore `~`:

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> L'esempio precedente usa i valori letterali binari [introdotti in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) e [migliorati in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `~`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatore di complemento bit per bit](~/_csharplang/spec/expressions.md#bitwise-complement-operator) nelle [specifiche del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Finalizzatori](../../programming-guide/classes-and-structs/destructors.md)
- [Operatore &](and-operator.md)
- [Operatore |](or-operator.md)
- [Operatore ^](xor-operator.md)
