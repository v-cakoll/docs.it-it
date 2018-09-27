---
title: 'ByRef (F #)'
description: 'Informazioni su byref e tipi byref simili in F #, che vengono usati per la programmazione di basso livello.'
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47235520"
---
# <a name="byrefs"></a><span data-ttu-id="91d26-103">Zkratka</span><span class="sxs-lookup"><span data-stu-id="91d26-103">Byrefs</span></span>

<span data-ttu-id="91d26-104">F # ha due aree delle funzionalità principali relativi allo spazio di programmazione di basso livello:</span><span class="sxs-lookup"><span data-stu-id="91d26-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="91d26-105">Il `byref` / `inref` / `outref` tipi, ovvero un puntatori gestiti.</span><span class="sxs-lookup"><span data-stu-id="91d26-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="91d26-106">Presentano le restrizioni sull'utilizzo in modo che non è possibile compilare un programma che non è valido in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91d26-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="91d26-107">Oggetto `byref`-come struct, ovvero un [struttura](structures.md) che ha una semantica simile e le stesse restrizioni in fase di compilazione come `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="91d26-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="91d26-108">Un esempio è <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="91d26-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="91d26-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91d26-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="91d26-110">ByRef inref e outref</span><span class="sxs-lookup"><span data-stu-id="91d26-110">Byref, inref, and outref</span></span>

<span data-ttu-id="91d26-111">Esistono tre forme di `byref`:</span><span class="sxs-lookup"><span data-stu-id="91d26-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="91d26-112">`inref<'T>`, un puntatore gestito per leggere il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="91d26-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="91d26-113">`outref<'T>`, un puntatore gestito per la scrittura del valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="91d26-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="91d26-114">`byref<'T>`, un puntatore gestito per leggere e scrivere il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="91d26-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="91d26-115">Oggetto `byref<'T>` può essere passato in cui un `inref<'T>` è previsto.</span><span class="sxs-lookup"><span data-stu-id="91d26-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="91d26-116">Analogamente, un `byref<'T>` può essere passato in cui un `outref<'T>` è previsto.</span><span class="sxs-lookup"><span data-stu-id="91d26-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="91d26-117">Usando i tipi ByRef</span><span class="sxs-lookup"><span data-stu-id="91d26-117">Using byrefs</span></span>

<span data-ttu-id="91d26-118">Usare un `inref<'T>`, è necessario ottenere un valore del puntatore con `&`:</span><span class="sxs-lookup"><span data-stu-id="91d26-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="91d26-119">Per scrivere il puntatore del mouse utilizzando un `outref<'T>` oppure `byref<'T>`, è inoltre necessario che il valore ottenere un puntatore a `mutable`.</span><span class="sxs-lookup"><span data-stu-id="91d26-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="91d26-120">Se si sta scrivendo solo il puntatore anziché leggerlo, è consigliabile usare `outref<'T>` invece di `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="91d26-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="91d26-121">Semantica Inref</span><span class="sxs-lookup"><span data-stu-id="91d26-121">Inref semantics</span></span>

<span data-ttu-id="91d26-122">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="91d26-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

<span data-ttu-id="91d26-123">Semanticamente, ciò significa che i seguenti:</span><span class="sxs-lookup"><span data-stu-id="91d26-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="91d26-124">Il titolare del `x` puntatore possa utilizzarlo solo per leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="91d26-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="91d26-125">Qualsiasi puntatore acquisito al `struct` campi annidati all'interno `SomeStruct` sono di tipo specificato `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="91d26-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="91d26-126">Si verifica quanto segue anche:</span><span class="sxs-lookup"><span data-stu-id="91d26-126">The following is also true:</span></span>

* <span data-ttu-id="91d26-127">Non vi è alcuna implicazione che gli altri thread o gli alias non hanno accesso in scrittura a `x`.</span><span class="sxs-lookup"><span data-stu-id="91d26-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="91d26-128">Non vi è alcuna implicazione che `SomeStruct` non è modificabile in virtù della `x` in corso un `inref`.</span><span class="sxs-lookup"><span data-stu-id="91d26-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="91d26-129">Tuttavia, per F # tipi di valori che **vengono** modificabile, il `this` puntatore viene dedotto come un `inref`.</span><span class="sxs-lookup"><span data-stu-id="91d26-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="91d26-130">Tutte queste regole insieme significa che il titolare di un `inref` puntatore non può modificare il contenuto della memoria che puntano all'immediato.</span><span class="sxs-lookup"><span data-stu-id="91d26-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="91d26-131">Semantica Outref</span><span class="sxs-lookup"><span data-stu-id="91d26-131">Outref semantics</span></span>

<span data-ttu-id="91d26-132">Lo scopo di `outref<'T>` consiste nell'indicare che il puntatore deve essere letto solo da.</span><span class="sxs-lookup"><span data-stu-id="91d26-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="91d26-133">In modo imprevisto, `outref<'T>` consente la lettura sottostante valore malgrado il nome.</span><span class="sxs-lookup"><span data-stu-id="91d26-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="91d26-134">Si tratta di garantire la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="91d26-134">This is for compatibility purposes.</span></span> <span data-ttu-id="91d26-135">A livello semantico `outref<'T>` non è diversa da `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="91d26-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="91d26-136">Interoperabilità con c#</span><span class="sxs-lookup"><span data-stu-id="91d26-136">Interop with C#</span></span> #

<span data-ttu-id="91d26-137">C# supporta le `in ref` e `out ref` parole chiave, oltre a `ref` restituisce.</span><span class="sxs-lookup"><span data-stu-id="91d26-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="91d26-138">La tabella seguente illustra in che modo F # interpreta c# genera di cosa:</span><span class="sxs-lookup"><span data-stu-id="91d26-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="91d26-139">Costrutto di linguaggio c#</span><span class="sxs-lookup"><span data-stu-id="91d26-139">C# construct</span></span>|<span data-ttu-id="91d26-140">F # deduce</span><span class="sxs-lookup"><span data-stu-id="91d26-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="91d26-141">`ref` Valore restituito</span><span class="sxs-lookup"><span data-stu-id="91d26-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="91d26-142">`ref readonly` Valore restituito</span><span class="sxs-lookup"><span data-stu-id="91d26-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="91d26-143">`in ref` Parametro</span><span class="sxs-lookup"><span data-stu-id="91d26-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="91d26-144">`out ref` Parametro</span><span class="sxs-lookup"><span data-stu-id="91d26-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="91d26-145">Nella tabella seguente mostra F # genera di cosa:</span><span class="sxs-lookup"><span data-stu-id="91d26-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="91d26-146">Costrutto F #</span><span class="sxs-lookup"><span data-stu-id="91d26-146">F# construct</span></span>|<span data-ttu-id="91d26-147">Costrutto generato</span><span class="sxs-lookup"><span data-stu-id="91d26-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="91d26-148">`inref<'T>` argomento</span><span class="sxs-lookup"><span data-stu-id="91d26-148">`inref<'T>` argument</span></span>|<span data-ttu-id="91d26-149">`[In]` attributo nell'argomento</span><span class="sxs-lookup"><span data-stu-id="91d26-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="91d26-150">`inref<'T>` restituire</span><span class="sxs-lookup"><span data-stu-id="91d26-150">`inref<'T>` return</span></span>|<span data-ttu-id="91d26-151">`modreq` attributo sul valore</span><span class="sxs-lookup"><span data-stu-id="91d26-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="91d26-152">`inref<'T>` in uno slot astratto o implementazione</span><span class="sxs-lookup"><span data-stu-id="91d26-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="91d26-153">`modreq` argomento o return</span><span class="sxs-lookup"><span data-stu-id="91d26-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="91d26-154">`outref<'T>` argomento</span><span class="sxs-lookup"><span data-stu-id="91d26-154">`outref<'T>` argument</span></span>|<span data-ttu-id="91d26-155">`[Out]` attributo nell'argomento</span><span class="sxs-lookup"><span data-stu-id="91d26-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="91d26-156">L'inferenza del tipo e le regole di overload</span><span class="sxs-lookup"><span data-stu-id="91d26-156">Type inference and overloading rules</span></span>

<span data-ttu-id="91d26-157">Un `inref<'T>` tipo viene dedotto dal compilatore F # nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="91d26-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="91d26-158">Un tipo restituito o parametro .NET con un `IsReadOnly` attributo.</span><span class="sxs-lookup"><span data-stu-id="91d26-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="91d26-159">Il `this` indicatore di misura su un tipo struct che nessun campo modificabile.</span><span class="sxs-lookup"><span data-stu-id="91d26-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="91d26-160">L'indirizzo di una posizione di memoria derivato da un altro `inref<_>` puntatore.</span><span class="sxs-lookup"><span data-stu-id="91d26-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="91d26-161">Quando un indirizzo implicito di un `inref` è stata posta, un overload con un argomento di tipo `SomeType` è preferibile a un overload con un argomento di tipo `inref<SomeType>`.</span><span class="sxs-lookup"><span data-stu-id="91d26-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="91d26-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91d26-162">For example:</span></span>

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

<span data-ttu-id="91d26-163">In entrambi i casi, l'overload che accettano `System.DateTime` vengono risolte invece l'overload che accettano `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="91d26-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="91d26-164">Strutture di tipo ByRef</span><span class="sxs-lookup"><span data-stu-id="91d26-164">Byref-like structs</span></span>

<span data-ttu-id="91d26-165">Oltre al `byref` / `inref` / `outref` trio, è possibile definire struct che possono rispettare `byref`-come la semantica.</span><span class="sxs-lookup"><span data-stu-id="91d26-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="91d26-166">Questa operazione viene eseguita con il <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attributo:</span><span class="sxs-lookup"><span data-stu-id="91d26-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="91d26-167">`IsByRefLike` non implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="91d26-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="91d26-168">Entrambi devono essere presenti nel tipo.</span><span class="sxs-lookup"><span data-stu-id="91d26-168">Both must be present on the type.</span></span>

<span data-ttu-id="91d26-169">Un "`byref`-ad esempio" struct in F # è un tipo di valore con associazione dello stack.</span><span class="sxs-lookup"><span data-stu-id="91d26-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="91d26-170">Non viene allocato nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="91d26-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="91d26-171">Oggetto `byref`-come struct è utile per la programmazione ad alte prestazioni, come viene applicato con set di controlli accurati su durata e di non acquisizione.</span><span class="sxs-lookup"><span data-stu-id="91d26-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="91d26-172">Le regole sono:</span><span class="sxs-lookup"><span data-stu-id="91d26-172">The rules are:</span></span>

* <span data-ttu-id="91d26-173">Possono essere utilizzati come parametri di funzione, i parametri dei metodi, variabili locali, metodo viene restituito.</span><span class="sxs-lookup"><span data-stu-id="91d26-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="91d26-174">Essi non può essere statico o istanza i membri di una classe o struct normali.</span><span class="sxs-lookup"><span data-stu-id="91d26-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="91d26-175">Non è possibile acquisire da qualsiasi costrutto di chiusura (`async` metodi o espressioni lambda).</span><span class="sxs-lookup"><span data-stu-id="91d26-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="91d26-176">Non possono essere utilizzati come un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="91d26-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="91d26-177">Quest'ultimo punto è essenziale per la programmazione in F # pipeline stile come `|>` è una funzione generica che Parametrizza relativi tipi di input.</span><span class="sxs-lookup"><span data-stu-id="91d26-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="91d26-178">Questa restrizione può essere assoluta per `|>` in futuro, perché è in linea e non esegue tutte le chiamate a funzioni generiche non inline nel relativo corpo.</span><span class="sxs-lookup"><span data-stu-id="91d26-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="91d26-179">Anche se queste regole limitano molto fortemente utilizzo, a tale scopo per soddisfare la promessa di high performance computing in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="91d26-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="91d26-180">Valori restituiti ByRef</span><span class="sxs-lookup"><span data-stu-id="91d26-180">Byref returns</span></span>

<span data-ttu-id="91d26-181">Valori restituiti byref da funzioni F # o i membri possono essere generati e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="91d26-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="91d26-182">Quando si utilizza un `byref`-metodo di restituzione, il valore è dereferenziato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="91d26-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="91d26-183">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91d26-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="91d26-184">Per evitare il dereferenziazione implicito, ad esempio passando un riferimento tramite più chiamate concatenate, usano `&x` (dove `x` è il valore).</span><span class="sxs-lookup"><span data-stu-id="91d26-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="91d26-185">È anche possibile assegnare direttamente a una restituzione `byref`.</span><span class="sxs-lookup"><span data-stu-id="91d26-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="91d26-186">Si consideri il seguente programma (elevata imperativo):</span><span class="sxs-lookup"><span data-stu-id="91d26-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

<span data-ttu-id="91d26-187">L'output è il seguente.</span><span class="sxs-lookup"><span data-stu-id="91d26-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="91d26-188">Definizione dell'ambito per i tipi ByRef</span><span class="sxs-lookup"><span data-stu-id="91d26-188">Scoping for byrefs</span></span>

<span data-ttu-id="91d26-189">Oggetto `let`-valore associato non può avere il proprio riferimento superano l'ambito in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="91d26-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="91d26-190">Ad esempio, di seguito non è consentito:</span><span class="sxs-lookup"><span data-stu-id="91d26-190">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="91d26-191">Ciò impedisce all'utente di ottenere risultati diversi a seconda se esegue la compilazione con ottimizzazioni attiva o disattiva.</span><span class="sxs-lookup"><span data-stu-id="91d26-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
