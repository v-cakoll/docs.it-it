---
title: Espressioni di valore predefinito - Riferimento in C
description: Utilizzare le espressioni di valore predefinito per ottenere il valore predefinito di un tipo
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 2adfd8d24066e9dad50c3c18407d3ade71b4b68e
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507178"
---
# <a name="default-value-expressions-c-reference"></a>Espressioni di valore predefinito (riferimenti in C

Un'espressione di valore predefinito produce il [valore predefinito](../builtin-types/default-values.md) di un tipo. Esistono due tipi di espressioni di valore predefinito: la chiamata [all'operatore predefinito](#default-operator) e un [valore letterale predefinito](#default-literal).

È inoltre `default` possibile utilizzare la parola chiave come etichetta case predefinita all'interno di un'istruzione [ `switch` ](../keywords/switch.md).

## <a name="default-operator"></a>operatore default

L'argomento dell'operatore `default` deve essere il nome o il parametro di un tipo, come illustrato nell'esempio seguente:

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

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
