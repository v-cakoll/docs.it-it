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
# <a name="whats-new-in-f-46"></a>Novità di F# 4,6

F#4,6 aggiunge più miglioramenti al F# linguaggio.

## <a name="get-started"></a>Attività iniziali

F#4,6 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio. Per ulteriori informazioni, [vedere Introduzione F# ](../get-started/index.md) a.

## <a name="anonymous-records"></a>Record anonimi

I [record anonimi](../language-reference/anonymous-records.md) sono un nuovo F# tipo di tipo F# introdotto in 4,6. Si tratta di aggregazioni semplici di valori denominati che non devono essere dichiarati prima dell'uso. È possibile dichiararli come struct o tipi di riferimento. Si tratta di tipi di riferimento per impostazione predefinita.

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

Possono anche essere dichiarati come struct per quando si desidera raggruppare i tipi di valore e funzionano in scenari sensibili alle prestazioni:

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

Sono piuttosto potenti e possono essere usati in molti scenari. Per altre informazioni, vedere [record anonimi](../language-reference/anonymous-records.md).

## <a name="valueoption-functions"></a>Funzioni ValueOption

Il tipo ValueOption aggiunto in F# 4,5 dispone ora della "parità di funzione associata al modulo" con il tipo di opzione. Di seguito sono riportati alcuni esempi di uso più comune:

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

Questo consente l'uso di ValueOption come l'opzione negli scenari in cui la presenza di un tipo di valore migliora le prestazioni.
