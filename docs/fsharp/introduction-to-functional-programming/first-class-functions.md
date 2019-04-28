---
title: Funzioni di prima classe
description: Informazioni sulle funzioni di prima classe e come sono importanti per la programmazione funzionale in F#.
ms.date: 10/29/2018
ms.openlocfilehash: 505ad686614b53d779cb617fc04ac74c2a88b31b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772762"
---
# <a name="first-class-functions"></a>Funzioni di prima classe

Delle caratteristiche peculiari dei linguaggi di programmazione funzionale sono l'elevazione delle funzioni di prima qualità. Dovrebbe essere possibile eseguire con una funzione qualsiasi è possibile eseguire con i valori degli altri tipi predefiniti e in grado di eseguire questa operazione con un livello paragonabile di impegno.

Le misure tipiche dello stato di prima classe includono quanto segue:

- È possibile associare funzioni agli identificatori? Vale a dire, può è assegnare loro nomi?

- È possibile archiviare funzioni in strutture di dati, ad esempio in un elenco?

- È possibile passare una funzione come argomento in una chiamata di funzione?

- È possibile restituire una funzione da una chiamata di funzione?

Le ultime due misure definiscono i cosiddetti *operazioni di ordine superiore* oppure *funzioni di ordine superiore*. Funzioni di ordine superiore accettano funzioni come argomenti e restituiscono funzioni come valore di chiamate di funzione. Queste operazioni supportano fondamenti della programmazione funzionale come mapping di funzioni e composizione di funzioni.

## <a name="give-the-value-a-name"></a>Assegnare il valore di un nome

Se una funzione è un valore di prima classe, è necessario essere in grado di assegnare un nome, così come è possibile assegnare valori interi, stringhe e altri tipi predefiniti. Questa è definita nella letteratura di programmazione funzionale come associazione di un identificatore a un valore. F#viene utilizzato [ `let` associazioni](../language-reference/functions/let-bindings.md) per associare i nomi ai valori: `let <identifier> = <value>`. Il codice seguente illustra due esempi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

È possibile denominare una funzione con la stessa semplicità. L'esempio seguente definisce una funzione denominata `squareIt` associando l'identificatore `squareIt` per il [espressione lambda](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`. Funzione `squareIt` dispone di un parametro `n`, e restituisce il quadrato di tale parametro.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

F#sono disponibili le seguenti sintassi più concisa per ottenere lo stesso risultato più rapido.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

Gli esempi che seguono principalmente utilizzano il primo stile, `let <function-name> = <lambda-expression>`per evidenziare le analogie tra la dichiarazione di funzioni e la dichiarazione di altri tipi di valori. Tuttavia, tutte le funzioni denominate possono anche essere scritti con la sintassi concisa. Alcuni esempi sono scritti in entrambe le direzioni.

## <a name="store-the-value-in-a-data-structure"></a>Il valore in una struttura di Data Store

Un valore di prima classe può essere archiviato in una struttura di dati. Il codice seguente illustra esempi in cui archiviano i valori negli elenchi e Tuple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

Per verificare che il nome di una funzione archiviato in una tupla restituisce in effetti una funzione, l'esempio seguente usa il `fst` e `snd` operatori per estrarre il primo e secondo elemento di tupla `funAndArgTuple`. È il primo elemento della tupla `squareIt` e il secondo elemento è `num`. Identificatore `num` è associato in un esempio precedente all'intero 10, un argomento valido per il `squareIt` (funzione). La seconda espressione si applica il primo elemento della tupla per il secondo elemento della tupla: `squareIt num`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

Analogamente, come identificatore `num` e intero 10 può essere usato in modo intercambiabile, pertanto, possibile identifier `squareIt` ed espressione lambda `fun n -> n * n`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a>Passare il valore come argomento

Se un valore ha lo stato di prima classe in un linguaggio, è possibile passarlo come argomento a una funzione. Ad esempio, è comune passare stringhe e numeri interi come argomenti. Il codice seguente mostra numeri interi e stringhe passate come argomenti in F#.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

Se le funzioni dispone dello stato di prima classe, è necessario essere in grado di passarle come argomenti nello stesso modo. Tenere presente che questa è la prima caratteristica delle funzioni di ordine superiore.

Nell'esempio seguente, funzionare `applyIt` ha due parametri, `op` e `arg`. Se invia una funzione che ha un parametro per `op` e un argomento appropriato per la funzione `arg`, la funzione restituisce il risultato dell'applicazione `op` a `arg`. Nell'esempio seguente, l'argomento della funzione sia l'argomento integer vengono inviati nello stesso modo, tramite i relativi nomi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

Possibilità di inviare una funzione come argomento a un'altra funzione sottostante astrazioni comuni nei linguaggi di programmazione funzionale, ad esempio operazioni mappa o un filtro. Un'operazione di mappa, ad esempio, è una funzione di ordine superiore che acquisisce il calcolo condiviso dalle funzioni che scorrere un elenco, eseguono un'operazione su ogni elemento e quindi restituiscono un elenco dei risultati. È possibile incrementare ogni elemento in un elenco di numeri interi, o al quadrato di ogni elemento o per modificare ogni elemento in un elenco di stringhe in lettere maiuscole. La parte del calcolo tendenti all'errore è il processo ricorsivo che scorre l'elenco e compila un elenco dei risultati da restituire. Tale parte viene acquisita nella funzione di mapping. Tutto è necessario scrivere per una particolare applicazione è la funzione che si desidera applicare singolarmente a ogni elemento di elenco (aggiunta, elevazione al quadrato, modificare maiuscole e minuscole). Che funzione viene inviata come argomento alla funzione di mapping, altrettanto `squareIt` viene inviato a `applyIt` nell'esempio precedente.

F#fornisce metodi di mapping per la maggior parte dei tipi di raccolta, inclusi [sono elencati](../language-reference/lists.md), [matrici](../language-reference/arrays.md), e [sequenze](../language-reference/sequences.md). Gli esempi seguenti usano gli elenchi. La sintassi è `List.map <the function> <the list>`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

Per altre informazioni, vedere [Elenca](../language-reference/lists.md).

## <a name="return-the-value-from-a-function-call"></a>Il valore restituito da una chiamata di funzione

Infine, se una funzione ha lo stato di prima classe in un linguaggio, è necessario essere in grado di restituire come valore di una chiamata di funzione, così come è restituire altri tipi, ad esempio numeri interi che stringhe.

Le chiamate di funzione seguenti restituiscono numeri interi e visualizzarli.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

La seguente chiamata di funzione restituisce una stringa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

La seguente chiamata di funzione, dichiarate come inline, restituisce un valore booleano. Il valore visualizzato è `True`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

La possibilità di restituire una funzione come valore di una chiamata di funzione è la seconda caratteristica delle funzioni di ordine superiore. Nell'esempio riportato di seguito `checkFor` viene definito come una funzione che accetta un argomento, `item`e restituisce una nuova funzione come relativo valore. La funzione restituita accetta un elenco come argomento, `lst`e Cerca `item` in `lst`. Se `item` è presente, la funzione restituisce `true`. Se `item` non è presente, la funzione restituisce `false`. Come nella sezione precedente, il codice seguente usa una funzione, elenco fornito [List. exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), la ricerca nell'elenco.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

Il codice seguente usa `checkFor` per creare una nuova funzione che accetta un solo argomento, un elenco e le ricerche per 7 nell'elenco.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

L'esempio seguente usa lo stato di prima classe di funzioni in F# per dichiarare una funzione `compose`, che restituisce una composizione di due argomenti della funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> Per una versione ancora più breve, vedere la sezione seguente, "Funzioni sottoposte a currying."

Il codice seguente invia due funzioni come argomenti `compose`, entrambi di che accettano un solo argomento dello stesso tipo. Il valore restituito è una nuova funzione che prevede una composizione di due argomenti della funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> F#sono disponibili due operatori, `<<` e `>>`, che consente di combinare funzioni. Ad esempio, `let squareAndDouble2 = doubleIt << squareIt` equivale a `let squareAndDouble = compose doubleIt squareIt` nell'esempio precedente.

L'esempio seguente di restituzione di una funzione come valore di una chiamata di funzione crea un semplice gioco di individuazione. Per creare un gioco, chiamare `makeGame` con il valore di cui un utente di indovinare inviato per `target`. Il valore restituito dalla funzione `makeGame` è una funzione che accetta un argomento (il valore ipotizzato) e segnala se il valore indicato è corretto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

Il codice seguente chiama `makeGame`, inviare il valore `7` per `target`. Identificatore `playGame` è associata all'espressione lambda restituita. Pertanto `playGame` è una funzione che accetta come un argomento valore per `guess`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a>Funzioni sottoposte a currying

Molti degli esempi nella sezione precedente possono essere scritti in modo più conciso, sfruttando i vantaggi di implicita *currying* in F# dichiarazioni di funzione. Il currying è un processo che trasforma una funzione che ha più di un parametro in una serie di funzioni incorporate, ognuno dei quali ha un singolo parametro. In F#, funzioni con più parametri sono intrinsecamente sottoposte a currying. Ad esempio, `compose` dalla sezione precedente può essere scritta come mostrato nello stile conciso seguente, con tre parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

Tuttavia, il risultato è una funzione di un parametro che restituisce una funzione di un parametro che a sua volta restituisce un'altra funzione di un parametro, come illustrato nel `compose4curried`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

È possibile accedere a questa funzione in diversi modi. Ognuno degli esempi seguenti restituito di 18. È possibile sostituire `compose4` con `compose4curried` in uno degli esempi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

Per verificare che la funzione continui a funzionare come in precedenza, provare di nuovo i test case originali.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> È possibile limitare il currying racchiudendo parametri tra parentesi Tuple. Per altre informazioni, vedere "Parametro modelli" nella [parametri e argomenti](../language-reference/parameters-and-arguments.md).

L'esempio seguente usa il currying implicita per scrivere una versione più breve di `makeGame`. I dettagli relativi `makeGame` costruisce e restituisce il `game` funzione sono meno esplicite nel formato seguente, ma è possibile verificare utilizzando i test case originali che il risultato è lo stesso.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

Per ulteriori informazioni su currying, vedere "Applicazione parziale di argomenti" nella [funzioni](../language-reference/functions/index.md).

## <a name="identifier-and-function-definition-are-interchangeable"></a>Identificatore e definizione di funzione sono intercambiabili

Il nome della variabile `num` nella precedente esempi restituisce il numero intero 10 e non sorprende che where `num` è valido, 10 sia valido. Lo stesso vale per gli identificatori di funzione e i relativi valori: via Internet è il nome della funzione può essere utilizzato, l'espressione lambda a cui è associato è utilizzabile.

L'esempio seguente definisce una `Boolean` funzione chiamata `isNegative`e quindi Usa il nome della funzione e la definizione della funzione in modo intercambiabile. I tre esempi successivi viene sempre restituito e visualizzato `False`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

Per sfruttare ulteriormente, un unico passaggio, sostituire il valore che `applyIt` al quale è associato `applyIt`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>Le funzioni sono valori di prima classe f\#

Gli esempi nelle sezioni precedenti illustrano che funzioni in F# soddisfano i criteri per essere considerate valori F#:

- È possibile associare un identificatore per una definizione di funzione.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- È possibile archiviare una funzione in una struttura di dati.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- È possibile passare una funzione come argomento.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- È possibile restituire una funzione come valore di una chiamata di funzione.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

Per altre informazioni sui F#, vedere la [ F# riferimenti al linguaggio](../language-reference/index.md).

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Il codice seguente contiene tutti gli esempi in questo argomento.

### <a name="code"></a>Codice

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a>Vedere anche

- [Elenchi](../language-reference/lists.md)
- [Tuple](../language-reference/tuples.md)
- [Funzioni](../language-reference/functions/index.md)
- [`let` associazioni](../language-reference/functions/let-bindings.md)
- [Espressioni lambda: Parola chiave `fun`](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
