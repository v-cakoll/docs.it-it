---
title: Operatore ++ (Riferimenti per C#)
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: b29f4f1ab00c0f8026f118cb72b090e3b728bfc5
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2018
ms.locfileid: "48030470"
---
# <a name="-operator-c-reference"></a>Operatore ++ (Riferimenti per C#)

L'operatore di incremento unario `++` incrementa il suo operando di 1. È supportato in due forme: l'operatore di incremento suffisso, `x++`, e l'operatore di incremento prefisso, `++x`.

## <a name="postfix-increment-operator"></a>Operatore di incremento suffisso

Il risultato di `x++` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a>Operatore di incremento prefisso

Il risultato di `++x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a>Note

L'operatore di incremento è predefinito per tutti i [tipi integrali](../keywords/integral-types-table.md) (incluso il tipo [char](../keywords/char.md)), i [tipi a virgola mobile](../keywords/floating-point-types-table.md) e i tipi [enumerazione](../keywords/enum.md).

Un operando dell'operatore di incremento deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../../csharp/programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `++`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Operatori di incremento e decremento in forma suffissa](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) e [Operatori di incremento e decremento in forma prefissa](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatore --](decrement-operator.md)
- [Procedura: incrementare e decrementare i puntatori](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
