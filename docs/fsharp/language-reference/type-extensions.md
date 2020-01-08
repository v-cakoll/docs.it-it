---
title: Estensioni di tipo
description: Informazioni su F# come le estensioni di tipo consentono di aggiungere nuovi membri a un tipo di oggetto definito in precedenza.
ms.date: 11/04/2019
ms.openlocfilehash: 3e2c6971156bd562ed5d5428e6b7ffdc520c4cf5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341575"
---
# <a name="type-extensions"></a><span data-ttu-id="4a4ac-103">Estensioni di tipo</span><span class="sxs-lookup"><span data-stu-id="4a4ac-103">Type extensions</span></span>

<span data-ttu-id="4a4ac-104">Le estensioni di tipo (dette anche _potenziamenti_) sono una famiglia di funzionalità che consentono di aggiungere nuovi membri a un tipo di oggetto definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="4a4ac-105">Le tre funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-105">The three features are:</span></span>

- <span data-ttu-id="4a4ac-106">Estensioni di tipo intrinseco</span><span class="sxs-lookup"><span data-stu-id="4a4ac-106">Intrinsic type extensions</span></span>
- <span data-ttu-id="4a4ac-107">Estensioni di tipo facoltative</span><span class="sxs-lookup"><span data-stu-id="4a4ac-107">Optional type extensions</span></span>
- <span data-ttu-id="4a4ac-108">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="4a4ac-108">Extension methods</span></span>

<span data-ttu-id="4a4ac-109">Ognuno di essi può essere usato in scenari diversi e presenta compromessi diversi.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a4ac-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a4ac-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="4a4ac-111">Estensioni di tipo intrinseco</span><span class="sxs-lookup"><span data-stu-id="4a4ac-111">Intrinsic type extensions</span></span>

<span data-ttu-id="4a4ac-112">Un'estensione di tipo intrinseco è un'estensione del tipo che estende un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="4a4ac-113">Le estensioni di tipo intrinseco devono essere definite nello stesso file **e** nello stesso spazio dei nomi o modulo del tipo che stanno estendendo.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="4a4ac-114">Qualsiasi altra definizione comporterà l'esecuzione di [estensioni di tipo facoltative](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="4a4ac-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="4a4ac-115">Le estensioni di tipo intrinseco sono talvolta un modo più semplice per separare la funzionalità dalla dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="4a4ac-116">Nell'esempio seguente viene illustrato come definire un'estensione di tipo intrinseco:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="4a4ac-117">L'utilizzo di un'estensione di tipo consente di separare ognuno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-117">Using a type extension allows you to separate each of the following:</span></span>

- <span data-ttu-id="4a4ac-118">Dichiarazione di un tipo di `Variant`</span><span class="sxs-lookup"><span data-stu-id="4a4ac-118">The declaration of a `Variant` type</span></span>
- <span data-ttu-id="4a4ac-119">Funzionalità per la stampa della classe `Variant` in base alla relativa forma</span><span class="sxs-lookup"><span data-stu-id="4a4ac-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
- <span data-ttu-id="4a4ac-120">Un modo per accedere alla funzionalità di stampa con `.`-Notation di tipo oggetto</span><span class="sxs-lookup"><span data-stu-id="4a4ac-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="4a4ac-121">Si tratta di un'alternativa alla definizione di tutti gli elementi come membro in `Variant`.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="4a4ac-122">Sebbene non si tratta di un approccio intrinsecamente migliore, può trattarsi di una rappresentazione più pulita delle funzionalità in alcune situazioni.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="4a4ac-123">Le estensioni di tipo intrinseco vengono compilate come membri del tipo che aumentano e vengono visualizzate nel tipo quando il tipo viene esaminato mediante reflection.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="4a4ac-124">Estensioni di tipo facoltative</span><span class="sxs-lookup"><span data-stu-id="4a4ac-124">Optional type extensions</span></span>

<span data-ttu-id="4a4ac-125">Un'estensione di tipo facoltativa è un'estensione che viene visualizzata all'esterno del modulo, dello spazio dei nomi o dell'assembly originale del tipo esteso.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="4a4ac-126">Le estensioni di tipo facoltative sono utili per estendere un tipo non definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="4a4ac-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-127">For example:</span></span>

```fsharp
module Extensions

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for _ in 1 .. n -> x
        }
```

<span data-ttu-id="4a4ac-128">È ora possibile accedere `RepeatElements` come se fosse un membro di <xref:System.Collections.Generic.IEnumerable%601> purché il modulo `Extensions` venga aperto nell'ambito in cui si lavora.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="4a4ac-129">Le estensioni facoltative non vengono visualizzate nel tipo esteso quando vengono esaminate mediante reflection.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="4a4ac-130">Le estensioni facoltative devono trovarsi nei moduli e sono incluse nell'ambito solo quando il modulo che contiene l'estensione è aperto o è altrimenti nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="4a4ac-131">I membri di estensione facoltativi vengono compilati in membri statici per i quali l'istanza dell'oggetto viene passata in modo implicito come primo parametro.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="4a4ac-132">Tuttavia, agiscono come se fossero membri di istanza o membri statici in base al modo in cui sono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="4a4ac-133">Anche i membri di estensione facoltativi non C# sono visibili ai consumer o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-133">Optional extension members are also not visible to C# or Visual Basic consumers.</span></span> <span data-ttu-id="4a4ac-134">Possono essere utilizzati solo in altro F# codice.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="4a4ac-135">Limitazione generica di estensioni di tipo intrinseche e facoltative</span><span class="sxs-lookup"><span data-stu-id="4a4ac-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="4a4ac-136">È possibile dichiarare un'estensione di tipo in un tipo generico in cui la variabile di tipo è vincolata.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="4a4ac-137">Il requisito è che il vincolo della dichiarazione di estensione corrisponda al vincolo del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="4a4ac-138">Tuttavia, anche quando vengono confrontati vincoli tra un tipo dichiarato e un'estensione del tipo, è possibile che un vincolo venga dedotto dal corpo di un membro esteso che impone un requisito diverso per il parametro di tipo rispetto al tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="4a4ac-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="4a4ac-140">Non è possibile fare in modo che questo codice funzioni con un'estensione di tipo facoltativa:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-140">There is no way to get this code to work with an optional type extension:</span></span>

- <span data-ttu-id="4a4ac-141">Così come è, il membro `Sum` ha un vincolo diverso per `'T` (`static member get_Zero` e `static member (+)`) rispetto a quello definito dall'estensione del tipo.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
- <span data-ttu-id="4a4ac-142">La modifica dell'estensione di tipo in modo che abbia lo stesso vincolo di `Sum` non corrisponderà più al vincolo definito in `IEnumerable<'T>`.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
- <span data-ttu-id="4a4ac-143">Se si modifica `member this.Sum` in `member inline this.Sum` verrà fornito un errore che segnala la mancata corrispondenza tra i vincoli di tipo.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="4a4ac-144">Gli elementi desiderati sono metodi statici che "fluttuano nello spazio" e possono essere presentati come se estendono un tipo.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="4a4ac-145">Questa è la posizione in cui i metodi di estensione diventano necessari.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="4a4ac-146">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="4a4ac-146">Extension methods</span></span>

<span data-ttu-id="4a4ac-147">Infine, i metodi di estensione, dettiC# anche "membri di estensione di stile", F# possono essere dichiarati in come metodo membro statico in una classe.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="4a4ac-148">I metodi di estensione sono utili per i casi in cui si desidera definire le estensioni in un tipo generico che vincola la variabile di tipo.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="4a4ac-149">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="4a4ac-150">Quando viene usato, questo codice lo farà apparire come se `Sum` fosse definito in <xref:System.Collections.Generic.IEnumerable%601>, purché `Extensions` sia stato aperto o si trovi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="4a4ac-151">Altre osservazioni</span><span class="sxs-lookup"><span data-stu-id="4a4ac-151">Other remarks</span></span>

<span data-ttu-id="4a4ac-152">Le estensioni del tipo hanno anche gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-152">Type extensions also have the following attributes:</span></span>

- <span data-ttu-id="4a4ac-153">Tutti i tipi a cui è possibile accedere possono essere estesi.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-153">Any type that can be accessed can be extended.</span></span>
- <span data-ttu-id="4a4ac-154">Le estensioni di tipo intrinseco e facoltativo possono definire _qualsiasi_ tipo di membro, non solo metodi.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-154">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="4a4ac-155">È possibile, ad esempio, anche le proprietà di estensione.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-155">So extension properties are also possible, for example.</span></span>
- <span data-ttu-id="4a4ac-156">Il token `self-identifier` nella [sintassi](type-extensions.md#syntax) rappresenta l'istanza del tipo richiamato, esattamente come i membri normali.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-156">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
- <span data-ttu-id="4a4ac-157">I membri estesi possono essere membri statici o di istanza.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-157">Extended members can be static or instance members.</span></span>
- <span data-ttu-id="4a4ac-158">Le variabili di tipo in un'estensione del tipo devono corrispondere ai vincoli del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-158">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="4a4ac-159">Per le estensioni di tipo esistono anche le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a4ac-159">The following limitations also exist for type extensions:</span></span>

- <span data-ttu-id="4a4ac-160">Le estensioni di tipo non supportano metodi virtuali o astratti.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-160">Type extensions do not support virtual or abstract methods.</span></span>
- <span data-ttu-id="4a4ac-161">Le estensioni di tipo non supportano i metodi di override come aumenti.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-161">Type extensions do not support override methods as augmentations.</span></span>
- <span data-ttu-id="4a4ac-162">Le estensioni di tipo non supportano i [parametri di tipo risolti staticamente](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4a4ac-162">Type extensions do not support [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>
- <span data-ttu-id="4a4ac-163">Le estensioni di tipo facoltative non supportano i costruttori come aumenti.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-163">Optional Type extensions do not support constructors as augmentations.</span></span>
- <span data-ttu-id="4a4ac-164">Non è possibile definire le estensioni di tipo per le [abbreviazioni di tipo](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="4a4ac-164">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
- <span data-ttu-id="4a4ac-165">Le estensioni di tipo non sono valide per `byref<'T>` (anche se possono essere dichiarate).</span><span class="sxs-lookup"><span data-stu-id="4a4ac-165">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
- <span data-ttu-id="4a4ac-166">Le estensioni di tipo non sono valide per gli attributi (anche se possono essere dichiarate).</span><span class="sxs-lookup"><span data-stu-id="4a4ac-166">Type extensions are not valid for attributes (though they can be declared).</span></span>
- <span data-ttu-id="4a4ac-167">È possibile definire estensioni che sovraccaricano altri metodi con lo stesso nome, ma F# il compilatore fornisce la preferenza a metodi non di estensione se è presente una chiamata ambigua.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-167">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="4a4ac-168">Infine, se esistono più estensioni di tipo intrinseco per un tipo, tutti i membri devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-168">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="4a4ac-169">Per le estensioni di tipo facoltative, i membri di diverse estensioni di tipo dello stesso tipo possono avere gli stessi nomi.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-169">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="4a4ac-170">Gli errori di ambiguità si verificano solo se il codice client apre due ambiti diversi che definiscono gli stessi nomi dei membri.</span><span class="sxs-lookup"><span data-stu-id="4a4ac-170">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a4ac-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a4ac-171">See also</span></span>

- [<span data-ttu-id="4a4ac-172">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="4a4ac-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4a4ac-173">Membri</span><span class="sxs-lookup"><span data-stu-id="4a4ac-173">Members</span></span>](./members/index.md)
