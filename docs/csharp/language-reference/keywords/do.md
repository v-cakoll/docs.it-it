---
title: do - Riferimenti per C#
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: d75dd816278a876fa05d133e5eb189d606300a5c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401927"
---
# <a name="do-c-reference"></a>do (Riferimenti per C#)

L'istruzione `do` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`. Poiché tale espressione viene valutata dopo ogni esecuzione del ciclo, un ciclo `do-while` viene eseguito una o più volte. Questo comportamento è diverso da quello del ciclo [while](while.md), che viene eseguito zero o più volte.

In qualsiasi punto all'interno del blocco `do` è possibile uscire dal ciclo usando l'istruzione [break](break.md).

È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md). Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo. In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.

È anche possibile uscire `do-while` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .

## <a name="example"></a>Esempio

L'esempio seguente illustra l'utilizzo dell'istruzione `do`. Selezionare **Esegui** per eseguire il codice di esempio. Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.

[!code-csharp-interactive[do loop example](snippets/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Istruzione do](~/_csharplang/spec/statements.md#the-do-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Istruzione while](while.md)
