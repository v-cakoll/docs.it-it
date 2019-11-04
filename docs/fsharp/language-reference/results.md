---
title: Risultati
description: Informazioni su come usare il F# tipo ' Result ' per semplificare la scrittura di codice a tolleranza di errore.
ms.date: 04/24/2017
ms.openlocfilehash: 187aa26ccbaac7e0ec998756377bb7b0489eb1ab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424844"
---
# <a name="results"></a>Risultati

A partire F# da 4,1, è disponibile un tipo di `Result<'T,'TFailure>` che è possibile usare per la scrittura di codice a tolleranza di errore che può essere composto.

## <a name="syntax"></a>Sintassi

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>Note

Si noti che il tipo di risultato è un' [unione discriminata struct](discriminated-unions.md#struct-discriminated-unions), ovvero un'altra funzionalità F# introdotta in 4,1.  Qui viene applicata la semantica di uguaglianza strutturale.

Il tipo di `Result` viene in genere usato per la gestione di errori monadica, che è spesso detta [programmazione orientata](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) alle ferrovie F# all'interno della community.  Nell'esempio seguente viene illustrato questo approccio.

```fsharp
// Define a simple type which has fields that can be validated
type Request =
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() =
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

Come si può notare, è piuttosto semplice concatenare diverse funzioni di convalida se si impone che tutti restituiscano un `Result`.  In questo modo è possibile suddividere le funzionalità di questo tipo in parti più piccole, che sono componibili in quanto necessarie.  Questo ha anche il valore aggiunto per *applicare l'uso* di [criteri](pattern-matching.md) di ricerca alla fine di un ciclo di convalida, che a sua volta impone un livello superiore di correttezza del programma.

## <a name="see-also"></a>Vedere anche

- [Unioni discriminate](discriminated-unions.md)
- [Criteri di ricerca](pattern-matching.md)
