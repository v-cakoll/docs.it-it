---
title: Funzioni di prima classe
description: Informazioni sulle funzioni di prima classe e su come sono importanti per la programmazione funzionale F#in.
ms.date: 10/29/2018
ms.openlocfilehash: 4681d32abd59cc4aade6f4cb2d062e7888bcfbbc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629722"
---
# <a name="first-class-functions"></a>Funzioni di prima classe

Una caratteristica che definisce i linguaggi di programmazione funzionale è l'elevazione delle funzioni allo stato di prima classe. Si dovrebbe essere in grado di eseguire questa operazione con una funzione con i valori degli altri tipi incorporati ed è possibile eseguire questa operazione con un grado di impegno analogo.

Di seguito sono riportate le misure tipiche dello stato di prima classe:

- È possibile associare funzioni agli identificatori? Ovvero, è possibile assegnare loro i nomi?

- È possibile archiviare funzioni in strutture di dati, ad esempio in un elenco?

- È possibile passare una funzione come argomento in una chiamata di funzione?

- È possibile restituire una funzione da una chiamata di funzione?

Le ultime due misure definiscono quelle note come *operazioni di ordine superiore* o *funzioni di ordine superiore*. Le funzioni di ordine superiore accettano funzioni come argomenti e restituiscono funzioni come valore delle chiamate di funzione. Queste operazioni supportano tali pilastri della programmazione funzionale come funzioni di mapping e composizione di funzioni.

## <a name="give-the-value-a-name"></a>Assegnare un nome al valore

Se una funzione è un valore di prima classe, è necessario essere in grado di denominarlo, così come è possibile denominare numeri interi, stringhe e altri tipi incorporati. Questa operazione viene definita in letteratura sulla programmazione funzionale come associazione di un identificatore a un valore. F#`let <identifier> = <value>`USA [ `let` i binding](../language-reference/functions/let-bindings.md) per associare i nomi ai valori:. Nel codice seguente vengono illustrati due esempi.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet20.fs)]

È possibile assegnare un nome semplice a una funzione. Nell'esempio seguente viene definita una funzione `squareIt` denominata associando l' `squareIt` identificatore all' [espressione](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`lambda. La `squareIt` funzione ha un parametro `n`,, e restituisce il quadrato di tale parametro.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

F#fornisce la sintassi più concisa seguente per ottenere lo stesso risultato con minore digitazione.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet22.fs)]

Gli esempi che seguono prevalentemente usano il primo `let <function-name> = <lambda-expression>`stile,, per evidenziare le analogie tra la dichiarazione di funzioni e la dichiarazione di altri tipi di valori. Tuttavia, tutte le funzioni denominate possono anche essere scritte con la sintassi concisa. Alcuni esempi sono scritti in entrambi i modi.

## <a name="store-the-value-in-a-data-structure"></a>Archiviare il valore in una struttura di dati

Un valore di prima classe può essere archiviato in una struttura di dati. Nel codice seguente vengono illustrati esempi in cui vengono archiviati i valori negli elenchi e nelle Tuple.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet23.fs)]

Per verificare che un nome di funzione archiviato in una tupla restituisca effettivamente una funzione, nell'esempio seguente vengono utilizzati `fst` gli `snd` operatori e per estrarre il primo e il secondo elemento `funAndArgTuple`dalla tupla. Il primo elemento della tupla è `squareIt` e il secondo elemento è `num`. L' `num` identificatore è associato in un esempio precedente a un numero intero 10, un argomento `squareIt` valido per la funzione. La seconda espressione applica il primo elemento della tupla al secondo elemento della tupla: `squareIt num`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet24.fs)]

Allo stesso modo, così `num` come l'identificatore e il numero intero 10 possono essere usati in modo `squareIt` interscambiabile `fun n -> n * n`, quindi possono essere identificati ed espressioni lambda.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a>Passare il valore come argomento

Se un valore ha uno stato di prima classe in un linguaggio, è possibile passarlo come argomento a una funzione. Ad esempio, è normale passare numeri interi e stringhe come argomenti. Il codice seguente illustra i numeri interi e le stringhe passate F#come argomenti in.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet26.fs)]

Se le funzioni hanno uno stato di prima classe, è necessario essere in grado di passarle come argomenti nello stesso modo. Tenere presente che si tratta della prima caratteristica delle funzioni di ordine superiore.

Nell'esempio seguente la funzione `applyIt` ha due parametri, `op` e `arg`. Se si invia in una funzione che include un parametro per `op` e un argomento appropriato per la funzione a `arg`, la funzione restituisce il risultato dell'applicazione `op` di `arg`a. Nell'esempio seguente, sia l'argomento della funzione che l'argomento integer vengono inviati nello stesso modo, usando i rispettivi nomi.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet27.fs)]

La possibilità di inviare una funzione come argomento a un'altra funzione si basa sulle astrazioni comuni nei linguaggi di programmazione funzionale, ad esempio le operazioni di mapping o filtro. Un'operazione di mapping, ad esempio, è una funzione di ordine superiore che acquisisce il calcolo condiviso dalle funzioni che eseguono un elenco, eseguono un'operazione a ogni elemento e quindi restituiscono un elenco dei risultati. Potrebbe essere necessario incrementare ogni elemento in un elenco di numeri interi o per quadrare ogni elemento o per modificare ogni elemento di un elenco di stringhe in lettere maiuscole. La parte soggetta a errori del calcolo è il processo ricorsivo che scorre l'elenco e compila un elenco dei risultati da restituire. Tale parte viene acquisita nella funzione di mapping. È necessario scrivere solo per una particolare applicazione, ovvero la funzione che si desidera applicare singolarmente a ogni elemento dell'elenco (aggiunta, quadratura, modifica di maiuscole e minuscole). Questa funzione viene inviata come argomento alla funzione di mapping, così come `squareIt` viene inviata a `applyIt` nell'esempio precedente.

F#fornisce metodi di mapping per la maggior parte dei tipi di raccolta, inclusi [elenchi](../language-reference/lists.md), [matrici](../language-reference/arrays.md)e [sequenze](../language-reference/sequences.md). Negli esempi seguenti vengono utilizzati gli elenchi. La sintassi è `List.map <the function> <the list>`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet28.fs)]

Per ulteriori informazioni, vedere la pagina relativa agli [elenchi](../language-reference/lists.md).

## <a name="return-the-value-from-a-function-call"></a>Restituire il valore da una chiamata di funzione

Infine, se una funzione ha uno stato di prima classe in un linguaggio, è necessario essere in grado di restituirla come valore di una chiamata di funzione, proprio come si restituiscono altri tipi, ad esempio numeri interi e stringhe.

La funzione seguente chiama i valori integer e li Visualizza.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet29.fs)]

La seguente chiamata di funzione restituisce una stringa.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet30.fs)]

La chiamata di funzione seguente, dichiarata inline, restituisce un valore booleano. Il valore visualizzato è `True`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet31.fs)]

La possibilità di restituire una funzione come valore di una chiamata di funzione è la seconda caratteristica delle funzioni di ordine superiore. Nell'esempio `checkFor` seguente viene definito come una funzione che accetta un argomento, `item`, e restituisce una nuova funzione come valore. La funzione restituita accetta un elenco come argomento, `lst`, e `item` Cerca in `lst`. Se `item` è presente, la funzione restituisce `true`. Se `item` non è presente, la funzione restituisce `false`. Come nella sezione precedente, il codice seguente usa una funzione List specificata, [List. Exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), per eseguire la ricerca nell'elenco.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

Il codice seguente usa `checkFor` per creare una nuova funzione che accetta un argomento, un elenco e cerca 7 nell'elenco.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet33.fs)]

Nell'esempio seguente viene utilizzato lo stato di prima classe delle funzioni F# in per dichiarare una funzione `compose`,, che restituisce una composizione di due argomenti della funzione.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> Per una versione ancora più breve, vedere la sezione seguente, "funzioni sottoposte a currying".

Il codice seguente invia due funzioni come argomenti a `compose`, entrambe che accettano un solo argomento dello stesso tipo. Il valore restituito è una nuova funzione che è una composizione dei due argomenti della funzione.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> F#fornisce due operatori, `<<` e `>>`, che compongono funzioni. Ad esempio, `let squareAndDouble2 = doubleIt << squareIt` è equivalente a `let squareAndDouble = compose doubleIt squareIt` nell'esempio precedente.

Nell'esempio seguente di restituzione di una funzione come valore di una chiamata di funzione viene creato un semplice gioco di indovinare. Per creare un gioco, chiamare `makeGame` con il valore per `target`il quale si vuole che un utente possa indovinare. Il valore restituito dalla funzione `makeGame` è una funzione che accetta un argomento (l'ipotesi) e indica se l'ipotesi è corretta.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet36.fs)]

Il codice seguente chiama `makeGame`, inviando il `7` valore `target`per. Identificatore `playGame` associato all'espressione lambda restituita. Pertanto, `playGame` è una funzione che accetta come un solo argomento un valore per `guess`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a>Funzioni sottoposte a currying

Molti degli esempi della sezione precedente possono essere scritti in modo più conciso sfruttando il *currying* implicito nelle F# dichiarazioni di funzione. Il currying è un processo che trasforma una funzione con più di un parametro in una serie di funzioni incorporate, ognuna con un solo parametro. In F#le funzioni che dispongono di più di un parametro sono intrinsecamente sottoposte a currying. È ad esempio `compose` possibile scrivere nella sezione precedente, come illustrato nel seguente stile conciso, con tre parametri.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet38.fs)]

Tuttavia, il risultato è una funzione di un parametro che restituisce una funzione di un parametro che a sua volta restituisce un'altra funzione di un parametro, come `compose4curried`illustrato in.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet39.fs)]

È possibile accedere a questa funzione in diversi modi. Ognuno degli esempi seguenti restituisce e visualizza 18. È possibile sostituire `compose4` con `compose4curried` in uno degli esempi.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet40.fs)]

Per verificare che la funzione continui a funzionare come in precedenza, provare a eseguire nuovamente i test case originali.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> È possibile limitare il currying racchiudendo i parametri nelle Tuple. Per ulteriori informazioni, vedere "modelli di parametro" in [parametri e argomenti](../language-reference/parameters-and-arguments.md).

Nell'esempio seguente viene usato il currying implicito per scrivere una versione `makeGame`più breve di. I dettagli del modo `makeGame` in cui i costrutti `game` e restituiscono la funzione sono meno espliciti in questo formato, ma è possibile verificare usando i test case originali che il risultato è lo stesso.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet42.fs)]

Per ulteriori informazioni sul currying, vedere la sezione relativa all'applicazione parziale degli argomenti nelle [funzioni](../language-reference/functions/index.md).

## <a name="identifier-and-function-definition-are-interchangeable"></a>L'identificatore e la definizione di funzione sono intercambiabili

Il nome `num` della variabile negli esempi precedenti restituisce il numero intero 10 e non è sorprendente che la posizione `num` sia valida, 10 è anche valida. Lo stesso vale per gli identificatori di funzione e i relativi valori: ovunque sia possibile usare il nome della funzione, è possibile usare l'espressione lambda a cui è associata.

Nell'esempio seguente viene definita `Boolean` una funzione `isNegative`denominata, quindi vengono utilizzati in modo intercambiabile il nome della funzione e la definizione della funzione. I tre esempi successivi restituiscono e visualizzano `False`tutti.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet43.fs)]

Per eseguire un'ulteriore operazione, sostituire il valore `applyIt` associato a per. `applyIt`

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>Le funzioni sono valori di prima classe in F\#

Gli esempi nelle sezioni precedenti dimostrano che le F# funzioni in soddisfano i criteri per i valori di F#prima classe in:

- È possibile associare un identificatore a una definizione di funzione.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

- È possibile archiviare una funzione in una struttura di dati.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet45.fs)]

- È possibile passare una funzione come argomento.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet46.fs)]

- È possibile restituire una funzione come valore di una chiamata di funzione.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

Per ulteriori informazioni su F#, vedere le [ F# ](../language-reference/index.md)informazioni di riferimento sul linguaggio.

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Il codice seguente contiene tutti gli esempi in questo argomento.

### <a name="code"></a>Codice

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a>Vedere anche

- [Elenchi](../language-reference/lists.md)
- [Tuple](../language-reference/tuples.md)
- [Funzioni](../language-reference/functions/index.md)
- [`let`Associazioni](../language-reference/functions/let-bindings.md)
- [Espressioni lambda: Parola chiave `fun`](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
