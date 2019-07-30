---
title: Cos'è F#
description: Informazioni sul linguaggio di F# programmazione e sulla F# programmazione di questo tipo. Informazioni sui tipi di dati avanzati, sulle funzioni e sul modo in cui si integrano.
ms.date: 08/03/2018
ms.openlocfilehash: 0c576fe49fadebd68e4fc9d2b20ea8f0cb991af5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630452"
---
# <a name="what-is-f"></a>Che cos'è F\#

F#è un linguaggio di programmazione funzionale che semplifica la scrittura di codice corretto e gestibile.

F#la programmazione comporta principalmente la definizione di tipi e funzioni che vengono dedotti e generalizzati automaticamente. Ciò consente di rimanere concentrati sul dominio del problema e di manipolarne i dati, anziché i dettagli della programmazione.

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

F#dispone di numerose funzionalità, tra cui:

* Sintassi leggera
* Non modificabile per impostazione predefinita
* Inferenza del tipo e generalizzazione automatica
* Funzioni di prima classe
* Tipi di dati avanzati
* Criteri di ricerca
* Programmazione asincrona

Un set completo di funzionalità è documentato nelle informazioni di [ F# riferimento sul linguaggio](./language-reference/index.md).

## <a name="rich-data-types"></a>Tipi di dati avanzati

I tipi di dati, ad esempio i [record](./language-reference/records.md) e le [unioni discriminate](./language-reference/discriminated-unions.md) , consentono di rappresentare dati complessi e domini.

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

F#i record e le unioni discriminate sono non null, non modificabili e confrontabili per impostazione predefinita, rendendoli molto facili da utilizzare.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Applicare la correttezza alle funzioni e ai criteri di ricerca

F#le funzioni sono facili da dichiarare e potenti in pratica. In [combinazione con i](./language-reference/pattern-matching.md)criteri di ricerca, consentono di definire il comportamento la cui correttezza viene applicata dal compilatore.

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

F#anche le funzioni sono di prima classe, ovvero possono essere passate come parametri e restituite da altre funzioni.

## <a name="functions-to-define-operations-on-objects"></a>Funzioni per la definizione di operazioni sugli oggetti

F#dispone del supporto completo per gli oggetti, che sono tipi di dati utili quando è necessario combinare dati e funzionalità. F#le funzioni vengono usate per modificare gli oggetti.

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

Anziché scrivere codice orientato a oggetti, in F#, spesso si scrive codice che considera gli oggetti come un altro tipo di dati per le funzioni da modificare. Le funzionalità come le [interfacce generiche](./language-reference/interfaces.md), le [espressioni di oggetti](./language-reference/object-expressions.md)e l'utilizzo oculato dei [membri](./language-reference/members/index.md) sono comuni nei programmi più grandi F# .

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni su un set di F# funzionalità più ampio, vedere la [ F# presentazione](tour.md).
