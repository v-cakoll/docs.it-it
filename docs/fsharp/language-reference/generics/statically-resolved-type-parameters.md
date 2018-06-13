---
title: Parametri di tipo risolti staticamente (F#)
description: "Informazioni sull'utilizzo di F # parametro di tipo risolti staticamente, che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione."
ms.date: 05/16/2016
ms.openlocfilehash: 12c2af4d9df7ae1e5e77efc9413eb8777459a83c
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233782"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="de534-103">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="de534-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="de534-104">Oggetto *parametro di tipo risolti staticamente* è un parametro di tipo che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="de534-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="de534-105">Sono preceduti da un simbolo di accento circonflesso (^).</span><span class="sxs-lookup"><span data-stu-id="de534-105">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="de534-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de534-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="de534-107">Note</span><span class="sxs-lookup"><span data-stu-id="de534-107">Remarks</span></span>
<span data-ttu-id="de534-108">Nel linguaggio F #, esistono due tipi distinti di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="de534-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="de534-109">Il primo tipo è il parametro di tipo generico standard.</span><span class="sxs-lookup"><span data-stu-id="de534-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="de534-110">Questi sono indicati da un apostrofo ('), come in `'T` e `'U`.</span><span class="sxs-lookup"><span data-stu-id="de534-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="de534-111">Sono equivalenti ai parametri di tipo generico in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de534-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="de534-112">L'altro tipo viene risolto in modo statico ed è indicato da un simbolo di punto di inserimento, come in `^T` e `^U`.</span><span class="sxs-lookup"><span data-stu-id="de534-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="de534-113">I parametri di tipo risolti staticamente sono particolarmente utili in combinazione con vincoli di membro, ovvero i vincoli che consentono di specificare che un argomento di tipo deve disporre di un particolare membro o i membri per poter essere usato.</span><span class="sxs-lookup"><span data-stu-id="de534-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="de534-114">Non è possibile creare questo tipo di vincolo utilizzando un parametro di tipo generico regolare.</span><span class="sxs-lookup"><span data-stu-id="de534-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="de534-115">Nella tabella seguente sono riepilogate le analogie e differenze tra i due tipi di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="de534-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="de534-116">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="de534-116">Feature</span></span>|<span data-ttu-id="de534-117">Generico</span><span class="sxs-lookup"><span data-stu-id="de534-117">Generic</span></span>|<span data-ttu-id="de534-118">Risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="de534-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="de534-119">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de534-119">Syntax</span></span>|<span data-ttu-id="de534-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="de534-120">`'T`, `'U`</span></span>|<span data-ttu-id="de534-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="de534-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="de534-122">Tempi di risoluzione</span><span class="sxs-lookup"><span data-stu-id="de534-122">Resolution time</span></span>|<span data-ttu-id="de534-123">Fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="de534-123">Run time</span></span>|<span data-ttu-id="de534-124">Fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="de534-124">Compile time</span></span>|
|<span data-ttu-id="de534-125">Vincoli di membro</span><span class="sxs-lookup"><span data-stu-id="de534-125">Member constraints</span></span>|<span data-ttu-id="de534-126">Non può essere utilizzato con vincoli di membro.</span><span class="sxs-lookup"><span data-stu-id="de534-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="de534-127">Può essere utilizzato con vincoli di membro.</span><span class="sxs-lookup"><span data-stu-id="de534-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="de534-128">Generazione del codice</span><span class="sxs-lookup"><span data-stu-id="de534-128">Code generation</span></span>|<span data-ttu-id="de534-129">Un tipo (o metodo) con parametri di tipo generico standard comporta la generazione di un singolo tipo o metodo generico.</span><span class="sxs-lookup"><span data-stu-id="de534-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="de534-130">Più istanze di tipi e metodi generate, uno per ogni tipo che è necessario.</span><span class="sxs-lookup"><span data-stu-id="de534-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="de534-131">Utilizzare con i tipi</span><span class="sxs-lookup"><span data-stu-id="de534-131">Use with types</span></span>|<span data-ttu-id="de534-132">Può essere utilizzato nei tipi.</span><span class="sxs-lookup"><span data-stu-id="de534-132">Can be used on types.</span></span>|<span data-ttu-id="de534-133">Può essere utilizzato per i tipi.</span><span class="sxs-lookup"><span data-stu-id="de534-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="de534-134">Utilizzare con le funzioni inline</span><span class="sxs-lookup"><span data-stu-id="de534-134">Use with inline functions</span></span>|<span data-ttu-id="de534-135">No.</span><span class="sxs-lookup"><span data-stu-id="de534-135">No.</span></span> <span data-ttu-id="de534-136">Una funzione inline non può essere parametrizzata con un parametro di tipo generico standard.</span><span class="sxs-lookup"><span data-stu-id="de534-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="de534-137">Sì.</span><span class="sxs-lookup"><span data-stu-id="de534-137">Yes.</span></span> <span data-ttu-id="de534-138">Impossibile utilizzare i parametri di tipo risolti staticamente in funzioni o metodi che non sono in linea.</span><span class="sxs-lookup"><span data-stu-id="de534-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="de534-139">Molte funzioni F # principale libreria, in particolare gli operatori sono stati risolti in modo statico i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="de534-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="de534-140">Queste funzioni e operatori sono inline e causare la generazione di codice efficiente per calcoli numerici.</span><span class="sxs-lookup"><span data-stu-id="de534-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="de534-141">Metodi inline e funzioni che usano operatori, o altre funzioni di parametri di tipo risolti staticamente inoltre possono utilizzare i parametri di tipo risolti staticamente stessi.</span><span class="sxs-lookup"><span data-stu-id="de534-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="de534-142">Inferenza deduce spesso tali funzioni inline per sono parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="de534-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="de534-143">Nell'esempio seguente viene illustrata una definizione di operatore viene dedotto un parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="de534-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="de534-144">Il tipo risolto `(+@)` si basa sull'utilizzo di `(+)` e `(*)`, entrambi di che provocano l'inferenza del tipo di dedurre i vincoli di membro sui parametri di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="de534-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="de534-145">Il tipo risolto, come illustrato nell'interprete F #, è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="de534-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="de534-146">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="de534-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="de534-147">A partire da F # 4.1, è inoltre possibile specificare nomi di tipo concreto nelle firme di parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="de534-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="de534-148">Nelle versioni precedenti del linguaggio, il nome del tipo è effettivamente possibile dedurre dal compilatore, ma non può effettivamente essere specificato nella firma.</span><span class="sxs-lookup"><span data-stu-id="de534-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="de534-149">A partire da F # 4.1, è inoltre possibile specificare i nomi di tipo concreto nelle firme di parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="de534-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="de534-150">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="de534-150">Here's an example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="de534-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de534-151">See Also</span></span>
[<span data-ttu-id="de534-152">Generics</span><span class="sxs-lookup"><span data-stu-id="de534-152">Generics</span></span>](index.md)

[<span data-ttu-id="de534-153">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="de534-153">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="de534-154">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="de534-154">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="de534-155">Vincoli</span><span class="sxs-lookup"><span data-stu-id="de534-155">Constraints</span></span>](constraints.md)

[<span data-ttu-id="de534-156">Funzioni inline</span><span class="sxs-lookup"><span data-stu-id="de534-156">Inline Functions</span></span>](../functions/inline-functions.md)
