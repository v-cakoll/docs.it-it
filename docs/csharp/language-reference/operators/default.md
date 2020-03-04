---
title: Operatore default - Riferimenti per C#
description: Usare l'operatore predefinito per produrre il valore predefinito di un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: ba4c02caa53a9d532be4012a4543a25cd41b6023
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239313"
---
# <a name="default-operator-c-reference"></a>Operatore default (Riferimenti per C#)

L'operatore `default` produce il [valore predefinito](../builtin-types/default-values.md) di un tipo. L'argomento dell'operatore `default` deve essere il nome di un tipo o di un parametro di tipo.

L'esempio seguente illustra l'utilizzo dell'operatore `default`:

[!code-csharp-interactive[default of T](~/samples/snippets/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

È anche possibile usare la parola chiave `default` come etichetta case predefinita all'interno di un' [istruzione`switch`](../keywords/switch.md).

## <a name="default-literal"></a>valore letterale predefinito

A partire da C# 7.1, è possibile usare il valore letterale `default` per produrre il valore predefinito di un tipo quando il compilatore è in grado di dedurre il tipo di espressione. L'espressione letterale `default` produce lo stesso valore dell'espressione `default(T)` in cui `T` è il tipo derivato. È possibile usare il valore letterale `default` in uno dei seguenti casi:

- Nell'assegnazione o nell'inizializzazione di una variabile.
- Nella dichiarazione del valore predefinito per un parametro del [metodo facoltativo](../../methods.md#optional-parameters-and-arguments).
- In una chiamata al metodo per fornire un valore di argomento.
- In un' [istruzione`return`](../keywords/return.md) o come espressione in un [membro con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

L'esempio seguente illustra l'utilizzo del valore letterale `default`:

[!code-csharp-interactive[default literal](~/samples/snippets/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni con valore predefinito](~/_csharplang/spec/expressions.md#default-value-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Per altre informazioni sul valore letterale `default`, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Valori predefiniti dei C# tipi](../builtin-types/default-values.md)
- [Generics in .NET](../../../standard/generics/index.md)
