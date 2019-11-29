---
title: Introduzione F# a in Visual Studio per Mac
description: Informazioni su come usare F# con Visual Studio per Mac.
ms.date: 07/03/2018
ms.openlocfilehash: cd45ab9c59cef76e4bf85a93f39d8e2ee063d200
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552375"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Introduzione F# a in Visual Studio per Mac

F#e gli strumenti F# visivi sono supportati nell'IDE Visual Studio per Mac. Assicurarsi che Visual Studio per Mac sia [installato](install-fsharp.md#install-f-with-visual-studio-for-mac).

## <a name="creating-a-console-application"></a>Creazione di un'applicazione console

Uno dei progetti più semplici in Visual Studio per Mac è l'applicazione console.  Ecco come eseguire questa operazione.  Una volta aperto Visual Studio per Mac:

1. Scegliere **nuova soluzione**dal menu **file** .

2. Nella finestra di dialogo nuovo progetto sono disponibili 2 modelli diversi per l'applicazione console.  Ne esiste una in Other-> .NET che ha come destinazione il .NET Framework.  L'altro modello è disponibile in .NET Core-> app che è destinato a .NET Core.  Uno dei due modelli dovrebbe funzionare ai fini di questo articolo.

3. In app console passare C# a F# se necessario.  Per procedere, scegliere il pulsante **Avanti** .  

4. Assegnare un nome al progetto e scegliere le opzioni desiderate per l'app.  Si noti che il riquadro di anteprima sul lato della schermata in cui verrà visualizzata la struttura di directory che verrà creata in base alle opzioni selezionate.  

5. Scegliere **Crea**.  A questo punto dovrebbe essere F# visualizzato un progetto nella Esplora soluzioni.

## <a name="writing-your-code"></a>Scrittura del codice

Per iniziare, scrivere prima di tutto il codice.  Verificare che il file `Program.fs` sia aperto e quindi sostituirne il contenuto con il codice seguente:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Nell'esempio di codice precedente è stato definito un `square` di funzione che accetta un input denominato `x` e lo moltiplica per se stesso.  Poiché F# usa l' [inferenza del tipo](../language-reference/type-inference.md), non è necessario specificare il tipo di `x`.  Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e assegna un tipo a `x` in base al modo in cui viene chiamato `square`.  Se si passa il mouse su `square`, viene visualizzato quanto segue:

```console
val square: x:int -> int
```

Questa è la nota come la firma del tipo della funzione.  Può essere letto come segue: "Square è una funzione che accetta un numero intero denominato x e produce un Integer".  Si noti che il compilatore ha `square` il tipo di `int` per ora, perché la moltiplicazione non è generica in *tutti* i tipi, ma è piuttosto generica in un set chiuso di tipi.  Il F# compilatore ha scelto `int` a questo punto, ma modificherà la firma del tipo se si chiama `square` con un tipo di input diverso, ad esempio un `float`.

Viene definita un'altra funzione, `main`, che è decorata con l'attributo `EntryPoint` per indicare F# al compilatore che l'esecuzione del programma dovrebbe iniziare da questa posizione.  Segue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui è possibile passare argomenti della riga di comando a questa funzione e viene restituito un codice Integer (in genere `0`).

Si trova in questa funzione che viene chiamata la funzione `square` con un argomento di `12`.  Il F# compilatore assegna quindi il tipo di `square` da `int -> int`, ovvero una funzione che accetta un `int` e produce un `int`.  La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile ai linguaggi di programmazione di tipo C, parametri che corrispondono a quelli specificati nella stringa di formato, quindi stampa il risultato e una nuova riga.

## <a name="running-your-code"></a>Esecuzione del codice

È possibile eseguire il codice e visualizzare i risultati facendo clic su **Esegui** dal menu di primo livello e quindi **Avvia senza eseguire debug**.  Il programma verrà eseguito senza debug e sarà possibile visualizzare i risultati.

A questo punto, nella Visual Studio per Mac finestra della console dovrebbe essere visualizzato quanto segue:

```console
12 squared is 144!
```

La procedura è stata completata.  Il primo F# progetto è stato creato in Visual Studio per Mac, è stata F# scritta una funzione che ha stampato i risultati della chiamata a tale funzione ed è stato eseguito il progetto per visualizzare alcuni risultati.

## <a name="using-f-interactive"></a>Uso F# di Interactive

Una delle funzionalità migliori degli strumenti visivi F# in Visual Studio per Mac è la F# finestra interattiva.  Consente di inviare codice a un processo in cui è possibile chiamare tale codice e visualizzare il risultato in modo interattivo.

Per iniziare a usarlo, evidenziare la funzione `square` definita nel codice.  Quindi, fare clic su **modifica** dal menu di primo livello.  Selezionare quindi **Invia selezione a F# interattivo**.  Viene eseguito il codice nella finestra F# interattiva.  In alternativa, è possibile fare clic con il pulsante destro del mouse sulla selezione e scegliere **Invia selezione a F# interattivo**.  Verrà visualizzata la F# finestra interattiva con quanto segue:

```console
>

val square : x:int -> int

>
```

Viene visualizzata la stessa firma di funzione per la funzione `square`, che è stata visualizzata in precedenza al passaggio del mouse sulla funzione.  Poiché `square` è ora definito nel processo F# interattivo, è possibile chiamarlo con valori diversi:

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

In questo modo viene eseguita la funzione, viene associato il risultato a un nuovo nome `it`e vengono visualizzati il tipo e il valore di `it`.  Si noti che è necessario terminare ogni riga con `;;`.  Questo è il F# modo in cui Interactive conosce al termine della chiamata di funzione.  È anche possibile definire nuove funzioni in F# Interactive:

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Il precedente definisce una nuova funzione, `isOdd`, che accetta un `int` e controlla se è dispari.  È possibile chiamare questa funzione per vedere cosa restituisce con input diversi.  È possibile chiamare funzioni all'interno di chiamate di funzione:

```console
> isOdd (square 15);;
val it : bool = true
```

È anche possibile usare l' [operatore di invio tramite pipe](../language-reference/symbol-and-operator-reference/index.md) per eseguire il pipeline del valore in due funzioni:

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

L'operatore di inoltrare pipe e altro ancora sono trattati nelle esercitazioni successive.

Si tratta solo di una panoramica delle operazioni che è possibile F# eseguire con Interactive.  Per altre informazioni, vedere [programmazione interattiva con F# ](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Passaggi successivi

Se non è già stato fatto, consultare la [presentazione F#di ](../tour.md), che illustra alcune delle funzionalità principali del F# linguaggio.  Viene fornita una panoramica di alcune funzionalità di F#e vengono forniti esempi di codice ampi che è possibile copiare in Visual Studio per Mac ed eseguire.  Sono disponibili anche alcune eccezionali risorse esterne che è possibile usare, presentate nella [ F# guida](../index.yml).

## <a name="see-also"></a>Vedere anche

- [F#Guida](../index.yml)
- [Panoramica di F#](../tour.md)
- [F#riferimenti per il linguaggio](../language-reference/index.md)
- [Inferenza del tipo](../language-reference/type-inference.md)
- [Riferimenti per simboli e operatori](../language-reference/symbol-and-operator-reference/index.md)
