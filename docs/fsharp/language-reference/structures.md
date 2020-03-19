---
title: Strutture
description: Informazioni sulla struttura F , un tipo di oggetto compatto spesso più efficiente di una classe per i tipi con una piccola quantità di dati e un comportamento semplice.
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400281"
---
# <a name="structures"></a><span data-ttu-id="4538f-103">Strutture</span><span class="sxs-lookup"><span data-stu-id="4538f-103">Structures</span></span>

<span data-ttu-id="4538f-104">Una *struttura* è un tipo di oggetto compatto che può essere più efficiente di una classe per i tipi che dispongono di una piccola quantità di dati e di un comportamento semplice.</span><span class="sxs-lookup"><span data-stu-id="4538f-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="4538f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4538f-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="4538f-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4538f-106">Remarks</span></span>

<span data-ttu-id="4538f-107">Le strutture sono *tipi di valore*, ovvero vengono archiviate direttamente nello stack o, quando vengono utilizzate come campi o elementi della matrice, inline nel tipo padre.</span><span class="sxs-lookup"><span data-stu-id="4538f-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="4538f-108">A differenza di record e classi, le strutture hanno una semantica pass-by-value.</span><span class="sxs-lookup"><span data-stu-id="4538f-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="4538f-109">Ciò significa che sono utili principalmente per piccole aggregazioni di dati accessibili e copiati di frequente.</span><span class="sxs-lookup"><span data-stu-id="4538f-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="4538f-110">Nella sintassi precedente sono illustrate due forme.</span><span class="sxs-lookup"><span data-stu-id="4538f-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="4538f-111">La prima non è la sintassi leggera, ma viene comunque usata frequentemente perché, quando si usano la parole chiave  e , è possibile omettere l'attributo , che viene visualizzato nella seconda forma.</span><span class="sxs-lookup"><span data-stu-id="4538f-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="4538f-112">È possibile abbreviare `StructAttribute` in `Struct`.</span><span class="sxs-lookup"><span data-stu-id="4538f-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="4538f-113">Il *type-definition-elements-and-members* nella sintassi precedente rappresenta le dichiarazioni e le definizioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="4538f-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="4538f-114">Le strutture possono disporre di costruttori e campi modificabili e non modificabili e possono dichiarare i membri e le implementazioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4538f-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="4538f-115">Per ulteriori informazioni, vedere [Membri](./members/index.md).</span><span class="sxs-lookup"><span data-stu-id="4538f-115">For more information, see [Members](./members/index.md).</span></span>

<span data-ttu-id="4538f-116">Le strutture non possono partecipare all'ereditarietà, non possono contenere associazioni `let` o `do` e non possono contenere in modo ricorsivo campi del proprio tipo (nonostante possano contenere celle di riferimento che facciano riferimento al proprio tipo).</span><span class="sxs-lookup"><span data-stu-id="4538f-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="4538f-117">Poiché le strutture non consentono associazioni `let`, è necessario dichiarare i campi nelle strutture usando la parola chiave `val`.</span><span class="sxs-lookup"><span data-stu-id="4538f-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="4538f-118">La parola chiave `val` definisce un campo e il relativo tipo, ma non consente l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="4538f-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="4538f-119">Al contrario, le dichiarazioni `val` sono inizializzate su zero o null.</span><span class="sxs-lookup"><span data-stu-id="4538f-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="4538f-120">Per questo motivo, le strutture che hanno un costruttore implicito (ovvero, i parametri forniti immediatamente dopo il nome della struttura nella dichiarazione) richiedono di annotare le dichiarazioni `val` con l'attributo `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="4538f-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="4538f-121">Le strutture che hanno un costruttore definito supportano comunque l'inizializzazione su zero.</span><span class="sxs-lookup"><span data-stu-id="4538f-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="4538f-122">Quindi, l'attributo `DefaultValue` è una dichiarazione che tale valore zero è valido per il campo.</span><span class="sxs-lookup"><span data-stu-id="4538f-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="4538f-123">I costruttori impliciti per le strutture non eseguono alcuna azione perché le associazioni `let` e `do` non sono consentite per il tipo, ma i valori di parametro di costruttore implicito passati sono disponibili come campi privati.</span><span class="sxs-lookup"><span data-stu-id="4538f-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="4538f-124">I costruttori espliciti potrebbero comportare l'inizializzazione dei valori di campo.</span><span class="sxs-lookup"><span data-stu-id="4538f-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="4538f-125">Quando si ha una struttura con un costruttore esplicito, è comunque supportata l'inizializzazione su zero. Tuttavia, non usare l'attributo `DefaultValue` sulle dichiarazioni `val` perché è in conflitto con il costruttore esplicito.</span><span class="sxs-lookup"><span data-stu-id="4538f-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="4538f-126">Per ulteriori `val` informazioni sulle dichiarazioni, vedere [Campi espliciti: `val` parola chiave](./members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="4538f-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="4538f-127">Gli attributi e modificatori di accessibilità sono consentiti nelle strutture e seguono le stesse regole per gli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="4538f-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="4538f-128">Per ulteriori informazioni, vedere [Attributi](attributes.md) e [controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="4538f-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="4538f-129">Gli esempi di codice seguenti illustrano le definizioni delle strutture.</span><span class="sxs-lookup"><span data-stu-id="4538f-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="4538f-130">Struct ByRefLike</span><span class="sxs-lookup"><span data-stu-id="4538f-130">ByRefLike structs</span></span>

<span data-ttu-id="4538f-131">È possibile definire struct personalizzati che `byref`possono aderire alla semantica simile: vedere [Byrefs](byrefs.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="4538f-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="4538f-132">Questa operazione viene <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> eseguita con l'attributo:</span><span class="sxs-lookup"><span data-stu-id="4538f-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="4538f-133">`IsByRefLike`non implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="4538f-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="4538f-134">Entrambi devono essere presenti nel tipo.</span><span class="sxs-lookup"><span data-stu-id="4538f-134">Both must be present on the type.</span></span>

<span data-ttu-id="4538f-135">Uno`byref`struct "-like" in F è un tipo di valore associato allo stack.</span><span class="sxs-lookup"><span data-stu-id="4538f-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="4538f-136">Non viene mai allocato nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="4538f-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="4538f-137">Un `byref`-like struct è utile per la programmazione ad alte prestazioni, in quanto viene applicato con set di controlli sicuri sulla durata e non acquisizione.</span><span class="sxs-lookup"><span data-stu-id="4538f-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="4538f-138">Le regole sono:</span><span class="sxs-lookup"><span data-stu-id="4538f-138">The rules are:</span></span>

- <span data-ttu-id="4538f-139">Possono essere utilizzati come parametri di funzione, parametri di metodo, variabili locali, restituisce il metodo.</span><span class="sxs-lookup"><span data-stu-id="4538f-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
- <span data-ttu-id="4538f-140">Non possono essere membri statici o di istanza di una classe o di uno struct normale.</span><span class="sxs-lookup"><span data-stu-id="4538f-140">They cannot be static or instance members of a class or normal struct.</span></span>
- <span data-ttu-id="4538f-141">Non possono essere acquisiti`async` da alcun costrutto di chiusura (metodi o espressioni lambda).</span><span class="sxs-lookup"><span data-stu-id="4538f-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
- <span data-ttu-id="4538f-142">Non possono essere utilizzati come parametro generico.</span><span class="sxs-lookup"><span data-stu-id="4538f-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="4538f-143">Anche se queste regole limitano fortemente l'utilizzo, lo fanno per soddisfare la promessa di calcolo ad alte prestazioni in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="4538f-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="4538f-144">Strutture ReadOnly</span><span class="sxs-lookup"><span data-stu-id="4538f-144">ReadOnly structs</span></span>

<span data-ttu-id="4538f-145">È possibile annotare <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> gli struct con l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4538f-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="4538f-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4538f-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="4538f-147">`IsReadOnly`non implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="4538f-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="4538f-148">È necessario aggiungere entrambi `IsReadOnly` per avere uno struct.</span><span class="sxs-lookup"><span data-stu-id="4538f-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="4538f-149">L'utilizzo di questo attributo genera metadati che `inref<'T>` consentono `in ref`a F e C' di considerarlo rispettivamente come e , in modo da essere in grado di considerarlo come e , in modo cogiurio .</span><span class="sxs-lookup"><span data-stu-id="4538f-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="4538f-150">La definizione di un valore modificabile all'interno di uno struct readonly genera un errore.</span><span class="sxs-lookup"><span data-stu-id="4538f-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="4538f-151">Record struct e unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="4538f-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="4538f-152">È possibile rappresentare [i record](records.md) e le [unioni discriminate](discriminated-unions.md) come struct con l'attributo `[<Struct>]` .</span><span class="sxs-lookup"><span data-stu-id="4538f-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="4538f-153">Per ulteriori informazioni, consulta ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="4538f-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="4538f-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4538f-154">See also</span></span>

- [<span data-ttu-id="4538f-155">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="4538f-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4538f-156">Classi</span><span class="sxs-lookup"><span data-stu-id="4538f-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="4538f-157">Record</span><span class="sxs-lookup"><span data-stu-id="4538f-157">Records</span></span>](records.md)
- [<span data-ttu-id="4538f-158">Membri</span><span class="sxs-lookup"><span data-stu-id="4538f-158">Members</span></span>](./members/index.md)
