---
title: while - Riferimenti per C#
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 486936ae29552891c6a58913b6d5cf9a0d725a69
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422489"
---
# <a name="while-c-reference"></a>while (Riferimenti per C#)

L'istruzione `while` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`. Poiché tale espressione viene valutata prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte. Questo comportamento è diverso dal ciclo [do](do.md), che viene eseguito una o più volte.

In qualsiasi punto all'interno del blocco `while` è possibile uscire dal ciclo usando l'istruzione [break](break.md).

È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md). Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo. In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.

Si può uscire da un ciclo `while` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).

## <a name="example"></a>Esempio

L'esempio seguente illustra l'utilizzo dell'istruzione `while`. Selezionare **Esegui** per eseguire il codice di esempio. Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [L'istruzione while](~/_csharplang/spec/statements.md#the-while-statement) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Istruzione do](do.md)
