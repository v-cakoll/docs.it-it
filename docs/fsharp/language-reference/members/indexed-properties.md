---
title: Proprietà indicizzate (F#)
description: "Informazioni sulle proprietà indicizzate F # che sono proprietà che forniscono l'accesso di tipo matrice ai dati ordinati."
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45583424"
---
# <a name="indexed-properties"></a>Proprietà indicizzate

*Proprietà indicizzate* vengono ordinate in proprietà che forniscono l'accesso di tipo matrice ai dati. Sono disponibili per tre formati seguenti:

* `Item`
* `Ordinal`
* `Cardinal`

Un membro di F # nome deve essere uno di questi tre nomi per fornire l'accesso di tipo matrice. `IndexerName` viene usato per rappresentare uno qualsiasi dei tre opzioni seguenti:

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

Le forme di sintassi precedente viene illustrato come definire le proprietà indicizzate che hanno entrambi un `get` e un `set` (metodo), hanno un `get` solo, metodo o dispone di un `set` solo metodo. È anche possibile combinare entrambi la sintassi illustrata per solo get e la sintassi illustrata solo per set e produrre una proprietà con get e set. Questo modulo di quest'ultimo consente di copiare gli attributi e modificatori di accessibilità diversa su get e set di metodi.

Quando la *IndexerName* è `Item`, il compilatore considera la proprietà come una proprietà indicizzata predefinita. Oggetto *proprietà indicizzata predefinita* è una proprietà che è possibile accedere usando la sintassi di tipo matrice sull'istanza dell'oggetto. Ad esempio, se `obj` è un oggetto del tipo che definisce questa proprietà, la sintassi `obj.[index]` viene utilizzato per accedere alla proprietà.

La sintassi per l'accesso a una proprietà indicizzata non predefinito è fornire il nome della proprietà e l'indice tra parentesi. Ad esempio, se la proprietà è `Ordinal`, si scrive `obj.Ordinal(index)` per accedervi.

Indipendentemente dalla forma utilizzata, è consigliabile usare sempre il currying per il `set` metodo su una proprietà indicizzata. Per informazioni sulle funzioni sottoposte a currying, vedere [funzioni](../functions/index.md).

## <a name="example"></a>Esempio

Esempio di codice seguente illustra la definizione e utilizzo predefinita e la proprietà indicizzata non predefinite con get e set di metodi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Output

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Proprietà indicizzate con più variabili di indice

Proprietà indicizzate possono avere più di una variabile di indice. In tal caso, le variabili sono separate da virgole quando la proprietà viene utilizzata. Il metodo set in tale proprietà deve avere due argomenti sottoposti a currying, la prima delle quali è una tupla contenente le chiavi e il secondo dei quali è il valore da impostare.

Il codice seguente illustra l'uso di una proprietà indicizzata con più variabili di indice.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
