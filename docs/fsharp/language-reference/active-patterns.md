---
title: Criteri attivi
description: 'Informazioni su come utilizzare i criteri attivi per definire partizioni denominate che suddividono i dati di input nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 7b6da38baa35f30ae6de8a930be60a4e4fc0fc0d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493891"
---
# <a name="active-patterns"></a>Criteri attivi

I *criteri attivi* consentono di definire partizioni denominate che suddividono i dati di input, in modo che sia possibile utilizzarli in un'espressione di criteri di ricerca analoga a quella di un'unione discriminata. È possibile usare i criteri attivi per decomporre i dati in modo personalizzato per ogni partizione.

## <a name="syntax"></a>Sintassi

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch = expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a>Osservazioni

Nella sintassi precedente, gli identificatori sono nomi per le partizioni dei dati di input rappresentati da *argomenti*oppure, in altre parole, nomi per subset del set di tutti i valori degli argomenti. In una definizione del criterio attivo possono essere presenti fino a sette partizioni. L' *espressione* descrive il form in cui scomporre i dati. È possibile utilizzare una definizione di criterio attivo per definire le regole per determinare quale delle partizioni denominate appartengono i valori specificati come argomenti. I simboli (| e |) sono denominati *clip di banana* e la funzione creata da questo tipo di associazione let è detta *riconoscimento attivo*.

Si consideri, ad esempio, il criterio attivo seguente con un argomento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

È possibile usare il criterio attivo in un'espressione di criteri di ricerca, come nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

L'output di questo programma è il seguente:

```console
7 is odd
11 is odd
32 is even
```

Un altro uso dei modelli attivi consiste nel scomporre i tipi di dati in diversi modi, ad esempio quando gli stessi dati sottostanti hanno varie rappresentazioni possibili. Ad esempio, un `Color` oggetto può essere scomposto in una rappresentazione RGB o in una rappresentazione HSB.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

L'output del programma precedente è il seguente:

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

In combinazione, queste due modalità di utilizzo dei modelli attivi consentono di partizionare e scomporre i dati nel formato appropriato ed eseguire i calcoli appropriati sui dati appropriati nel formato più pratico per il calcolo.

Le espressioni di criteri di ricerca risultanti consentono di scrivere i dati in modo pratico e leggibile, semplificando notevolmente la creazione di rami e il codice di analisi dei dati.

## <a name="partial-active-patterns"></a>Modelli attivi parziali

In alcuni casi, è necessario partizionare solo una parte dello spazio di input. In tal caso, si scrive un set di modelli parziali ognuno dei quali corrisponde ad alcuni input ma non corrisponde ad altri input. I criteri attivi che non producono sempre un valore sono detti *modelli attivi parziali*. hanno un valore restituito che è un tipo di opzione. Per definire un criterio attivo parziale, è possibile usare un carattere jolly ( \_ ) alla fine dell'elenco di modelli all'interno delle clip a banana. Il codice seguente illustra l'uso di un criterio attivo parziale.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

L'output dell'esempio precedente è il seguente:

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Quando si usano modelli attivi parziali, talvolta le singole scelte possono essere disgiunte o escludono a vicenda, ma non devono esserlo. Nell'esempio seguente, il quadrato del pattern e il cubo del pattern non sono disgiunti, perché alcuni numeri sono sia quadrati che cubi, ad esempio 64. Il programma seguente usa il modello e per combinare i modelli di cubo e quadrato. Vengono stampati tutti i numeri interi fino a 1000 che sono sia quadrati che cubi, oltre a quelli che sono solo cubi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

L'output è il seguente:

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a>Modelli attivi con parametri

I criteri attivi accettano sempre almeno un argomento per l'elemento di cui viene eseguita la corrispondenza, ma possono anche richiedere argomenti aggiuntivi, nel qual caso viene applicato il *criterio attivo con parametri* del nome. Gli argomenti aggiuntivi consentono di specializzare un modello generale. Ad esempio, i modelli attivi che usano espressioni regolari per analizzare le stringhe spesso includono l'espressione regolare come parametro aggiuntivo, come nel codice seguente, che usa anche il criterio attivo parziale `Integer` definito nell'esempio di codice precedente. In questo esempio vengono fornite stringhe che usano espressioni regolari per diversi formati di data per personalizzare il criterio attivo ParseRegex generale. Il criterio attivo Integer viene utilizzato per convertire le stringhe corrispondenti in numeri interi che possono essere passati al costruttore DateTime.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

L'output del codice precedente è il seguente:

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

I criteri attivi non sono limitati solo alle espressioni di criteri di ricerca, ma possono essere usati anche nelle associazioni let.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

L'output del codice precedente è il seguente:

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F #](index.md)
- [Espressioni match](match-expressions.md)
