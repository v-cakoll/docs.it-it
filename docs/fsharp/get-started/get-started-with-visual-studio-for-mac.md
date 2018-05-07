---
title: 'Introduzione a F # in Visual Studio per Mac'
description: 'Imparare a usare F # con Visual Studio per Mac.'
ms.date: 02/13/2017
ms.openlocfilehash: 58e65e703b092f2ee5d74386051b158c932013b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Introduzione a F # in Visual Studio per Mac

F # e gli strumenti di Visual F # sono supportati in Visual Studio per Mac IDE.  Per iniziare, è necessario [scaricare Visual Studio per Mac](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), se hai già fatto.  Questo articolo viene utilizzata la 2017 di Community di Visual Studio per Mac, ma è possibile utilizzare F # con la versione di propria scelta.

## <a name="installing-f"></a>L'installazione di F # #

Dopo il download di Visual Studio per Mac, verrà chiesto di scegliere ciò che si desidera installare.  Ai fini di questo articolo è lascerà le impostazioni predefinite.  A differenza di Visual Studio per Windows, non è necessario installare in modo specifico il supporto di F #.  Premere "Installa" per continuare.

Al termine dell'installazione, scegliere "Avvia Visual Studio".  È anche possibile avviarla tramite Finder su macOS.

## <a name="creating-a-console-application"></a>Creazione di un'applicazione console

Uno dei progetti più semplici in Visual Studio per Mac è l'applicazione Console.  Ecco come eseguire questa operazione.  Una volta aperto Visual Studio per Mac:

1. Nel **File** dal menu **nuova soluzione**.

2.  Nella finestra di dialogo Nuovo progetto, sono presenti 2 diversi modelli per l'applicazione Console.  È presente in altro -> .NET destinato a .NET Framework.  L'altro modello è disponibile in .NET Core -> applicazione destinato a .NET Core.  Modello dovrebbe funzionare allo scopo di questo articolo.

3. In app console, cambiare c# a F #.  Scegliere il **Avanti** pulsante per spostarsi in avanti.  

4. Assegnare un nome al progetto e scegliere le opzioni desiderate per l'app.  Si noti, nel riquadro di anteprima per il lato della schermata che mostra la struttura di directory che verrà creata in base alle opzioni selezionate.  

5. Scegliere **Crea**.  Dovrebbe essere un progetto F # in Esplora soluzioni.

## <a name="writing-your-code"></a>Scrittura del codice

È possibile iniziare subito scrivendo prima del codice.  Assicurarsi che il `Program.fs` file è aperto e quindi sostituire il contenuto con quanto segue:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

Nell'esempio di codice precedente, una funzione `square` è stato definito che accetta un input denominato `x` e viene moltiplicata per se stesso.  Poiché F # utilizza [l'inferenza del tipo](../language-reference/type-inference.md), il tipo di `x` non deve essere specificato.  Il compilatore F # riconosce i tipi in cui moltiplicazione è valida e di assegnare un tipo per `x` in base alla modalità `square` viene chiamato.  Se si passa il mouse `square`, si dovrebbe visualizzare quanto segue:

```
val square: x:int -> int
```

Questo è ciò che è noto come la firma del tipo della funzione.  È possibile leggere simile al seguente: "quadrati è una funzione che accetta un valore intero denominato x e genera un numero intero".  Si noti che il compilatore ha `square` il `int` tipo per il momento - infatti moltiplicazione non è generica tra *tutti* tipi, ma è piuttosto generico in un set chiuso di tipi.  Il compilatore F # prelevato `int` a questo punto, ma verranno regolati la firma di tipo se si chiama `square` con un altro tipo di input, ad esempio un `float`.

Un'altra funzione, `main`, è definito, decorata con il `EntryPoint` attributo per indicare al compilatore F # l'esecuzione del programma deve iniziare non esiste.  Segue la stessa convenzione di altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui gli argomenti della riga di comando possono essere passati a questa funzione e viene restituito un codice integer (in genere `0`).

In questa funzione che viene chiamato il `square` funzione con un argomento di `12`.  Il compilatore F # viene quindi assegnato il tipo di `square` da `int -> int` (ovvero, una funzione che accetta un `int` e produce un `int`).  La chiamata a `printfn` è una funzione di stampa formattata che utilizza una stringa di formato, simile ai linguaggi di programmazione di tipo C, i parametri che corrispondono a quelli specificati nella stringa di formato e quindi stampato il risultato e una nuova riga.

## <a name="running-your-code"></a>Esecuzione del codice

È possibile eseguire il codice e visualizzare i risultati facendo clic su **eseguire** dal menu di primo livello e quindi **Avvia senza eseguire debug**.  Questo verrà eseguito il programma senza eseguire il debug e consente di visualizzare i risultati.

Viene visualizzato quanto segue nella finestra della console che Visual Studio per Mac viene stampato:

```
12 squared is 144!
```

La procedura è stata completata.  È stato creato il primo progetto F # in Visual Studio per Mac, scrivere che una funzione di F # stampati i risultati della chiamata di funzione ed eseguire il progetto per visualizzare alcuni risultati.

## <a name="using-f-interactive"></a>Utilizzo di F # Interactive

Uno dei migliori funzionalità di Visual F # gli strumenti in Visual Studio per Mac è la finestra F # Interactive.  Consente di inviare codice tramite un processo in cui è possibile richiamare il codice e visualizzare il risultato in modo interattivo.

Per iniziare a utilizzarlo, evidenziare il `square` funzione definita nel codice.  Successivamente, fare clic su **modifica** dal menu di primo livello.  Successivamente, selezionare **Invia selezione a F # Interactive**.  Si esegue il codice nella finestra F # Interactive.  In alternativa, è possibile fare clic con il pulsante destro sulla selezione e scegliere **Invia selezione a F # Interactive**.  Dovrebbe essere finestra F # Interactive vengono visualizzati con le operazioni seguenti in essa contenuti:

```
>

val square : x:int -> int

>
```

Mostra la stessa firma della funzione per il `square` funzione, illustrato in precedenza quando passa la funzione.  Poiché `square` è ora definito nel processo di F # Interactive, è possibile chiamare con valori diversi:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Questa viene eseguita la funzione, il risultato viene associato a un nuovo nome `it`e visualizza il tipo e il valore di `it`.  Si noti che è necessario terminare ogni riga con `;;`.  Si tratta come F # Interactive SA al termine della chiamata alla funzione.  È inoltre possibile definire nuove funzioni in F # Interactive:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Quanto indicato sopra definisce una nuova funzione `isOdd`, che accetta un `int` e controlla se è dispari.  È possibile chiamare questa funzione per visualizzare il risultato con input diversi.  È possibile chiamare funzioni nelle chiamate di funzione:

```
> isOdd (square 15);;
val it : bool = true
```

È inoltre possibile utilizzare il [operatore pipe forward](../language-reference/symbol-and-operator-reference/index.md) alla pipeline il valore in due funzioni:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

L'operatore pipe forward e altro ancora, vengono trattato nelle esercitazioni successive.

Si tratta solo Scopriamo cosa si può fare con F # Interactive.  Per ulteriori informazioni, vedere [programmazione interattiva con F #](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Passaggi successivi

Se non hai già fatto, controllare il [presentazione di F #](../tour.md), che vengono illustrate alcune delle funzionalità principali del linguaggio F #.  Verrà fornisce una panoramica di alcune delle funzionalità di F # e fornire esempi di codice molto che è possibile copiare in Visual Studio per Mac ed eseguire.  Esistono inoltre alcune importanti risorse esterne, è possibile utilizzare, ha nel [Guida F #](../index.md).

## <a name="see-also"></a>Vedere anche
 [Visual F#](../index.md)  
 [Panoramica di F#](../tour.md)  
 [Riferimenti al linguaggio F #](../language-reference/index.md)  
 [Inferenza del tipo](../language-reference/type-inference.md)  
 [Simboli e l'operatore di riferimento](../language-reference/symbol-and-operator-reference/index.md)  
