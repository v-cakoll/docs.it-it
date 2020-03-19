---
title: Criteri attivi
description: Informazioni su come usare i modelli attivi per definire le partizioni denominate che suddividono i dati di input nel linguaggio di programmazione F .
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187065"
---
# <a name="active-patterns"></a>Criteri attivi

*I modelli attivi* consentono di definire partizioni denominate che suddividono i dati di input, in modo da poter utilizzare questi nomi in un'espressione di criteri di ricerca come per un'unione discriminata. È possibile usare i criteri attivi per decomporre i dati in modo personalizzato per ogni partizione.

## <a name="syntax"></a>Sintassi

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a>Osservazioni

Nella sintassi precedente, gli identificatori sono nomi per le partizioni dei dati di input rappresentati da *argomenti*o, in altre parole, i nomi per i sottoinsiemi del set di tutti i valori degli argomenti. In una definizione di modello attivo possono essere presenti fino a sette partizioni. *L'espressione* descrive la forma in cui scomporre i dati. È possibile usare una definizione di modello attivo per definire le regole per determinare a quali partizioni denominate appartengono i valori assegnati come argomenti. I simboli (sezione e ) sono detti clip di *banana* e la funzione creata da questo tipo di rilegatura let è chiamata *sistema di riconoscimento attivo.*

Ad esempio, si consideri il seguente modello attivo con un argomento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

È possibile utilizzare il modello attivo in un'espressione di criteri di ricerca, come nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

L'output di questo programma è il seguente:

```console
7 is odd
11 is odd
32 is even
```

Un altro utilizzo dei modelli attivi consiste nel scomporre i tipi di dati in più modi, ad esempio quando gli stessi dati sottostanti hanno diverse rappresentazioni possibili. Ad esempio, `Color` un oggetto può essere scomposto in una rappresentazione RGB o HSB.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

L'output del programma di cui sopra è il seguente:

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

In combinazione, questi due modi di utilizzare i modelli attivi consentono di partizionare e scomporre i dati nel formato appropriato ed eseguire i calcoli appropriati sui dati appropriati nella forma più conveniente per il calcolo.

Le espressioni di criteri di ricerca risultanti consentono di scrivere i dati in modo pratico e molto leggibile e che semplifica notevolmente il codice di analisi dei dati e di diramazione potenzialmente complesso.

## <a name="partial-active-patterns"></a>Modelli attivi parziali

A volte, è necessario partizionare solo una parte dello spazio di input. In tal caso, si scrive un set di modelli parziali ognuno dei quali corrisponde ad alcuni input ma non corrisponde ad altri input. I modelli attivi che non sempre producono un valore sono detti *modelli attivi parziali*; hanno un valore restituito che è un tipo di opzione. Per definire un modello attivo parziale,\_si utilizza un carattere jolly ( ) alla fine dell'elenco dei motivi all'interno delle clip di banana. Il codice seguente illustra l'uso di un modello attivo parziale.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

L'output dell'esempio precedente è il seguente:

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Quando si usano modelli attivi parziali, a volte le singole scelte possono essere disgiunte o che si escludono a vicenda, ma non è necessario esserlo. Nell'esempio seguente, il modello Square e il modello Cube non sono disgiunti, perché alcuni numeri sono entrambi quadrati e cubi, ad esempio 64. Il programma seguente utilizza il modello AND per combinare i modelli Square e Cube. Stampa tutti i numeri interi fino a 1000 che sono sia quadrati che cubi, così come quelli che sono solo cubi.

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

## <a name="parameterized-active-patterns"></a>Modelli attivi con parametriParameterized Active Patterns

I modelli attivi accettano sempre almeno un argomento per l'elemento corrispondente, ma possono accettare anche argomenti aggiuntivi, nel qual caso si applica il *modello attivo* con parametri name. Argomenti aggiuntivi consentono di specializzata in un modello generale. Ad esempio, i modelli attivi che usano espressioni regolari per analizzare le stringhe spesso includono l'espressione `Integer` regolare come parametro aggiuntivo, come nel codice seguente, che usa anche il modello attivo parziale definito nell'esempio di codice precedente. In questo esempio vengono fornite stringhe che utilizzano espressioni regolari per vari formati di data per personalizzare il modello attivo ParseRegex generale. Il modello attivo Integer viene utilizzato per convertire le stringhe corrispondenti in numeri interi che possono essere passati al costruttore DateTime.The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

L'output del codice precedente è il seguente:

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

I modelli attivi non sono limitati solo alle espressioni di criteri di ricerca, è anche possibile usarli nelle let-bindings.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

L'output del codice precedente è il seguente:

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento al linguaggio F](index.md)
- [Espressioni match](match-expressions.md)
