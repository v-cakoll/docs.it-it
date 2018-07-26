---
title: do (Riferimenti per C#)
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: b918b378623a239803fb4e0a65fcf82fd677b21f
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961326"
---
# <a name="do-c-reference"></a>do (Riferimenti per C#)

L'istruzione `do` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`. Poiché tale espressione viene valutata dopo ogni esecuzione del ciclo, un ciclo `do-while` viene eseguito una o più volte. Questo comportamento è diverso da quello del ciclo [while](while.md), che viene eseguito zero o più volte.

In qualsiasi punto all'interno del blocco `do` è possibile uscire dal ciclo usando l'istruzione [break](break.md).

È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md). Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo. In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.

Si può uscire da un ciclo `do-while` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).

## <a name="example"></a>Esempio

L'esempio seguente illustra l'utilizzo dell'istruzione `do`. Selezionare **Esegui** per eseguire il codice di esempio. Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

 [Riferimenti per C#](../index.md)  
 [Guida per programmatori C#](../../programming-guide/index.md)  
 [Parole chiave di C#](index.md)  
 [Istruzione do-while (C++)](/cpp/cpp/do-while-statement-cpp)  
 [Istruzioni di iterazione](iteration-statements.md)  
 [Istruzione While](while.md)  
