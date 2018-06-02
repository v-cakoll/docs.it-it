---
title: 'Introduzione a F # in Visual Studio'
description: "Informazioni sull'utilizzo di F # con Visual Studio."
ms.date: 02/13/2017
ms.openlocfilehash: 22fbe8086ec133605e1d9b4b28e524fe2ed8ac28
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2018
ms.locfileid: "34728534"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introduzione a F # in Visual Studio

F # e gli strumenti di Visual F # sono supportate nell'IDE di Visual Studio.  Per iniziare, è necessario [scaricare Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), se hai già fatto.  In questo articolo usa l'edizione Community di Visual Studio 2017, ma è possibile utilizzare F # con la versione di propria scelta.

## <a name="installing-f"></a>L'installazione di F # #

Se si sta scaricando Visual Studio per la prima volta, verrà installato prima di tutto il programma di installazione di Visual Studio.  Installare qualsiasi versione di Visual Studio 2017 dal programma di installazione. Se è già stata installata, fare clic su **modifica**.

Successivamente verrà visualizzato un elenco dei carichi di lavoro. È possibile installare F # tramite uno qualsiasi dei carichi di lavoro seguenti:

|Carico di lavoro|Operazione|
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

## <a name="next-steps"></a>Passaggi successivi

Se non hai già fatto, controllare il [presentazione di F #](../tour.md), che vengono illustrate alcune delle funzionalità principali del linguaggio F #.  Verrà fornisce una panoramica di alcune delle funzionalità di F # e fornire esempi di codice molto che è possibile copiare in Visual Studio ed eseguire.  Esistono inoltre alcune importanti risorse esterne, è possibile utilizzare, ha nel [Guida F #](../index.md).

## <a name="see-also"></a>Vedere anche
 [Visual F#](index.md)  
 [Panoramica di F#](../tour.md)  
 [Riferimenti al linguaggio F #](../language-reference/index.md)  
 [Inferenza del tipo](../language-reference/type-inference.md)  
 [Simboli e l'operatore di riferimento](../language-reference/symbol-and-operator-reference/index.md)  
