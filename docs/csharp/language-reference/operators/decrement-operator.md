---
title: Operatore -- - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 4fba014e8dabc13cd874e17f23515dc29d93f24b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236922"
---
# <a name="---operator-c-reference"></a>Operatore -- (Riferimenti per C#)

L'operatore di decremento unario `--` decrementa il proprio operando di 1. È supportato in due forme: l'operatore di decremento suffisso, `x--`, e l'operatore di decremento prefisso, `--x`.

## <a name="postfix-decrement-operator"></a>Operatore di decremento suffisso

Il risultato di `x--` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixDecrement)]

## <a name="prefix-decrement-operator"></a>Operatore di decremento prefisso

Il risultato di `--x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixDecrement)]

## <a name="remarks"></a>Note

L'operatore di decremento è predefinito per tutti i [tipi integrali](../keywords/integral-types-table.md) (incluso il tipo [char](../keywords/char.md)), i [tipi a virgola mobile](../keywords/floating-point-types-table.md) e i tipi [enumerazione](../keywords/enum.md).

Un operando dell'operatore di decremento deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../../csharp/programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `--`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Operatori di incremento e decremento in forma suffissa](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) e [Operatori di incremento e decremento in forma prefissa](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatore ++](increment-operator.md)
- [Procedura: Incrementare e decrementare i puntatori](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
