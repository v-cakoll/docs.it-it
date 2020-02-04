---
title: Introduzione a F# in Visual Studio Code
description: Informazioni su come usare F# con Visual Studio Code e la suite di plug-in Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: 2aa62bb1afc220348f884865e55c4d7de4359b7f
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980353"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introduzione a F# in Visual Studio Code

È possibile scrivere F# in [Visual Studio Code](https://code.visualstudio.com) con il [plug](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) -in IONIDE per ottenere un'ottima esperienza IDE (Integrated Development Environment) multipiattaforma con IntelliSense e refactoring del codice. Visitare [Ionide.io](http://ionide.io) per altre informazioni sul plug-in.

Per iniziare, verificare che [ F# sia installato correttamente il plug](install-fsharp.md#install-f-with-visual-studio-code)-in Ionide.

## <a name="create-your-first-project-with-ionide"></a>Creare il primo progetto con Ionide

Per creare un nuovo F# progetto, aprire una riga di comando e creare un nuovo progetto con la interfaccia della riga di comando di .NET Core:

```dotnetcli
dotnet new console -lang "F#" -o FirstIonideProject
```

Al termine, passare alla directory del progetto e aprire Visual Studio Code:

```console
cd FirstIonideProject
code .
```

Dopo il caricamento del progetto in Visual Studio Code, il F# riquadro Esplora soluzioni sul lato sinistro della finestra verrà visualizzato. Ciò significa che Ionide ha caricato correttamente il progetto appena creato. È possibile scrivere codice nell'editor prima di questo momento, ma, una volta eseguita questa operazione, tutto il caricamento verrà completato.

## <a name="configure-f-interactive"></a>Configurare F# interattivo

Prima di tutto, assicurarsi che lo scripting di .NET Core sia l'ambiente di scripting predefinito:

1. Aprire le impostazioni del Visual Studio Code (**codice** > **Preferenze** > **Impostazioni**).
1. Cercare il termine  **F# script**.
1. Fare clic sulla casella di controllo " **FSharp: Use SDK scripts**".

Questa operazione è attualmente necessaria a causa di alcuni comportamenti legacy nello scripting basato su .NET Framework che non funzionano con gli script di .NET Core e Ionide sta attualmente cercando la compatibilità con le versioni precedenti. In futuro, lo scripting di .NET Core diventerà il valore predefinito.

### <a name="write-your-first-script"></a>Scrivere il primo script

Dopo aver configurato Visual Studio Code per usare lo script di .NET Core, passare alla visualizzazione Esplora in Visual Studio Code e creare un nuovo file. Denominarlo *MyFirstScript. FSX*.

A questo punto aggiungere il codice seguente:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Questa funzione converte una parola in una forma di [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). Il passaggio successivo consiste nel valutarlo tramite F# Interactive (FSI).

Evidenziare l'intera funzione (dovrebbe essere lungo 11 righe). Una volta evidenziato, mantenere premuto **ALT** e premere **invio**. Si noterà che nella parte inferiore della schermata viene visualizzata una finestra del terminale che dovrebbe essere simile alla seguente:

![Esempio di F# output interattivo con Ionide](./media/getting-started-vscode/vscode-fsi.png)

Questa operazione ha tre elementi:

1. Il processo FSI è stato avviato.
2. Ha inviato il codice evidenziato nel processo FSI.
3. Il processo FSI ha valutato il codice inviato.

Poiché ciò che è stato inviato è una [funzione](../language-reference/functions/index.md), è ora possibile chiamare tale funzione con FSI! Nella finestra interattiva digitare quanto segue:

```fsharp
toPigLatin "banana";;
```

Dovrebbe essere visualizzato il risultato seguente:

```fsharp
val it : string = "ananabay"
```

A questo punto, proviamo con una vocale come prima lettera. Immettere quanto segue:

```fsharp
toPigLatin "apple";;
```

Dovrebbe essere visualizzato il risultato seguente:

```fsharp
val it : string = "appleyay"
```

La funzione sembra funzionare come previsto. È stata appena scritta la prima F# funzione in Visual Studio Code e la si è valutata con FSI!

> [!NOTE]
> Come si può notare, le righe in FSI vengono terminate con `;;`. Questo perché FSI consente di immettere più righe. Il `;;` alla fine consente a FSI di scoprire quando il codice è terminato.

## <a name="explaining-the-code"></a>Spiegazione del codice

Se non si è certi di cosa stia effettivamente eseguendo il codice, ecco una procedura dettagliata.

Come si può vedere, `toPigLatin` è una funzione che accetta una parola come input e la converte in una rappresentazione Pig-Latin della parola. Le regole per questa operazione sono le seguenti:

Se il primo carattere di una parola inizia con una vocale, aggiungere "Yay" alla fine della parola. Se non inizia con una vocale, sposta il primo carattere alla fine della parola e Aggiungi "Ay".

In FSI è possibile notare quanto segue:

```fsharp
val toPigLatin : word:string -> string
```

Questo indica che `toPigLatin` è una funzione che accetta un `string` come input (chiamato `word`) e restituisce un altro `string`. Questa operazione è nota come [firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale della F# chiave per comprendere F# il codice. Si noterà anche che se si passa il mouse sulla funzione in Visual Studio Code.

Nel corpo della funzione si noteranno due parti distinte:

1. Funzione interna, denominata `isVowel`, che determina se un carattere specificato (`c`) è una vocale controllando se corrisponde a uno dei modelli forniti tramite [criteri di ricerca](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Espressione [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) che controlla se il primo carattere è una vocale e costruisce un valore restituito dai caratteri di input in base a se il primo carattere è una vocale o meno:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Il flusso di `toPigLatin` è quindi:

Controllare se il primo carattere della parola di input è una vocale. In caso contrario, alleghi "Yay" alla fine della parola. In caso contrario, spostare il primo carattere alla fine della parola e aggiungere "Ay".

C'è un aspetto finale da tenere presente: in F#non esiste alcuna istruzione esplicita da restituire dalla funzione. Poiché F# è basato su espressioni e l'ultima espressione valutata nel corpo di una funzione determina il valore restituito della funzione. Poiché `if..then..else` è a sua volta un'espressione, la valutazione del corpo del blocco `then` o del corpo del blocco `else` determina il valore restituito dalla funzione `toPigLatin`.

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a>Trasformare l'app console in un generatore Pig Latin

Le sezioni precedenti di questo articolo hanno illustrato un primo passaggio comune nella F# scrittura di codice: scrittura di una funzione iniziale ed esecuzione interattiva con FSI. Questo è noto come sviluppo basato su REPL, in cui [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) sta per "Read-Evaluate-Print Loop". È un ottimo modo per sperimentare le funzionalità fino a quando non si dispone di qualcosa di funzionante.

Il passaggio successivo nello sviluppo basato su REPL consiste nello spostare il codice di lavoro F# in un file di implementazione. Può quindi essere compilato dal F# compilatore in un assembly che può essere eseguito.

Per iniziare, aprire il file *Program. FS* creato in precedenza con il interfaccia della riga di comando di .NET Core. Si noterà che il codice è già presente.

Successivamente, creare un nuovo [`module`](../language-reference/modules.md) denominato `PigLatin` e copiare la funzione `toPigLatin` creata in precedenza nel modo seguente:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L3-L14)]

Questo modulo deve essere superiore alla funzione `main` e al di sotto della dichiarazione di `open System`. L'ordine delle dichiarazioni è importante F#in, quindi è necessario definire la funzione prima di chiamarla in un file.

A questo punto, nella funzione `main` chiamare la funzione del generatore Pig Latin sugli argomenti:

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn "%s in Pig Latin is: %s" name newName

    0
```

A questo punto è possibile eseguire l'app console dalla riga di comando:

```dotnetcli
dotnet run apple banana
```

Si noterà che restituisce lo stesso risultato del file di script, ma questa volta come programma in esecuzione.

## <a name="troubleshooting-ionide"></a>Risoluzione dei problemi relativi a Ionide

Ecco alcuni modi in cui è possibile risolvere alcuni problemi che potrebbero verificarsi:

1. Per ottenere le funzionalità di modifica del codice di Ionide F# , è necessario salvare i file su disco e all'interno di una cartella aperta nell'area di lavoro Visual Studio Code.
1. Se sono state apportate modifiche al sistema o sono stati installati i prerequisiti di Ionide con Visual Studio Code aprire, riavviare Visual Studio Code.
1. Se nelle directory del progetto sono presenti caratteri non validi, Ionide potrebbe non funzionare.  Se questo è il caso, rinominare le directory del progetto.
1. Se nessuno dei comandi Ionide funziona, controllare i tasti di scelta [Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) per verificare se si sta eseguendo l'override per errore.
1. Se Ionide è danneggiato nel computer e nessuno dei precedenti ha risolto il problema, provare a rimuovere la directory `ionide-fsharp` nel computer e reinstallare la suite di plug-in.
1. Se non è stato possibile caricare un progetto F# (il Esplora soluzioni lo visualizzerà), fare clic con il pulsante destro del mouse sul progetto e fare clic su **Visualizza dettagli** per ottenere altre informazioni di diagnostica.

Ionide è un progetto open source creato e gestito da membri della F# community. Segnala i problemi e potrai contribuire al [repository GitHub ionide-VSCODE-FSharp](https://github.com/ionide/ionide-vscode-fsharp).

È anche possibile richiedere ulteriore assistenza da parte degli sviluppatori e F# della community di Ionide nel canale di [Ionide](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Passaggi successivi

Per ulteriori informazioni su F# e sulle funzionalità del linguaggio, vedere [Panoramica di F# ](../tour.md).
