---
title: Opzioni Value
description: Informazioni sul tipo F# di opzione value, ovvero una versione struct del tipo di opzione.
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424012"
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

È attualmente disponibile una funzione associata al modulo per le opzioni relative ai valori, `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

Come per la funzione `defaultArg`, `defaultValueArg` restituisce il valore sottostante dell'opzione del valore specificato, se esistente. in caso contrario, restituisce il valore predefinito specificato.

Attualmente non sono disponibili altre funzioni associate al modulo per le opzioni relative ai valori.

## <a name="see-also"></a>Vedere anche

- [Opzioni](options.md)
