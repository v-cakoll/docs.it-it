---
title: Proprietà indicizzate (F#)
description: "Informazioni sulle proprietà indicizzate F # che sono proprietà che forniscono l'accesso di tipo matrice ai dati ordinati."
ms.date: 05/16/2016
ms.openlocfilehash: 503cef9693cfe5e13d4e2d19a721d65bff1ce749
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="indexed-properties"></a>Proprietà indicizzate

*Proprietà indicizzate* sono proprietà che forniscono l'accesso di tipo matrice a ordinati i dati. Sono disponibili tre forme:

* `Item`
* `Ordinal`
* `Cardinal`

Un membro di F # deve chiamarsi uno di questi tre nomi per fornire l'accesso di tipo matrice. `IndexerName` viene utilizzato per rappresentare uno qualsiasi dei tre opzioni seguenti:


## <a name="syntax"></a>Sintassi

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>Note
Le forme di sintassi precedente viene illustrato come definire proprietà indicizzate che hanno entrambe un `get` e un `set` (metodo), hanno un `get` solo, metodo o un `set` solo metodo. È possibile combinare la sintassi illustrata solo per get e la sintassi illustrata solo per set e produrre una proprietà che contiene sia get che set. Questo modulo di quest'ultimo consente di inserire gli attributi e modificatori di accessibilità diversi su get e set di metodi.

Quando il *IndexerName* è `Item`, il compilatore considera la proprietà come una proprietà indicizzata predefinita. Oggetto *proprietà indicizzata predefinita* è una proprietà che è possibile accedere tramite la sintassi di tipo matrice sull'istanza dell'oggetto. Ad esempio, se `obj` è un oggetto del tipo che definisce questa proprietà, la sintassi `obj.[index]` viene utilizzato per accedere alla proprietà.

La sintassi per l'accesso a una proprietà indicizzata è fornire il nome della proprietà e l'indice racchiuso tra parentesi. Ad esempio, se la proprietà è `Ordinal`, si scrive `obj.Ordinal(index)` per accedervi.

Indipendentemente dal modulo utilizzato, è necessario utilizzare sempre il form sottoposte a currying per il `set` metodo su una proprietà indicizzata. Per informazioni sulle funzioni sottoposte a currying, vedere [funzioni](../functions/index.md).

## <a name="example"></a>Esempio

Esempio di codice seguente viene illustrata la definizione e utilizzo di predefinite e proprietà indicizzate non predefinite con get e set di metodi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Output

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Proprietà indicizzate con più variabili di indice
Proprietà indicizzate possono avere più di una variabile di indice. In tal caso, le variabili sono separate da virgole quando la proprietà viene utilizzata. Il metodo set in tale proprietà deve avere due argomenti sottoposti a currying, il primo dei quali è una tupla contenente le chiavi e il secondo dei quali è il valore da impostare.

Il codice seguente viene illustrato l'utilizzo di una proprietà indicizzata con più variabili di indice.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a>Vedere anche
[Membri](index.md)
