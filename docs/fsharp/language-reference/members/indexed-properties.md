---
title: Proprietà indicizzate
description: Altre informazioni sulle proprietà indicizzata in F#, che consentono l'accesso di tipo matrice ai dati ordinati.
ms.date: 10/17/2018
ms.openlocfilehash: 3817290505339803814e981cd5408cd4df6bd283
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611776"
---
# <a name="indexed-properties"></a>Proprietà indicizzate

Quando si definisce una classe che consente di astrarre dati ordinati, può talvolta essere utile fornire l'accesso indicizzato per i dati senza esporre l'implementazione sottostante. Questa operazione viene eseguita con il `Index` membro.

## <a name="syntax"></a>Sintassi

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>Note

Le forme di sintassi precedente viene illustrato come definire le proprietà indicizzate che hanno entrambi un `get` e un `set` (metodo), hanno un `get` solo, metodo o dispone di un `set` solo metodo. È anche possibile combinare entrambi la sintassi illustrata per solo get e la sintassi illustrata solo per set e produrre una proprietà con get e set. Questo modulo di quest'ultimo consente di copiare gli attributi e modificatori di accessibilità diversa su get e set di metodi.

Utilizzando il nome `Item`, il compilatore considera la proprietà come una proprietà indicizzata predefinita. Oggetto *proprietà indicizzata predefinita* è una proprietà che è possibile accedere usando la sintassi di tipo matrice sull'istanza dell'oggetto. Ad esempio, se `o` è un oggetto del tipo che definisce questa proprietà, la sintassi `o.[index]` viene utilizzato per accedere alla proprietà.

La sintassi per l'accesso a una proprietà indicizzata non predefinito è fornire il nome della proprietà e l'indice tra parentesi, proprio come un membro regolare. Ad esempio, se la proprietà sul `o` viene chiamato `Ordinal`, si scrive `o.Ordinal(index)` per accedervi.

Indipendentemente dalla forma utilizzata, è sempre necessario utilizzare il modulo sottoposti a currying per il metodo set su una proprietà indicizzata. Per informazioni sulle funzioni sottoposte a currying, vedere [funzioni](../functions/index.md).

## <a name="example"></a>Esempio

Esempio di codice seguente illustra la definizione e utilizzo predefinita e la proprietà indicizzata non predefinite con get e set di metodi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Output

```console
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