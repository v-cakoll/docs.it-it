---
title: Opzioni di valori
description: Scopri la F# tipo di opzione di valore, ovvero una versione di uno struct di tipo di opzione.
ms.date: 06/16/2018
ms.openlocfilehash: d5209e620d53e12e9344faea09321f640af21491
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613427"
---
# <a name="value-options"></a>Opzioni di valori

Il tipo di opzione del valore in F# viene utilizzato per contengono i seguenti due casi:

1. Uno scenario è appropriato per un [ F# opzione](options.md).
2. Usando un tipo struct offre un miglioramento delle prestazioni nel proprio scenario.

Non tutti gli scenari sensibili alle prestazioni sono "risolto" utilizzo di struct. È necessario considerare il costo aggiuntivo di copia quando vengono utilizzati invece i tipi di riferimento. Tuttavia, grande F# programmi comunemente creare molti tipi facoltativi che passano attraverso i percorsi critici, perché struct in alcuni casi possono produrre migliori prestazioni complessive in base alla durata di un programma.

## <a name="definition"></a>Definizione

Opzione valore viene definito come un [unione discriminata di struct](discriminated-unions.md#struct-discriminated-unions) che è simile al tipo di opzione di riferimento. In questo modo può essere considerata la relativa definizione:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Opzione valore conforme a confronto e uguaglianza strutturale. La differenza principale è che il nome compilato, nome del tipo e tutti i nomi dei casi a indicare che si tratta di un tipo di valore.

## <a name="using-value-options"></a>Utilizzo delle opzioni di valore

Opzioni di valore vengono utilizzate allo stesso modo [opzioni](options.md). `ValueSome` viene utilizzato per indicare che un valore è presente, e `ValueNone` viene usato quando non è presente un valore:

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

Come per gli [le opzioni](options.md), la convenzione di denominazione per una funzione che restituisce `ValueOption` consiste nel prefisso `try`.

## <a name="value-option-properties-and-methods"></a>Valore opzione proprietà e metodi

Al momento non è una proprietà per le opzioni di valore: `Value`. Un <xref:System.InvalidOperationException> viene generata se nessun valore è presente quando viene richiamata questa proprietà.

## <a name="value-option-functions"></a>Funzioni con valori di opzione

È attualmente disponibile una funzione associata al modulo per le opzioni di valore, `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

Come con la `defaultArg` funzione, `defaultValueArg` restituisce il valore sottostante dell'opzione di valore specificato se presente; in caso contrario, restituisce il valore predefinito specificato.

In questo momento, non sono presenti altre funzioni associata al modulo per le opzioni di valore.

## <a name="see-also"></a>Vedere anche

- [Opzioni](options.md)