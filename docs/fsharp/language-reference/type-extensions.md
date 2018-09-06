---
title: Estensioni di tipo (F#)
description: 'Informazioni su come le estensioni di tipo F # consentono che aggiungere nuovi membri a un tipo di oggetto definito in precedenza.'
ms.date: 07/20/2018
ms.openlocfilehash: 27238db1fd0803f62c32755fbc4ab7688f5c107e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855061"
---
# <a name="type-extensions"></a><span data-ttu-id="538b7-103">Estensioni di tipo</span><span class="sxs-lookup"><span data-stu-id="538b7-103">Type extensions</span></span>

<span data-ttu-id="538b7-104">Estensioni di tipo (chiamato anche _aumenti_) è una famiglia di funzionalità che consentono di aggiungere nuovi membri a un tipo di oggetto definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="538b7-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="538b7-105">Le tre funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="538b7-105">The three features are:</span></span>

* <span data-ttu-id="538b7-106">Estensioni di tipo intrinseco</span><span class="sxs-lookup"><span data-stu-id="538b7-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="538b7-107">Estensioni di tipo facoltativa</span><span class="sxs-lookup"><span data-stu-id="538b7-107">Optional type extensions</span></span>
* <span data-ttu-id="538b7-108">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="538b7-108">Extension methods</span></span>

<span data-ttu-id="538b7-109">Ognuno può essere usato in diversi scenari e si comporta alcuni compromessi.</span><span class="sxs-lookup"><span data-stu-id="538b7-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="538b7-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="538b7-110">Syntax</span></span>

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

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="538b7-111">Estensioni di tipo intrinseco</span><span class="sxs-lookup"><span data-stu-id="538b7-111">Intrinsic type extensions</span></span>

<span data-ttu-id="538b7-112">Un'estensione di tipo intrinseco è un'estensione del tipo che estende un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="538b7-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="538b7-113">Estensioni di tipo intrinseche devono essere definite nello stesso file **e** nello stesso spazio dei nomi o modulo come tipo di cui sta estendendo.</span><span class="sxs-lookup"><span data-stu-id="538b7-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="538b7-114">Qualsiasi altra definizione comporterà li in corso [estensioni di tipo facoltativa](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="538b7-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="538b7-115">Le estensioni di tipo intrinseco in alcuni casi sono un modo più semplice per separare la funzionalità dalla dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="538b7-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="538b7-116">Nell'esempio seguente viene illustrato come definire un'estensione di tipo intrinseco:</span><span class="sxs-lookup"><span data-stu-id="538b7-116">The following example shows how to define an intrinsic type extension:</span></span>

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

<span data-ttu-id="538b7-117">Usando un'estensione di tipo consente di separare gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="538b7-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="538b7-118">La dichiarazione di un `Variant` tipo</span><span class="sxs-lookup"><span data-stu-id="538b7-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="538b7-119">La funzionalità per stampare il `Variant` classe in base alla "forma"</span><span class="sxs-lookup"><span data-stu-id="538b7-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="538b7-120">Un modo per accedere alla funzionalità di stampa con oggetto stile `.`-notation</span><span class="sxs-lookup"><span data-stu-id="538b7-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="538b7-121">Si tratta di un'alternativa per la definizione del tutto come membro del `Variant`.</span><span class="sxs-lookup"><span data-stu-id="538b7-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="538b7-122">Sebbene non sia un approccio migliore per sua natura, può essere una rappresentazione più chiara delle funzionalità in alcune situazioni.</span><span class="sxs-lookup"><span data-stu-id="538b7-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="538b7-123">Estensioni di tipo intrinseche vengono compilate come membri del tipo di potenziare e vengono visualizzati sul tipo quando il tipo viene esaminato tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="538b7-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="538b7-124">Estensioni di tipo facoltativa</span><span class="sxs-lookup"><span data-stu-id="538b7-124">Optional type extensions</span></span>

<span data-ttu-id="538b7-125">Un'estensione facoltativa di tipo è un'estensione che viene visualizzato di fuori di modulo originale, lo spazio dei nomi o assembly del tipo esteso.</span><span class="sxs-lookup"><span data-stu-id="538b7-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="538b7-126">Le estensioni di tipo facoltativo sono utili per estendere un tipo che non è stato definito manualmente.</span><span class="sxs-lookup"><span data-stu-id="538b7-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="538b7-127">Esempio:</span><span class="sxs-lookup"><span data-stu-id="538b7-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="538b7-128">È ora possibile accedere `RepeatElements` come se fosse un membro del <xref:System.Collections.Generic.IEnumerable%601> purché il `Extensions` modulo viene aperto nell'ambito che si lavora in.</span><span class="sxs-lookup"><span data-stu-id="538b7-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="538b7-129">Le estensioni facoltative non vengono visualizzati sul tipo esteso quando esaminato tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="538b7-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="538b7-130">Le estensioni facoltative devono trovarsi nei moduli e risultano nell'ambito solo quando il modulo che contiene l'estensione è aperto o in caso contrario, si trova nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="538b7-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="538b7-131">I membri di estensione facoltative vengono compilati in membri statici per il quale l'istanza dell'oggetto viene passata in modo implicito come primo parametro.</span><span class="sxs-lookup"><span data-stu-id="538b7-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="538b7-132">Tuttavia, agiscono come se fossero membri di istanza o membri statici in base al modo in cui sono dichiarate.</span><span class="sxs-lookup"><span data-stu-id="538b7-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="538b7-133">Limitazione generica di estensioni di tipo intrinseche e facoltativi</span><span class="sxs-lookup"><span data-stu-id="538b7-133">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="538b7-134">È possibile dichiarare un'estensione del tipo per un tipo generico in cui la variabile di tipo è vincolata.</span><span class="sxs-lookup"><span data-stu-id="538b7-134">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="538b7-135">Il requisito è che il vincolo della dichiarazione di estensione corrisponde al vincolo del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="538b7-135">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="538b7-136">Tuttavia, anche quando i vincoli vi siano corrispondenza tra un tipo dichiarato e un'estensione del tipo, è possibile che un vincolo possa essere dedotto dal corpo di un membro di tipo esteso che impone un requisito diverso per il parametro di tipo rispetto al tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="538b7-136">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="538b7-137">Esempio:</span><span class="sxs-lookup"><span data-stu-id="538b7-137">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="538b7-138">Non è possibile ottenere il codice deve funzionare con un'estensione di tipo facoltativa:</span><span class="sxs-lookup"><span data-stu-id="538b7-138">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="538b7-139">Come è, il `Sum` membro presenta un vincolo diverso in `'T` (`static member get_Zero` e `static member (+)`) rispetto a ciò che definisce l'estensione del tipo.</span><span class="sxs-lookup"><span data-stu-id="538b7-139">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="538b7-140">Modifica l'estensione del tipo con lo stesso vincolo come `Sum` non corrisponderanno più il vincolo definito in `IEnumerable<'T>`.</span><span class="sxs-lookup"><span data-stu-id="538b7-140">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="538b7-141">Apportare la modifica di membro da `member inline Sum` genererà un errore che i vincoli di tipo non corrispondono</span><span class="sxs-lookup"><span data-stu-id="538b7-141">Making changing the member to `member inline Sum` will give an error that type constraints are mismatched</span></span>

<span data-ttu-id="538b7-142">L'opzione desiderata sono metodi statici che "float nello spazio" e possono essere presentati come se si sta estendendo un tipo.</span><span class="sxs-lookup"><span data-stu-id="538b7-142">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="538b7-143">Si tratta in cui diventano necessari metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="538b7-143">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="538b7-144">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="538b7-144">Extension methods</span></span>

<span data-ttu-id="538b7-145">Infine, i metodi di estensione (talvolta denominati "c# stile i membri di estensione") possono essere dichiarati in F # come metodo di membro statico in una classe.</span><span class="sxs-lookup"><span data-stu-id="538b7-145">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="538b7-146">I metodi di estensione sono utili per quando si desidera definire le estensioni in un tipo generico che impostano la variabile di tipo.</span><span class="sxs-lookup"><span data-stu-id="538b7-146">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="538b7-147">Esempio:</span><span class="sxs-lookup"><span data-stu-id="538b7-147">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="538b7-148">Quando usato, questo codice verrà far sembrare come se `Sum` definito nel <xref:System.Collections.Generic.IEnumerable%601>, purché `Extensions` è stata aperta o si trova nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="538b7-148">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="538b7-149">Altre note</span><span class="sxs-lookup"><span data-stu-id="538b7-149">Other remarks</span></span>

<span data-ttu-id="538b7-150">Le estensioni di tipo hanno anche gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="538b7-150">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="538b7-151">È possibile estendere qualsiasi tipo di cui è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="538b7-151">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="538b7-152">Possono definire le estensioni di tipo intrinseche e facoltativi _qualsiasi_ tipo di membro, non solo i metodi.</span><span class="sxs-lookup"><span data-stu-id="538b7-152">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="538b7-153">Pertanto, le proprietà di estensione sono anche possibili, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="538b7-153">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="538b7-154">Il `self-identifier` token nel [sintassi](type-extensions.md#syntax) rappresenta l'istanza del tipo viene richiamato, come membri ordinari.</span><span class="sxs-lookup"><span data-stu-id="538b7-154">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="538b7-155">I membri estesi possono essere statici o membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="538b7-155">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="538b7-156">Variabili di tipo in un'estensione del tipo devono corrispondere ai vincoli del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="538b7-156">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="538b7-157">Le limitazioni seguenti sono anche disponibili per le estensioni di tipo:</span><span class="sxs-lookup"><span data-stu-id="538b7-157">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="538b7-158">Metodi virtuali o astratti non supportano le estensioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="538b7-158">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="538b7-159">Le estensioni di tipo non supportano i metodi di override come aumenti.</span><span class="sxs-lookup"><span data-stu-id="538b7-159">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="538b7-160">Le estensioni di tipo non supportano [staticamente parametri di tipo risolti](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="538b7-160">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="538b7-161">Le estensioni di tipo facoltative non supportano i costruttori come aumenti.</span><span class="sxs-lookup"><span data-stu-id="538b7-161">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="538b7-162">Non è possibile definire le estensioni di tipo [abbreviazioni di tipo](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="538b7-162">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="538b7-163">Le estensioni di tipo non sono valide per `byref<'T>` (anche se possono essere dichiarati).</span><span class="sxs-lookup"><span data-stu-id="538b7-163">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="538b7-164">Le estensioni di tipo non sono valide per gli attributi (anche se possono essere dichiarati).</span><span class="sxs-lookup"><span data-stu-id="538b7-164">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="538b7-165">È possibile definire le estensioni che eseguono l'overload di altri metodi con lo stesso nome, ma il compilatore F # assegna la priorità ai metodi di estensione nel caso di una chiamata ambigua.</span><span class="sxs-lookup"><span data-stu-id="538b7-165">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="538b7-166">Infine, in presenza di più estensioni di tipo intrinseche per un tipo, tutti i membri devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="538b7-166">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="538b7-167">Le estensioni di tipo facoltativo, membri nelle estensioni di tipo diverso nello stesso tipo possono avere gli stessi nomi.</span><span class="sxs-lookup"><span data-stu-id="538b7-167">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="538b7-168">Errori di ambiguità si verificano solo se il codice client apre due ambiti diversi che definiscono gli stessi nomi di membro.</span><span class="sxs-lookup"><span data-stu-id="538b7-168">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="538b7-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="538b7-169">See also</span></span>

- [<span data-ttu-id="538b7-170">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="538b7-170">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="538b7-171">Membri</span><span class="sxs-lookup"><span data-stu-id="538b7-171">Members</span></span>](members/index.md)
