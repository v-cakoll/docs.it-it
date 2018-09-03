---
title: Operatore false (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43253249"
---
# <a name="false-operator-c-reference"></a>Operatore false (Riferimenti per C#)

Restituisce il valore [bool](bool.md) `true` per indicare che un operando è `false` e restituisce `false` in caso contrario.

Prima di C# 2.0, gli operatori `true` e `false` erano usati per creare tipi di valore nullable definiti dall'utente compatibili con tipi quali `SqlBool`. Tuttavia, il linguaggio fornisce ora supporto incorporato per tipi di valore nullable e, quando possibile, è consigliabile usarli al posto dell'overload degli operatori `true` e `false`. Per altre informazioni, vedere [Tipi nullable](../../programming-guide/nullable-types/index.md).

Con valori booleani nullable, l'espressione `a != b` non è necessariamente uguale a `!(a == b)` perché uno o entrambi i valori potrebbero essere null. È necessario eseguire l'overload di entrambi gli operatori `true` e `false` separatamente per gestire correttamente i valori null nell'espressione. Nell'esempio riportato di seguito viene illustrato come eseguire l'overload e usare gli operatori `true` e `false`.

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

Un tipo che esegue l'overload degli operatori `true` e `false` può essere usato per il controllo dell'espressione nelle istruzioni [if](if-else.md), [do](do.md), [while](while.md) e [for](for.md) e nelle [espressioni condizionali](../operators/conditional-operator.md).

Se un tipo definisce l'operatore `false`, deve anche definire l'operatore [true](true.md).

Un tipo non può eseguire direttamente l'overload degli operatori logici condizionali ([ && ](../operators/conditional-and-operator.md) e [&#124;&#124;](../operators/conditional-or-operator.md)), ma è possibile ottenere un effetto equivalente eseguendo l'overload dei normali operatori logici e degli operatori `true` e `false`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)  
- [Guida per programmatori C#](../../programming-guide/index.md)  
- [Parole chiave di C#](index.md)  
- [Operatori C#](../operators/index.md)  
- [true](true.md)  