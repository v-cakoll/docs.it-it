---
title: Operatore default - Riferimenti per C#
ms.custom: seodec18
description: Usare l'operatore default per produrre il valore predefinito di un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 5623cb9dc3790b5bb99635c41cb3f122f4c71d8e
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796940"
---
# <a name="default-operator-c-reference"></a>Operatore default (Riferimenti per C#)

L'operatore `default` produce il [valore predefinito](../keywords/default-values-table.md) di un tipo. L'argomento dell'operatore `default` deve essere il nome di un tipo o di un parametro di tipo.

L'esempio seguente illustra l'utilizzo dell'operatore `default`:

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

È anche possibile usare la parola chiave `default` come etichetta case predefinita all'interno dell'[istruzione `switch`](../keywords/switch.md).

## <a name="default-literal"></a>valore letterale predefinito

A partire da C# 7.1, è possibile usare il valore letterale `default` per produrre il valore predefinito di un tipo quando il compilatore è in grado di dedurre il tipo di espressione. L'espressione letterale `default` produce lo stesso valore dell'espressione `default(T)` in cui `T` è il tipo derivato. È possibile usare il valore letterale `default` in uno dei seguenti casi:

- Nell'assegnazione o nell'inizializzazione di una variabile.
- Nella dichiarazione del valore predefinito per un parametro di metodo facoltativo.
- In una chiamata al metodo per fornire un valore di argomento.
- In un'istruzione `return` o come espressione in un membro con corpo di espressione.

L'esempio seguente illustra l'utilizzo del valore letterale `default`:

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni con valore predefinito](~/_csharplang/spec/expressions.md#default-value-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Per altre informazioni sul valore letterale `default`, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Tabella dei valori predefiniti](../keywords/default-values-table.md)