---
title: Novità di F . 4.5 - Guida di F
description: Ottenere una panoramica delle nuove funzionalità disponibili in F .
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186127"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="4225d-103">Novità di F .</span><span class="sxs-lookup"><span data-stu-id="4225d-103">What's new in F# 4.5</span></span>

<span data-ttu-id="4225d-104">Il linguaggio F .</span><span class="sxs-lookup"><span data-stu-id="4225d-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="4225d-105">Molte di queste funzionalità sono state aggiunte insieme per consentire di scrivere codice efficiente in F , garantendo al contempo che questo codice sia sicuro.</span><span class="sxs-lookup"><span data-stu-id="4225d-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="4225d-106">In questo modo significa aggiungere alcuni concetti al linguaggio e una quantità significativa di analisi del compilatore quando si utilizzano questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="4225d-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="4225d-107">Introduzione</span><span class="sxs-lookup"><span data-stu-id="4225d-107">Get started</span></span>

<span data-ttu-id="4225d-108">Il linguaggio F . 4.5 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4225d-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="4225d-109">Per altre informazioni, [iniziare a usare F.](../get-started/index.md)</span><span class="sxs-lookup"><span data-stu-id="4225d-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="4225d-110">Span e struct simili a byref</span><span class="sxs-lookup"><span data-stu-id="4225d-110">Span and byref-like structs</span></span>

<span data-ttu-id="4225d-111">Il <xref:System.Span%601> tipo introdotto in .NET Core consente di rappresentare i buffer in memoria in modo fortemente tipizzato, che è ora consentito in F , a partire da F .</span><span class="sxs-lookup"><span data-stu-id="4225d-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="4225d-112">L'esempio seguente mostra come riutilizzare una <xref:System.Span%601> funzione che opera su un con diverse rappresentazioni del buffer:The following example shows how you can re-use a function operating on a with different buffer representations:</span><span class="sxs-lookup"><span data-stu-id="4225d-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

<span data-ttu-id="4225d-113">Un aspetto importante è che Span e altri struct di [tipo byref](../language-reference/structures.md#byreflike-structs) hanno un'analisi statica molto rigida eseguita dal compilatore che ne limitano l'utilizzo in modi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="4225d-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="4225d-114">Questo è il compromesso fondamentale tra prestazioni, espressività e sicurezza che viene introdotto in F .</span><span class="sxs-lookup"><span data-stu-id="4225d-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="4225d-115">Rinnovato darefs</span><span class="sxs-lookup"><span data-stu-id="4225d-115">Revamped byrefs</span></span>

<span data-ttu-id="4225d-116">Prima della versione 4.5, [i Byref](../language-reference/byrefs.md) in F , erano non sicuri e non sono stati validi per numerose applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4225d-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="4225d-117">Problemi di solidità intorno byrefs sono stati risolti in F .</span><span class="sxs-lookup"><span data-stu-id="4225d-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="4225d-118">inref<'T> e outref<'T></span><span class="sxs-lookup"><span data-stu-id="4225d-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="4225d-119">Per rappresentare la nozione di puntatore gestito di sola lettura, di sola scrittura `inref<'T>` `outref<'T>` e di lettura/scrittura, in Fè 4.5 vengono introdotti rispettivamente i tipi , per rappresentare puntatori di sola lettura e di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="4225d-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="4225d-120">Ognuno ha una semantica diversa.</span><span class="sxs-lookup"><span data-stu-id="4225d-120">Each have different semantics.</span></span> <span data-ttu-id="4225d-121">Ad esempio, non è `inref<'T>`possibile scrivere in un:</span><span class="sxs-lookup"><span data-stu-id="4225d-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="4225d-122">Per impostazione predefinita, l'inferenza `inref<'T>` del tipo dedurrà i puntatori gestiti come in linea con la natura non modificabile del codice F , a meno che qualcosa non sia già stato dichiarato modificabile.</span><span class="sxs-lookup"><span data-stu-id="4225d-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="4225d-123">Per rendere un elemento scrivibile, è necessario `mutable` dichiarare un tipo come prima di passare il relativo indirizzo a una funzione o membro che lo modifica.</span><span class="sxs-lookup"><span data-stu-id="4225d-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="4225d-124">Per ulteriori informazioni, vedere [Byrefs](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="4225d-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="4225d-125">Strutture Readonly</span><span class="sxs-lookup"><span data-stu-id="4225d-125">Readonly structs</span></span>

<span data-ttu-id="4225d-126">A partire da F . <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute></span><span class="sxs-lookup"><span data-stu-id="4225d-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="4225d-127">Ciò impedisce di dichiarare un membro modificabile nella struttura e genera metadati che consentono a F e C , di considerarlo come readonly quando utilizzato da un assembly.</span><span class="sxs-lookup"><span data-stu-id="4225d-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="4225d-128">Per ulteriori informazioni, consultate [Structs ReadOnly](../language-reference/structures.md#readonly-structs).</span><span class="sxs-lookup"><span data-stu-id="4225d-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="4225d-129">Puntatori Void</span><span class="sxs-lookup"><span data-stu-id="4225d-129">Void pointers</span></span>

<span data-ttu-id="4225d-130">Il `voidptr` tipo viene aggiunto a F .</span><span class="sxs-lookup"><span data-stu-id="4225d-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="4225d-131">`NativePtr.ofVoidPtr`per convertire un puntatore void in un puntatore int nativo</span><span class="sxs-lookup"><span data-stu-id="4225d-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="4225d-132">`NativePtr.toVoidPtr`per convertire un puntatore int nativo in un puntatore void</span><span class="sxs-lookup"><span data-stu-id="4225d-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="4225d-133">Ciò è utile quando si interagisce con un componente nativo che utilizza puntatori void.</span><span class="sxs-lookup"><span data-stu-id="4225d-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="4225d-134">Parola chiave `match!`</span><span class="sxs-lookup"><span data-stu-id="4225d-134">The `match!` keyword</span></span>

<span data-ttu-id="4225d-135">La `match!` parola chiave migliora la corrispondenza dei criteri di ricerca all'interno di un'espressione di calcolo:The keyword enhances pattern matching when inside a computation expression:</span><span class="sxs-lookup"><span data-stu-id="4225d-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

<span data-ttu-id="4225d-136">Ciò consente di abbreviare il codice che spesso comporta la combinazione di opzioni (o altri tipi) con espressioni di calcolo, ad esempio async.</span><span class="sxs-lookup"><span data-stu-id="4225d-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="4225d-137">Per saperne di più, vedi [match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="4225d-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="4225d-138">Requisiti di upcast rilassati nelle espressioni di matrice, elenco e sequenza</span><span class="sxs-lookup"><span data-stu-id="4225d-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="4225d-139">La combinazione di tipi in cui uno può ereditare da un'altra all'interno di espressioni `:>` `upcast`di matrice, elenco e sequenza ha tradizionalmente richiesto l'upcast di qualsiasi tipo derivato al relativo tipo padre con o .</span><span class="sxs-lookup"><span data-stu-id="4225d-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="4225d-140">Questo è ora rilassato, dimostrato come segue:</span><span class="sxs-lookup"><span data-stu-id="4225d-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="4225d-141">Rilassamento del rientro per le espressioni di matrice ed elenco</span><span class="sxs-lookup"><span data-stu-id="4225d-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="4225d-142">Prima della versione 4.5 di F, era necessario applicare un rientro eccessivo alle espressioni di matrice ed elenco quando vengono passate come argomenti alle chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="4225d-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="4225d-143">Questo non è più necessario:</span><span class="sxs-lookup"><span data-stu-id="4225d-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
