---
title: 'Espressioni lambda: Parola chiave fun'
description: Informazioni su come usare il F# parola chiave 'divertente' per definire un'espressione lambda, che è una funzione anonima.
ms.date: 05/16/2016
ms.openlocfilehash: c59d32bd4226384213453f1a9d362209e68a6fb5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645382"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Espressioni lambda: Parola chiave fun (F#)

Il `fun` parola chiave viene usata per definire un'espressione lambda, vale a dire, una funzione anonima.

## <a name="syntax"></a>Sintassi

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Note

Il *elenco di parametri* costituito in genere i nomi e, facoltativamente, i tipi dei parametri. Più in generale, il *dall'elenco dei parametri* può essere costituita da uno F# modelli. Per un elenco completo delle possibili modelli, vedere [criteri di ricerca](../pattern-matching.md). Elenchi di parametri validi includono gli esempi seguenti.

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

Il *espressione* è il corpo della funzione, di cui l'ultima espressione genera un valore restituito. Esempi di espressioni lambda validi includono quanto segue:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a>Uso di espressioni lambda

Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni su un elenco o un'altra raccolta e si desidera evitare le attività aggiuntive di definizione di una funzione. Molti F# libreria le funzioni accettano valori di funzioni come argomenti e può essere particolarmente utile usare un'espressione lambda in questi casi. Il codice seguente si applica un'espressione lambda a elementi di un elenco. In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
