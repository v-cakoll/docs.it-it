---
title: 'Funzioni ricorsive: Parola chiave REC'
description: Viene illustrato come F# usare la parola chiave ' REC ' con la parola chiave ' Let ' per definire una funzione ricorsiva.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630648"
---
# <a name="recursive-functions-the-rec-keyword"></a>Funzioni ricorsive: Parola chiave REC

La `rec` parola chiave viene utilizzata insieme `let` alla parola chiave per definire una funzione ricorsiva.

## <a name="syntax"></a>Sintassi

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>Note

Le F# funzioni ricorsive, funzioni che chiamano se stesse, vengono identificate in modo esplicito nel linguaggio. In questo modo, identificatore viene definito disponibile nell'ambito della funzione.

Il codice seguente illustra una funzione ricorsiva che calcola il numero di<sup>Fibonacci</sup> n.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> In pratica, il codice simile a quello precedente è uno spreco di memoria e tempo del processore perché comporta il ricalcolo dei valori calcolati in precedenza.

I metodi sono implicitamente ricorsivi all'interno del tipo. non è necessario aggiungere la `rec` parola chiave. Le associazioni let all'interno delle classi non sono implicitamente ricorsive.

## <a name="mutually-recursive-functions"></a>Funzioni ricorsive reciproche

A volte lefunzioni sono reciprocamente ricorsive, vale a dire che le chiamate formano un cerchio, in cui una funzione chiama un'altra che a sua volta chiama la prima, con un numero qualsiasi di chiamate tra. È necessario definire tali funzioni insieme nell'associazione uno `let` , usando la `and` parola chiave per collegarle insieme.

Nell'esempio seguente vengono illustrate due funzioni ricorsive reciproche.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
