---
title: Introduzione F# a in Visual Studio Code
description: Informazioni su come usare F# con Visual Studio Code e la suite di plug-in Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: baaa87207122cfe314972aee5dfaf8a41de2c394
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629972"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introduzione F# a in Visual Studio Code

È possibile scrivere F# in [Visual Studio Code](https://code.visualstudio.com) con il [plug](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) -in IONIDE per ottenere un'ottima esperienza IDE (Integrated Development Environment) multipiattaforma con IntelliSense e i refactoring del codice di base. Visitare [Ionide.io](http://ionide.io) per altre informazioni sul plug-in.

Per iniziare, verificare che [ F# sia installato correttamente il plug](install-fsharp.md#install-f-with-visual-studio-code)-in Ionide.

> [!NOTE]
> Ionide genererà i F# progetti di .NET Framework, non DotNet core, che possono avere problemi di compatibilità tra piattaforme. Se si esegue in **Linux** o **OSX**, un modo più semplice per iniziare consiste nell'usare gli strumenti da [riga di comando](get-started-command-line.md).

## <a name="creating-your-first-project-with-ionide"></a>Creazione del primo progetto con Ionide

Per creare un nuovo F# progetto, aprire Visual Studio Code in una nuova cartella. è possibile assegnarle un nome qualsiasi.

Successivamente, aprire il riquadro comandi (**visualizzare > riquadro comandi**) e digitare quanto segue:

```
> F# new project
```

Questo è basato sul progetto [Forge](https://github.com/fsharp-editing/Forge) .

> [!NOTE]
> Se non vengono visualizzate le opzioni del modello, provare ad aggiornare i modelli eseguendo il comando seguente nel riquadro `>F#: Refresh Project Templates`comandi:.

Selezionare "F#: Nuovo progetto "premendo **invio**. Questa operazione consente di passare al passaggio successivo, che consente di selezionare un modello di progetto.

Selezionare il `classlib` modello e premere **invio**.

Selezionare quindi una directory in cui creare il progetto. Se si lascia vuota, viene utilizzata la directory corrente.

Infine, assegnare un nome al progetto nel passaggio finale. F#Usa il [caso Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi di progetto. Questo articolo usa `ClassLibraryDemo` come nome. Dopo aver immesso il nome desiderato per il progetto, premere **invio**.

Se è stato eseguito il passaggio precedente, è necessario ottenere l'area di lavoro Visual Studio Code sul lato sinistro per visualizzare il codice seguente:

1. F# Progetto stesso, sotto la `ClassLibraryDemo` cartella.
2. Struttura di directory corretta per l'aggiunta di [`Paket`](https://fsprojects.github.io/Paket/)pacchetti tramite.
3. Uno script di compilazione multipiattaforma con [`FAKE`](https://fsharp.github.io/FAKE/).
4. Eseguibile che può recuperare i pacchetti e risolvere le `paket.exe` dipendenze.
5. Un `.gitignore` file se si desidera aggiungere questo progetto al controllo del codice sorgente basato su git.

## <a name="writing-some-code"></a>Scrittura di codice

Aprire la cartella *ClassLibraryDemo* .  Verranno visualizzati i file seguenti:

1. `ClassLibraryDemo.fs`, un F# file di implementazione con una classe definita.
2. `ClassLibraryDemo.fsproj`, un F# file di progetto utilizzato per compilare il progetto.
3. `Script.fsx`, un F# file di script che carica il file di origine.
4. `paket.references`, un file Paket che specifica le dipendenze del progetto.

Aprire `Script.fsx`e aggiungere il codice seguente alla fine:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Questa funzione converte una parola in una forma di [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). Il passaggio successivo consiste nel valutarlo tramite F# Interactive (FSI).

Evidenziare l'intera funzione (dovrebbe essere lungo 11 righe). Una volta evidenziato, mantenere il tasto **ALT** e premere **invio**. Si noterà una finestra popup sotto e dovrebbe essere visualizzata una schermata simile alla seguente:

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
> Come si può notare, le righe in FSI vengono terminate con `;;`. Questo perché FSI consente di immettere più righe. Alla fine, può essere ingradodistabilirequandoilcodiceèterminato.`;;`

## <a name="explaining-the-code"></a>Spiegazione del codice

Se non si è certi di cosa stia effettivamente eseguendo il codice, ecco una procedura dettagliata.

Come si può notare, `toPigLatin` è una funzione che accetta una parola come input e la converte in una rappresentazione Pig-Latin della parola. Le regole per questa operazione sono le seguenti:

Se il primo carattere di una parola inizia con una vocale, aggiungere "Yay" alla fine della parola. Se non inizia con una vocale, sposta il primo carattere alla fine della parola e Aggiungi "Ay".

In FSI è possibile notare quanto segue:

```fsharp
val toPigLatin : word:string -> string
```

Si tratta di una funzione che accetta `string` come input (chiamato `word`) e restituisce un altro `string`oggetto. `toPigLatin` Questa operazione è nota come [firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale della F# chiave per comprendere F# il codice. Si noterà anche che se si passa il mouse sulla funzione in Visual Studio Code.

Nel corpo della funzione si noteranno due parti distinte:

1. Funzione interna, denominata `isVowel`, che determina se un carattere specificato (`c`) è una vocale controllando se corrisponde a uno dei modelli forniti tramite [criteri di ricerca](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Espressione che controlla se il primo carattere è una vocale e costruisce un valore restituito dai caratteri di input in base a se il primo carattere è una vocale o meno:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Il flusso di `toPigLatin` è quindi:

Controllare se il primo carattere della parola di input è una vocale. In caso contrario, alleghi "Yay" alla fine della parola. In caso contrario, spostare il primo carattere alla fine della parola e aggiungere "Ay".

Si noti che, a differenza di molti altri linguaggi, non esiste alcuna istruzione esplicita da restituire dalla funzione. Poiché F# è basato su espressioni e l'ultima espressione nel corpo di una funzione è il valore restituito. Poiché `if..then..else` è a sua volta un'espressione, il corpo `then` del blocco `else` o il corpo del blocco verrà restituito a seconda del valore di input.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Trasferimento del codice di script nel file di implementazione

Le sezioni precedenti di questo articolo hanno illustrato un primo passaggio comune nella F# scrittura di codice: scrittura di una funzione iniziale ed esecuzione interattiva con FSI. Questo è noto come sviluppo basato su REPL, in cui [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) sta per "Read-Evaluate-Print Loop". È un ottimo modo per sperimentare le funzionalità fino a quando non si dispone di qualcosa di funzionante.

Il passaggio successivo nello sviluppo basato su REPL consiste nello spostare il codice di lavoro F# in un file di implementazione. Può quindi essere compilato dal F# compilatore in un assembly che può essere eseguito.

Per iniziare, aprire `ClassLibraryDemo.fs`.  Si noterà che il codice è già presente. Procedere ed eliminare la definizione della classe, ma assicurarsi di lasciare la [`namespace`](../language-reference/namespaces.md) dichiarazione nella parte superiore.

Successivamente, creare un nuovo [`module`](../language-reference/modules.md) oggetto `PigLatin` denominato e copiarvi la `toPigLatin` funzione:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Successivamente, aprire nuovamente `Script.fsx` il file ed eliminare l'intera `toPigLatin` funzione, ma assicurarsi di lasciare le due righe seguenti nel file:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Selezionare entrambe le righe di testo e premere ALT + INVIO per eseguire queste righe in FSI. Il contenuto della libreria Pig Latin viene caricato nel processo FSI e `open` `ClassLibraryDemo` nello spazio dei nomi in modo da poter accedere alla funzionalità.

Quindi, nella finestra FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Operazione completata Si ottengono gli stessi risultati di prima, ma ora caricati da un F# file di implementazione. La differenza principale consiste nel fatto F# che i file di origine vengono compilati in assembly che possono essere eseguiti ovunque, non solo in FSI.

## <a name="summary"></a>Riepilogo

In questo articolo si è appreso come:

1. Come configurare Visual Studio Code con Ionide.
2. Come creare il primo F# progetto con Ionide.
3. Come usare F# lo scripting per scrivere la prima F# funzione in Ionide ed eseguirla in FSI.
4. Come eseguire la migrazione del codice di F# script all'origine e quindi chiamare tale codice da FSI.

A questo punto si è pronti per scrivere F# altro codice usando Visual Studio Code e Ionide.

## <a name="troubleshooting"></a>risoluzione dei problemi

Ecco alcuni modi in cui è possibile risolvere alcuni problemi che potrebbero verificarsi:

1. Per ottenere le funzionalità di modifica del codice di Ionide F# , è necessario salvare i file su disco e all'interno di una cartella aperta nell'area di lavoro Visual Studio Code.
2. Se sono state apportate modifiche al sistema o sono stati installati i prerequisiti di Ionide con Visual Studio Code aprire, riavviare Visual Studio Code.
3. Verificare che sia possibile usare il F# compilatore e F# interattivo dalla riga di comando senza un percorso completo. È possibile eseguire `fsc` questa operazione digitando rispettivamente in una riga di comando per il `fsharpi` F# compilatore e `fsi` o F# per gli strumenti visivi in Windows e mono in Mac/Linux.
4. Se nelle directory del progetto sono presenti caratteri non validi, Ionide potrebbe non funzionare.  Se questo è il caso, rinominare le directory del progetto.
5. Se nessuno dei comandi Ionide funziona, controllare i tasti di scelta [Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per verificare se si sta eseguendo l'override per errore.
6. Se Ionide è danneggiato nel computer e nessuno dei precedenti ha risolto il problema, provare a rimuovere la `ionide-fsharp` directory nel computer e reinstallare la suite di plug-in.

Ionide è un progetto open source creato e gestito da membri della F# community. Segnala i [problemi e potrai contribuire al Ionide-VSCode: Repository](https://github.com/ionide/ionide-vscode-fsharp)GitHub di FSharp.

Se si verifica un problema per il report, seguire [le istruzioni per ottenere i log da usare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

È anche possibile richiedere ulteriore assistenza da parte degli sviluppatori e F# della community di Ionide nel canale di [Ionide](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Passaggi successivi

Per ulteriori informazioni su F# e sulle funzionalità del linguaggio, vedere [Panoramica di F# ](../tour.md).
