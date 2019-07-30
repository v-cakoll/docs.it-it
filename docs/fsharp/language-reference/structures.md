---
title: Strutture
description: Informazioni sulla F# struttura, un tipo di oggetto compatto spesso più efficiente rispetto a una classe per i tipi con una piccola quantità di dati e un comportamento semplice.
ms.date: 05/16/2016
ms.openlocfilehash: e638b450fe43e0993c9980cade246c3f26d25e2d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630768"
---
# <a name="structures"></a><span data-ttu-id="7ec67-103">Strutture</span><span class="sxs-lookup"><span data-stu-id="7ec67-103">Structures</span></span>

<span data-ttu-id="7ec67-104">Una *struttura* è un tipo di oggetto compatto che può essere più efficiente rispetto a una classe per i tipi con una piccola quantità di dati e un comportamento semplice.</span><span class="sxs-lookup"><span data-stu-id="7ec67-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ec67-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ec67-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="7ec67-106">Note</span><span class="sxs-lookup"><span data-stu-id="7ec67-106">Remarks</span></span>

<span data-ttu-id="7ec67-107">Le strutture sono *tipi di valore*, il che significa che vengono archiviate direttamente nello stack o, quando vengono usate come campi o elementi di matrice, inline nel tipo padre.</span><span class="sxs-lookup"><span data-stu-id="7ec67-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="7ec67-108">A differenza di record e classi, le strutture hanno una semantica pass-by-value.</span><span class="sxs-lookup"><span data-stu-id="7ec67-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="7ec67-109">Ciò significa che sono utili principalmente per piccole aggregazioni di dati accessibili e copiati di frequente.</span><span class="sxs-lookup"><span data-stu-id="7ec67-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="7ec67-110">Nella sintassi precedente sono illustrate due forme.</span><span class="sxs-lookup"><span data-stu-id="7ec67-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="7ec67-111">La prima non è la sintassi leggera, ma viene comunque usata frequentemente perché, quando si usano la parole chiave `struct` e `end`, è possibile omettere l'attributo `StructAttribute`, che viene visualizzato nella seconda forma.</span><span class="sxs-lookup"><span data-stu-id="7ec67-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="7ec67-112">È possibile abbreviare `StructAttribute` in `Struct`.</span><span class="sxs-lookup"><span data-stu-id="7ec67-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="7ec67-113">Il *tipo-definizione-elementi-e-membri* nella sintassi precedente rappresenta le dichiarazioni e le definizioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="7ec67-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="7ec67-114">Le strutture possono disporre di costruttori e campi modificabili e non modificabili e possono dichiarare i membri e le implementazioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7ec67-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="7ec67-115">Per ulteriori informazioni, vedere [membri](./members/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ec67-115">For more information, see [Members](./members/index.md).</span></span>

<span data-ttu-id="7ec67-116">Le strutture non possono partecipare all'ereditarietà, non possono contenere associazioni `let` o `do` e non possono contenere in modo ricorsivo campi del proprio tipo (nonostante possano contenere celle di riferimento che facciano riferimento al proprio tipo).</span><span class="sxs-lookup"><span data-stu-id="7ec67-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="7ec67-117">Poiché le strutture non consentono associazioni `let`, è necessario dichiarare i campi nelle strutture usando la parola chiave `val`.</span><span class="sxs-lookup"><span data-stu-id="7ec67-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="7ec67-118">La parola chiave `val` definisce un campo e il relativo tipo, ma non consente l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="7ec67-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="7ec67-119">Al contrario, le dichiarazioni `val` sono inizializzate su zero o null.</span><span class="sxs-lookup"><span data-stu-id="7ec67-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="7ec67-120">Per questo motivo, le strutture che hanno un costruttore implicito (ovvero, i parametri forniti immediatamente dopo il nome della struttura nella dichiarazione) richiedono di annotare le dichiarazioni `val` con l'attributo `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="7ec67-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="7ec67-121">Le strutture che hanno un costruttore definito supportano comunque l'inizializzazione su zero.</span><span class="sxs-lookup"><span data-stu-id="7ec67-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="7ec67-122">Quindi, l'attributo `DefaultValue` è una dichiarazione che tale valore zero è valido per il campo.</span><span class="sxs-lookup"><span data-stu-id="7ec67-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="7ec67-123">I costruttori impliciti per le strutture non eseguono alcuna azione perché le associazioni `let` e `do` non sono consentite per il tipo, ma i valori di parametro di costruttore implicito passati sono disponibili come campi privati.</span><span class="sxs-lookup"><span data-stu-id="7ec67-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="7ec67-124">I costruttori espliciti potrebbero comportare l'inizializzazione dei valori di campo.</span><span class="sxs-lookup"><span data-stu-id="7ec67-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="7ec67-125">Quando si ha una struttura con un costruttore esplicito, è comunque supportata l'inizializzazione su zero. Tuttavia, non usare l'attributo `DefaultValue` sulle dichiarazioni `val` perché è in conflitto con il costruttore esplicito.</span><span class="sxs-lookup"><span data-stu-id="7ec67-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="7ec67-126">Per ulteriori informazioni sulle `val` dichiarazioni, vedere [campi espliciti: `val` Parola chiave](./members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="7ec67-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="7ec67-127">Gli attributi e modificatori di accessibilità sono consentiti nelle strutture e seguono le stesse regole per gli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="7ec67-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="7ec67-128">Per altre informazioni, vedere [attributi](attributes.md) e [controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="7ec67-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="7ec67-129">Gli esempi di codice seguenti illustrano le definizioni delle strutture.</span><span class="sxs-lookup"><span data-stu-id="7ec67-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="7ec67-130">Struct ByRefLike</span><span class="sxs-lookup"><span data-stu-id="7ec67-130">ByRefLike structs</span></span>

<span data-ttu-id="7ec67-131">È possibile definire struct personalizzati che possono essere conformi alla `byref`semantica di tipo: vedere [ByRef](byrefs.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="7ec67-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="7ec67-132">Questa operazione viene eseguita con <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> l'attributo:</span><span class="sxs-lookup"><span data-stu-id="7ec67-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="7ec67-133">`IsByRefLike`non implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="7ec67-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="7ec67-134">Entrambi devono essere presenti nel tipo.</span><span class="sxs-lookup"><span data-stu-id="7ec67-134">Both must be present on the type.</span></span>

<span data-ttu-id="7ec67-135">Uno struct`byref`"-like" in F# è un tipo di valore associato allo stack.</span><span class="sxs-lookup"><span data-stu-id="7ec67-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="7ec67-136">Non viene mai allocato nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="7ec67-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="7ec67-137">Uno `byref`struct simile è utile per la programmazione a prestazioni elevate, in quanto viene applicato con un set di controlli sicuri sulla durata e non sull'acquisizione.</span><span class="sxs-lookup"><span data-stu-id="7ec67-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="7ec67-138">Le regole sono:</span><span class="sxs-lookup"><span data-stu-id="7ec67-138">The rules are:</span></span>

* <span data-ttu-id="7ec67-139">Possono essere usati come parametri di funzione, parametri di metodo, variabili locali, restituzione di metodi.</span><span class="sxs-lookup"><span data-stu-id="7ec67-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="7ec67-140">Non possono essere membri statici o di istanza di una classe o di uno struct normale.</span><span class="sxs-lookup"><span data-stu-id="7ec67-140">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="7ec67-141">Non possono essere acquisiti da alcun costrutto di`async` chiusura (metodi o espressioni lambda).</span><span class="sxs-lookup"><span data-stu-id="7ec67-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="7ec67-142">Non possono essere usati come parametro generico.</span><span class="sxs-lookup"><span data-stu-id="7ec67-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="7ec67-143">Sebbene queste regole limitino molto fortemente l'utilizzo, lo fanno per soddisfare la promessa di un calcolo ad alte prestazioni in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="7ec67-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="7ec67-144">Struct di sola lettura</span><span class="sxs-lookup"><span data-stu-id="7ec67-144">ReadOnly structs</span></span>

<span data-ttu-id="7ec67-145">È possibile annotare gli struct con <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> l'attributo.</span><span class="sxs-lookup"><span data-stu-id="7ec67-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="7ec67-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7ec67-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="7ec67-147">`IsReadOnly`non implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="7ec67-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="7ec67-148">È necessario aggiungere entrambi per avere uno `IsReadOnly` struct.</span><span class="sxs-lookup"><span data-stu-id="7ec67-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="7ec67-149">L'utilizzo di questo attributo genera i F# metadati C# che lasciano e sanno trattare `inref<'T>` come `in ref`e, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="7ec67-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="7ec67-150">La definizione di un valore modificabile all'interno di uno struct di sola lettura genera un errore.</span><span class="sxs-lookup"><span data-stu-id="7ec67-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="7ec67-151">Record struct e unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="7ec67-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="7ec67-152">È possibile rappresentare i [record](records.md) e le [unioni discriminate](discriminated-unions.md) come struct con `[<Struct>]` l'attributo.</span><span class="sxs-lookup"><span data-stu-id="7ec67-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="7ec67-153">Per altre informazioni, vedere ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="7ec67-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ec67-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ec67-154">See also</span></span>

- [<span data-ttu-id="7ec67-155">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="7ec67-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7ec67-156">Classi</span><span class="sxs-lookup"><span data-stu-id="7ec67-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="7ec67-157">Record</span><span class="sxs-lookup"><span data-stu-id="7ec67-157">Records</span></span>](records.md)
- [<span data-ttu-id="7ec67-158">Membri</span><span class="sxs-lookup"><span data-stu-id="7ec67-158">Members</span></span>](./members/index.md)
