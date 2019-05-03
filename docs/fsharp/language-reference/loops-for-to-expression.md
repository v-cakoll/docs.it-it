---
title: 'Espressione Loops: for...to'
description: Vedere il F# for... su espressione viene usato per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.
ms.date: 05/16/2016
ms.openlocfilehash: 041e98fa4bcc140aa3cd699f6ed35bf52c8b4175
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904033"
---
# <a name="loops-forto-expression"></a>Espressione Loops: for...to

Il `for...to` espressione viene usata per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.

## <a name="syntax"></a>Sintassi

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Note

Il tipo dell'identificatore viene dedotto dal tipo dei *avviare* e *fine* espressioni. I tipi per queste espressioni devono essere numeri interi a 32 bit.

Anche se tecnicamente un'espressione, `for...to` è più simile a un'istruzione tradizionale in un linguaggio di programmazione imperativa. Il tipo restituito per il *corpo-expression* deve essere `unit`. Gli esempi seguenti illustrano vari usi del `for...to` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Di seguito è riportato l'output del codice precedente.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cicli: `for...in` Expression](loops-for-in-expression.md)
- [Cicli: `while...do` Expression](loops-while-do-expression.md)