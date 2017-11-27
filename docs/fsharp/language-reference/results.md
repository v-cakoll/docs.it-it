---
title: 'Risultati (F #)'
description: 'Informazioni su come utilizzare il tipo di ''Generare'' F # per semplificare la scrittura di codice a tolleranza di errore.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: 26478ccfbf88d43c0b194e77d9aacc313515283f
ms.sourcegitcommit: 8d14e8c1b15009330c9880f8523686158924e1a4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2017
---
# <a name="results"></a><span data-ttu-id="c42c9-104">Risultati</span><span class="sxs-lookup"><span data-stu-id="c42c9-104">Results</span></span>

<span data-ttu-id="c42c9-105">A partire da F # 4.1, sussiste un `Result<'T,'TFailure>` tipo che è possibile utilizzare per la scrittura di codice a tolleranza di errore che può essere composte.</span><span class="sxs-lookup"><span data-stu-id="c42c9-105">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="c42c9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c42c9-106">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="c42c9-107">Note</span><span class="sxs-lookup"><span data-stu-id="c42c9-107">Remarks</span></span>

<span data-ttu-id="c42c9-108">Si noti che il tipo di risultato è un [unione discriminata struct](discriminated-unions.md#struct-discriminated-unions), ovvero un'altra funzionalità introdotta in F # 4.1.</span><span class="sxs-lookup"><span data-stu-id="c42c9-108">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="c42c9-109">Semantica di uguaglianza strutturale applicate.</span><span class="sxs-lookup"><span data-stu-id="c42c9-109">Structural equality semantics apply here.</span></span>

<span data-ttu-id="c42c9-110">Il `Result` tipo viene utilizzato in genere monadic gestione degli errori, che viene spesso definito come [programmazione orientata a ferroviario](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) all'interno della community di F #.</span><span class="sxs-lookup"><span data-stu-id="c42c9-110">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="c42c9-111">Questo semplice esempio viene illustrato questo approccio.</span><span class="sxs-lookup"><span data-stu-id="c42c9-111">The following trivial example demonstrates this approach.</span></span>

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
    | String.Empty -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | String.Empty -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> OK req

let validateRequest reqResult =
    reqResult 
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() = 
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (OK req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req1.Name req1.Email
    | Error e -> printfn "Error: %s" e
    // Prints " "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (OK req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req1.Name req1.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="c42c9-112">Come si può notare, è piuttosto semplice concatenare varie funzioni di convalida se si forza il loro tutti per restituire un `Result`.</span><span class="sxs-lookup"><span data-stu-id="c42c9-112">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="c42c9-113">Questo consente di interrompere la funzionalità simile al seguente in porzioni più piccole, ovvero come componibile secondo le esigenze di.</span><span class="sxs-lookup"><span data-stu-id="c42c9-113">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="c42c9-114">Questo è anche il valore aggiunto del *applicazione* l'utilizzo di [criteri di ricerca](pattern-matching.md) alla fine di una sessione di convalida, che a sua volta applica un livello più elevato di correttezza di programma.</span><span class="sxs-lookup"><span data-stu-id="c42c9-114">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="c42c9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c42c9-115">See Also</span></span>

[<span data-ttu-id="c42c9-116">Unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="c42c9-116">Discriminated Unions</span></span>](discriminated-unions.md)

[<span data-ttu-id="c42c9-117">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="c42c9-117">Pattern Matching</span></span>](pattern-matching.md)
