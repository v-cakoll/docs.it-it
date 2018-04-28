---
title: Proprietà indicizzate (F#)
description: "Informazioni sulle proprietà indicizzate F # che sono proprietà che forniscono l'accesso di tipo matrice ai dati ordinati."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 39396b3a5ec43f9a8ab0df96afeb69e05801c752
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="indexed-properties"></a><span data-ttu-id="86e83-103">Proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="86e83-103">Indexed Properties</span></span>

<span data-ttu-id="86e83-104">*Proprietà indicizzate* sono proprietà che forniscono l'accesso di tipo matrice a ordinati i dati.</span><span class="sxs-lookup"><span data-stu-id="86e83-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span>


## <a name="syntax"></a><span data-ttu-id="86e83-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86e83-105">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="86e83-106">Note</span><span class="sxs-lookup"><span data-stu-id="86e83-106">Remarks</span></span>
<span data-ttu-id="86e83-107">Le tre forme di sintassi precedente viene illustrato come definire proprietà indicizzate che hanno entrambi un `get` e un `set` (metodo), hanno un `get` solo, metodo o un `set` solo metodo.</span><span class="sxs-lookup"><span data-stu-id="86e83-107">The three forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="86e83-108">È possibile combinare la sintassi illustrata solo per get e la sintassi illustrata solo per set e produrre una proprietà che contiene sia get che set.</span><span class="sxs-lookup"><span data-stu-id="86e83-108">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="86e83-109">Questo modulo di quest'ultimo consente di inserire gli attributi e modificatori di accessibilità diversi su get e set di metodi.</span><span class="sxs-lookup"><span data-stu-id="86e83-109">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="86e83-110">Quando il *PropertyName* è `Item`, il compilatore considera la proprietà come una proprietà indicizzata predefinita.</span><span class="sxs-lookup"><span data-stu-id="86e83-110">When the *PropertyName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="86e83-111">Oggetto *proprietà indicizzata predefinita* è una proprietà che è possibile accedere tramite la sintassi di tipo matrice sull'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="86e83-111">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="86e83-112">Ad esempio, se `obj` è un oggetto del tipo che definisce questa proprietà, la sintassi `obj.[index]` viene utilizzato per accedere alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="86e83-112">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="86e83-113">La sintassi per l'accesso a una proprietà indicizzata è fornire il nome della proprietà e l'indice racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="86e83-113">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="86e83-114">Ad esempio, se la proprietà è `Ordinal`, si scrive `obj.Ordinal(index)` per accedervi.</span><span class="sxs-lookup"><span data-stu-id="86e83-114">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="86e83-115">Indipendentemente dal modulo utilizzato, è necessario utilizzare sempre il form sottoposte a currying per il `set` metodo su una proprietà indicizzata.</span><span class="sxs-lookup"><span data-stu-id="86e83-115">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="86e83-116">Per informazioni sulle funzioni sottoposte a currying, vedere [funzioni](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="86e83-116">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="86e83-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="86e83-117">Example</span></span>

<span data-ttu-id="86e83-118">Esempio di codice seguente viene illustrata la definizione e utilizzo di predefinite e proprietà indicizzate non predefinite con get e set di metodi.</span><span class="sxs-lookup"><span data-stu-id="86e83-118">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="86e83-119">Output</span><span class="sxs-lookup"><span data-stu-id="86e83-119">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="86e83-120">Proprietà indicizzate con più variabili di indice</span><span class="sxs-lookup"><span data-stu-id="86e83-120">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="86e83-121">Proprietà indicizzate possono avere più di una variabile di indice.</span><span class="sxs-lookup"><span data-stu-id="86e83-121">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="86e83-122">In tal caso, le variabili sono separate da virgole quando la proprietà viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="86e83-122">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="86e83-123">Il metodo set in tale proprietà deve avere due argomenti sottoposti a currying, il primo dei quali è una tupla contenente le chiavi e il secondo dei quali è il valore da impostare.</span><span class="sxs-lookup"><span data-stu-id="86e83-123">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="86e83-124">Il codice seguente viene illustrato l'utilizzo di una proprietà indicizzata con più variabili di indice.</span><span class="sxs-lookup"><span data-stu-id="86e83-124">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="86e83-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86e83-125">See Also</span></span>
[<span data-ttu-id="86e83-126">Membri</span><span class="sxs-lookup"><span data-stu-id="86e83-126">Members</span></span>](index.md)
