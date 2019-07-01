---
title: Cos'è F#
description: Informazioni sugli aspetti di F# linguaggio di programmazione è e cosa F# programmazione è ad esempio. Informazioni sui tipi di dati avanzato, funzioni e come interagiscono.
ms.date: 08/03/2018
ms.openlocfilehash: fc4f4db771c43a4ec08cc9d3a247cf1f38e60457
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486837"
---
# <a name="what-is-f"></a><span data-ttu-id="32162-104">Che cos'è F\#</span><span class="sxs-lookup"><span data-stu-id="32162-104">What is F\#</span></span>

<span data-ttu-id="32162-105">F#è un linguaggio di programmazione funzionale che rende più semplice scrivere il codice corretto e facile da gestire.</span><span class="sxs-lookup"><span data-stu-id="32162-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="32162-106">F#programmazione principalmente include la definizione di tipi e funzioni che sono di tipo dedotto e generalizzate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="32162-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="32162-107">In questo modo lo stato attivo deve rimanere nel dominio del problema e la modifica dei dati, piuttosto che i dettagli di programmazione.</span><span class="sxs-lookup"><span data-stu-id="32162-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

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

<span data-ttu-id="32162-108">F#offre numerose funzionalità, tra cui:</span><span class="sxs-lookup"><span data-stu-id="32162-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="32162-109">Sintassi leggera</span><span class="sxs-lookup"><span data-stu-id="32162-109">Lightweight syntax</span></span>
* <span data-ttu-id="32162-110">Non modificabili per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="32162-110">Immutable by default</span></span>
* <span data-ttu-id="32162-111">Generalizzazione automatica e l'inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="32162-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="32162-112">Funzioni di prima classe</span><span class="sxs-lookup"><span data-stu-id="32162-112">First-class functions</span></span>
* <span data-ttu-id="32162-113">Tipi di dati potenti</span><span class="sxs-lookup"><span data-stu-id="32162-113">Powerful data types</span></span>
* <span data-ttu-id="32162-114">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="32162-114">Pattern matching</span></span>
* <span data-ttu-id="32162-115">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="32162-115">Async programming</span></span>

<span data-ttu-id="32162-116">Un set completo di funzionalità sono documentati nel [ F# riferimenti al linguaggio](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="32162-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="32162-117">Tipi di dati avanzati</span><span class="sxs-lookup"><span data-stu-id="32162-117">Rich data types</span></span>

<span data-ttu-id="32162-118">Tipi di dati, ad esempio [record](language-reference/records.md) e [unioni discriminate](language-reference/discriminated-unions.md) consentono di rappresentare dati complessi e domini.</span><span class="sxs-lookup"><span data-stu-id="32162-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

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

<span data-ttu-id="32162-119">F#i record e unioni discriminate sono non null, non modificabile e paragonabile per impostazione predefinita, che lo rendono molto facile da usare.</span><span class="sxs-lookup"><span data-stu-id="32162-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="32162-120">Imposto la correttezza con funzioni e criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="32162-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="32162-121">F#le funzioni sono facili da dichiarare e potenti in pratica.</span><span class="sxs-lookup"><span data-stu-id="32162-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="32162-122">In combinazione con [criteri di ricerca](language-reference/pattern-matching.md), consentono di definire il comportamento viene applicata la cui correttezza dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="32162-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

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

<span data-ttu-id="32162-123">F#le funzioni sono inoltre eccellente, vale a dire possono essere passati come parametri e restituiti da altre funzioni.</span><span class="sxs-lookup"><span data-stu-id="32162-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="32162-124">Funzioni che consentono di definire le operazioni sugli oggetti</span><span class="sxs-lookup"><span data-stu-id="32162-124">Functions to define operations on objects</span></span>

<span data-ttu-id="32162-125">F#include il supporto completo per gli oggetti, ovvero i tipi di dati utili quando è necessario combinare i dati e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="32162-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="32162-126">F#funzioni vengono usate per modificare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="32162-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] 'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="32162-127">Anziché scrivere codice che è orientata agli oggetti, in F#, spesso verrà scritto codice che gestisce gli oggetti come un altro tipo di dati per le funzioni per modificare.</span><span class="sxs-lookup"><span data-stu-id="32162-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="32162-128">Funzionalità, ad esempio [interfacce generiche](language-reference/interfaces.md), [espressioni di oggetto](language-reference/object-expressions.md)e l'uso attento di [membri](language-reference/members/index.md) sono comuni in più grande F# programmi.</span><span class="sxs-lookup"><span data-stu-id="32162-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="32162-129">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="32162-129">Next steps</span></span>

<span data-ttu-id="32162-130">Per altre informazioni su un set più ampio di F# funzionalità, consultare i [ F# presentazione](tour.md).</span><span class="sxs-lookup"><span data-stu-id="32162-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
