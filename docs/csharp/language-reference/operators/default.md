---
title: Operatore default - Riferimenti per C#
description: Utilizzare l'operatore predefinito per produrre il valore predefinito di un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 0d37fe952e71e74f014872231a2e58663dea9d18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399483"
---
# <a name="default-operator-c-reference"></a>Operatore default (Riferimenti per C#)

L'operatore `default` produce il [valore predefinito](../builtin-types/default-values.md) di un tipo. L'argomento dell'operatore `default` deve essere il nome di un tipo o di un parametro di tipo.

L'esempio seguente illustra l'utilizzo dell'operatore `default`:

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

È inoltre `default` possibile utilizzare la parola chiave come etichetta case predefinita all'interno di un'istruzione [ `switch` ](../keywords/switch.md).

## <a name="default-literal"></a>valore letterale predefinito

A partire da C# 7.1, è possibile usare il valore letterale `default` per produrre il valore predefinito di un tipo quando il compilatore è in grado di dedurre il tipo di espressione. L'espressione letterale `default` produce lo stesso valore dell'espressione `default(T)` in cui `T` è il tipo derivato. È possibile usare il valore letterale `default` in uno dei seguenti casi:

- Nell'assegnazione o nell'inizializzazione di una variabile.
- Nella dichiarazione del valore predefinito per un [parametro di metodo facoltativo.](../../methods.md#optional-parameters-and-arguments)
- In una chiamata al metodo per fornire un valore di argomento.
- In [ `return` un'istruzione](../keywords/return.md) o come espressione in un [membro con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

L'esempio seguente illustra l'utilizzo del valore letterale `default`:

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni con valore predefinito](~/_csharplang/spec/expressions.md#default-value-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Per altre informazioni sul valore letterale `default`, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Valori predefiniti dei tipi c'è](../builtin-types/default-values.md)
- [Generics in .NET](../../../standard/generics/index.md)
