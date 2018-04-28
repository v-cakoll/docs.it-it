---
title: 'Cicli: espressione for...to (F#)'
description: "Vedere come il ciclo for di F #... per l'espressione viene utilizzato per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 95a8960d71c82c01118d2e71479fc0ec5298a02b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
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
