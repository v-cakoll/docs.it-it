---
title: 'Cicli: espressione for...to (F#)'
description: "Vedere come il ciclo for di F #.. su espressione viene usato per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo."
ms.date: 05/16/2016
ms.openlocfilehash: 8160fd30c4f3afe8bb6b58f468802ef1c0ef32ee
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43800469"
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
- [Cicli: espressione `for...in`](loops-for-in-expression.md)
- [Cicli: espressione `while...do`](loops-while-do-expression.md)
