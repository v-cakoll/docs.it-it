---
title: 'Espressioni lambda: Parola chiave fun'
description: Informazioni su come usare la F# parola chiave "Fun" per definire un'espressione lambda, che è una funzione anonima.
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630672"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Espressioni lambda: Parola chiave fun (F#)

La `fun` parola chiave viene usata per definire un'espressione lambda, ovvero una funzione anonima.

## <a name="syntax"></a>Sintassi

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Note

Il *parametro-list* è in genere costituito da nomi e, facoltativamente, da tipi di parametri. Più in generale, l' *elenco di parametri* può essere composto da F# qualsiasi modello. Per un elenco completo dei modelli possibili [, vedere Criteri](../pattern-matching.md)di ricerca. Gli elenchi di parametri validi includono gli esempi seguenti.

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

L' *espressione* è il corpo della funzione, l'ultima espressione di che genera un valore restituito. Di seguito sono riportati alcuni esempi di espressioni lambda valide:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a>Uso di espressioni lambda

Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni in un elenco o in un'altra raccolta e si desidera evitare il lavoro aggiuntivo di definizione di una funzione. Molte F# funzioni della libreria accettano valori di funzione come argomenti e può essere particolarmente utile usare un'espressione lambda in tali casi. Il codice seguente applica un'espressione lambda agli elementi di un elenco. In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
