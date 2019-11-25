---
title: Proprietà indicizzate
description: Informazioni sulle proprietà indicizzate in F#, che consentono l'accesso di tipo matrice ai dati ordinati.
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976605"
---
# <a name="indexed-properties"></a><span data-ttu-id="ac2fd-103">Proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="ac2fd-103">Indexed Properties</span></span>

<span data-ttu-id="ac2fd-104">Quando si definisce una classe che astrae i dati ordinati, a volte può essere utile fornire l'accesso indicizzato a tali dati senza esporre l'implementazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="ac2fd-105">Questa operazione viene eseguita con il membro `Item`.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac2fd-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac2fd-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="ac2fd-107">Note</span><span class="sxs-lookup"><span data-stu-id="ac2fd-107">Remarks</span></span>

<span data-ttu-id="ac2fd-108">I formati della sintassi precedente illustrano come definire le proprietà indicizzate che hanno un metodo di `get` e un `set`, avere solo un metodo di `get` o avere un solo metodo `set`.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="ac2fd-109">È anche possibile combinare la sintassi mostrata solo per Get e la sintassi mostrata solo per set e produrre una proprietà con Get e set.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="ac2fd-110">Quest'ultimo formato consente di inserire modificatori e attributi di accessibilità diversi nei metodi get e set.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="ac2fd-111">Utilizzando il nome `Item`, il compilatore considera la proprietà come una proprietà indicizzata predefinita.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="ac2fd-112">Una *proprietà indicizzata predefinita* è una proprietà a cui è possibile accedere utilizzando la sintassi di tipo matrice nell'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="ac2fd-113">Se, ad esempio, `o` è un oggetto del tipo che definisce questa proprietà, viene utilizzata la sintassi `o.[index]` per accedere alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="ac2fd-114">La sintassi per l'accesso a una proprietà indicizzata non predefinita consiste nel fornire il nome della proprietà e l'indice tra parentesi, come un membro normale.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="ac2fd-115">Se, ad esempio, la proprietà `o` viene chiamata `Ordinal`, è possibile scrivere `o.Ordinal(index)` per accedervi.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="ac2fd-116">Indipendentemente dal formato utilizzato, è consigliabile utilizzare sempre il modulo sottoposto a currying per il metodo set su una proprietà indicizzata.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="ac2fd-117">Per informazioni sulle funzioni sottoposte a currying, vedere [funzioni](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac2fd-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="ac2fd-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac2fd-118">Example</span></span>

<span data-ttu-id="ac2fd-119">Nell'esempio di codice riportato di seguito viene illustrata la definizione e l'utilizzo di proprietà indicizzate predefinite e non predefinite con metodi get e set.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="ac2fd-120">Output</span><span class="sxs-lookup"><span data-stu-id="ac2fd-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="ac2fd-121">Proprietà indicizzate con più valori di indice</span><span class="sxs-lookup"><span data-stu-id="ac2fd-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="ac2fd-122">Le proprietà indicizzate possono avere più di un valore di indice.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="ac2fd-123">In tal caso, i valori sono separati da virgole quando si usa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="ac2fd-124">Il metodo set in tale proprietà deve avere due argomenti sottoposti a currying, il primo dei quali è una tupla contenente le chiavi e il secondo oggetto è il valore da impostare.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="ac2fd-125">Il codice seguente illustra l'uso di una proprietà indicizzata con più valori di indice.</span><span class="sxs-lookup"><span data-stu-id="ac2fd-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="ac2fd-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac2fd-126">See also</span></span>

- [<span data-ttu-id="ac2fd-127">Membri</span><span class="sxs-lookup"><span data-stu-id="ac2fd-127">Members</span></span>](index.md)
