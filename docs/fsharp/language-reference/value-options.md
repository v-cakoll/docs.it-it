---
title: Opzioni Value
description: Informazioni sul tipo F# di opzione value, ovvero una versione struct del tipo di opzione.
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837116"
---
# <a name="value-options"></a><span data-ttu-id="e3ae6-103">Opzioni Value</span><span class="sxs-lookup"><span data-stu-id="e3ae6-103">Value Options</span></span>

<span data-ttu-id="e3ae6-104">Il tipo di opzione valore F# in viene utilizzato quando si verificano le due circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3ae6-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="e3ae6-105">Uno scenario è appropriato per un' [ F# opzione](options.md).</span><span class="sxs-lookup"><span data-stu-id="e3ae6-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="e3ae6-106">L'uso di uno struct offre un vantaggio in merito alle prestazioni nello scenario.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="e3ae6-107">Non tutti gli scenari sensibili alle prestazioni sono "risolti" utilizzando gli struct.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="e3ae6-108">È necessario prendere in considerazione il costo aggiuntivo di copia quando si usano i tipi anziché i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="e3ae6-109">Tuttavia, i F# programmi di grandi dimensioni in genere creano un'istanza di molti tipi facoltativi che passano attraverso percorsi sensibili e, in questi casi, gli struct possono produrre spesso migliori prestazioni complessive per la durata di un programma.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="e3ae6-110">Definizione</span><span class="sxs-lookup"><span data-stu-id="e3ae6-110">Definition</span></span>

<span data-ttu-id="e3ae6-111">L'opzione value è definita come un' [unione discriminata struct](discriminated-unions.md#struct-discriminated-unions) simile al tipo di opzione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="e3ae6-112">La definizione può essere considerata in questo modo:</span><span class="sxs-lookup"><span data-stu-id="e3ae6-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="e3ae6-113">L'opzione value è conforme all'uguaglianza strutturale e al confronto.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="e3ae6-114">La differenza principale consiste nel fatto che il nome compilato, il nome del tipo e i nomi dei case indicano che si tratta di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="e3ae6-115">Uso delle opzioni di valore</span><span class="sxs-lookup"><span data-stu-id="e3ae6-115">Using Value Options</span></span>

<span data-ttu-id="e3ae6-116">Le opzioni relative ai valori vengono usate come le [Opzioni](options.md).</span><span class="sxs-lookup"><span data-stu-id="e3ae6-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="e3ae6-117">`ValueSome` viene utilizzato per indicare che è presente un valore e `ValueNone` viene utilizzato quando non è presente un valore:</span><span class="sxs-lookup"><span data-stu-id="e3ae6-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="e3ae6-118">Come per le [Opzioni](options.md), la convenzione di denominazione per una funzione che restituisce `ValueOption` consiste nel precedere `try`.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="e3ae6-119">Proprietà e metodi delle opzioni di valore</span><span class="sxs-lookup"><span data-stu-id="e3ae6-119">Value Option properties and methods</span></span>

<span data-ttu-id="e3ae6-120">Al momento esiste una proprietà per le opzioni relative al valore: `Value`.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="e3ae6-121">Se non è presente alcun valore quando questa proprietà viene richiamata, viene generata un'<xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="e3ae6-122">Funzioni opzione valore</span><span class="sxs-lookup"><span data-stu-id="e3ae6-122">Value Option functions</span></span>

<span data-ttu-id="e3ae6-123">Il modulo `ValueOption` in FSharp. core contiene funzionalità equivalenti al modulo di `Option`.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-123">The `ValueOption` module in FSharp.Core contains equivalent functionality to the `Option` module.</span></span> <span data-ttu-id="e3ae6-124">Esistono alcune differenze nel nome, ad esempio `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="e3ae6-124">There are a few differences in name, such as `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="e3ae6-125">Questa operazione agisce esattamente come `defaultArg` nel modulo di `Option`, ma agisce invece su un'opzione di valore.</span><span class="sxs-lookup"><span data-stu-id="e3ae6-125">This acts just like `defaultArg` in the `Option` module, but operates on a Value Option instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3ae6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3ae6-126">See also</span></span>

- [<span data-ttu-id="e3ae6-127">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e3ae6-127">Options</span></span>](options.md)
