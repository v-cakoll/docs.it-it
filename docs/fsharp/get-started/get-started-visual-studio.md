---
title: Introduzione F# a in Visual Studio
description: Informazioni su come usare F# con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 80b4fc5b7631eace719832fe32003cad578ead27
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552826"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introduzione F# a in Visual Studio

F#e gli strumenti F# visivi sono supportati nell'IDE di Visual Studio.

Per iniziare, verificare che [Visual Studio sia installato con F# ](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Creazione di un'applicazione console

Uno dei progetti più semplici in Visual Studio è l'applicazione console.  Ecco come eseguire questa operazione.  Una volta aperto Visual Studio:

1. Scegliere **nuovo**dal menu **file** , quindi **progetto**.

2. Nella finestra di dialogo nuovo progetto, in **modelli**, verrà visualizzato **Visual F#** .  Scegliere questa per visualizzare i F# modelli.

3. Selezionare app **Console .NET Core** o **app console**.

4. Scegliere il pulsante **OK** per creare il F# progetto.  A questo punto dovrebbe essere F# visualizzato un progetto nella Esplora soluzioni.

## <a name="writing-your-code"></a>Scrittura del codice

Per iniziare, scrivere prima di tutto il codice.  Verificare che il file `Program.fs` sia aperto e quindi sostituirne il contenuto con il codice seguente:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Nell'esempio di codice precedente è stato definito un `square` di funzione che accetta un input denominato `x` e lo moltiplica per se stesso.  Poiché F# usa l' [inferenza del tipo](../language-reference/type-inference.md), non è necessario specificare il tipo di `x`.  Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e assegna un tipo a `x` in base al modo in cui viene chiamato `square`.  Se si passa il mouse su `square`, viene visualizzato quanto segue:

```fsharp
val square: x:int -> int
```

Questa è la nota come la firma del tipo della funzione.  Può essere letto come segue: "Square è una funzione che accetta un numero intero denominato x e produce un Integer".  Si noti che il compilatore ha `square` il tipo di `int` per ora, perché la moltiplicazione non è generica in *tutti* i tipi, ma è piuttosto generica in un set chiuso di tipi.  Il F# compilatore ha scelto `int` a questo punto, ma modificherà la firma del tipo se si chiama `square` con un tipo di input diverso, ad esempio un `float`.

Viene definita un'altra funzione, `main`, che è decorata con l'attributo `EntryPoint` per indicare F# al compilatore che l'esecuzione del programma dovrebbe iniziare da questa posizione.  Segue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui è possibile passare argomenti della riga di comando a questa funzione e viene restituito un codice Integer (in genere `0`).

Si trova in questa funzione che viene chiamata la funzione `square` con un argomento di `12`.  Il F# compilatore assegna quindi il tipo di `square` da `int -> int`, ovvero una funzione che accetta un `int` e produce un `int`.  La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile ai linguaggi di programmazione di tipo C, parametri che corrispondono a quelli specificati nella stringa di formato, quindi stampa il risultato e una nuova riga.

## <a name="running-your-code"></a>Esecuzione del codice

È possibile eseguire il codice e visualizzare i risultati premendo **Ctrl**+**F5**.  Il programma viene eseguito senza debug e consente di visualizzare i risultati.  In alternativa, è possibile scegliere la voce di menu di primo livello **debug** in Visual Studio e scegliere **Avvia senza eseguire debug**.

A questo punto verrà visualizzato quanto segue nella finestra della console visualizzata da Visual Studio:

```console
12 squared is 144!
```

La procedura è stata completata.  Il primo F# progetto è stato creato in Visual Studio, è stata F# scritta una funzione che ha stampato i risultati della chiamata a tale funzione ed è stato eseguito il progetto per visualizzare alcuni risultati.

## <a name="next-steps"></a>Passaggi successivi

Se non è già stato fatto, consultare la [presentazione F#di ](../tour.md), che illustra alcune delle funzionalità principali del F# linguaggio.  Viene fornita una panoramica di alcune funzionalità di F#e vengono forniti esempi di codice ampi che è possibile copiare in Visual Studio ed eseguire.  È anche possibile ottenere altre informazioni sulla F# documentazione nella [ F# Home page di docs](../index.yml).

## <a name="see-also"></a>Vedere anche

- [Panoramica di F#](../tour.md)
- [F#riferimenti per il linguaggio](../language-reference/index.md)
- [Inferenza del tipo](../language-reference/type-inference.md)
- [Riferimenti per simboli e operatori](../language-reference/symbol-and-operator-reference/index.md)
