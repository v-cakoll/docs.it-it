---
title: 'Funzioni ricorsive: Parola chiave rec'
description: Informazioni su come il F# parola chiave 'rec' viene usato con la parola chiave 'let'. per definire una funzione ricorsiva.
ms.date: 05/16/2016
ms.openlocfilehash: 86eaf1c8a5566d8b9cbc4dcb72f945e2497e5439
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645314"
---
# <a name="recursive-functions-the-rec-keyword"></a>Funzioni ricorsive: Parola chiave rec

Il `rec` parola chiave viene usata in combinazione con il `let` parola chiave per definire una funzione ricorsiva.

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

Funzioni ricorsive, le funzioni che chiamano se stesse, vengono identificate in modo esplicito nel F# linguaggio. Ciò rende disponibili l'identificatore che viene definito nell'ambito della funzione.

Il codice seguente illustra una funzione ricorsiva che calcola la *n*<sup>th</sup> numero di Fibonacci.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> In pratica, codice come quello precedente è dispendioso di memoria e tempo processore dal momento che implica il ricalcolo di valori calcolati in precedenza.

I metodi sono implicitamente ricorsivo all'interno del tipo; non è necessario aggiungere il `rec` (parola chiave). Associazioni let nelle classi sono implicitamente non ricorsivo.

## <a name="mutually-recursive-functions"></a>Funzioni ricorsive reciproche

Le funzioni sono talvolta *ricorsive reciproche*, vale a dire le chiamate formano un cerchio, in cui una funzione chiama un'altra che a sua volta chiama la prima, con qualsiasi numero di chiamate tra. È necessario definire tali funzioni tra loro in quello `let` binding, utilizzando il `and` parola chiave per collegarli tra loro.

Nell'esempio seguente vengono illustrati due si escludono a vicenda funzioni ricorsive.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
