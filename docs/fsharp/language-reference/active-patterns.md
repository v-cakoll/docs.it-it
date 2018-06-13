---
title: Modelli attivi (F#)
description: 'Informazioni su come usare i criteri attivi per definire partizioni denominate che suddividono i dati di input nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b8c3270b1efbeb3495ac69bf1217fddf8a5a73e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564446"
---
# <a name="active-patterns"></a>Criteri attivi

*Criteri attivi* consentono di definire partizioni denominate che suddividono i dati di input, in modo che è possibile utilizzare questi nomi in un'espressione di corrispondenza dei modelli come se trattasse di un'unione discriminata. È possibile usare i criteri attivi per decomporre i dati in modo personalizzato per ogni partizione.


## <a name="syntax"></a>Sintassi

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>Note
Nella sintassi precedente, gli identificatori sono nomi per le partizioni di dati di input sono rappresentati da *argomenti*, o, in altre parole, i nomi per sottoinsiemi del set di tutti i valori degli argomenti. In una definizione di tipo (modello attivo) possono essere presenti fino a sette partizioni. Il *espressione* descrive il form in cui scomporre i dati. È possibile utilizzare una definizione (modello attivo) per definire le regole per determinare quali partizioni denominate i valori forniti come argomenti appartengono a. Il (| e |) i simboli sono detti *banana clip* e viene chiamata la funzione creata da questo tipo di associazione consentono un *riconoscimento attivo*.

Ad esempio, si consideri il seguente (modello attivo) con un argomento.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

È possibile utilizzare il modello attivo in un'espressione, come nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

L'output di questo programma è come segue:

```
7 is odd
11 is odd
32 is even
```

Viene utilizzato un altro di criteri attivi per scomporre i tipi di dati in più modi, ad esempio quando gli stessi dati sottostanti dispongono di varie rappresentazioni possibili. Ad esempio, un `Color` oggetto può essere scomposta in una rappresentazione RGB o in una rappresentazione HSB.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

L'output del programma precedente è come segue:

```
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

In combinazione, queste due modalità di utilizzo di criteri attivi consentono di partizione e scomporre i dati in formato appena appropriato ed eseguire i calcoli appropriati sui dati appropriati nella forma più semplice per il calcolo.

Le espressioni di corrispondenza risultante abilitare dati deve essere scritto in un modo pratico è molto leggibili, semplificando notevolmente la diramazione potenzialmente complesse e codice di analisi di dati.


## <a name="partial-active-patterns"></a>Criteri attivi parziali
In alcuni casi, è necessario partizionare solo una parte dello spazio di input. In tal caso, scrivere un set di modelli parziali, ognuno dei quali corrisponde alcuni input ma non altri input. Criteri attivi che non producono sempre un valore sono detti *criteri attivi parziali*; hanno un valore restituito è un tipo di opzione. Per definire un modello attivo parziale, utilizzare un carattere jolly (_) alla fine dell'elenco di modelli interni banana clip. Il codice seguente viene illustrato l'utilizzo di un modello attivo parziale.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

L'output dell'esempio precedente è come segue:

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Quando si utilizza criteri attivi parziali, talvolta singole scelte possono essere contigui o si escludono a vicenda, ma è necessario. Nell'esempio seguente, il criterio Square e il modello di cubo non sono non contigui, perché alcuni numeri sono quadrati e cubi, ad esempio 64. Il seguente programma stampa tutti i valori interi fino a 1000000 quadrati e cubi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

L'output è indicato di seguito:

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a>Criteri attivi con parametri
Modelli attivi accettano sempre almeno un argomento per l'elemento viene cercata la corrispondenza, ma possono accettare argomenti aggiuntivi nonché, nel qual caso il nome *con parametri (modello attivo)* si applica. Gli argomenti aggiuntivi consentono un criterio generale specializzati. Ad esempio, i criteri attivi che usano espressioni regolari per analizzare le stringhe spesso includono l'espressione regolare come parametro aggiuntivo, come illustrato nel codice seguente, che utilizza anche il modello attivo parziale `Integer` definito nell'esempio di codice precedente. In questo esempio, le stringhe che utilizzano espressioni regolari per vari formati di data vengono fornite per personalizzare l'attivo generale ParseRegex. Il modello attivo Integer viene utilizzato per convertire le stringhe corrispondenti in numeri interi che possono essere passati al costruttore DateTime.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

L'output del codice precedente è come segue:

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Criteri attivi non sono limitati solo a espressioni di corrispondenza di schema, è possibile utilizzare anche in consentono di associazioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

L'output del codice precedente è come segue:

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Espressioni match](match-expressions.md)

