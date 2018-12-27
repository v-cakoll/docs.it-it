---
title: Risultati
description: Informazioni su come usare il F# 'Result' digitare che consentono di scrivere codice a tolleranza di errore.
ms.date: 04/24/2017
ms.openlocfilehash: 8b419412b406018a21f2c23103c8193fec8766f2
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612712"
---
# <a name="results"></a>Risultati

A partire da F# 4.1, è presente un `Result<'T,'TFailure>` tipo di cui è possibile usare per la scrittura di codice a tolleranza di errore che può essere creato.

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

Si noti che il tipo di risultato è un [unione discriminata di struct](discriminated-unions.md#struct-discriminated-unions), che è un'altra funzionalità introdotta in F# 4.1.  Vengono applicate la semantica di uguaglianza strutturale.

Il `Result` tipo viene generalmente utilizzato in monadic gestione degli errori, che è noto anche come [programmazione orientata ad ferroviarie](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) all'interno di F# della community.  L'esempio di semplice seguente illustra questo approccio.

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

Come può notare, è piuttosto semplice concatenare diverse funzioni di convalida se si forza vengano tutte restituite una `Result`.  Questo consente di interrompere la funzionalità simile al seguente in porzioni più piccole che sono componibili come necessari in qualsiasi momento per essere.  Ciò ha anche il valore aggiunto del *applicando* l'uso di [criteri di ricerca](pattern-matching.md) alla fine di un ciclo di convalida, che a sua volta applica un livello più elevato della correttezza del programma.

## <a name="see-also"></a>Vedere anche

- [Unioni discriminate](discriminated-unions.md)
- [Criteri di ricerca](pattern-matching.md)