---
title: Introduzione F# a in Visual Studio
description: Informazioni su come usare F# con Visual Studio.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337340"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introduzione F# a in Visual Studio

F#e gli strumenti F# visivi sono supportati in visual Studio Integrated Development Environment (IDE).

Per iniziare, assicurarsi che [Visual Studio sia installato con F# supporto](install-fsharp.md#install-f-with-visual-studio).

## <a name="create-a-console-application"></a>Creare un'applicazione console

Uno dei progetti più semplici in Visual Studio è l'app console. Di seguito viene illustrata la procedura di creazione:

1. Aprire Visual Studio 2019.

2. Nella finestra iniziale scegliere **Crea un nuovo progetto**.

3. Nella pagina **Crea un nuovo progetto** scegliere **F#** dall'elenco di lingue.

4. Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.

5. Nella pagina **Configura nuovo progetto** immettere un nome nella casella **nome progetto** . Scegliere **Crea**.

   Visual Studio crea il nuovo F# progetto. È possibile visualizzarlo nella finestra Esplora soluzioni.

## <a name="write-the-code"></a>Scrivere il codice

Per iniziare, scrivere il codice. Verificare che il file `Program.fs` sia aperto e quindi sostituirne il contenuto con il codice seguente:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Nell'esempio di codice precedente viene definita una funzione denominata `square` che accetta un input denominato `x` e lo moltiplica per se stesso. Poiché F# usa l' [inferenza del tipo](../language-reference/type-inference.md), non è necessario specificare il tipo di `x`. Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e assegna un tipo a `x` in base al modo in cui viene chiamato `square`. Se si passa il mouse su `square`, viene visualizzato quanto segue:

```fsharp
val square: x:int -> int
```

Questa è la nota come la firma del tipo della funzione. Può essere letto come segue: "Square è una funzione che accetta un numero intero denominato x e produce un Integer". Il compilatore ha `square` il tipo di `int` per ora; Questo perché la moltiplicazione non è generica in *tutti i* tipi, ma piuttosto in un set chiuso di tipi. Il F# compilatore modificherà la firma del tipo se si chiama `square` con un tipo di input diverso, ad esempio una `float`.

Viene definita un'altra funzione, `main`, che è decorata con l'attributo `EntryPoint`. Questo attributo indica al F# compilatore che l'esecuzione del programma dovrebbe iniziare da questa posizione. Segue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui è possibile passare argomenti della riga di comando a questa funzione e viene restituito un codice Integer (in genere `0`).

Si trova nella funzione del punto di ingresso, `main`, che viene chiamata la funzione `square` con un argomento di `12`. Il F# compilatore assegna quindi il tipo di `square` da `int -> int`, ovvero una funzione che accetta un `int` e produce un `int`. La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato e stampa il risultato (e una nuova riga). La stringa di formato, simile ai linguaggi di programmazione di tipo C, presenta parametri (`%d`) che corrispondono agli argomenti passati, in questo caso `12` e `(square 12)`.

## <a name="run-the-code"></a>Eseguire il codice

È possibile eseguire il codice e visualizzare i risultati premendo **Ctrl**+**F5**. In alternativa, è possibile scegliere **debug** > **Avvia senza eseguire debug** dalla barra dei menu di livello superiore. Viene eseguito il programma senza debug.

L'output seguente viene stampato nella finestra della console aperta da Visual Studio:

```console
12 squared is: 144!
```

La procedura è stata completata. Il primo F# progetto è stato creato in Visual Studio, è stata F# scritta una funzione che calcola e stampa un valore ed esegue il progetto per visualizzare i risultati.

## <a name="next-steps"></a>Passaggi successivi

Se non è già stato fatto, consultare la [presentazione F#di ](../tour.md), che illustra alcune delle funzionalità principali del F# linguaggio. Viene fornita una panoramica di alcune funzionalità di F# ed esempi di codice ampi che è possibile copiare in Visual Studio ed eseguire.

> [!div class="nextstepaction"]
> [Panoramica di F#](../tour.md)

## <a name="see-also"></a>Vedere anche

- [F#riferimenti per il linguaggio](../language-reference/index.md)
- [Inferenza del tipo](../language-reference/type-inference.md)
- [Riferimenti per simboli e operatori](../language-reference/symbol-and-operator-reference/index.md)
