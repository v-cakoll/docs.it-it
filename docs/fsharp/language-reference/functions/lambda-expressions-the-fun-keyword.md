---
title: 'Espressioni lambda: parola chiave fun (F#)'
description: "Informazioni su come utilizzare la parola chiave 'fun' F # per definire un'espressione lambda, che è una funzione anonima."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Espressioni lambda: parola chiave fun (F#)

Il `fun` parola chiave viene utilizzata per definire un'espressione lambda, vale a dire, una funzione anonima.


## <a name="syntax"></a>Sintassi

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Note
Il *elenco di parametri* consiste in genere di nomi e, facoltativamente, tipi di parametri. Più in generale, il *elenco di parametri* può essere composto da qualsiasi modello F #. Per un elenco completo di modelli possibili, vedere [criteri di ricerca](../pattern-matching.md). Elenchi di parametri validi includono i seguenti esempi.

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

Il *espressione* è il corpo della funzione, di cui l'ultima espressione genera un valore restituito. Esempi di espressioni lambda validi includono:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a>Uso di espressioni lambda
Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni su un elenco o un'altra raccolta e si desidera evitare il lavoro aggiuntivo della definizione di una funzione. Molte funzioni della libreria F # accettano valori di funzione come argomenti e può risultare particolarmente utile utilizzare un'espressione lambda in questi casi. Il codice seguente si applica un'espressione lambda a elementi di un elenco. In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a>Vedere anche
[Funzioni](index.md)
