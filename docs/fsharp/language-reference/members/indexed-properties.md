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
# <a name="indexed-properties"></a><span data-ttu-id="47297-103">Proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="47297-103">Indexed Properties</span></span>

<span data-ttu-id="47297-104">*Proprietà indicizzate* vengono ordinate in proprietà che forniscono l'accesso di tipo matrice ai dati.</span><span class="sxs-lookup"><span data-stu-id="47297-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span> <span data-ttu-id="47297-105">Sono disponibili per tre formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="47297-105">They come in three forms:</span></span>

* `Item`
* `Ordinal`
* `Cardinal`

<span data-ttu-id="47297-106">Un membro di F # nome deve essere uno di questi tre nomi per fornire l'accesso di tipo matrice.</span><span class="sxs-lookup"><span data-stu-id="47297-106">An F# member must be named one of these three names to provide array-like access.</span></span> <span data-ttu-id="47297-107">`IndexerName` viene usato per rappresentare uno qualsiasi dei tre opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47297-107">`IndexerName` is used to represent any of the three options below:</span></span>

## <a name="syntax"></a><span data-ttu-id="47297-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47297-108">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="47297-109">Note</span><span class="sxs-lookup"><span data-stu-id="47297-109">Remarks</span></span>

<span data-ttu-id="47297-110">Le forme di sintassi precedente viene illustrato come definire le proprietà indicizzate che hanno entrambi un `get` e un `set` (metodo), hanno un `get` solo, metodo o dispone di un `set` solo metodo.</span><span class="sxs-lookup"><span data-stu-id="47297-110">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="47297-111">È anche possibile combinare entrambi la sintassi illustrata per solo get e la sintassi illustrata solo per set e produrre una proprietà con get e set.</span><span class="sxs-lookup"><span data-stu-id="47297-111">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="47297-112">Questo modulo di quest'ultimo consente di copiare gli attributi e modificatori di accessibilità diversa su get e set di metodi.</span><span class="sxs-lookup"><span data-stu-id="47297-112">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="47297-113">Quando la *IndexerName* è `Item`, il compilatore considera la proprietà come una proprietà indicizzata predefinita.</span><span class="sxs-lookup"><span data-stu-id="47297-113">When the *IndexerName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="47297-114">Oggetto *proprietà indicizzata predefinita* è una proprietà che è possibile accedere usando la sintassi di tipo matrice sull'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="47297-114">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="47297-115">Ad esempio, se `obj` è un oggetto del tipo che definisce questa proprietà, la sintassi `obj.[index]` viene utilizzato per accedere alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="47297-115">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="47297-116">La sintassi per l'accesso a una proprietà indicizzata non predefinito è fornire il nome della proprietà e l'indice tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="47297-116">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="47297-117">Ad esempio, se la proprietà è `Ordinal`, si scrive `obj.Ordinal(index)` per accedervi.</span><span class="sxs-lookup"><span data-stu-id="47297-117">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="47297-118">Indipendentemente dalla forma utilizzata, è consigliabile usare sempre il currying per il `set` metodo su una proprietà indicizzata.</span><span class="sxs-lookup"><span data-stu-id="47297-118">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="47297-119">Per informazioni sulle funzioni sottoposte a currying, vedere [funzioni](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="47297-119">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="47297-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="47297-120">Example</span></span>

<span data-ttu-id="47297-121">Esempio di codice seguente illustra la definizione e utilizzo predefinita e la proprietà indicizzata non predefinite con get e set di metodi.</span><span class="sxs-lookup"><span data-stu-id="47297-121">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="47297-122">Output</span><span class="sxs-lookup"><span data-stu-id="47297-122">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="47297-123">Proprietà indicizzate con più variabili di indice</span><span class="sxs-lookup"><span data-stu-id="47297-123">Indexed Properties with Multiple Index Variables</span></span>

<span data-ttu-id="47297-124">Proprietà indicizzate possono avere più di una variabile di indice.</span><span class="sxs-lookup"><span data-stu-id="47297-124">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="47297-125">In tal caso, le variabili sono separate da virgole quando la proprietà viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="47297-125">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="47297-126">Il metodo set in tale proprietà deve avere due argomenti sottoposti a currying, la prima delle quali è una tupla contenente le chiavi e il secondo dei quali è il valore da impostare.</span><span class="sxs-lookup"><span data-stu-id="47297-126">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="47297-127">Il codice seguente illustra l'uso di una proprietà indicizzata con più variabili di indice.</span><span class="sxs-lookup"><span data-stu-id="47297-127">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a><span data-ttu-id="47297-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47297-128">See also</span></span>

- [<span data-ttu-id="47297-129">Membri</span><span class="sxs-lookup"><span data-stu-id="47297-129">Members</span></span>](index.md)
