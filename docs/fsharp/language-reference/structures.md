---
title: Strutture (F#)
description: "Informazioni su F # struttura, un tipo di oggetto compatto spesso più efficiente rispetto a una classe per i tipi con una piccola quantità di dati e comportamento semplice."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a><span data-ttu-id="0c828-104">Strutture</span><span class="sxs-lookup"><span data-stu-id="0c828-104">Structures</span></span>

<span data-ttu-id="0c828-105">Oggetto *struttura* è un tipo di oggetto compatto che può essere più efficiente rispetto a una classe per tipi che dispongono di una piccola quantità di dati e comportamento semplice.</span><span class="sxs-lookup"><span data-stu-id="0c828-105">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c828-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c828-106">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a><span data-ttu-id="0c828-107">Note</span><span class="sxs-lookup"><span data-stu-id="0c828-107">Remarks</span></span>
<span data-ttu-id="0c828-108">Le strutture sono *i tipi di valore*, il che significa che sono archiviati direttamente sullo stack o, quando vengono utilizzati come campi o tipo di elementi di matrice, inline nell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="0c828-108">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="0c828-109">A differenza di record e classi, le strutture hanno una semantica pass-by-value.</span><span class="sxs-lookup"><span data-stu-id="0c828-109">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="0c828-110">Ciò significa che sono utili principalmente per piccole aggregazioni di dati accessibili e copiati di frequente.</span><span class="sxs-lookup"><span data-stu-id="0c828-110">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="0c828-111">Nella sintassi precedente sono illustrate due forme.</span><span class="sxs-lookup"><span data-stu-id="0c828-111">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="0c828-112">La prima non è la sintassi leggera, ma viene comunque usata frequentemente perché, quando si usano la parole chiave `struct` e `end`, è possibile omettere l'attributo `StructAttribute`, che viene visualizzato nella seconda forma.</span><span class="sxs-lookup"><span data-stu-id="0c828-112">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="0c828-113">È possibile abbreviare `StructAttribute` in `Struct`.</span><span class="sxs-lookup"><span data-stu-id="0c828-113">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="0c828-114">Il *gli elementi di definizione del tipo* nella sintassi precedente rappresenta definizioni e dichiarazioni di membri.</span><span class="sxs-lookup"><span data-stu-id="0c828-114">The *type-definition-elements* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="0c828-115">Le strutture possono disporre di costruttori e campi modificabili e non modificabili e possono dichiarare i membri e le implementazioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0c828-115">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="0c828-116">Per ulteriori informazioni, vedere [membri](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c828-116">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="0c828-117">Le strutture non possono partecipare all'ereditarietà, non possono contenere associazioni `let` o `do` e non possono contenere in modo ricorsivo campi del proprio tipo (nonostante possano contenere celle di riferimento che facciano riferimento al proprio tipo).</span><span class="sxs-lookup"><span data-stu-id="0c828-117">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="0c828-118">Poiché le strutture non consentono associazioni `let`, è necessario dichiarare i campi nelle strutture usando la parola chiave `val`.</span><span class="sxs-lookup"><span data-stu-id="0c828-118">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="0c828-119">La parola chiave `val` definisce un campo e il relativo tipo, ma non consente l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="0c828-119">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="0c828-120">Al contrario, le dichiarazioni `val` sono inizializzate su zero o null.</span><span class="sxs-lookup"><span data-stu-id="0c828-120">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="0c828-121">Per questo motivo, le strutture che hanno un costruttore implicito (ovvero, i parametri forniti immediatamente dopo il nome della struttura nella dichiarazione) richiedono di annotare le dichiarazioni `val` con l'attributo `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="0c828-121">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="0c828-122">Le strutture che hanno un costruttore definito supportano comunque l'inizializzazione su zero.</span><span class="sxs-lookup"><span data-stu-id="0c828-122">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="0c828-123">Quindi, l'attributo `DefaultValue` è una dichiarazione che tale valore zero è valido per il campo.</span><span class="sxs-lookup"><span data-stu-id="0c828-123">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="0c828-124">I costruttori impliciti per le strutture non eseguono alcuna azione perché le associazioni `let` e `do` non sono consentite per il tipo, ma i valori di parametro di costruttore implicito passati sono disponibili come campi privati.</span><span class="sxs-lookup"><span data-stu-id="0c828-124">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="0c828-125">I costruttori espliciti potrebbero comportare l'inizializzazione dei valori di campo.</span><span class="sxs-lookup"><span data-stu-id="0c828-125">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="0c828-126">Quando si ha una struttura con un costruttore esplicito, è comunque supportata l'inizializzazione su zero. Tuttavia, non usare l'attributo `DefaultValue` sulle dichiarazioni `val` perché è in conflitto con il costruttore esplicito.</span><span class="sxs-lookup"><span data-stu-id="0c828-126">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="0c828-127">Per ulteriori informazioni su `val` dichiarazioni, vedere [campi espliciti: il `val` parola chiave](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="0c828-127">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="0c828-128">Gli attributi e modificatori di accessibilità sono consentiti nelle strutture e seguono le stesse regole per gli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="0c828-128">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="0c828-129">Per ulteriori informazioni, vedere [attributi](attributes.md) e [controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="0c828-129">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="0c828-130">Gli esempi di codice seguenti illustrano le definizioni delle strutture.</span><span class="sxs-lookup"><span data-stu-id="0c828-130">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="0c828-131">I record di struct e unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="0c828-131">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="0c828-132">A partire da F # 4.1, è possibile rappresentare [record](records.md) e [unioni discriminate](discriminated-unions.md) come struct con il `[<Struct>]` attributo.</span><span class="sxs-lookup"><span data-stu-id="0c828-132">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="0c828-133">Ogni articolo per altre informazioni, vedere.</span><span class="sxs-lookup"><span data-stu-id="0c828-133">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0c828-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c828-134">See Also</span></span>
[<span data-ttu-id="0c828-135">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="0c828-135">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="0c828-136">Classi</span><span class="sxs-lookup"><span data-stu-id="0c828-136">Classes</span></span>](classes.md)

[<span data-ttu-id="0c828-137">Record</span><span class="sxs-lookup"><span data-stu-id="0c828-137">Records</span></span>](records.md)

[<span data-ttu-id="0c828-138">Membri</span><span class="sxs-lookup"><span data-stu-id="0c828-138">Members</span></span>](members/index.md)
