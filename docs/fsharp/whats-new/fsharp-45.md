---
title: Novità di F# 4,5- F# Guida
description: Ottenere una panoramica delle nuove funzionalità disponibili in F# 4,5.
ms.date: 11/27/2019
ms.openlocfilehash: b699165125d345ad783b24da8a0a994cba72d4ba
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715694"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="03748-103">Novità di F# 4,5</span><span class="sxs-lookup"><span data-stu-id="03748-103">What's new in F# 4.5</span></span>

<span data-ttu-id="03748-104">F#4,5 aggiunge più miglioramenti al F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="03748-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="03748-105">Molte di queste funzionalità sono state aggiunte insieme per consentire di scrivere codice efficiente in F# garantendo al tempo stesso la sicurezza del codice.</span><span class="sxs-lookup"><span data-stu-id="03748-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="03748-106">In questo modo si aggiungono alcuni concetti al linguaggio e una quantità significativa di analisi del compilatore quando si usano questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="03748-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="03748-107">Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="03748-107">Get started</span></span>

<span data-ttu-id="03748-108">F#4,5 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="03748-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="03748-109">Per ulteriori informazioni, [vedere Introduzione F# ](../get-started/index.md) a.</span><span class="sxs-lookup"><span data-stu-id="03748-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="03748-110">Struct di span e di tipo ByRef</span><span class="sxs-lookup"><span data-stu-id="03748-110">Span and byref-like structs</span></span>

<span data-ttu-id="03748-111">Il tipo di <xref:System.Span%601> introdotto in .NET Core consente di rappresentare i buffer in memoria in modo fortemente tipizzato, che ora è consentito in F# a partire da F# 4,5.</span><span class="sxs-lookup"><span data-stu-id="03748-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="03748-112">Nell'esempio seguente viene illustrato come è possibile riutilizzare una funzione che opera su un <xref:System.Span%601> con diverse rappresentazioni del buffer:</span><span class="sxs-lookup"><span data-stu-id="03748-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="03748-113">Un aspetto importante è che span e altri struct di [tipo ByRef](../language-reference/structures.md#byreflike-structs) hanno un'analisi statica molto rigida eseguita dal compilatore che limitano l'utilizzo in modi che potrebbero risultare imprevisti.</span><span class="sxs-lookup"><span data-stu-id="03748-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="03748-114">Questo è il compromesso fondamentale tra prestazioni, espressività e sicurezza introdotta in F# 4,5.</span><span class="sxs-lookup"><span data-stu-id="03748-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="03748-115">ByRef rinnovati</span><span class="sxs-lookup"><span data-stu-id="03748-115">Revamped byrefs</span></span>

<span data-ttu-id="03748-116">Prima del F# 4,5, le [ByRef](../language-reference/byrefs.md) in F# non erano sicure e non erano valide per numerose applicazioni.</span><span class="sxs-lookup"><span data-stu-id="03748-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="03748-117">Sono stati risolti i problemi di sonorità relativi F# ai byref in 4,5 e viene applicata la stessa analisi statica eseguita per gli struct span e di tipo ByRef.</span><span class="sxs-lookup"><span data-stu-id="03748-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="03748-118">inref < t > e outref <' t ></span><span class="sxs-lookup"><span data-stu-id="03748-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="03748-119">Per rappresentare la nozione di un puntatore gestito di sola lettura, di sola scrittura e di lettura/scrittura F# , 4,5 introduce i tipi di `inref<'T>``outref<'T>` per rappresentare rispettivamente i puntatori di sola lettura e di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="03748-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="03748-120">Ognuna con una semantica diversa.</span><span class="sxs-lookup"><span data-stu-id="03748-120">Each have different semantics.</span></span> <span data-ttu-id="03748-121">Ad esempio, non è possibile scrivere in un `inref<'T>`:</span><span class="sxs-lookup"><span data-stu-id="03748-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="03748-122">Per impostazione predefinita, l'inferenza del tipo dedurrà i puntatori gestiti come `inref<'T>` essere in linea con la F# natura non modificabile del codice, a meno che un elemento non sia già stato dichiarato come modificabile.</span><span class="sxs-lookup"><span data-stu-id="03748-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="03748-123">Per rendere scrivibile un elemento, è necessario dichiarare un tipo come `mutable` prima di passare il relativo indirizzo a una funzione o a un membro che lo manipola.</span><span class="sxs-lookup"><span data-stu-id="03748-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="03748-124">Per ulteriori informazioni, vedere [ByRef](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="03748-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="03748-125">Struct di sola lettura</span><span class="sxs-lookup"><span data-stu-id="03748-125">Readonly structs</span></span>

<span data-ttu-id="03748-126">A partire F# da 4,5, è possibile aggiungere annotazioni a uno struct con <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> di questo tipo:</span><span class="sxs-lookup"><span data-stu-id="03748-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="03748-127">Ciò impedisce di dichiarare un membro modificabile nello struct e di emettere metadati che consentono F# e C# di considerarli come ReadOnly quando vengono utilizzati da un assembly.</span><span class="sxs-lookup"><span data-stu-id="03748-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="03748-128">Per altre informazioni, vedere [struct](../language-reference/structures.md#readonly-structs)di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="03748-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="03748-129">Puntatori void</span><span class="sxs-lookup"><span data-stu-id="03748-129">Void pointers</span></span>

<span data-ttu-id="03748-130">Il tipo di `voidptr` viene aggiunto F# a 4,5, così come le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="03748-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="03748-131">`NativePtr.ofVoidPtr` convertire un puntatore void in un puntatore int nativo</span><span class="sxs-lookup"><span data-stu-id="03748-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="03748-132">`NativePtr.toVoidPtr` convertire un puntatore int nativo in un puntatore void</span><span class="sxs-lookup"><span data-stu-id="03748-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="03748-133">Questa operazione è utile quando si interopera con un componente nativo che utilizza i puntatori void.</span><span class="sxs-lookup"><span data-stu-id="03748-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="03748-134">Parola chiave `match!`</span><span class="sxs-lookup"><span data-stu-id="03748-134">The `match!` keyword</span></span>

<span data-ttu-id="03748-135">La parola chiave `match!` ottimizza i criteri di ricerca all'interno di un'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="03748-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="03748-136">In questo modo è possibile abbreviare il codice che spesso include opzioni di combinazione, o altri tipi, con espressioni di calcolo come Async.</span><span class="sxs-lookup"><span data-stu-id="03748-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="03748-137">Per altre informazioni, vedere [match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="03748-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="03748-138">Requisiti di multicast più rilassati nelle espressioni array, List e Sequence</span><span class="sxs-lookup"><span data-stu-id="03748-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="03748-139">Quando si combinano i tipi in cui è possibile ereditare da un altro oggetto all'interno delle espressioni array, List e Sequence, è necessario eseguire il cast di tutti i tipi derivati nel tipo padre con `:>` o `upcast`.</span><span class="sxs-lookup"><span data-stu-id="03748-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="03748-140">Questo aspetto è ora rilassato, illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="03748-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="03748-141">Rilassamento dei rientri per le espressioni di matrici ed elenchi</span><span class="sxs-lookup"><span data-stu-id="03748-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="03748-142">Prima del F# 4,5, era necessario rientrare eccessivamente le espressioni di matrici ed elenchi quando venivano passati come argomenti alle chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="03748-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="03748-143">Questa operazione non è più necessaria:</span><span class="sxs-lookup"><span data-stu-id="03748-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting = 
    System.Console.WriteLine(format="{0}", arg = [| 
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
