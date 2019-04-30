---
title: Introduzione a F# in Visual Studio per Mac
description: Informazioni su come usare F# con Visual Studio per Mac.
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949721"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Introduzione a F# in Visual Studio per Mac

F#e l'oggetto visivo F# gli strumenti sono supportati in Visual Studio per Mac dell'IDE. Assicurarsi di aver [Visual Studio per Mac installati](install-fsharp.md#install-f-with-visual-studio-for-mac).

## <a name="creating-a-console-application"></a>Creazione di un'applicazione console

Uno dei progetti più semplici in Visual Studio per Mac è l'applicazione Console.  Ecco come eseguire questa operazione.  Dopo aver aperto Visual Studio per Mac:

1. Nel **File** dal menu **nuova soluzione**.

2. Nella finestra di dialogo Nuovo progetto, sono presenti 2 diversi modelli di applicazione Console.  È disponibile in altro -> .NET che usi .NET Framework.  L'altro modello è disponibile in .NET Core -> App che ha come destinazione .NET Core.  Modello a dovrebbe funzionare allo scopo di questo articolo.

3. Nel gruppo di app console, modificare C# a F# se necessario.  Scegliere il **successivo** pulsante per spostarsi in avanti.  

4. Assegnare un nome al progetto e scegliere le opzioni desiderate per l'app.  Si noti che, nel riquadro di anteprima per il lato della schermata che mostra la struttura di directory che verrà creata in base alle opzioni selezionate.  

5. Scegliere **Crea**.  A questo punto dovrebbe vedere un F# progetto in Esplora soluzioni.

## <a name="writing-your-code"></a>La scrittura del codice

Iniziamo a scrivere del codice prima di tutto.  Assicurarsi che il `Program.fs` file è aperto e quindi sostituirne il contenuto con quanto segue:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

Nell'esempio di codice precedente, una funzione `square` è stato definito che accetta un input denominato `x` e il risultato viene moltiplicato per se stesso.  Poiché F# viene utilizzato [inferenza del tipo](../language-reference/type-inference.md), il tipo di `x` non deve essere specificato.  Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e di assegnare un tipo `x` basato sul `square` viene chiamato.  Se si posiziona `square`, si dovrebbe visualizzare quanto segue:

```
val square: x:int -> int
```

Questo è ciò che è noto come la firma della funzione tipo.  Questo può essere letto come segue: "Quadrati è una funzione che accetta un numero intero denominato x e genera un numero intero".  Si noti che il compilatore assegna `square` il `int` tipo per il momento - infatti la moltiplicazione non è generica tra *tutte* tipi, ma è piuttosto generico in un set chiuso di tipi.  Il F# compilatore prelevata `int` a questo punto, ma regolerà la firma del tipo se si chiama `square` con un diverso tipo di input, ad esempio un' `float`.

Un'altra funzione, `main`, è definito, decorata con il `EntryPoint` attributo per indicare il F# compilatore che l'esecuzione del programma deve iniziare non esiste.  Ne consegue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui gli argomenti della riga di comando possono essere passati a questa funzione e viene restituito un codice integer (in genere `0`).

È in questa funzione che definiamo il `square` con un argomento di funzione `12`.  Il F# compilatore quindi assegna il tipo di `square` essere `int -> int` (vale a dire, una funzione che accetta un' `int` e genera un `int`).  La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile a linguaggi di programmazione di tipo C, i parametri che corrispondono a quelle specificate nella stringa di formato e quindi stampato il risultato e una nuova riga.

## <a name="running-your-code"></a>Esecuzione del codice

È possibile eseguire il codice e visualizzare i risultati facendo clic su **eseguiti** dal menu di primo livello e quindi **Avvia senza eseguire debug**.  Questo verrà eseguito il programma senza eseguire debug e consente di visualizzare i risultati.

Si dovrebbe ora visualizzare quanto segue nella finestra della console che Visual Studio per Mac apparse stampato:

```
12 squared is 144!
```

La procedura è stata completata.  È stata creata la prima F# progetto in Visual Studio per Mac, scritto un F# funzione stampa i risultati della chiamata di funzioneranno e di eseguire il progetto per visualizzare alcuni risultati.

## <a name="using-f-interactive"></a>Usando F# interattiva

Una delle funzionalità dell'oggetto visivo migliore F# strumenti in Visual Studio per Mac è il F# finestra interattiva.  Permette l'invio di codice a un processo in cui è possibile richiamare il codice e visualizzare il risultato in modo interattivo tramite.

Per iniziare a usarlo, evidenziare il `square` funzione definita nel codice.  Successivamente, fare clic su **modifica** dal menu di primo livello.  Successivamente, selezionare **Invia selezione a F# Interactive**.  Si esegue il codice di F# finestra interattiva.  In alternativa, è possibile fare clic con il pulsante destro sulla selezione e scegliere **Invia selezione a F# Interactive**.  Dovrebbe vedere il F# finestra interattiva vengono visualizzati con il codice seguente in esso:

```
>

val square : x:int -> int

>
```

Mostra la stessa firma della funzione per il `square` funzione, illustrato in precedenza quando passato sopra la funzione.  In quanto `square` ora è definito nel F# processo interattivo, è possibile chiamarlo con valori diversi:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Ciò viene eseguita la funzione, il risultato viene associato a un nuovo nome `it`e visualizza il tipo e il valore di `it`.  Si noti che è necessario terminare ogni riga con `;;`.  Si tratta di come F# Interactive SA al termine della chiamata alla funzione.  È anche possibile definire nuove funzioni in F# Interactive:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Il codice precedente definisce una nuova funzione `isOdd`, che accetta un `int` e verifica se è dispari.  È possibile chiamare questa funzione per visualizzare il risultato con input diversi.  È possibile chiamare funzioni nelle chiamate di funzione:

```
> isOdd (square 15);;
val it : bool = true
```

È anche possibile usare la [operatore pipe feedforward](../language-reference/symbol-and-operator-reference/index.md) per passare il valore nelle due funzioni:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

L'operatore pipe feedforward e altro ancora, sono trattato nelle esercitazioni successive.

Questo è solo uno sguardo a operazioni eseguibili con F# Interactive.  Per altre informazioni, consultare [programmazione interattiva con F# ](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Passaggi successivi

Se hai già fatto, consultare il [presentazione del F# ](../tour.md), che include alcune funzionalità di base del F# linguaggio.  In questo caso sarà una panoramica su alcune delle funzionalità di F#e fornire esempi di codice molto ampio che è possibile copiare in Visual Studio per Mac e di esecuzione.  Esistono anche alcune eccezionali risorse esterne è possibile usare, presentati nel [ F# Guida](../index.md).

## <a name="see-also"></a>Vedere anche

- [Visual F#](../index.md)
- [Panoramica di F#](../tour.md)
- [F#riferimenti al linguaggio](../language-reference/index.md)
- [Inferenza del tipo](../language-reference/type-inference.md)
- [Simbolo e operatore di riferimento](../language-reference/symbol-and-operator-reference/index.md)
