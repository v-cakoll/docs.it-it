---
title: 'Introduzione a F # in Visual Studio'
description: 'Informazioni sull''utilizzo di F # con Visual Studio.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 944bbbba6a26634ace269d86cbbdde9ef9de7bcd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="get-started-with-f-in-visual-studio"></a>Introduzione a F # in Visual Studio

F # e gli strumenti di Visual F # sono supportate nell'IDE di Visual Studio.  Per iniziare, è necessario [scaricare Visual Studio](https://www.visualstudio.com/downloads/download-visual-studio-vs), se hai già fatto.  In questo articolo usa l'edizione Community di Visual Studio 2017, ma è possibile utilizzare F # con la versione di propria scelta.

## <a name="installing-f"></a>L'installazione di F # #

Se si sta scaricando Visual Studio per la prima volta, verrà installato prima di tutto il programma di installazione di Visual Studio.  Installare qualsiasi versione di Visual Studio 2017 dal programma di installazione. Se è già stata installata, fare clic su **modifica**.

Successivamente verrà visualizzato un elenco dei carichi di lavoro. È possibile installare F # tramite uno qualsiasi dei carichi di lavoro seguenti:

|Carico di lavoro|Azione|
|--------|------|
| Sviluppo multipiattaforma .NET Core | Nessuna azione - F # è installata per impostazione predefinita |
| Sviluppo ASP.NET e Web | Nessuna azione - F # è installata per impostazione predefinita |
| Sviluppo di Azure | Nessuna azione - F # è installata per impostazione predefinita |
| Sviluppo di applicazioni per dispositivi mobili con .NET | Nessuna azione - F # è installata per impostazione predefinita |
| Applicazioni analitiche e di analisi scientifica dei dati | Nessuna azione - F # è installata per impostazione predefinita |
| Sviluppo per desktop .NET | Selezionare **il supporto per desktop linguaggio F #** dal lato destro |
| Archiviazione ed elaborazione dei dati | Selezionare **il supporto per desktop linguaggio F #** dal lato destro |

Successivamente, fare clic su **modifica** nel lato inferiore destro.  Verranno installati tutti gli elementi selezionati.  È quindi possibile aprire Visual Studio 2017 con supporto del linguaggio F # facendo **avviare**.

## <a name="creating-a-console-application"></a>Creazione di un'applicazione console

Uno dei progetti più semplici in Visual Studio è l'applicazione Console.  Ecco come eseguire questa operazione.  Una volta aperto Visual Studio:

1. Nel **File** dal menu **New**, quindi scegliere **progetto**.

2.  Nel nuovo progetto nella finestra di dialogo, **modelli**, dovrebbe essere **Visual F #**.  Selezionare questa opzione per visualizzare i modelli di F #.

3. Selezionare l'opzione **.NET Core app Console** o **app Console**.

3. Scegliere il **OK** pulsante per creare il progetto F #!  Dovrebbe essere un progetto F # in Esplora soluzioni.

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

È possibile eseguire il codice e visualizzare risultati premendo **ctrl + f5**.  Questo verrà eseguito il programma senza eseguire il debug e consente di visualizzare i risultati.  In alternativa, è possibile scegliere di **Debug** menu di primo livello di elemento in Visual Studio e scegliere **Avvia senza eseguire debug**.

Viene visualizzato quanto segue nella finestra della console che Visual Studio viene stampato:

```
12 squared is 144!
```

La procedura è stata completata.  È stato creato il primo progetto F # in Visual Studio, scrivere che una funzione di F # stampati i risultati della chiamata di funzione ed eseguire il progetto per visualizzare alcuni risultati.

## <a name="using-f-interactive"></a>Utilizzo di F # Interactive

Uno dei migliori funzionalità di Visual F # gli strumenti in Visual Studio è la finestra F # Interactive.  Consente di inviare codice tramite un processo in cui è possibile richiamare il codice e visualizzare il risultato in modo interattivo.

Per iniziare a utilizzarlo, evidenziare il `square` funzione definita nel codice.  Successivamente, tenere premuto il **Alt** chiave e premere **invio**.  Si esegue il codice nella finestra F # Interactive.  Dovrebbe essere finestra F # Interactive vengono visualizzati con le operazioni seguenti in essa contenuti:

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

Quanto indicato sopra definisce una nuova funzione `isOdd`, che accetta un `int` e controlla se è dispari. È possibile chiamare questa funzione per visualizzare il risultato con input diversi.  È possibile chiamare funzioni nelle chiamate di funzione:

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

Si tratta solo Scopriamo cosa si può fare con F # Interactive. Per ulteriori informazioni, vedere [programmazione interattiva con F #](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Passaggi successivi

Se non hai già fatto, controllare il [presentazione di F #](../tour.md), che vengono illustrate alcune delle funzionalità principali del linguaggio F #.  Verrà fornisce una panoramica di alcune delle funzionalità di F # e fornire esempi di codice molto che è possibile copiare in Visual Studio ed eseguire.  Esistono inoltre alcune importanti risorse esterne, è possibile utilizzare, ha nel [Guida F #](../index.md).

## <a name="see-also"></a>Vedere anche
 [Visual F#](index.md)  
 [Panoramica di F#](../tour.md)  
 [Riferimenti al linguaggio F #](../language-reference/index.md)  
 [Inferenza del tipo](../language-reference/type-inference.md)  
 [Simboli e l'operatore di riferimento](../language-reference/symbol-and-operator-reference/index.md)  
