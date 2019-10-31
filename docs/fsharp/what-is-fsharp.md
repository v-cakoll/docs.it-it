---
title: Cos'è F#
description: Informazioni sul linguaggio di programmazione F# e sulla programmazione di questo tipo. Informazioni sui tipi di dati avanzati, sulle funzioni e sul modo in cui si integrano.
ms.date: 08/03/2018
ms.openlocfilehash: 3cba509f59a8e81e1a0264de7451e9d80304d768
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332727"
---
# <a name="what-is-f"></a><span data-ttu-id="caa42-104">Che cos'è F @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="caa42-104">What is F\#</span></span>

<span data-ttu-id="caa42-105">F# è un linguaggio di programmazione funzionale che semplifica la scrittura di codice corretto e mantenibile.</span><span class="sxs-lookup"><span data-stu-id="caa42-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="caa42-106">La programmazione in F# comporta principalmente la definizione di tipi e funzioni che vengono automaticamente inferiti e generalizzati.</span><span class="sxs-lookup"><span data-stu-id="caa42-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="caa42-107">Ciò consente di rimanere concentrati sul dominio del problema e sulla manipolazione dei dati, anziché sui dettagli della programmazione.</span><span class="sxs-lookup"><span data-stu-id="caa42-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="caa42-108">F# dispone di numerose funzionalità, tra cui:</span><span class="sxs-lookup"><span data-stu-id="caa42-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="caa42-109">Sintassi leggera</span><span class="sxs-lookup"><span data-stu-id="caa42-109">Lightweight syntax</span></span>
* <span data-ttu-id="caa42-110">Immutabile per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="caa42-110">Immutable by default</span></span>
* <span data-ttu-id="caa42-111">Inferenza dei tipi e generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="caa42-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="caa42-112">Funzioni di prima classe</span><span class="sxs-lookup"><span data-stu-id="caa42-112">First-class functions</span></span>
* <span data-ttu-id="caa42-113">Tipi di dati avanzati</span><span class="sxs-lookup"><span data-stu-id="caa42-113">Powerful data types</span></span>
* <span data-ttu-id="caa42-114">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="caa42-114">Pattern matching</span></span>
* <span data-ttu-id="caa42-115">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="caa42-115">Async programming</span></span>

<span data-ttu-id="caa42-116">L'insieme completo delle funzionalità è documentato nella [Guida di riferimento del linguaggio F#](./language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="caa42-116">A full set of features are documented in the [F# language reference](./language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="caa42-117">Tipi di dati avanzati</span><span class="sxs-lookup"><span data-stu-id="caa42-117">Rich data types</span></span>

<span data-ttu-id="caa42-118">I tipi di dati, ad esempio i [record](./language-reference/records.md) e le [unioni discriminate](./language-reference/discriminated-unions.md), consentono di rappresentare dati e domini complessi.</span><span class="sxs-lookup"><span data-stu-id="caa42-118">Data types such as [Records](./language-reference/records.md) and [Discriminated Unions](./language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="caa42-119">I record F# e le unioni discriminate sono non null, non modificabili e confrontabili per impostazione predefinita, rendendoli molto facili da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="caa42-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="caa42-120">Applicare la correttezza alle funzioni e ai criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="caa42-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="caa42-121">Le funzioni F# sono facili da dichiarare e potenti nella pratica.</span><span class="sxs-lookup"><span data-stu-id="caa42-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="caa42-122">In combinazione con i [criteri di ricerca](./language-reference/pattern-matching.md), consentono di definire un comportamento la cui correttezza viene verificata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="caa42-122">When combined with [pattern matching](./language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="caa42-123">Anche le funzioni F# sono di prima classe, ovvero possono essere passate come parametri e restituite da altre funzioni.</span><span class="sxs-lookup"><span data-stu-id="caa42-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="caa42-124">Funzioni per definire operazioni sugli oggetti</span><span class="sxs-lookup"><span data-stu-id="caa42-124">Functions to define operations on objects</span></span>

<span data-ttu-id="caa42-125">F# dispone del supporto completo per gli oggetti, che sono tipi di dati utili quando è necessario combinare dati e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="caa42-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="caa42-126">Le funzioni F# vengono usate per modificare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="caa42-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="caa42-127">Anziché scrivere codice orientato a oggetti, in F# spesso si scrive codice che considera gli oggetti semplicemente come un altro tipo di dati modificabili dalle funzioni.</span><span class="sxs-lookup"><span data-stu-id="caa42-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="caa42-128">Funzionalità come le [interfacce generiche](./language-reference/interfaces.md), le [espressioni di oggetti](./language-reference/object-expressions.md) e l'utilizzo oculato dei [membri](./language-reference/members/index.md) sono comuni nei programmi F# più grandi.</span><span class="sxs-lookup"><span data-stu-id="caa42-128">Features such as [generic interfaces](./language-reference/interfaces.md), [object expressions](./language-reference/object-expressions.md), and judicious use of [members](./language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="caa42-129">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="caa42-129">Next steps</span></span>

<span data-ttu-id="caa42-130">Per informazioni su un insieme più ampio di funzionalità, vedere la [Panoramica di F#](tour.md).</span><span class="sxs-lookup"><span data-stu-id="caa42-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
