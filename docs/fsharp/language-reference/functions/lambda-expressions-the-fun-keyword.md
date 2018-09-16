---
title: 'Espressioni lambda: parola chiave fun (F#)'
description: "Informazioni su come usare la parola chiave 'divertente' di F # per definire un'espressione lambda, che è una funzione anonima."
ms.date: 05/16/2016
ms.openlocfilehash: a37757f6b7328cd348bbf13f058a6dbc881769cf
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45683095"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Espressioni lambda: parola chiave fun (F#)

Il `fun` parola chiave viene usata per definire un'espressione lambda, vale a dire, una funzione anonima.

## <a name="syntax"></a>Sintassi

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Note

Il *elenco di parametri* costituito in genere i nomi e, facoltativamente, i tipi dei parametri. Più in generale, il *elenco di parametri* può essere costituita da eventuali criteri F #. Per un elenco completo delle possibili modelli, vedere [criteri di ricerca](../pattern-matching.md). Elenchi di parametri validi includono gli esempi seguenti.

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

Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni su un elenco o un'altra raccolta e si desidera evitare le attività aggiuntive di definizione di una funzione. Molte funzioni della libreria F # che accettano valori di funzione come argomenti e può essere particolarmente utile usare un'espressione lambda in questi casi. Il codice seguente si applica un'espressione lambda a elementi di un elenco. In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
