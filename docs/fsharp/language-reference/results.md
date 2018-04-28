---
title: 'Risultati (F #)'
description: "Informazioni su come utilizzare il tipo di 'Generare' F # per semplificare la scrittura di codice a tolleranza di errore."
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 35fd1d3b1590291e18aa28460cf5939606c21d3a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="results"></a>Risultati

A partire da F # 4.1, sussiste un `Result<'T,'TFailure>` tipo che è possibile utilizzare per la scrittura di codice a tolleranza di errore che può essere composte.

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

Si noti che il tipo di risultato è un [unione discriminata struct](discriminated-unions.md#struct-discriminated-unions), ovvero un'altra funzionalità introdotta in F # 4.1.  Semantica di uguaglianza strutturale applicate.

Il `Result` tipo viene utilizzato in genere monadic gestione degli errori, che viene spesso definito come [programmazione orientata a ferroviario](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) all'interno della community di F #.  Questo semplice esempio viene illustrato questo approccio.

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

Come si può notare, è piuttosto semplice concatenare varie funzioni di convalida se si forza il loro tutti per restituire un `Result`.  Questo consente di interrompere la funzionalità simile al seguente in porzioni più piccole, ovvero come componibile secondo le esigenze di.  Questo è anche il valore aggiunto del *applicazione* l'utilizzo di [criteri di ricerca](pattern-matching.md) alla fine di una sessione di convalida, che a sua volta applica un livello più elevato di correttezza di programma.

## <a name="see-also"></a>Vedere anche

[Unioni discriminate](discriminated-unions.md)

[Criteri di ricerca](pattern-matching.md)
