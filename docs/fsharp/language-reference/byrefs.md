---
title: Byref
description: Informazioni sui tipi ByRef e di tipo ByRef in F#, usati per la programmazione di basso livello.
ms.date: 11/04/2019
ms.openlocfilehash: 2d98d325dc4ad26548fb2cc6aa5b872e152ee0a8
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092788"
---
# <a name="byrefs"></a><span data-ttu-id="9f448-103">Byref</span><span class="sxs-lookup"><span data-stu-id="9f448-103">Byrefs</span></span>

<span data-ttu-id="9f448-104">F#in sono presenti due principali aree funzionali che occupano lo spazio di programmazione di basso livello:</span><span class="sxs-lookup"><span data-stu-id="9f448-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="9f448-105">Il `byref`/`inref`i tipi di `outref` /, ovvero i puntatori gestiti.</span><span class="sxs-lookup"><span data-stu-id="9f448-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="9f448-106">Hanno restrizioni sull'utilizzo, in modo da non poter compilare un programma non valido in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9f448-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="9f448-107">Uno struct di tipo `byref`, ovvero una [struttura](structures.md) con semantica simile e le stesse restrizioni della fase di compilazione di `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="9f448-108">Un esempio è <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="9f448-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f448-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f448-109">Syntax</span></span>

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a><span data-ttu-id="9f448-110">ByRef, inref e outref</span><span class="sxs-lookup"><span data-stu-id="9f448-110">Byref, inref, and outref</span></span>

<span data-ttu-id="9f448-111">Esistono tre tipi di `byref`:</span><span class="sxs-lookup"><span data-stu-id="9f448-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="9f448-112">`inref<'T>`, un puntatore gestito per la lettura del valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="9f448-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="9f448-113">`outref<'T>`, un puntatore gestito per la scrittura nel valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="9f448-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="9f448-114">`byref<'T>`, un puntatore gestito per la lettura e la scrittura del valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="9f448-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="9f448-115">È possibile passare un `byref<'T>` in cui è prevista una `inref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="9f448-116">Analogamente, è possibile passare un `byref<'T>` in cui è prevista una `outref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="9f448-117">Utilizzo di ByRef</span><span class="sxs-lookup"><span data-stu-id="9f448-117">Using byrefs</span></span>

<span data-ttu-id="9f448-118">Per usare una `inref<'T>`, è necessario ottenere un valore di puntatore con `&`:</span><span class="sxs-lookup"><span data-stu-id="9f448-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="9f448-119">Per scrivere nel puntatore usando un `outref<'T>` o `byref<'T>`, è necessario anche fare in modo che si prenda un puntatore per `mutable`.</span><span class="sxs-lookup"><span data-stu-id="9f448-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="9f448-120">Se si scrive solo il puntatore anziché leggerlo, provare a usare `outref<'T>` anziché `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="9f448-121">Semantica di Inref</span><span class="sxs-lookup"><span data-stu-id="9f448-121">Inref semantics</span></span>

<span data-ttu-id="9f448-122">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="9f448-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="9f448-123">Semanticamente, questo significa quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9f448-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="9f448-124">Il titolare del puntatore `x` può utilizzarlo solo per leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="9f448-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="9f448-125">Ogni puntatore acquisito per `struct` campi annidati all'interno di `SomeStruct` viene assegnato al tipo `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="9f448-126">Si verifica anche quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9f448-126">The following is also true:</span></span>

* <span data-ttu-id="9f448-127">Non esiste alcuna implicazione che altri thread o alias non dispongano dell'accesso in scrittura ai `x`.</span><span class="sxs-lookup"><span data-stu-id="9f448-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="9f448-128">Non esiste alcuna implicazione che `SomeStruct` sia immutabile in virtù della `x` essere un `inref`.</span><span class="sxs-lookup"><span data-stu-id="9f448-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="9f448-129">Tuttavia, per F# i **tipi di valore** non modificabili, il puntatore `this` viene dedotto come `inref`.</span><span class="sxs-lookup"><span data-stu-id="9f448-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="9f448-130">Ognuna di queste regole significa che il titolare di un puntatore `inref` potrebbe non modificare il contenuto immediato della memoria a cui punta.</span><span class="sxs-lookup"><span data-stu-id="9f448-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="9f448-131">Semantica di Outref</span><span class="sxs-lookup"><span data-stu-id="9f448-131">Outref semantics</span></span>

<span data-ttu-id="9f448-132">Lo scopo di `outref<'T>` è indicare che il puntatore deve essere scritto solo in.</span><span class="sxs-lookup"><span data-stu-id="9f448-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="9f448-133">In modo imprevisto, `outref<'T>` consente di leggere il valore sottostante nonostante il nome.</span><span class="sxs-lookup"><span data-stu-id="9f448-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="9f448-134">Per motivi di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="9f448-134">This is for compatibility purposes.</span></span> <span data-ttu-id="9f448-135">Semanticamente, `outref<'T>` non è diverso da `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="9f448-136">Interoperabilità con C\#</span><span class="sxs-lookup"><span data-stu-id="9f448-136">Interop with C\#</span></span>

<span data-ttu-id="9f448-137">C#supporta le parole chiave `in ref` e `out ref`, oltre a `ref` restituisce.</span><span class="sxs-lookup"><span data-stu-id="9f448-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="9f448-138">Nella tabella seguente viene illustrato F# come interpretare C# gli elementi generati:</span><span class="sxs-lookup"><span data-stu-id="9f448-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="9f448-139">C#costruire</span><span class="sxs-lookup"><span data-stu-id="9f448-139">C# construct</span></span>|<span data-ttu-id="9f448-140">F#deduce</span><span class="sxs-lookup"><span data-stu-id="9f448-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="9f448-141">`ref` valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f448-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="9f448-142">`ref readonly` valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f448-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="9f448-143">Parametro `in ref`.</span><span class="sxs-lookup"><span data-stu-id="9f448-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="9f448-144">Parametro `out ref`.</span><span class="sxs-lookup"><span data-stu-id="9f448-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="9f448-145">La tabella seguente mostra cosa F# genera:</span><span class="sxs-lookup"><span data-stu-id="9f448-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="9f448-146">F#costruire</span><span class="sxs-lookup"><span data-stu-id="9f448-146">F# construct</span></span>|<span data-ttu-id="9f448-147">Costrutto emesso</span><span class="sxs-lookup"><span data-stu-id="9f448-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="9f448-148">`inref<'T>` argomento</span><span class="sxs-lookup"><span data-stu-id="9f448-148">`inref<'T>` argument</span></span>|<span data-ttu-id="9f448-149">attributo `[In]` sull'argomento</span><span class="sxs-lookup"><span data-stu-id="9f448-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="9f448-150">`inref<'T>` restituito</span><span class="sxs-lookup"><span data-stu-id="9f448-150">`inref<'T>` return</span></span>|<span data-ttu-id="9f448-151">`modreq` attributo per valore</span><span class="sxs-lookup"><span data-stu-id="9f448-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="9f448-152">`inref<'T>` nello slot o nell'implementazione astratta</span><span class="sxs-lookup"><span data-stu-id="9f448-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="9f448-153">`modreq` sull'argomento o sulla restituzione</span><span class="sxs-lookup"><span data-stu-id="9f448-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="9f448-154">`outref<'T>` argomento</span><span class="sxs-lookup"><span data-stu-id="9f448-154">`outref<'T>` argument</span></span>|<span data-ttu-id="9f448-155">attributo `[Out]` sull'argomento</span><span class="sxs-lookup"><span data-stu-id="9f448-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="9f448-156">Regole di overload e inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="9f448-156">Type inference and overloading rules</span></span>

<span data-ttu-id="9f448-157">Un tipo di `inref<'T>` viene dedotto dal F# compilatore nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f448-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="9f448-158">Un parametro .NET o un tipo restituito con un attributo `IsReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="9f448-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="9f448-159">Puntatore `this` su un tipo struct senza campi modificabili.</span><span class="sxs-lookup"><span data-stu-id="9f448-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="9f448-160">Indirizzo di una posizione di memoria derivata da un altro puntatore `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="9f448-161">Quando viene eseguito un indirizzo implicito di un `inref`, un overload con un argomento di tipo `SomeType` è preferibile a un overload di con un argomento di tipo `inref<SomeType>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="9f448-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9f448-162">For example:</span></span>

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

<span data-ttu-id="9f448-163">In entrambi i casi, gli overload che accettano `System.DateTime` vengono risolti anziché gli overload che assumono `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="9f448-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="9f448-164">Struct di tipo ByRef</span><span class="sxs-lookup"><span data-stu-id="9f448-164">Byref-like structs</span></span>

<span data-ttu-id="9f448-165">Oltre al `byref`/`inref`/`outref` Trio, è possibile definire struct personalizzati che possono rispettare la semantica di tipo `byref`.</span><span class="sxs-lookup"><span data-stu-id="9f448-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="9f448-166">Questa operazione viene eseguita con l'attributo <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>:</span><span class="sxs-lookup"><span data-stu-id="9f448-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="9f448-167">`IsByRefLike` non implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="9f448-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="9f448-168">Entrambi devono essere presenti nel tipo.</span><span class="sxs-lookup"><span data-stu-id="9f448-168">Both must be present on the type.</span></span>

<span data-ttu-id="9f448-169">Uno struct "`byref`-like" in F# è un tipo di valore associato allo stack.</span><span class="sxs-lookup"><span data-stu-id="9f448-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="9f448-170">Non viene mai allocato nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="9f448-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="9f448-171">Uno struct di tipo `byref`è utile per la programmazione a prestazioni elevate, in quanto viene applicato con un set di controlli sicuri sulla durata e non sull'acquisizione.</span><span class="sxs-lookup"><span data-stu-id="9f448-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="9f448-172">Le regole sono:</span><span class="sxs-lookup"><span data-stu-id="9f448-172">The rules are:</span></span>

* <span data-ttu-id="9f448-173">Possono essere usati come parametri di funzione, parametri di metodo, variabili locali, restituzione di metodi.</span><span class="sxs-lookup"><span data-stu-id="9f448-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="9f448-174">Non possono essere membri statici o di istanza di una classe o di uno struct normale.</span><span class="sxs-lookup"><span data-stu-id="9f448-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="9f448-175">Non possono essere acquisiti da alcun costrutto di chiusura (`async` metodi o espressioni lambda).</span><span class="sxs-lookup"><span data-stu-id="9f448-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="9f448-176">Non possono essere usati come parametro generico.</span><span class="sxs-lookup"><span data-stu-id="9f448-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="9f448-177">Questo ultimo punto è fondamentale per F# la programmazione in stile pipeline, perché `|>` è una funzione generica che parametrizza i relativi tipi di input.</span><span class="sxs-lookup"><span data-stu-id="9f448-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="9f448-178">Questa restrizione può essere attenuata per `|>` in futuro, in quanto è inline e non esegue chiamate a funzioni generiche non inline nel corpo.</span><span class="sxs-lookup"><span data-stu-id="9f448-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="9f448-179">Sebbene queste regole limitino fortemente l'utilizzo, lo fanno per soddisfare la promessa di un calcolo ad alte prestazioni in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="9f448-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="9f448-180">ByRef restituisce</span><span class="sxs-lookup"><span data-stu-id="9f448-180">Byref returns</span></span>

<span data-ttu-id="9f448-181">I ritorni F# ByRef da funzioni o membri possono essere prodotti e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="9f448-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="9f448-182">Quando si utilizza un metodo di restituzione di `byref`, il valore viene dereferenziato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="9f448-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="9f448-183">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9f448-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) = 
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="9f448-184">Per restituire un valore ByRef, la variabile che contiene il valore deve essere più lunga dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="9f448-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="9f448-185">Inoltre, per restituire ByRef, utilizzare `&value` (dove value è una variabile che dura più a lungo dell'ambito corrente).</span><span class="sxs-lookup"><span data-stu-id="9f448-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="9f448-186">Per evitare la dereferenziazione implicita, ad esempio il passaggio di un riferimento tramite più chiamate concatenate, usare `&x` (dove `x` è il valore).</span><span class="sxs-lookup"><span data-stu-id="9f448-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="9f448-187">È anche possibile assegnare direttamente a un `byref`restituito.</span><span class="sxs-lookup"><span data-stu-id="9f448-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="9f448-188">Si consideri il seguente programma (estremamente imperativo):</span><span class="sxs-lookup"><span data-stu-id="9f448-188">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="9f448-189">L'output è il seguente.</span><span class="sxs-lookup"><span data-stu-id="9f448-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="9f448-190">Ambito per ByRef</span><span class="sxs-lookup"><span data-stu-id="9f448-190">Scoping for byrefs</span></span>

<span data-ttu-id="9f448-191">Il riferimento di un valore associato a `let`non può superare l'ambito in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="9f448-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="9f448-192">Il codice seguente, ad esempio, non è consentito:</span><span class="sxs-lookup"><span data-stu-id="9f448-192">For example, the following is disallowed:</span></span>

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

<span data-ttu-id="9f448-193">Ciò impedisce di ottenere risultati diversi a seconda che vengano compilate con le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="9f448-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
