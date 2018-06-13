---
title: 'Cicli: espressione for...to (F#)'
description: "Vedere come il ciclo for di F #... per l'espressione viene utilizzato per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo."
ms.date: 05/16/2016
ms.openlocfilehash: 841c7d557abc11e0253cb87ab8081cc77671b44b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563402"
---
# <a name="loops-forto-expression"></a>Espressione Loops: for...to

Il `for...to` espressione viene utilizzata per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.


## <a name="syntax"></a>Sintassi

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Note
Il tipo dell'identificatore viene dedotto dal tipo del *avviare* e *fine* espressioni. Tipi per le espressioni devono essere numeri interi a 32 bit.

Anche se tecnicamente un'espressione, `for...to` è più simile a un'istruzione tradizionale in un linguaggio di programmazione imperativa. Il tipo restituito per il *espressione corpo* deve essere `unit`. Gli esempi seguenti illustrano vari usi del `for...to` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Di seguito è riportato l'output del codice precedente.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Cicli: espressione `for...in`](loops-for-in-expression.md)

[Cicli: espressione `while...do`](loops-while-do-expression.md)
