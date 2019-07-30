---
title: Parametri di tipo risolti staticamente
description: Informazioni su come usare un F# parametro di tipo risolto in modo statico, che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione.
ms.date: 05/16/2016
ms.openlocfilehash: 43ed79b6e5f43a499a27b05e26472b021c455e44
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630588"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="ec944-103">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="ec944-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="ec944-104">Un *parametro di tipo risolto* in modo statico è un parametro di tipo che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ec944-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="ec944-105">Sono preceduti da un accento circonflesso (^).</span><span class="sxs-lookup"><span data-stu-id="ec944-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="ec944-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec944-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="ec944-107">Note</span><span class="sxs-lookup"><span data-stu-id="ec944-107">Remarks</span></span>

<span data-ttu-id="ec944-108">Nella F# lingua sono presenti due tipi distinti di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="ec944-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="ec944-109">Il primo tipo è il parametro di tipo generico standard.</span><span class="sxs-lookup"><span data-stu-id="ec944-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="ec944-110">Questi sono indicati da un apostrofo ('), come `'T` in `'U`e.</span><span class="sxs-lookup"><span data-stu-id="ec944-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="ec944-111">Sono equivalenti a parametri di tipo generico in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec944-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="ec944-112">L'altro tipo viene risolto in modo statico ed è indicato da un simbolo del cursore, come `^T` in `^U`e.</span><span class="sxs-lookup"><span data-stu-id="ec944-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="ec944-113">I parametri di tipo risolti staticamente sono principalmente utili insieme ai vincoli dei membri, ovvero vincoli che consentono di specificare che un argomento di tipo deve avere un membro o membri specifici per poter essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ec944-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="ec944-114">Non è possibile creare questo tipo di vincolo usando un normale parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ec944-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="ec944-115">Nella tabella seguente sono riepilogate le analogie e le differenze tra i due tipi di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="ec944-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="ec944-116">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="ec944-116">Feature</span></span>|<span data-ttu-id="ec944-117">Generico</span><span class="sxs-lookup"><span data-stu-id="ec944-117">Generic</span></span>|<span data-ttu-id="ec944-118">Risoluzione statica</span><span class="sxs-lookup"><span data-stu-id="ec944-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="ec944-119">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec944-119">Syntax</span></span>|<span data-ttu-id="ec944-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="ec944-120">`'T`, `'U`</span></span>|<span data-ttu-id="ec944-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="ec944-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="ec944-122">Tempo di risoluzione</span><span class="sxs-lookup"><span data-stu-id="ec944-122">Resolution time</span></span>|<span data-ttu-id="ec944-123">Fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ec944-123">Run time</span></span>|<span data-ttu-id="ec944-124">Tempo di compilazione</span><span class="sxs-lookup"><span data-stu-id="ec944-124">Compile time</span></span>|
|<span data-ttu-id="ec944-125">Vincoli membri</span><span class="sxs-lookup"><span data-stu-id="ec944-125">Member constraints</span></span>|<span data-ttu-id="ec944-126">Non può essere usato con vincoli di membri.</span><span class="sxs-lookup"><span data-stu-id="ec944-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="ec944-127">Può essere usato con i vincoli dei membri.</span><span class="sxs-lookup"><span data-stu-id="ec944-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="ec944-128">Generazione del codice</span><span class="sxs-lookup"><span data-stu-id="ec944-128">Code generation</span></span>|<span data-ttu-id="ec944-129">Un tipo (o metodo) con parametri di tipo generico standard determina la generazione di un singolo tipo o metodo generico.</span><span class="sxs-lookup"><span data-stu-id="ec944-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="ec944-130">Vengono generate più creazioni di istanze di tipi e metodi, una per ogni tipo necessario.</span><span class="sxs-lookup"><span data-stu-id="ec944-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="ec944-131">Usare con i tipi</span><span class="sxs-lookup"><span data-stu-id="ec944-131">Use with types</span></span>|<span data-ttu-id="ec944-132">Può essere usato sui tipi.</span><span class="sxs-lookup"><span data-stu-id="ec944-132">Can be used on types.</span></span>|<span data-ttu-id="ec944-133">Non può essere usato sui tipi.</span><span class="sxs-lookup"><span data-stu-id="ec944-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="ec944-134">Usare con funzioni inline</span><span class="sxs-lookup"><span data-stu-id="ec944-134">Use with inline functions</span></span>|<span data-ttu-id="ec944-135">No.</span><span class="sxs-lookup"><span data-stu-id="ec944-135">No.</span></span> <span data-ttu-id="ec944-136">Una funzione inline non può essere parametrizzata con un parametro di tipo generico standard.</span><span class="sxs-lookup"><span data-stu-id="ec944-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="ec944-137">Sì.</span><span class="sxs-lookup"><span data-stu-id="ec944-137">Yes.</span></span> <span data-ttu-id="ec944-138">Non è possibile usare i parametri di tipo risolti staticamente in funzioni o metodi che non sono inline.</span><span class="sxs-lookup"><span data-stu-id="ec944-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="ec944-139">Molte F# funzioni della libreria principale, in particolare gli operatori, hanno parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="ec944-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="ec944-140">Queste funzioni e operatori sono inline e generano una generazione efficiente del codice per i calcoli numerici.</span><span class="sxs-lookup"><span data-stu-id="ec944-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="ec944-141">I metodi e le funzioni inline che usano operatori o altre funzioni con parametri di tipo risolti staticamente possono usare anche parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="ec944-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="ec944-142">Spesso, l'inferenza del tipo deduce tali funzioni inline per avere parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="ec944-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="ec944-143">Nell'esempio seguente viene illustrata una definizione di operatore inferita per avere un parametro di tipo risolto in modo statico.</span><span class="sxs-lookup"><span data-stu-id="ec944-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="ec944-144">Il tipo risolto di `(+@)` è basato sull'uso `(+)` di e `(*)`, entrambi che provocano l'inferenza del tipo per dedurre i vincoli dei membri nei parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="ec944-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="ec944-145">Il tipo risolto, come illustrato nell' F# interprete, è il seguente.</span><span class="sxs-lookup"><span data-stu-id="ec944-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="ec944-146">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ec944-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="ec944-147">A partire F# da 4,1, è anche possibile specificare nomi di tipi concreti nelle firme dei parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="ec944-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="ec944-148">Nelle versioni precedenti del linguaggio, il nome del tipo può essere effettivamente dedotto dal compilatore, ma non può essere effettivamente specificato nella firma.</span><span class="sxs-lookup"><span data-stu-id="ec944-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="ec944-149">A partire F# da 4,1, è anche possibile specificare nomi di tipi concreti nelle firme dei parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="ec944-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="ec944-150">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="ec944-150">Here's an example:</span></span>

```fsharp
let inline konst x _ = x

type CFunctor() = 
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a><span data-ttu-id="ec944-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec944-151">See also</span></span>

- [<span data-ttu-id="ec944-152">Generics</span><span class="sxs-lookup"><span data-stu-id="ec944-152">Generics</span></span>](index.md)
- [<span data-ttu-id="ec944-153">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="ec944-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="ec944-154">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="ec944-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="ec944-155">Vincoli</span><span class="sxs-lookup"><span data-stu-id="ec944-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="ec944-156">Funzioni inline</span><span class="sxs-lookup"><span data-stu-id="ec944-156">Inline Functions</span></span>](../functions/inline-functions.md)
