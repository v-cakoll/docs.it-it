---
title: Che cos'èF#
description: Informazioni sugli aspetti di F# linguaggio di programmazione è e cosa F# programmazione è ad esempio. Informazioni sui tipi di dati avanzato, funzioni e come interagiscono.
ms.date: 08/03/2018
ms.openlocfilehash: ea82147e4e6d3c980fb224eeafd805c7ed53f8f2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966959"
---
# <a name="what-is-f"></a>Che cos'è F\#

F#è un linguaggio di programmazione funzionale che rende più semplice scrivere il codice corretto e facile da gestire.

F#programmazione principalmente include la definizione di tipi e funzioni che sono di tipo dedotto e generalizzate automaticamente. In questo modo lo stato attivo deve rimanere nel dominio del problema e la modifica dei dati, piuttosto che i dettagli di programmazione.

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

F#offre numerose funzionalità, tra cui:

* Sintassi leggera
* Non modificabili per impostazione predefinita
* Generalizzazione automatica e l'inferenza del tipo
* Funzioni di prima classe
* Tipi di dati potenti
* Criteri di ricerca
* Programmazione asincrona

Un set completo di funzionalità sono documentati nel [ F# riferimenti al linguaggio](language-reference/index.md).

## <a name="rich-data-types"></a>Tipi di dati avanzati

Tipi di dati, ad esempio [record](language-reference/records.md) e [unioni discriminate](language-reference/discriminated-unions.md) consentono di rappresentare dati complessi e domini.

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

F#i record e unioni discriminate sono non null, non modificabile e paragonabile per impostazione predefinita, che lo rendono molto facile da usare.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Imposto la correttezza con funzioni e criteri di ricerca

F#le funzioni sono facili da dichiarare e potenti in pratica. In combinazione con [criteri di ricerca](language-reference/pattern-matching.md), consentono di definire il comportamento viene applicata la cui correttezza dal compilatore.

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

F#le funzioni sono inoltre eccellente, vale a dire possono essere passati come parametri e restituiti da altre funzioni.

## <a name="functions-to-define-operations-on-objects"></a>Funzioni che consentono di definire le operazioni sugli oggetti

F#include il supporto completo per gli oggetti, ovvero i tipi di dati utili quando è necessario combinare i dati e funzionalità. F#funzioni vengono usate per modificare gli oggetti.

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
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

Anziché scrivere codice che è orientata agli oggetti, in F#, spesso verrà scritto codice che gestisce gli oggetti come un altro tipo di dati per le funzioni per modificare. Funzionalità, ad esempio [interfacce generiche](language-reference/interfaces.md), [espressioni di oggetto](language-reference/object-expressions.md)e l'uso attento di [membri](language-reference/members/index.md) sono comuni in più grande F# programmi.

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni su un set più ampio di F# funzionalità, consultare i [ F# presentazione](tour.md).