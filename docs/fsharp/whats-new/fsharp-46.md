---
title: Novità di F# 4,6- F# Guida
description: Ottenere una panoramica delle nuove funzionalità disponibili in F# 4,6.
ms.date: 11/27/2019
ms.openlocfilehash: 620c1edd8ea212fee306a02d5844b6b322808251
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980392"
---
# <a name="whats-new-in-f-46"></a><span data-ttu-id="c216c-103">Novità di F# 4,6</span><span class="sxs-lookup"><span data-stu-id="c216c-103">What's new in F# 4.6</span></span>

<span data-ttu-id="c216c-104">F#4,6 aggiunge più miglioramenti al F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="c216c-104">F# 4.6 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="c216c-105">Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="c216c-105">Get started</span></span>

<span data-ttu-id="c216c-106">F#4,6 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c216c-106">F# 4.6 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="c216c-107">Per ulteriori informazioni, [vedere Introduzione F# ](../get-started/index.md) a.</span><span class="sxs-lookup"><span data-stu-id="c216c-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="anonymous-records"></a><span data-ttu-id="c216c-108">Record anonimi</span><span class="sxs-lookup"><span data-stu-id="c216c-108">Anonymous records</span></span>

<span data-ttu-id="c216c-109">I [record anonimi](../language-reference/anonymous-records.md) sono un nuovo F# tipo di tipo F# introdotto in 4,6.</span><span class="sxs-lookup"><span data-stu-id="c216c-109">[Anonymous records](../language-reference/anonymous-records.md) are a new kind of F# type introduced in F# 4.6.</span></span> <span data-ttu-id="c216c-110">Si tratta di aggregazioni semplici di valori denominati che non devono essere dichiarati prima dell'uso.</span><span class="sxs-lookup"><span data-stu-id="c216c-110">They are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="c216c-111">È possibile dichiararli come struct o tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c216c-111">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="c216c-112">Si tratta di tipi di riferimento per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c216c-112">They're reference types by default.</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="c216c-113">Possono anche essere dichiarati come struct per quando si desidera raggruppare i tipi di valore e funzionano in scenari sensibili alle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="c216c-113">They can also be declared as structs for when you want to group value types and are operating in performance-sensitive scenarios:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="c216c-114">Sono piuttosto potenti e possono essere usati in molti scenari.</span><span class="sxs-lookup"><span data-stu-id="c216c-114">They're quite powerful and can be used in numerous scenarios.</span></span> <span data-ttu-id="c216c-115">Per altre informazioni, vedere [record anonimi](../language-reference/anonymous-records.md).</span><span class="sxs-lookup"><span data-stu-id="c216c-115">Learn more at [Anonymous records](../language-reference/anonymous-records.md).</span></span>

## <a name="valueoption-functions"></a><span data-ttu-id="c216c-116">Funzioni ValueOption</span><span class="sxs-lookup"><span data-stu-id="c216c-116">ValueOption functions</span></span>

<span data-ttu-id="c216c-117">Il tipo ValueOption aggiunto in F# 4,5 dispone ora della "parità di funzione associata al modulo" con il tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="c216c-117">The ValueOption type added in F# 4.5 now has "module-bound function parity" with the Option type.</span></span> <span data-ttu-id="c216c-118">Di seguito sono riportati alcuni esempi di uso più comune:</span><span class="sxs-lookup"><span data-stu-id="c216c-118">Some of the more commonly-used examples are as follows:</span></span>

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> ValueNone
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> ValueSome

let reversedString = strOpt |> ValueOption.bind reverse
```

<span data-ttu-id="c216c-119">Questo consente l'uso di ValueOption come l'opzione negli scenari in cui la presenza di un tipo di valore migliora le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c216c-119">This allows for ValueOption to be used just like Option in scenarios where having a value type improves performance.</span></span>
