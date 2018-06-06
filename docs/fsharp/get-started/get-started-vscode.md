---
title: 'Introduzione a F # in Visual Studio Code'
description: "Informazioni sull'utilizzo di F # con codice di Visual Studio e la suite di plug-in Ionide."
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728628"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introduzione a F # in Visual Studio Code

È possibile scrivere F # in [Visual Studio Code](https://code.visualstudio.com) con il [plug-in Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), per ottenere un'esperienza ottimale per ambiente di sviluppo integrato (IDE) multipiattaforma e leggero con IntelliSense e il codice di base refactoring. Visitare [Ionide.io](http://ionide.io) per ulteriori informazioni sulla famiglia di plug-in.

## <a name="prerequisites"></a>Prerequisiti

È necessario disporre [git installato](https://git-scm.com/download) e disponibili del TRACCIATO per utilizzare modelli di progetto in Ionide. È possibile verificare che sia installato correttamente digitando `git --version` in un prompt dei comandi e quindi premendo **invio**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

Usa Ionide [Mono](http://www.mono-project.com). Il modo più semplice per installare Mono in macOS è tramite Homebrew. È sufficiente digitare quanto segue in terminale:

```
brew install mono
```

È necessario installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

Usa anche su Linux, Ionide [Mono](https://www.mono-project.com). Se si è in Debian o Ubuntu, è possibile utilizzare le operazioni seguenti:

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

È necessario installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Se si è in Windows, è necessario [installare Visual Studio con il supporto di F #](get-started-visual-studio.md#installing-f). Questo modo vengono installati tutti i componenti necessari per scrivere, compilare ed eseguire codice F #.

È necessario installare anche il [.NET Core SDK](https://www.microsoft.com/net/download/).

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a>L'installazione di Visual Studio Code e il plug-in Ionide

È possibile installare Visual Studio Code dal [code.visualstudio.com](https://code.visualstudio.com) sito Web.

Successivamente, scegliere l'icona delle estensioni e cercare "Ionide":

Il plug-in solo necessari per il supporto di F # in Visual Studio Code è [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Tuttavia, è inoltre possibile installare [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere [CAMUFFARE](https://fsharp.github.io/FAKE/) supportano e [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) ottenere [Paket](https://fsprojects.github.io/Paket/) supportano. FALSIFICARE e Paket sono F # community strumenti aggiuntivi per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.

## <a name="creating-your-first-project-with-ionide"></a>Creazione del primo progetto con Ionide

Per creare un nuovo progetto F #, aprire Visual Studio Code in una nuova cartella (è possibile assegnare il nome desiderato).

Successivamente, aprire la tavolozza delle comando (**Vista > tavolozza delle comando**) e digitare quanto segue:

```
> F# new project
```

Questa è una tecnologia di [FORGE](https://github.com/fsharp-editing/Forge) progetto.

> [!NOTE]
Se le opzioni del modello non viene visualizzato, provare ad aggiornare i modelli eseguendo il comando seguente nel riquadro comandi: `>F#: Refresh Project Templates`.

Selezionare "progetto F #: nuovo", raggiungendo **invio**. Consente di andare al passaggio successivo, ovvero per la selezione di un modello di progetto.

Selezionare il `classlib` modello e premere **invio**.

Successivamente, selezionare una directory in cui creare il progetto. Se si lascia vuoto, utilizza la directory corrente.

Infine, denominare il progetto nel passaggio finale. F # utilizza [maiuscole minuscole Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi dei progetti. Questo articolo usa `ClassLibraryDemo` come nome. Dopo aver immesso il nome desiderato per il progetto, premere **invio**.

Se è stato eseguito il passaggio precedente, è necessario ottenere Visual Studio codice area di lavoro sul lato sinistro vengono visualizzati con i componenti seguenti:

1. F # del progetto stesso, trova di sotto di `ClassLibraryDemo` cartella.
2. La struttura di directory corretto per l'aggiunta di pacchetti tramite [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Una libreria multipiattaforma compilare lo script con [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. Il `paket.exe` eseguibile che consente di recuperare i pacchetti e risolvere le dipendenze per l'utente.
5. Oggetto `.gitignore` file se si desidera aggiungere il progetto al controllo del codice sorgente basati su Git.

## <a name="writing-some-code"></a>Scrittura di codice

Aprire il *ClassLibraryDemo* cartella.  È necessario visualizzare i file seguenti:

1. `ClassLibraryDemo.fs`, un file di implementazione F # con una classe definita.
2. `ClassLibraryDemo.fsproj`, un file di progetto F # per compilare questo progetto.
3. `Script.fsx`, un file di script F # che carica il file di origine.
4. `paket.references`, un file Paket che specifica le dipendenze di progetto.

Aprire `Script.fsx`e aggiungere il codice seguente alla fine di esso:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Questa funzione converte una parola a una forma di [latino Pig](https://en.wikipedia.org/wiki/Pig_Latin). Il passaggio successivo consiste nel valutare l'utilizzo di F # Interactive (FSI).

Evidenziare l'intera funzione (deve essere lunga 11 righe). Una volta che viene evidenziato, tenere premuto il **Alt** chiave e fare clic su **invio**. Si noterà una finestra popup di sotto e risulterà simile al seguente:

![Esempio di output F # Interactive con Ionide](media/getting-started-vscode/vscode-fsi.png)

Questo ha tre operazioni:

1. Avviato il processo FSI.
2. Inviato il codice evidenziato tramite il processo FSI.
3. Il processo FSI valutato il codice che è inviati.

Perché è stato inviato tramite un [funzione](../language-reference/functions/index.md), è ora possibile chiamare questa funzione FSI! Nella finestra interattiva, digitare quanto segue:

```fsharp
toPigLatin "banana";;
```

Verrà visualizzato il risultato seguente:

```fsharp
val it : string = "ananabay"
```

A questo punto, provare con una vocale come la prima lettera. Immettere quanto segue:

```fsharp
toPigLatin "apple";;
```

Verrà visualizzato il risultato seguente:

```fsharp
val it : string = "appleyay"
```

La funzione sembra funzionare come previsto. Complimenti, sufficiente ha scritto la prima funzione F # nel codice di Visual Studio e viene valutato con FSI.

>[!NOTE]
Come si può notare, le righe nel FSI vengono terminate con `;;`. Questo avviene perché FSI consente di immettere più righe. Il `;;` alla fine informa FSI al termine il codice.

## <a name="explaining-the-code"></a>Descrivere il codice

Se non si conosce il codice effettivamente operazioni, di seguito è una procedura guidata.

Come si può notare, `toPigLatin` è una funzione che accetta una parola come input e lo converte in una rappresentazione Pig-Latin di quella parola. Le regole per questo sono come segue:

Se il primo carattere in una parola inizia con una vocale, aggiungere "yay" alla fine della parola. Se non inizia con una vocale, spostare il primo carattere alla fine della parola e aggiungervi "generato".

Si può notare quanto segue in FSI:

```fsharp
val toPigLatin : word:string -> string
```

Ciò indica che `toPigLatin` è una funzione che accetta un `string` come input (chiamato `word`) e restituisce un altro `string`. Questo è noto come il [la firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale di F # che è essenziale per comprendere il codice F #. Si noterà inoltre questa se si passa il mouse la funzione nel codice di Visual Studio.

Nel corpo della funzione, si noteranno due parti distinte:

1. Una funzione interna, chiamata `isVowel`, che determina se un determinato carattere (`c`) è una vocale controllando se corrisponde a uno dei modelli forniti tramite [criteri di ricerca](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Un' [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) espressione che controlla se il primo carattere è una vocale e costrutti di valore restituito dai caratteri di input in base a se il primo carattere è una vocale o meno:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Il flusso di `toPigLatin` pertanto:

Controllare se il primo carattere della parola input è una vocale. Questo caso, è possibile collegare "yay" alla fine della parola. In caso contrario, spostare il primo carattere alla fine della parola e aggiungervi "generato".

Un elemento finale a questo proposito: nessuna istruzione esplicita da restituire dalla funzione, a differenza dei molti altri linguaggi. In questo modo F # è basato su espressioni e l'ultima espressione nel corpo di una funzione è il valore restituito. Poiché `if..then..else` è a sua volta un'espressione, il corpo del `then` blocco o il corpo del `else` blocco verrà restituito in base al valore di input.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Spostare il codice di script nel file di implementazione

Nelle sezioni precedenti di questo articolo è illustrato un comune primo passaggio nella scrittura di codice F #: scrittura di una funzione iniziale e l'esecuzione in modo interattivo con FSI. Questo è noto come lo sviluppo basato su REPL, dove [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) è l'acronimo di "Lettura-Evaluate-Print Loop". È un ottimo modo per sperimentare funzionalità fino a quando non si dispone di un elemento di lavoro.

Il passaggio successivo di sviluppo basato su REPL consiste nello spostare il codice di lavoro in un file di implementazione di F #. Si può quindi essere compilato dal compilatore F # in un assembly che può essere eseguito.

Per iniziare, aprire `ClassLibraryDemo.fs`.  Si noterà che il codice è già in non esiste. Vado Avanti ed eliminare la definizione della classe, ma assicurarsi di lasciare il [ `namespace` ](../language-reference/namespaces.md) dichiarazione nella parte superiore.

Successivamente, creare un nuovo [ `module` ](../language-reference/modules.md) chiamato `PigLatin` e copiare il `toPigLatin` funzione in cui vengono di conseguenza:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Aprire quindi il `Script.fsx` file nuovamente ed eliminare l'intera `toPigLatin` funzionare, ma assicurarsi di mantenere le due righe seguenti nel file:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

La prima riga è necessaria per FSI scripting per caricare `ClassLibraryDemo.fs`. La seconda riga è un aspetto pratico: omettendola è facoltativo, ma è necessario digitare `open ClassLibraryDemo` in una finestra FSI se si desidera portare il `ToPigLatin` modulo nell'ambito.

Successivamente, nella finestra FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Operazione completata Ottenere gli stessi risultati, ma ora è caricata da un file di implementazione di F #. La differenza principale è che i file di origine F # sono compilati in assembly che possono essere eseguiti in qualsiasi punto, non solo in FSI.

## <a name="summary"></a>Riepilogo

In questo articolo, si è appreso:

1. Come impostare il codice di Visual Studio con Ionide.
2. Modalità di creazione del primo progetto F # con Ionide.
3. Modalità di utilizzo di script F # per scrivere la prima funzione F # in Ionide e quindi eseguirla in FSI.
4. Come per la migrazione del codice di script F # origine e quindi chiamare il codice da FSI.

Ora risposta corretta per scrivere più F # codice utilizzando codice di Visual Studio e Ionide.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Ecco alcuni modi in che è possibile risolvere determinati problemi che è possibile eseguire:

1. Per ottenere le funzionalità di Ionide di modifica del codice, è necessario che i file di F # salvata su disco e all'interno di una cartella in cui è aperta nell'area di lavoro di Visual Studio Code.
2. Se è stato installato Ionide prerequisiti con codice di Visual Studio aprire o apportate modifiche al sistema, riavviare Visual Studio Code.
3. Verificare che è possibile utilizzare il compilatore F # e F # interactive dalla riga di comando senza un percorso completo. È possibile farlo digitando `fsc` in una riga di comando per il compilatore F # e `fsi` o `fsharpi` per Visual F # degli strumenti in Windows e Mono in Linux o Mac, rispettivamente.
4. Se le directory di progetto contiene caratteri non validi, Ionide potrebbe non funzionare.  In questo caso, rinominare la directory di progetto.
5. Se nessuno dei comandi Ionide funzionino, controllare il [codice di Visual Studio keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per vedere se si sta eseguendo l'override li accidentalmente.
6. Se Ionide viene interrotta nel computer in uso e nessuna delle precedenti ha risolto il problema, provare a rimuovere il `ionide-fsharp` directory nel computer e reinstallare il plug-in gruppo.

Ionide è un progetto open source compilato e gestito dai membri della community di F #. Per segnalare problemi e frattempo il contributo di [Ionide VSCode: repository FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).

Se si dispone di un problema al report, seguire [le istruzioni per ottenere i log da utilizzare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

È inoltre possibile richiedere ulteriore assistenza da sviluppatori Ionide e della community di F # nel [Ionide Gitter canale](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Passaggi successivi

Per ulteriori informazioni su F # e le funzionalità del linguaggio, estrarre [presentazione di F #](../tour.md).
