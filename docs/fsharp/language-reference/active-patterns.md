---
title: Modelli attivi (F#)
description: 'Informazioni su come usare i criteri attivi per definire partizioni denominate che suddividono i dati di input nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4fb7d3e2b9c7e6f1c1ed9d64a47728c7f40017c8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204812"
---
# <a name="active-patterns"></a>Criteri attivi

*Criteri attivi* consentono di definire partizioni denominate che suddividono i dati di input, in modo che è possibile usare questi nomi in un criterio di corrispondenza espressione esattamente come si farebbe per un'unione discriminata. È possibile usare i criteri attivi per decomporre i dati in modo personalizzato per ogni partizione.

## <a name="syntax"></a>Sintassi

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>Note

Nella sintassi precedente, gli identificatori sono nomi per le partizioni dei dati di input che sono rappresentati da *argomenti*, o, in altre parole, i nomi per i subset del set di tutti i valori degli argomenti. In una definizione di criterio attivo possono essere presenti fino a sette partizioni. Il *espressione* descrive la forma in cui si desidera scomporre i dati. È possibile usare una definizione di criterio attivo per definire le regole per determinare quali partizioni denominate i valori forniti come argomenti appartengono a. I (| e |) i simboli sono dette *banana clip* e viene chiamata la funzione creata da questo tipo di binding "Let" un' *riconoscimento active*.

Ad esempio, prendere in considerazione il seguente criterio attivo con un argomento.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

È possibile usare il modello attivo in un criterio di corrispondenza espressione, come nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

Come indicato di seguito è riportato l'output di questo programma:

```
7 is odd
11 is odd
32 is even
```

Viene utilizzato un altro di criteri attivi per decomporre i tipi di dati in diversi modi, ad esempio quando gli stessi dati sottostanti dispongono di diverse rappresentazioni possibili. Ad esempio, un `Color` oggetto può essere scomposto in una rappresentazione RGB o in una rappresentazione HSB.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

Come indicato di seguito è riportato l'output del programma precedente:

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

In combinazione, queste due modalità di utilizzo dei modelli attivi consentono alla partizione e decomporre i dati nel proprio form appropriato ed eseguire i calcoli appropriati sui dati appropriati nella forma più semplice per il calcolo.

Le espressioni di corrispondenza risultante abilitare dati da scrivere in un modo pratico che è molto leggibili, semplificando notevolmente la diramazione potenzialmente complesso e il codice di analisi di dati.

## <a name="partial-active-patterns"></a>Criteri attivi parziali

In alcuni casi, è necessario partizionare solo una parte dello spazio di input. In tal caso, è scrivere un set di modelli parziali, ognuno dei quali corrisponde a una serie di dati e non agli altri input. Criteri attivi che non producono sempre un valore sono detti *parziali modelli attivi*; hanno un valore restituito che è un tipo di opzione. Per definire un modello attivo parziale, si utilizza un carattere jolly (\_) alla fine dell'elenco di modelli interni banana clip. Il codice seguente illustra l'uso di un modello attivo parziale.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

Come indicato di seguito è riportato l'output dell'esempio precedente:

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Quando si usano i modelli attivi parziali, in alcuni casi le singole scelte possono essere contigui o si escludono a vicenda, ma non è necessario. Nell'esempio seguente, il quadrato di modello e il modello di cubo non sono non contigui, perché alcuni numeri sono entrambi quadrati e cubi, ad esempio 64. Il seguente programma stampa tutti i numeri interi fino a 1000000 quadrati e i cubi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

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

Criteri attivi hanno sempre almeno un argomento per l'elemento di soddisfazione, ma possono accettare argomenti aggiuntivi, nel qual caso il nome *con parametri (modello attivo)* si applica. Argomenti aggiuntivi consentono un modello generale essere specializzata. Ad esempio, i modelli attivi che usano le espressioni regolari per analizzare le stringhe spesso includono l'espressione regolare come parametro aggiuntivo, come nel codice seguente, che usa anche il modello attivo parziale `Integer` definito nell'esempio di codice precedente. In questo esempio, le stringhe che utilizzano le espressioni regolari per i diversi formati di data vengono fornite per personalizzare l'attivo generale ParseRegex. Consente di convertire le stringhe corrispondenti in numeri interi che possono essere passati al costruttore DateTime (modello attivo) l'intero.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

Come indicato di seguito è riportato l'output del codice precedente:

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Criteri attivi non sono limitati solo a espressioni corrispondente con il criterio, è possibile usare anche nelle ti permettono di associazioni.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

Come indicato di seguito è riportato l'output del codice precedente:

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Espressioni match](match-expressions.md)
