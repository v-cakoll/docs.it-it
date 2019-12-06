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
# <a name="value-options"></a>Opzioni Value

Il tipo di opzione valore F# in viene utilizzato quando si verificano le due circostanze seguenti:

1. Uno scenario è appropriato per un' [ F# opzione](options.md).
2. L'uso di uno struct offre un vantaggio in merito alle prestazioni nello scenario.

Non tutti gli scenari sensibili alle prestazioni sono "risolti" utilizzando gli struct. È necessario prendere in considerazione il costo aggiuntivo di copia quando si usano i tipi anziché i tipi di riferimento. Tuttavia, i F# programmi di grandi dimensioni in genere creano un'istanza di molti tipi facoltativi che passano attraverso percorsi sensibili e, in questi casi, gli struct possono produrre spesso migliori prestazioni complessive per la durata di un programma.

## <a name="definition"></a>Definizione

L'opzione value è definita come un' [unione discriminata struct](discriminated-unions.md#struct-discriminated-unions) simile al tipo di opzione di riferimento. La definizione può essere considerata in questo modo:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

L'opzione value è conforme all'uguaglianza strutturale e al confronto. La differenza principale consiste nel fatto che il nome compilato, il nome del tipo e i nomi dei case indicano che si tratta di un tipo di valore.

## <a name="using-value-options"></a>Uso delle opzioni di valore

Le opzioni relative ai valori vengono usate come le [Opzioni](options.md). `ValueSome` viene utilizzato per indicare che è presente un valore e `ValueNone` viene utilizzato quando non è presente un valore:

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

Come per le [Opzioni](options.md), la convenzione di denominazione per una funzione che restituisce `ValueOption` consiste nel precedere `try`.

## <a name="value-option-properties-and-methods"></a>Proprietà e metodi delle opzioni di valore

Al momento esiste una proprietà per le opzioni relative al valore: `Value`. Se non è presente alcun valore quando questa proprietà viene richiamata, viene generata un'<xref:System.InvalidOperationException>.

## <a name="value-option-functions"></a>Funzioni opzione valore

Il modulo `ValueOption` in FSharp. core contiene funzionalità equivalenti al modulo di `Option`. Esistono alcune differenze nel nome, ad esempio `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

Questa operazione agisce esattamente come `defaultArg` nel modulo di `Option`, ma agisce invece su un'opzione di valore.

## <a name="see-also"></a>Vedere anche

- [Opzioni](options.md)
