---
title: Byref
description: Informazioni sui tipi di tipo byref e byref in F , utilizzati per la programmazione di basso livello.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187043"
---
# <a name="byrefs"></a><span data-ttu-id="41dd7-103">Byref</span><span class="sxs-lookup"><span data-stu-id="41dd7-103">Byrefs</span></span>

<span data-ttu-id="41dd7-104">F è dotata di due aree di funzionalità principali che si occupano dello spazio di programmazione di basso livello:</span><span class="sxs-lookup"><span data-stu-id="41dd7-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="41dd7-105">`byref` / I `inref` / tipi, ovvero puntatori gestiti. `outref`</span><span class="sxs-lookup"><span data-stu-id="41dd7-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="41dd7-106">Sono previste restrizioni sull'utilizzo in modo che non sia possibile compilare un programma non valido in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="41dd7-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="41dd7-107">Uno `byref`struct di tipo -like, ovvero una [struttura](structures.md) con semantica `byref<'T>`simile e le stesse restrizioni in fase di compilazione di .</span><span class="sxs-lookup"><span data-stu-id="41dd7-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="41dd7-108">Un esempio <xref:System.Span%601>è .</span><span class="sxs-lookup"><span data-stu-id="41dd7-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="41dd7-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41dd7-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="41dd7-110">Byref, inref e outref</span><span class="sxs-lookup"><span data-stu-id="41dd7-110">Byref, inref, and outref</span></span>

<span data-ttu-id="41dd7-111">Ci sono tre `byref`forme di :</span><span class="sxs-lookup"><span data-stu-id="41dd7-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="41dd7-112">`inref<'T>`, un puntatore gestito per la lettura del valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="41dd7-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="41dd7-113">`outref<'T>`, un puntatore gestito per la scrittura nel valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="41dd7-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="41dd7-114">`byref<'T>`, un puntatore gestito per la lettura e la scrittura del valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="41dd7-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="41dd7-115">Un `byref<'T>` può essere `inref<'T>` passato dove è previsto un an.</span><span class="sxs-lookup"><span data-stu-id="41dd7-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="41dd7-116">Analogamente, `byref<'T>` un oggetto `outref<'T>` può essere passato dove è previsto un oggetto.</span><span class="sxs-lookup"><span data-stu-id="41dd7-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="41dd7-117">Utilizzo di byrefsUsing byrefs</span><span class="sxs-lookup"><span data-stu-id="41dd7-117">Using byrefs</span></span>

<span data-ttu-id="41dd7-118">Per utilizzare `inref<'T>`un oggetto , è `&`necessario ottenere un valore del puntatore con :</span><span class="sxs-lookup"><span data-stu-id="41dd7-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="41dd7-119">Per scrivere sul puntatore `outref<'T>` `byref<'T>`utilizzando un oggetto o , è `mutable`inoltre necessario impostare il valore desiderato come puntatore a .</span><span class="sxs-lookup"><span data-stu-id="41dd7-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="41dd7-120">Se si scrive solo il puntatore anziché leggerlo, è consigliabile utilizzare `outref<'T>` anziché `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="41dd7-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="41dd7-121">Semantica di inref</span><span class="sxs-lookup"><span data-stu-id="41dd7-121">Inref semantics</span></span>

<span data-ttu-id="41dd7-122">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="41dd7-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="41dd7-123">Dal punto di vista semantico, ciò significa quanto segue:</span><span class="sxs-lookup"><span data-stu-id="41dd7-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="41dd7-124">Il titolare `x` del puntatore può utilizzarlo solo per leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="41dd7-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="41dd7-125">A tutti `struct` i puntatori acquisiti ai campi annidati all'interno `SomeStruct` viene assegnato il tipo `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="41dd7-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="41dd7-126">Vale anche quanto segue:</span><span class="sxs-lookup"><span data-stu-id="41dd7-126">The following is also true:</span></span>

* <span data-ttu-id="41dd7-127">Non è implicato che altri thread o alias non `x`dispongano dell'accesso in scrittura a .</span><span class="sxs-lookup"><span data-stu-id="41dd7-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="41dd7-128">Non c'è implicazione che `SomeStruct` sia immutabile in virtù di `x` essere un `inref`.</span><span class="sxs-lookup"><span data-stu-id="41dd7-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="41dd7-129">Tuttavia, per i tipi di valore F, che **non sono** modificabili, il `this` puntatore viene dedotto come un `inref`oggetto .</span><span class="sxs-lookup"><span data-stu-id="41dd7-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="41dd7-130">Tutte queste regole insieme significano `inref` che il titolare di un puntatore non può modificare il contenuto immediato della memoria a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="41dd7-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="41dd7-131">Semantica di Outref</span><span class="sxs-lookup"><span data-stu-id="41dd7-131">Outref semantics</span></span>

<span data-ttu-id="41dd7-132">Lo scopo `outref<'T>` di è quello di indicare che il puntatore deve essere scritto solo in.</span><span class="sxs-lookup"><span data-stu-id="41dd7-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="41dd7-133">Inaspettatamente, `outref<'T>` consente di leggere il valore sottostante nonostante il nome.</span><span class="sxs-lookup"><span data-stu-id="41dd7-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="41dd7-134">Questo è a scopo di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="41dd7-134">This is for compatibility purposes.</span></span> <span data-ttu-id="41dd7-135">Dal punto `outref<'T>` di vista `byref<'T>`semantico, non è diverso da .</span><span class="sxs-lookup"><span data-stu-id="41dd7-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="41dd7-136">Interoperabilità con C\#</span><span class="sxs-lookup"><span data-stu-id="41dd7-136">Interop with C\#</span></span>

<span data-ttu-id="41dd7-137">Oltre alle parole `in ref` `out ref` chiave e, `ref` in aggiunta alle parole chiave, Cè supporta le parole chiave e .</span><span class="sxs-lookup"><span data-stu-id="41dd7-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="41dd7-138">Nella tabella seguente viene illustrato il modo in cui F , interpreta ciò che viene generato da C:</span><span class="sxs-lookup"><span data-stu-id="41dd7-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="41dd7-139">Costrutti di C</span><span class="sxs-lookup"><span data-stu-id="41dd7-139">C# construct</span></span>|<span data-ttu-id="41dd7-140">Deduzioni di F</span><span class="sxs-lookup"><span data-stu-id="41dd7-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="41dd7-141">`ref`valore restituito</span><span class="sxs-lookup"><span data-stu-id="41dd7-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="41dd7-142">`ref readonly`valore restituito</span><span class="sxs-lookup"><span data-stu-id="41dd7-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="41dd7-143">Parametro `in ref`.</span><span class="sxs-lookup"><span data-stu-id="41dd7-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="41dd7-144">Parametro `out ref`.</span><span class="sxs-lookup"><span data-stu-id="41dd7-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="41dd7-145">Nella tabella seguente viene illustrato ciò che viene generato da F:</span><span class="sxs-lookup"><span data-stu-id="41dd7-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="41dd7-146">Costrutto F</span><span class="sxs-lookup"><span data-stu-id="41dd7-146">F# construct</span></span>|<span data-ttu-id="41dd7-147">Costrutto Emitted</span><span class="sxs-lookup"><span data-stu-id="41dd7-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="41dd7-148">`inref<'T>` argomento</span><span class="sxs-lookup"><span data-stu-id="41dd7-148">`inref<'T>` argument</span></span>|<span data-ttu-id="41dd7-149">`[In]`attributo sull'argomento</span><span class="sxs-lookup"><span data-stu-id="41dd7-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="41dd7-150">`inref<'T>`Ritorno</span><span class="sxs-lookup"><span data-stu-id="41dd7-150">`inref<'T>` return</span></span>|<span data-ttu-id="41dd7-151">`modreq`attributo sul valore</span><span class="sxs-lookup"><span data-stu-id="41dd7-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="41dd7-152">`inref<'T>`in slot astratto o implementazione</span><span class="sxs-lookup"><span data-stu-id="41dd7-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="41dd7-153">`modreq`sull'argomento o ritorno</span><span class="sxs-lookup"><span data-stu-id="41dd7-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="41dd7-154">`outref<'T>` argomento</span><span class="sxs-lookup"><span data-stu-id="41dd7-154">`outref<'T>` argument</span></span>|<span data-ttu-id="41dd7-155">`[Out]`attributo sull'argomento</span><span class="sxs-lookup"><span data-stu-id="41dd7-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="41dd7-156">Inferenza dei tipi e regole di overloadType inference and overloading rules</span><span class="sxs-lookup"><span data-stu-id="41dd7-156">Type inference and overloading rules</span></span>

<span data-ttu-id="41dd7-157">Un `inref<'T>` tipo viene dedotto dal compilatore F , nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="41dd7-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="41dd7-158">Un parametro .NET o `IsReadOnly` un tipo restituito con un attributo.</span><span class="sxs-lookup"><span data-stu-id="41dd7-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="41dd7-159">Puntatore `this` a un tipo struct senza campi modificabili.</span><span class="sxs-lookup"><span data-stu-id="41dd7-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="41dd7-160">Indirizzo di una posizione di `inref<_>` memoria derivata da un altro puntatore.</span><span class="sxs-lookup"><span data-stu-id="41dd7-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="41dd7-161">Quando viene preso `inref` un indirizzo implicito di un `SomeType` oggetto, un overload con un `inref<SomeType>`argomento di tipo è preferibile a un overload con un argomento di tipo .</span><span class="sxs-lookup"><span data-stu-id="41dd7-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="41dd7-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41dd7-162">For example:</span></span>

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

<span data-ttu-id="41dd7-163">In entrambi i casi, `System.DateTime` gli overload che utilizzano vengono risolti anziché gli overload che utilizzano `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="41dd7-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="41dd7-164">Struct simili a Byref</span><span class="sxs-lookup"><span data-stu-id="41dd7-164">Byref-like structs</span></span>

<span data-ttu-id="41dd7-165">`byref` / `inref` / `outref` Oltre al trio, è possibile definire le proprie strutture `byref`che possono aderire alla semantica -like.</span><span class="sxs-lookup"><span data-stu-id="41dd7-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="41dd7-166">Questa operazione viene <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> eseguita con l'attributo:</span><span class="sxs-lookup"><span data-stu-id="41dd7-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="41dd7-167">`IsByRefLike`non implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="41dd7-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="41dd7-168">Entrambi devono essere presenti nel tipo.</span><span class="sxs-lookup"><span data-stu-id="41dd7-168">Both must be present on the type.</span></span>

<span data-ttu-id="41dd7-169">Uno`byref`struct "-like" in F è un tipo di valore associato allo stack.</span><span class="sxs-lookup"><span data-stu-id="41dd7-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="41dd7-170">Non viene mai allocato nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="41dd7-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="41dd7-171">Un `byref`-like struct è utile per la programmazione ad alte prestazioni, in quanto viene applicato con set di controlli sicuri sulla durata e non acquisizione.</span><span class="sxs-lookup"><span data-stu-id="41dd7-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="41dd7-172">Le regole sono:</span><span class="sxs-lookup"><span data-stu-id="41dd7-172">The rules are:</span></span>

* <span data-ttu-id="41dd7-173">Possono essere utilizzati come parametri di funzione, parametri di metodo, variabili locali, restituisce il metodo.</span><span class="sxs-lookup"><span data-stu-id="41dd7-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="41dd7-174">Non possono essere membri statici o di istanza di una classe o di uno struct normale.</span><span class="sxs-lookup"><span data-stu-id="41dd7-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="41dd7-175">Non possono essere acquisiti`async` da alcun costrutto di chiusura (metodi o espressioni lambda).</span><span class="sxs-lookup"><span data-stu-id="41dd7-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="41dd7-176">Non possono essere utilizzati come parametro generico.</span><span class="sxs-lookup"><span data-stu-id="41dd7-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="41dd7-177">Quest'ultimo punto è fondamentale per la `|>` programmazione in stile pipeline F , così come una funzione generica che parametrizza i relativi tipi di input.</span><span class="sxs-lookup"><span data-stu-id="41dd7-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="41dd7-178">Questa restrizione può `|>` essere rilassata per in futuro, in quanto è inline e non effettua alcuna chiamata a funzioni generiche non inline nel suo corpo.</span><span class="sxs-lookup"><span data-stu-id="41dd7-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="41dd7-179">Sebbene queste regole limitino fortemente l'utilizzo, lo fanno per soddisfare la promessa di calcolo ad alte prestazioni in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="41dd7-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="41dd7-180">Restituzione Byref</span><span class="sxs-lookup"><span data-stu-id="41dd7-180">Byref returns</span></span>

<span data-ttu-id="41dd7-181">I ritorni a capo di Byref da funzioni o membri di F , possono essere prodotti e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="41dd7-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="41dd7-182">Quando si `byref`utilizza un metodo che restituisce, il valore viene dereferenziato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="41dd7-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="41dd7-183">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41dd7-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="41dd7-184">Per restituire un valore byref, la variabile che contiene il valore deve rimanere più lunga dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="41dd7-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="41dd7-185">Inoltre, per restituire byref, utilizzare `&value` (dove value è una variabile che si trova più a lungo dell'ambito corrente).</span><span class="sxs-lookup"><span data-stu-id="41dd7-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="41dd7-186">Per evitare la dereferenziazione implicita, ad `&x` esempio `x` il passaggio di un riferimento tramite più chiamate concatenate, usare (dove è il valore).</span><span class="sxs-lookup"><span data-stu-id="41dd7-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="41dd7-187">È inoltre possibile assegnare `byref`direttamente a un reso .</span><span class="sxs-lookup"><span data-stu-id="41dd7-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="41dd7-188">Si consideri il seguente programma (altamente imperativo):</span><span class="sxs-lookup"><span data-stu-id="41dd7-188">Consider the following (highly imperative) program:</span></span>

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

<span data-ttu-id="41dd7-189">L'output è il seguente.</span><span class="sxs-lookup"><span data-stu-id="41dd7-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="41dd7-190">Definizione dell'ambito per byrefs</span><span class="sxs-lookup"><span data-stu-id="41dd7-190">Scoping for byrefs</span></span>

<span data-ttu-id="41dd7-191">Un `let`valore associato non può avere il riferimento supera l'ambito in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="41dd7-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="41dd7-192">Ad esempio, non è consentito quanto segue:</span><span class="sxs-lookup"><span data-stu-id="41dd7-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="41dd7-193">In questo modo si evita di ottenere risultati diversi a seconda se si esegue la compilazione con ottimizzazioni o meno.</span><span class="sxs-lookup"><span data-stu-id="41dd7-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
