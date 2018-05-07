---
title: Funzioni come valori di prima classe (F#)
description: Informazioni su come le funzioni vengono elevate per stato di prima classe nel linguaggio di programmazione c#.
ms.date: 05/16/2016
ms.openlocfilehash: cccff5fcf9de150da26422f80cae032ddf21014c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="functions-as-first-class-values"></a>Funzioni come valori di prima classe

Una caratteristica di definizione dei linguaggi di programmazione funzionale è l'elevazione delle funzioni di stato di prima classe. Dovrebbe essere possibile eseguire con una funzione qualsiasi è possibile eseguire con i valori degli altri tipi predefiniti e in grado di farlo con un livello di impegno confrontabile.

Di seguito sono elencate le misure tipiche dello stato di prima classe:

- È possibile associare funzioni di identificatori Vale a dire può garantirvi nomi?

- È possibile archiviare funzioni nelle strutture dei dati, ad esempio in un elenco?

- È possibile passare una funzione come argomento in una chiamata di funzione?

- È possibile restituire una funzione da una chiamata di funzione

Le ultime due misure definiscono i cosiddetti *operazioni di ordine superiore* o *funzioni di ordine superiore*. Funzioni di ordine superiore accettano funzioni come argomenti e restituiscono funzioni come il valore delle chiamate di funzione. Queste operazioni supportano fondamenti della programmazione funzionale come mapping di funzioni e composizione di funzioni.


## <a name="give-the-value-a-name"></a>Assegnare il valore di un nome

Se una funzione è un valore di prima classe, è necessario essere in grado di assegnare un nome, così come è possibile assegnare valori integer, stringhe e altri tipi predefiniti. Si parla nella documentazione di programmazione funzionale come associazione di un identificatore a un valore. F # utilizza [ `let` associazioni](../language-reference/functions/let-bindings.md) per associare i nomi ai valori: `let <identifier> = <value>`. Il codice riportato di seguito sono illustrati due esempi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

È possibile denominare una funzione altrettanto facilmente. Nell'esempio seguente viene definita una funzione denominata `squareIt` associando l'identificatore `squareIt` per il [espressione lambda](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`. Funzione `squareIt` dispone di un parametro `n`, e restituisce il quadrato di tale parametro.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

F # offre quanto segue sintassi più concisa per ottenere lo stesso risultato con meno digitazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

Gli esempi che seguono per lo più utilizzano il primo stile, `let <function-name> = <lambda-expression>`, per evidenziare le analogie tra la dichiarazione di funzioni e la dichiarazione di altri tipi di valori. Tuttavia, tutte le funzioni denominate possono essere scritti con la sintassi concisa. Alcuni degli esempi sono scritti in entrambe le direzioni.


## <a name="store-the-value-in-a-data-structure"></a>Archiviare il valore in una struttura di dati

Un valore di prima classe può essere archiviato in una struttura di dati. Il codice seguente mostra esempi in cui archiviano i valori negli elenchi e Tuple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

Per verificare che il nome di una funzione archiviato in una tupla in realtà restituisce una funzione, l'esempio seguente usa il `fst` e `snd` operatori per estrarre il primo e secondo elemento da tupla `funAndArgTuple`. Il primo elemento nella tupla è `squareIt` e il secondo elemento è `num`. Identificatore `num` è associato in un esempio precedente all'intero 10, un argomento valido per il `squareIt` (funzione). La seconda espressione applica il primo elemento nella tupla al secondo elemento nella tupla: `squareIt num`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

Analogamente, come identificatore `num` e intero 10 può essere utilizzato in modo intercambiabile, in tal caso è possibile identificatore `squareIt` e l'espressione lambda `fun n -> n * n`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a>Passare il valore come argomento

Se un valore ha lo stato di prima classe in una lingua, è possibile passare come argomento a una funzione. Ad esempio, è pratica comune passare interi e stringhe come argomenti. Il codice seguente mostra i numeri interi e stringhe passate come argomenti in F #.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

Se lo stato di prima classe dispone di funzioni, è necessario essere in grado di passati come argomenti allo stesso modo. Tenere presente che questa è la prima caratteristica delle funzioni di ordine superiore.

Nell'esempio seguente, la funzione `applyIt` presenta due parametri, `op` e `arg`. Se si invia una funzione che dispone di un parametro per `op` e un argomento appropriato per la funzione `arg`, la funzione restituisce il risultato dell'applicazione `op` a `arg`. Nell'esempio seguente, l'argomento della funzione sia l'argomento integer vengono inviati nello stesso modo, tramite i relativi nomi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

La possibilità di inviare una funzione come argomento a un'altra funzione sottostante astrazioni comuni nei linguaggi di programmazione funzionale, ad esempio operazioni mappa o un filtro. Un'operazione di mapping, ad esempio, è una funzione di ordine superiore che acquisisce il calcolo condiviso dalle funzioni che scorrere un elenco, eseguono un'operazione su ogni elemento e quindi restituiscono un elenco dei risultati. È possibile incrementare ogni elemento in un elenco di numeri interi, o al quadrato di ogni elemento o per modificare ogni elemento in un elenco di stringhe in lettere maiuscole. La parte soggetta a errori di calcolo è il processo ricorsivo che scorre l'elenco e compila un elenco di risultati da restituire. Tale parte viene acquisita nella funzione di mapping. È necessario scrivere per una particolare applicazione è la funzione che si desidera applicare singolarmente a ogni elemento di elenco (aggiunta, elevazione al quadrato, modificare maiuscole e minuscole). Che funzione viene inviata come argomento alla funzione di mapping, proprio come `squareIt` viene inviato a `applyIt` nell'esempio precedente.

F # fornisce metodi di mapping per la maggior parte dei tipi di raccolta, tra cui [Elenca](../language-reference/lists.md), [matrici](../language-reference/arrays.md), e [sequenze](../language-reference/sequences.md). L'esempio seguente usa gli elenchi. La sintassi è `List.map <the function> <the list>`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

Per ulteriori informazioni, vedere [Elenca](../language-reference/lists.md).

## <a name="return-the-value-from-a-function-call"></a>Il valore restituito da una chiamata di funzione

Infine, se lo stato di prima classe dispone di una funzione in una lingua, è necessario essere in grado di restituire il valore di una chiamata di funzione, la esattamente come si restituiscono altri tipi, ad esempio numeri interi e stringhe.

Chiamate di funzione seguenti restituiscono valori integer e visualizzarli.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

La chiamata di funzione seguente restituisce una stringa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

La seguente chiamata di funzione, dichiarate inline, restituisce un valore booleano. Il valore visualizzato è `True`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

La possibilità di restituire una funzione come valore di una chiamata di funzione è la seconda caratteristica delle funzioni di ordine superiore. Nell'esempio seguente, `checkFor` viene definito come una funzione che accetta un solo argomento, `item`e restituisce una nuova funzione come relativo valore. La funzione restituita accetta un elenco come argomento, `lst`e Cerca `item` in `lst`. Se `item` è presente, la funzione restituisce `true`. Se `item` non è presente, la funzione restituisce `false`. Come nella sezione precedente, il codice seguente utilizza una funzione di elenco fornito, [List. exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), la ricerca nell'elenco.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

Il codice seguente usa `checkFor` per creare una nuova funzione che accetta un argomento, un elenco e cerca 7 nell'elenco.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

Nell'esempio seguente viene utilizzato lo stato di prima classe delle funzioni in F # per dichiarare una funzione, `compose`, che restituisce una composizione di due argomenti di funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
Per una versione ancora più breve, vedere la sezione seguente, "Funzioni sottoposte a currying."


Il codice seguente invia due funzioni come argomenti `compose`, entrambi di che accettano un solo argomento dello stesso tipo. Il valore restituito è una nuova funzione che è una composizione di due argomenti della funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
F # fornisce due operatori, `<<` e `>>`, che consente di combinare funzioni. Ad esempio, `let squareAndDouble2 = doubleIt << squareIt` equivale a `let squareAndDouble = compose doubleIt squareIt` nell'esempio precedente.

L'esempio seguente di restituzione di una funzione come valore di una chiamata di funzione crea un semplice gioco di individuazione. Per creare un gioco, chiamare `makeGame` con il valore desiderato da individuare inviato per `target`. Il valore restituito dalla funzione `makeGame` è una funzione che accetta un argomento, la proposta e segnala se il valore indicato è corretto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

Il codice seguente chiama `makeGame`, inviare il valore `7` per `target`. Identificatore `playGame` è associata all'espressione lambda restituita. Pertanto, `playGame` è una funzione che accetta come unico argomento un valore per `guess`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a>Funzioni sottoposte a currying

Molti degli esempi nella sezione precedente possono essere scritti in modo più conciso sfruttando l'operatore implicito *currying* nelle dichiarazioni di funzione F #. Currying è un processo di trasformazione di una funzione che ha più di un parametro in una serie di funzioni incorporate, ognuna delle quali presenta un singolo parametro. In F #, le funzioni contenenti più di un parametro sono intrinsecamente sottoposte a currying. Ad esempio, `compose` della sezione precedente può essere scritta come mostrato nella seguente stile conciso, con tre parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

Tuttavia, il risultato è una funzione di un parametro che restituisce una funzione di un parametro che a sua volta restituisce un'altra funzione di un parametro, come illustrato nella `compose4curried`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

È possibile accedere a questa funzione in diversi modi. Ognuno degli esempi seguenti restituito di 18. È possibile sostituire `compose4` con `compose4curried` in uno degli esempi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

Per verificare che la funzione continui a funzionare come in precedenza, provare di nuovo i test case originali.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
È possibile limitare il currying racchiudendo le tuple parametri. Per ulteriori informazioni, vedere "Parametro modelli" nella [parametri e argomenti](../language-reference/parameters-and-arguments.md).

Nell'esempio seguente viene utilizzato il currying implicito per scrivere una versione più breve di `makeGame`. I dettagli di `makeGame` crea e restituisce il `game` funzione sono meno espliciti in questo formato, ma è possibile verificare tramite i test case originali che il risultato è lo stesso.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

Per ulteriori informazioni sul currying, vedere "Applicazione parziale di argomenti" in [funzioni](../language-reference/functions/index.md).


## <a name="identifier-and-function-definition-are-interchangeable"></a>Identificatore e definizione di funzione sono intercambiabili
Il nome della variabile `num` nella precedente esempi restituisce l'intero 10 e non sorprende quello in `num` è valido, 10 sia valido. Lo stesso vale per gli identificatori di funzione e i relativi valori: ovunque può essere utilizzato il nome della funzione, l'espressione lambda a cui è associato è utilizzabile.

L'esempio seguente definisce un `Boolean` funzione chiamata `isNegative`e quindi viene utilizzato il nome della funzione e la definizione della funzione in modo intercambiabile. I tre esempi successivi viene sempre restituito e visualizzato `False`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

Per eseguire un'ulteriore è un unico passaggio, sostituire il valore che `applyIt` è associato a per `applyIt`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>Le funzioni sono valori di prima classe in F # #

Negli esempi nelle sezioni precedenti viene illustrato che funzioni in F # soddisfano i criteri per essere considerate valori in F #:

- È possibile associare un identificatore per una definizione di funzione.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- È possibile archiviare una funzione in una struttura di dati.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- È possibile passare una funzione come argomento.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- È possibile restituire una funzione come valore di una chiamata di funzione.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

Per ulteriori informazioni su F #, vedere il [riferimenti al linguaggio F #](../language-reference/index.md).

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Il codice seguente contiene tutti gli esempi in questo argomento.

### <a name="code"></a>Codice

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a>Vedere anche

[Elenchi](../language-reference/lists.md)

[Tuple](../language-reference/tuples.md)

[Funzioni](../language-reference/functions/index.md)

[`let` Associazioni](../language-reference/functions/let-bindings.md)

[Espressioni lambda: I `fun` (parola chiave)](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
