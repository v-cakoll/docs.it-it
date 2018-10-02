---
title: Parametri di tipo risolti staticamente (F#)
description: 'Informazioni su come utilizzare F # parametro di tipo risolti staticamente, che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione.'
ms.date: 05/16/2016
ms.openlocfilehash: 747917fef2746dcbf363ef4b717ace5e47229800
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032777"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="2f202-103">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="2f202-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="2f202-104">Oggetto *parametro di tipo risolti staticamente* è un parametro di tipo che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2f202-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="2f202-105">Sono preceduti da un simbolo di accento circonflesso (^).</span><span class="sxs-lookup"><span data-stu-id="2f202-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f202-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f202-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="2f202-107">Note</span><span class="sxs-lookup"><span data-stu-id="2f202-107">Remarks</span></span>

<span data-ttu-id="2f202-108">Nel linguaggio F #, sono disponibili due tipi distinti di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="2f202-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="2f202-109">Il primo tipo è il parametro di tipo generico standard.</span><span class="sxs-lookup"><span data-stu-id="2f202-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="2f202-110">Questi aggiornamenti sono indicati da un apostrofo ('), come in `'T` e `'U`.</span><span class="sxs-lookup"><span data-stu-id="2f202-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="2f202-111">Sono equivalenti ai parametri di tipo generico in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f202-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="2f202-112">L'altro tipo viene risolto in modo statico ed è indicato da un simbolo di punto di inserimento, come in `^T` e `^U`.</span><span class="sxs-lookup"><span data-stu-id="2f202-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="2f202-113">I parametri di tipo risolti staticamente sono particolarmente utili in combinazione con vincoli di membro, ovvero i vincoli che consentono di specificare che un argomento tipo deve avere una o più membri particolari per poter essere usato.</span><span class="sxs-lookup"><span data-stu-id="2f202-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="2f202-114">Non è possibile creare questo tipo di vincolo con un parametro di tipo generico regolari.</span><span class="sxs-lookup"><span data-stu-id="2f202-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="2f202-115">Nella tabella seguente sono riepilogate le analogie e differenze tra i due tipi di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="2f202-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="2f202-116">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="2f202-116">Feature</span></span>|<span data-ttu-id="2f202-117">Generico</span><span class="sxs-lookup"><span data-stu-id="2f202-117">Generic</span></span>|<span data-ttu-id="2f202-118">Risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="2f202-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="2f202-119">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f202-119">Syntax</span></span>|<span data-ttu-id="2f202-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="2f202-120">`'T`, `'U`</span></span>|<span data-ttu-id="2f202-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="2f202-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="2f202-122">Tempi di risoluzione</span><span class="sxs-lookup"><span data-stu-id="2f202-122">Resolution time</span></span>|<span data-ttu-id="2f202-123">Fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="2f202-123">Run time</span></span>|<span data-ttu-id="2f202-124">Fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="2f202-124">Compile time</span></span>|
|<span data-ttu-id="2f202-125">Vincoli di membro</span><span class="sxs-lookup"><span data-stu-id="2f202-125">Member constraints</span></span>|<span data-ttu-id="2f202-126">Non può essere utilizzato con vincoli di membro.</span><span class="sxs-lookup"><span data-stu-id="2f202-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="2f202-127">Può essere utilizzato con vincoli di membro.</span><span class="sxs-lookup"><span data-stu-id="2f202-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="2f202-128">Generazione del codice</span><span class="sxs-lookup"><span data-stu-id="2f202-128">Code generation</span></span>|<span data-ttu-id="2f202-129">Un tipo (o metodo) con i parametri di tipo generico standard comporta la generazione di un singolo tipo o metodo generico.</span><span class="sxs-lookup"><span data-stu-id="2f202-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="2f202-130">Vengono generati più creazioni di istanze di tipi e metodi, uno per ogni tipo che è necessario.</span><span class="sxs-lookup"><span data-stu-id="2f202-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="2f202-131">Utilizzare con i tipi</span><span class="sxs-lookup"><span data-stu-id="2f202-131">Use with types</span></span>|<span data-ttu-id="2f202-132">Può essere utilizzato nei tipi.</span><span class="sxs-lookup"><span data-stu-id="2f202-132">Can be used on types.</span></span>|<span data-ttu-id="2f202-133">Non è utilizzabile sui tipi.</span><span class="sxs-lookup"><span data-stu-id="2f202-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="2f202-134">Usare con le funzioni inline</span><span class="sxs-lookup"><span data-stu-id="2f202-134">Use with inline functions</span></span>|<span data-ttu-id="2f202-135">No.</span><span class="sxs-lookup"><span data-stu-id="2f202-135">No.</span></span> <span data-ttu-id="2f202-136">Una funzione inline non possa essere parametrizzata con un parametro di tipo generico standard.</span><span class="sxs-lookup"><span data-stu-id="2f202-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="2f202-137">Sì.</span><span class="sxs-lookup"><span data-stu-id="2f202-137">Yes.</span></span> <span data-ttu-id="2f202-138">Impossibile utilizzare i parametri di tipo risolti staticamente in funzioni o metodi che non sono inline.</span><span class="sxs-lookup"><span data-stu-id="2f202-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="2f202-139">Molte funzioni F # core library, in particolare gli operatori, sono stati risolti in modo statico i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="2f202-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="2f202-140">Questi operatori e funzioni inline e comportare la generazione di codice efficace per calcoli numerici.</span><span class="sxs-lookup"><span data-stu-id="2f202-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="2f202-141">Metodi inline e funzioni che utilizzano operatori oppure utilizzano altre funzioni, parametri di tipo risolti staticamente anche possono usare parametri di tipo risolti staticamente stessi.</span><span class="sxs-lookup"><span data-stu-id="2f202-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="2f202-142">Inferenza deduce spesso, tali funzioni inline per avere parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="2f202-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="2f202-143">L'esempio seguente illustra una definizione di operatore che si deduce che hanno un parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="2f202-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="2f202-144">Il tipo risolto `(+@)` si basa sull'utilizzo di entrambe `(+)` e `(*)`, entrambi di che provocano l'inferenza del tipo per dedurre i vincoli sui parametri di tipo risolti staticamente membro.</span><span class="sxs-lookup"><span data-stu-id="2f202-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="2f202-145">Il tipo risolto, come illustrato nell'interprete F #, è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2f202-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="2f202-146">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2f202-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="2f202-147">A partire da F # 4.1, è anche possibile specificare i nomi di tipo concreto nelle firme del parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="2f202-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="2f202-148">Nelle versioni precedenti del linguaggio, il nome del tipo può effettivamente essere dedotto dal compilatore, ma non è stato effettivamente essere specificato nella firma.</span><span class="sxs-lookup"><span data-stu-id="2f202-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="2f202-149">A partire da F # 4.1, è anche possibile specificare i nomi di tipo concreto nelle firme del parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="2f202-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="2f202-150">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="2f202-150">Here's an example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2f202-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f202-151">See also</span></span>

- [<span data-ttu-id="2f202-152">Generics</span><span class="sxs-lookup"><span data-stu-id="2f202-152">Generics</span></span>](index.md)
- [<span data-ttu-id="2f202-153">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="2f202-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="2f202-154">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="2f202-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="2f202-155">Vincoli</span><span class="sxs-lookup"><span data-stu-id="2f202-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="2f202-156">Funzioni inline</span><span class="sxs-lookup"><span data-stu-id="2f202-156">Inline Functions</span></span>](../functions/inline-functions.md)
