---
title: Introduzione a F# in Visual Studio Code
description: Informazioni su come usare F# con Visual Studio Code e Ionide plug-in suite.
ms.date: 12/23/2018
ms.openlocfilehash: 79863d57abbc71d59ce01fe30abf1db0a569f1e1
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2019
ms.locfileid: "57788492"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introduzione a F# in Visual Studio Code

È possibile scrivere F# nel [Visual Studio Code](https://code.visualstudio.com) con le [plug-in Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) per ottenere un'esperienza ottimale per ambiente di sviluppo integrato (IDE) cross-platform e leggero con IntelliSense e di base del codice refactoring. Visita [Ionide.io](http://ionide.io) per altre informazioni sul plug-in.

Per iniziare, assicurarsi di aver [ F# e il plug-in Ionide correttamente installato](install-fsharp.md#install-f-with-visual-studio-code).

> [!NOTE]
> Ionide genererà .NET Framework F# progetti, non core con dotnet, che possa verificarsi problemi di compatibilità multipiattaforma. Se si sta usando **Linux** oppure **OSX**, in modo più semplice per iniziare consiste nell'utilizzare i (strumenti da riga di comando) [https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line].

## <a name="creating-your-first-project-with-ionide"></a>Creazione del primo progetto con Ionide

Per creare un nuovo F# del progetto, aprire Visual Studio Code in una nuova cartella (è possibile specificare un nome qualsiasi).

Successivamente, aprire il riquadro comandi (**Visualizza > riquadro comandi**) e digitare il comando seguente:

```
> F# new project
```

Questa è una tecnologia di [FORGE](https://github.com/fsharp-editing/Forge) progetto.

> [!NOTE]
> Se le opzioni del modello non è visualizzato, provare ad aggiornare i modelli eseguendo il comando seguente nel riquadro comandi: `>F#: Refresh Project Templates`.

Selezionare "F#: Nuovo progetto"premendo **invio**. Consente di andare al passaggio successivo, ovvero per la selezione di un modello di progetto.

Selezionare il `classlib` modello di comandi e premere **invio**.

Successivamente, selezionare una directory per creare il progetto in. Se si lascia vuoto, utilizza la directory corrente.

Infine, denominare il progetto nel passaggio finale. F#viene utilizzato [maiuscole minuscole Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi dei progetti. Questo articolo usa `ClassLibraryDemo` come nome. Dopo aver immesso il nome desiderato per il progetto, premere **invio**.

Se è stato eseguito il passaggio precedente, si dovrebbe ottenere Visual Studio Code area di lavoro sul lato sinistro vengono visualizzati gli elementi seguenti:

1. Il F# progetto, visualizzati sotto il `ClassLibraryDemo` cartella.
2. La struttura di directory corretti per l'aggiunta dei pacchetti tramite [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Multi-piattaforma di compilazione skript [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. Il `paket.exe` eseguibile che consente di recuperare i pacchetti e di risolvere le dipendenze per l'utente.
5. Oggetto `.gitignore` file se si desidera aggiungere il progetto al controllo del codice sorgente basati su Git.

## <a name="writing-some-code"></a>Scrivere il codice

Aprire il *ClassLibraryDemo* cartella.  Si dovrebbero vedere i file seguenti:

1. `ClassLibraryDemo.fs`, un F# file di implementazione con una classe definita.
2. `ClassLibraryDemo.fsproj`, un F# file di progetto usato per compilare il progetto.
3. `Script.fsx`, un F# file di script che consente di caricare il file di origine.
4. `paket.references`, un file Paket che specifichi le dipendenze di progetto.

Apri `Script.fsx`e aggiungere il codice seguente alla fine di esso:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Questa funzione converte una parola in una forma di [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). Il passaggio successivo consiste nella valutazione usando F# Interactive (FSI).

Evidenziare l'intera funzione (deve essere lunga 11 righe). Una volta che viene evidenziato, tenere premuto il **Alt** chiave e fare clic su **invio**. Si noterà una finestra popup di seguito, e dovrebbe avere un aspetto simile al seguente:

![Esempio di F# file di output con Ionide Interactive](media/getting-started-vscode/vscode-fsi.png)

Ciò ha tre operazioni:

1. Avviato il processo FSI.
2. Il codice evidenziato inviato tramite il processo di FSI.
3. Il processo di FSI valutato il codice che è stato inviato tramite.

Perché non è ciò che è stato inviato tramite un [funzione](../language-reference/functions/index.md), è ora possibile chiamare questa funzione FSI! Nella finestra interattiva, digitare quanto segue:

```fsharp
toPigLatin "banana";;
```

Verrà visualizzato il risultato seguente:

```fsharp
val it : string = "ananabay"
```

A questo punto, proviamo a utilizzare una vocale come la prima lettera. Immettere quanto segue:

```fsharp
toPigLatin "apple";;
```

Verrà visualizzato il risultato seguente:

```fsharp
val it : string = "appleyay"
```

La funzione sembra funzionare come previsto. Congratulazioni, appena scritto la prima volta F# funzione in Visual Studio Code e viene valutato con FSI!

> [!NOTE]
> Come si può notare, le righe in FSI vengono terminate con `;;`. Questo avviene perché FSI consente di immettere più righe. Il `;;` alla fine consente FSI sapere quando termina il codice.

## <a name="explaining-the-code"></a>Che descrive il codice

Se non si è certi sulle operazioni effettivamente eseguite il codice, di seguito è una procedura dettagliata.

Come può notare, `toPigLatin` è una funzione che accetta una parola come input e lo converte in una rappresentazione di Pig Latin di tale parola. Le regole per questo sono come segue:

Se il primo carattere in una parola inizia con una vocale, aggiungere "yay" alla fine della parola. Se non viene avviato con una vocale, passare al primo carattere alla fine della parola e aggiungervi "ay".

Si può notare quanto segue nella FSI:

```fsharp
val toPigLatin : word:string -> string
```

Ciò indica che `toPigLatin` è una funzione che accetta una `string` come input (denominato `word`) e restituisce un altro `string`. Questo è noto come il [firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale di F# che è fondamentale per informazioni su F# codice. Noterete anche questo se si posiziona la funzione in Visual Studio Code.

Nel corpo della funzione, si noteranno due parti distinte:

1. Una funzione interna, chiamata `isVowel`, che determina se un determinato carattere (`c`) consiste nel verificare se corrisponde a uno dei modelli forniti tramite una vocale [criteri di ricerca](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Un' [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) espressione che controlla se il primo carattere è una vocale e costrutti di valore restituito dai caratteri di input in base se il primo carattere è stata una vocale o meno:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Il flusso di `toPigLatin` pertanto:

Controllare se il primo carattere della parola di input è una vocale. Se si tratta, collegare "yay" alla fine della parola. In caso contrario, passare al primo carattere alla fine della parola e aggiungervi "ay".

Un'operazione finale a questo proposito: non è nessuna istruzione esplicita da restituire dalla funzione, a differenza di molti altri linguaggi disponibili. Infatti, F# è basato su espressione e l'ultima espressione nel corpo di una funzione è il valore restituito. Poiché `if..then..else` è a sua volta un'espressione, il corpo del `then` blocco o nel corpo del `else` blocchi verranno restituiti in base al valore di input.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Spostare il codice di script nel file di implementazione

Nelle sezioni precedenti di questo articolo illustrato innanzitutto comune nella scrittura F# code: scrittura di una funzione iniziale ed eseguendola in modo interattivo con FSI. Questo è noto come lo sviluppo basato su REPL, dove [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) è l'acronimo di "Read-Eval-Print Loop". È un ottimo modo per provare a usare funzionalità fino a quando non si dispone di un elemento di lavoro.

Il passaggio successivo di sviluppo basato su REPL consiste nello spostare codice funzionante in un F# file di implementazione. Può quindi essere compilato per il F# compilatore in un assembly che può essere eseguito.

Per iniziare, aprire `ClassLibraryDemo.fs`.  Si noterà che il codice è già in non esiste. Andare avanti ed eliminare la definizione di classe, ma assicurarsi di lasciare il [ `namespace` ](../language-reference/namespaces.md) dichiarazione nella parte superiore.

Successivamente, creare una nuova [ `module` ](../language-reference/modules.md) chiamato `PigLatin` e copiare il `toPigLatin` funzione al suo interno di conseguenza:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Successivamente, aprire il `Script.fsx` nuovamente file ed eliminare l'intero `toPigLatin` funzionare, ma occorre assicurarsi di mantenere le due righe seguenti nel file:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```
Selezionare entrambe le righe di testo e premere Alt + INVIO per eseguire le righe seguenti in FSI. Si caricherà il contenuto della libreria di Pig Latin nel processo di FSI e `open` il `ClassLibraryDemo` dello spazio dei nomi in modo da poter accedere alla funzionalità.

Successivamente, nella finestra di FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Operazione completata Si ottengono gli stessi risultati man mano che in precedenza, ma ora caricati da un F# file di implementazione. La differenza principale è che F# file di origine sono compilati negli assembly che può essere eseguito ovunque, non solo in FSI.

## <a name="summary"></a>Riepilogo

In questo articolo, si è appreso:

1. Come configurare Visual Studio Code con Ionide.
2. Come creare la prima volta F# progetto con Ionide.
3. Come usare F# esecuzione script per scrivere la prima volta F# funzionano in Ionide e quindi eseguire il comando della FSI.
4. Come eseguire la migrazione del codice di script F# di origine e quindi richiamare il codice da FSI.

Sta ora riesce a scrivere molto altro ancora F# il codice tramite Visual Studio Code e Ionide.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Ecco alcuni modi, che è possibile risolvere alcuni problemi che si verificano:

1. Per ottenere il codice di funzioni di modifica del Ionide, il F# i file devono essere salvati su disco e all'interno di una cartella in cui è aperta nell'area di lavoro di Visual Studio Code.
2. Se è stato apportato modifiche al sistema o installato Ionide prerequisiti con Visual Studio Code aprire, riavviare Visual Studio Code.
3. Controllo che è possibile usare il F# compilatore e F# interattivo dalla riga di comando senza un percorso completo. È possibile farlo digitando `fsc` in una riga di comando per il F# compilatore, e `fsi` oppure `fsharpi` per l'oggetto visivo F# strumenti su Windows e Mono in Mac/Linux, rispettivamente.
4. Se le directory di progetto contiene caratteri non validi, Ionide potrebbe non funzionare.  In questo caso, rinominare la directory di progetto.
5. Se nessuno dei comandi Ionide lavora, verificare i [tasti di scelta rapida Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per vedere se si sta eseguendone l'override accidentale.
6. Se viene interrotto Ionide nel computer e nessuna delle precedenti ha risolto il problema, provare a rimuovere il `ionide-fsharp` directory nel computer e reinstallare il plug-in gruppo.

Ionide è un progetto open source compilato e gestito da membri del F# community. . Segnalare problemi e liberamente il contributo di [Ionide-Visual Studio code: Repository GitHub di FSharp](https://github.com/ionide/ionide-vscode-fsharp).

Se si dispone di un problema al report, seguire [le istruzioni per ottenere i log da utilizzare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

È anche possibile richiedere ulteriore assistenza per gli sviluppatori Ionide e F# community nella [Ionide Gitter canale](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni su F# e le funzionalità del linguaggio, consultare [Tour di F# ](../tour.md).
