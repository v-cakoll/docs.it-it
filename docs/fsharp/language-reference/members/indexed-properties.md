---
title: Proprietà indicizzate
description: Informazioni sulle proprietà indicizzate in F#, che consentono l'accesso di tipo matrice ai dati ordinati.
ms.date: 10/17/2018
ms.openlocfilehash: 379417e31b8e178d8c939e5b23dc144bfb17e562
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627561"
---
# <a name="indexed-properties"></a>Proprietà indicizzate

Quando si definisce una classe che astrae i dati ordinati, a volte può essere utile fornire l'accesso indicizzato a tali dati senza esporre l'implementazione sottostante. Questa operazione viene eseguita con `Item` il membro.

## <a name="syntax"></a>Sintassi

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>Note

Nei form della sintassi precedente viene illustrato come definire le proprietà indicizzate che dispongono sia di `get` un `set` metodo che di un metodo `get` , solo un metodo o solo `set` un metodo. È anche possibile combinare la sintassi mostrata solo per Get e la sintassi mostrata solo per set e produrre una proprietà con Get e set. Quest'ultimo formato consente di inserire modificatori e attributi di accessibilità diversi nei metodi get e set.

Utilizzando il nome `Item`, il compilatore considera la proprietà come una proprietà indicizzata predefinita. Una *proprietà indicizzata predefinita* è una proprietà a cui è possibile accedere utilizzando la sintassi di tipo matrice nell'istanza dell'oggetto. Se `o` , ad esempio, è un oggetto del tipo che definisce questa proprietà, viene utilizzata `o.[index]` la sintassi per accedere alla proprietà.

La sintassi per l'accesso a una proprietà indicizzata non predefinita consiste nel fornire il nome della proprietà e l'indice tra parentesi, come un membro normale. Se, ad esempio, viene chiamata `o` `Ordinal`la proprietà su, si `o.Ordinal(index)` scrive per accedervi.

Indipendentemente dal formato utilizzato, è consigliabile utilizzare sempre il modulo sottoposto a currying per il metodo set su una proprietà indicizzata. Per informazioni sulle funzioni sottoposte a currying, vedere [funzioni](../functions/index.md).

## <a name="example"></a>Esempio

Nell'esempio di codice riportato di seguito viene illustrata la definizione e l'utilizzo di proprietà indicizzate predefinite e non predefinite con metodi get e set.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Output

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>Proprietà indicizzate con più valori di indice

Le proprietà indicizzate possono avere più di un valore di indice. In tal caso, i valori sono separati da virgole quando si usa la proprietà. Il metodo set in tale proprietà deve avere due argomenti sottoposti a currying, il primo dei quali è una tupla contenente le chiavi e il secondo oggetto è il valore da impostare.

Il codice seguente illustra l'uso di una proprietà indicizzata con più valori di indice.

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
