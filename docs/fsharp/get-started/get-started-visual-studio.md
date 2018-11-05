---
title: 'Introduzione a F # in Visual Studio'
description: 'Informazioni su come utilizzare F # con Visual Studio.'
ms.date: 07/03/2018
ms.openlocfilehash: 3dac8466501338873aeb308ceac9274a7934a8a9
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43872851"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introduzione a F # in Visual Studio

F # e gli strumenti di Visual F # sono supportati nell'IDE di Visual Studio.

Per iniziare, assicurarsi di aver [installato Visual Studio con F #](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Creazione di un'applicazione console

Uno dei progetti più semplici in Visual Studio è l'applicazione Console.  Ecco come eseguire questa operazione.  Dopo aver aperto Visual Studio:

1. Nel **File** dal menu **New**, quindi scegliere **progetto**.

2.  Nel nuovo progetto nella finestra di dialogo **modelli**, verrà visualizzato **Visual F #**.  Scegliere questa opzione per visualizzare i modelli di F #.

3. Selezionare uno **app Console per .NET Core** oppure **app Console**.

3. Scegliere il **Okay** pulsante per creare il progetto F #.  Si noterà ora un progetto F # in Esplora soluzioni.

## <a name="writing-your-code"></a>La scrittura del codice

Iniziamo a scrivere del codice prima di tutto.  Assicurarsi che il `Program.fs` file è aperto e quindi sostituirne il contenuto con quanto segue:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

Nell'esempio di codice precedente, una funzione `square` è stato definito che accetta un input denominato `x` e il risultato viene moltiplicato per se stesso.  Poiché F # utilizza [inferenza](../language-reference/type-inference.md), il tipo di `x` non deve essere specificato.  Il compilatore F # riconosce i tipi in cui la moltiplicazione è valida e di assegnare un tipo a `x` basata sulla `square` viene chiamato.  Se si posiziona `square`, si dovrebbe visualizzare quanto segue:

```
val square: x:int -> int
```

Questo è ciò che è noto come la firma della funzione tipo.  Questo può essere letto come segue: "quadrati è una funzione che accetta un numero intero denominato x e genera un numero intero".  Si noti che il compilatore assegna `square` il `int` tipo per il momento - infatti la moltiplicazione non è generica tra *tutte* tipi, ma è piuttosto generico in un set chiuso di tipi.  Il compilatore F # prelevato `int` a questo punto, ma regolerà la firma del tipo se si chiama `square` con un diverso tipo di input, ad esempio un `float`.

Un'altra funzione, `main`, viene definito, decorata con il `EntryPoint` attributo per indicare al compilatore F # che l'esecuzione del programma deve iniziare non esiste.  Ne consegue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui gli argomenti della riga di comando possono essere passati a questa funzione e viene restituito un codice integer (in genere `0`).

È in questa funzione che definiamo il `square` con un argomento di funzione `12`.  Il compilatore F # quindi assegna il tipo di `square` essere `int -> int` (vale a dire, una funzione che accetta un' `int` e produce un `int`).  La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile a linguaggi di programmazione di tipo C, i parametri che corrispondono a quelle specificate nella stringa di formato e quindi stampato il risultato e una nuova riga.

## <a name="running-your-code"></a>Esecuzione del codice

È possibile eseguire il codice e visualizzare i risultati premendo **Ctrl**+**F5**.  Ciò viene eseguito il programma senza eseguire debug e consente di visualizzare i risultati.  In alternativa, è possibile scegliere il **Debug** menu di primo livello di elemento in Visual Studio e scegliere **Avvia senza eseguire debug**.

È ora verrà visualizzato quanto segue nella finestra della console che Visual Studio apparse stampato:

```
12 squared is 144!
```

La procedura è stata completata.  È stato creato il primo progetto F # in Visual Studio, scritto che una funzione F # stampa i risultati della chiamata di funzione ed eseguire il progetto per visualizzare alcuni risultati.

## <a name="next-steps"></a>Passaggi successivi

Se hai già fatto, consultare il [Panoramica di F #](../tour.md), che illustra alcune delle principali funzionalità del linguaggio F #.  Verrà offrono una panoramica su alcune delle funzionalità di F # e fornisce esempi di codice molto ampio che è possibile copiare in Visual Studio ed eseguire.  Esistono anche alcune eccezionali risorse esterne è possibile usare, presentati nel [Guida a F #](../index.md).

## <a name="see-also"></a>Vedere anche

- [Panoramica di F#](../tour.md)
- [Riferimenti al linguaggio F #](../language-reference/index.md)
- [Inferenza del tipo](../language-reference/type-inference.md)
- [Simbolo e operatore di riferimento](../language-reference/symbol-and-operator-reference/index.md)
