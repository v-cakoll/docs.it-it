---
title: while - Riferimenti per C#
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: af616c2381b993f86296cbfa43a01ba2f9e000c2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401862"
---
# <a name="while-c-reference"></a>while (Riferimenti per C#)

L'istruzione `while` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`. Poiché tale espressione viene valutata prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte. Questo comportamento è diverso dal ciclo [do](do.md), che viene eseguito una o più volte.

In qualsiasi punto all'interno del blocco `while` è possibile uscire dal ciclo usando l'istruzione [break](break.md).

È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md). Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo. In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.

È anche possibile uscire `while` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .

## <a name="example"></a>Esempio

L'esempio seguente illustra l'utilizzo dell'istruzione `while`. Selezionare **Esegui** per eseguire il codice di esempio. Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.

[!code-csharp-interactive[while loop example](snippets/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [L'istruzione while](~/_csharplang/spec/statements.md#the-while-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [istruzione do](do.md)
