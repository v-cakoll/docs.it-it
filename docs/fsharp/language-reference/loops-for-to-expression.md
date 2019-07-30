---
title: 'Espressione Loops: for...to'
description: Vedere come il F# ... l'espressione to viene utilizzata per eseguire un'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626619"
---
# <a name="loops-forto-expression"></a>Espressione Loops: for...to

L' `for...to` espressione viene utilizzata per eseguire un'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.

## <a name="syntax"></a>Sintassi

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Note

Il tipo dell'identificatore viene dedotto dal tipo delle espressioni di *inizio* e *fine* . I tipi per queste espressioni devono essere interi a 32 bit.

Sebbene tecnicamente un'espressione, `for...to` è più simile a un'istruzione tradizionale in un linguaggio di programmazione imperativo. Il tipo restituito per *Body-Expression* deve essere `unit`. Negli esempi seguenti vengono illustrati diversi utilizzi `for...to` dell'espressione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Di seguito è riportato l'output del codice precedente.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cicli `for...in`Espressione](loops-for-in-expression.md)
- [Cicli `while...do`Espressione](loops-while-do-expression.md)
