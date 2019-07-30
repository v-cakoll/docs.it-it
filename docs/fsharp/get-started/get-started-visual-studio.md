---
title: Introduzione F# a in Visual Studio
description: Informazioni su come usare F# con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 24c9a81cfa61dc904db9b2213224677696d7eb9b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629764"
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

Per iniziare, scrivere prima di tutto il codice.  Verificare che il `Program.fs` file sia aperto e quindi sostituirne il contenuto con il codice seguente:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Nell'esempio di codice precedente è stata definita `square` una funzione che accetta un input denominato `x` e lo moltiplica per se stesso.  Poiché F# usa l'inferenza del [tipo](../language-reference/type-inference.md), `x` non è necessario specificare il tipo di.  Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e assegna un tipo a `x` in base alla `square` modalità di chiamata.  Se si passa il `square`puntatore del mouse, viene visualizzato quanto segue:

```fsharp
val square: x:int -> int
```

Questa è la nota come la firma del tipo della funzione.  Può essere letto come segue: "Square è una funzione che accetta un numero intero denominato x e produce un Integer".  Si noti che il compilatore `square` ha `int` assegnato il tipo per il momento. questo è dovuto al fatto che la moltiplicazione non è generica in *tutti i* tipi, bensì è generica in un set chiuso di tipi.  Il F# compilatore ha `int` scelto a questo punto, ma modificherà la firma del tipo se si `square` chiama con un tipo di input `float`diverso, ad esempio.

Viene definita un' `main`altra funzione,,, decorata con l' `EntryPoint` attributo per indicare al F# compilatore che l'esecuzione del programma dovrebbe iniziare da tale posizione.  Segue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui è possibile passare argomenti della riga di comando a questa funzione e viene restituito un codice Integer ( `0`in genere).

Si trova in questa funzione che viene chiamata la `square` funzione con un argomento di `12`.  Il F# compilatore `square` assegna quindi il tipo di a `int -> int` (ovvero, una funzione che accetta un oggetto `int` e produce un oggetto `int`).  La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile ai linguaggi di programmazione di tipo C, i parametri che corrispondono a quelli specificati nella stringa di formato, quindi stampa il risultato e una nuova riga.

## <a name="running-your-code"></a>Esecuzione del codice

È possibile eseguire il codice e visualizzare i risultati premendo **CTRL**+**F5**.  Il programma viene eseguito senza debug e consente di visualizzare i risultati.  In alternativa, è possibile scegliere la voce di menu di primo livello **debug** in Visual Studio e scegliere **Avvia senza eseguire debug**.

A questo punto verrà visualizzato quanto segue nella finestra della console visualizzata da Visual Studio:

```
12 squared is 144!
```

Congratulazioni!  Il primo F# progetto è stato creato in Visual Studio, è stata F# scritta una funzione che ha stampato i risultati della chiamata a tale funzione ed è stato eseguito il progetto per visualizzare alcuni risultati.

## <a name="next-steps"></a>Passaggi successivi

Se non è già stato fatto, consultare la [presentazione F#di ](../tour.md), che illustra alcune delle funzionalità principali del F# linguaggio.  Viene fornita una panoramica di alcune funzionalità di F#e vengono forniti esempi di codice ampi che è possibile copiare in Visual Studio ed eseguire.  Sono disponibili anche alcune eccezionali risorse esterne che è possibile usare, presentate nella [ F# guida](../index.md).

## <a name="see-also"></a>Vedere anche

- [Panoramica di F#](../tour.md)
- [F#riferimenti per il linguaggio](../language-reference/index.md)
- [Inferenza del tipo](../language-reference/type-inference.md)
- [Riferimenti per simboli e operatori](../language-reference/symbol-and-operator-reference/index.md)
