---
title: Introduzione a F# in Visual Studio Code
description: Informazioni su come utilizzare F# con Visual Studio Code e Ionide plug-in suite.
ms.date: 05/28/2018
ms.openlocfilehash: e962be2796cf0d6eb90d459730659e492f864716
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "50192668"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introduzione a F# in Visual Studio Code

È possibile scrivere F# [Visual Studio Code](https://code.visualstudio.com) con il [plug-in Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) per ottenere un'esperienza ottimale per ambiente di sviluppo integrato (IDE) cross-platform e leggero con IntelliSense e di base del codice refactoring. Visita [Ionide.io](http://ionide.io) per altre informazioni sul plug-in.

Per iniziare, assicurarsi di aver [F# e il plug-in Ionide correttamente installato](install-fsharp.md#install-f-with-visual-studio-code).

## <a name="creating-your-first-project-with-ionide"></a>Creazione del primo progetto con Ionide

Per creare un nuovo progetto F#, aprire Visual Studio Code in una nuova cartella (è possibile specificare un nome qualsiasi).

Successivamente, aprire il riquadro comandi (**Visualizza > riquadro comandi**) e digitare il comando seguente:

```
> F# new project
```

Questa è una tecnologia di [FORGE](https://github.com/fsharp-editing/Forge) progetto.

> [!NOTE]
Se le opzioni del modello non è visualizzato, provare ad aggiornare i modelli eseguendo il comando seguente nel riquadro comandi: `>F#: Refresh Project Templates`.

Selezionare "F#: nuovo progetto" premendo **invio**. Consente di andare al passaggio successivo, ovvero per la selezione di un modello di progetto.

Selezionare il `classlib` modello di comandi e premere **invio**.

Successivamente, selezionare una directory per creare il progetto in. Se si lascia vuoto, utilizza la directory corrente.

Infine, denominare il progetto nel passaggio finale. F# utilizza [maiuscole minuscole Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi dei progetti. Questo articolo usa `ClassLibraryDemo` come nome. Dopo aver immesso il nome desiderato per il progetto, premere **invio**.

Se è stato eseguito il passaggio precedente, si dovrebbe ottenere Visual Studio Code area di lavoro sul lato sinistro vengono visualizzati gli elementi seguenti:

1. F# del progetto stesso, visualizzati sotto il `ClassLibraryDemo` cartella.
2. La struttura di directory corretti per l'aggiunta dei pacchetti tramite [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Multi-piattaforma di compilazione skript [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. Il `paket.exe` eseguibile che consente di recuperare i pacchetti e di risolvere le dipendenze per l'utente.
5. Oggetto `.gitignore` file se si desidera aggiungere il progetto al controllo del codice sorgente basati su Git.

## <a name="writing-some-code"></a>Scrivere il codice

Aprire il *ClassLibraryDemo* cartella.  Si dovrebbero vedere i file seguenti:

1. `ClassLibraryDemo.fs`, un file di implementazione F# con una classe definita.
2. `ClassLibraryDemo.fsproj`, un file di progetto F# usato per compilare questo progetto.
3. `Script.fsx`, un file di script F# che carica il file di origine.
4. `paket.references`, un file Paket che specifichi le dipendenze di progetto.

Apri `Script.fsx`e aggiungere il codice seguente alla fine di esso:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Questa funzione converte una parola in una forma di [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). Il passaggio successivo consiste nel valutare con F# Interactive (FSI).

Evidenziare l'intera funzione (deve essere lunga 11 righe). Una volta che viene evidenziato, tenere premuto il **Alt** chiave e fare clic su **invio**. Si noterà una finestra popup di seguito, e dovrebbe avere un aspetto simile al seguente:

![Esempio di output di F# Interactive con Ionide](media/getting-started-vscode/vscode-fsi.png)

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

La funzione sembra funzionare come previsto. Complimenti, sufficiente ha scritto la prima funzione F# in Visual Studio Code e viene valutato con FSI.

>[!NOTE]
Come si può notare, le righe in FSI vengono terminate con `;;`. Questo avviene perché FSI consente di immettere più righe. Il `;;` alla fine consente FSI sapere quando termina il codice.

## <a name="explaining-the-code"></a>Che descrive il codice

Se non si è certi sulle operazioni effettivamente eseguite il codice, di seguito è una procedura dettagliata.

Come può notare, `toPigLatin` è una funzione che accetta una parola come input e lo converte in una rappresentazione di Pig Latin di tale parola. Le regole per questo sono come segue:

Se il primo carattere in una parola inizia con una vocale, aggiungere "yay" alla fine della parola. Se non viene avviato con una vocale, passare al primo carattere alla fine della parola e aggiungervi "ay".

Si può notare quanto segue nella FSI:

```fsharp
val toPigLatin : word:string -> string
```

Ciò indica che `toPigLatin` è una funzione che accetta una `string` come input (denominato `word`) e restituisce un altro `string`. Questo è noto come il [firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale di F# che è fondamentale per la comprensione del codice F#. Noterete anche questo se si posiziona la funzione in Visual Studio Code.

Nel corpo della funzione, si noteranno due parti distinte:

1. Una funzione interna, chiamata `isVowel`, che determina se un determinato carattere (`c`) consiste nel verificare se corrisponde a uno dei modelli forniti tramite una vocale [criteri di ricerca](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Un' [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) espressione che controlla se il primo carattere è una vocale e costrutti di valore restituito dai caratteri di input in base se il primo carattere è stata una vocale o meno:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Il flusso di `toPigLatin` pertanto:

Controllare se il primo carattere della parola di input è una vocale. Se si tratta, collegare "yay" alla fine della parola. In caso contrario, passare al primo carattere alla fine della parola e aggiungervi "ay".

Un'operazione finale a questo proposito: non è nessuna istruzione esplicita da restituire dalla funzione, a differenza di molti altri linguaggi disponibili. Infatti, F# è basato sull'espressione e l'ultima espressione nel corpo di una funzione è il valore restituito. Poiché `if..then..else` è a sua volta un'espressione, il corpo del `then` blocco o nel corpo del `else` blocchi verranno restituiti in base al valore di input.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Spostare il codice di script nel file di implementazione

Nelle sezioni precedenti di questo articolo illustrato innanzitutto comune nella scrittura di codice F#: scrittura di una funzione iniziale ed eseguendola in modo interattivo con FSI. Questo è noto come lo sviluppo basato su REPL, dove [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) è l'acronimo di "Read-Eval-Print Loop". È un ottimo modo per provare a usare funzionalità fino a quando non si dispone di un elemento di lavoro.

Il passaggio successivo di sviluppo basato su REPL consiste nello spostare codice funzionante in un file di implementazione F#. Può quindi essere compilato dal compilatore F# in un assembly che può essere eseguito.

Per iniziare, aprire `ClassLibraryDemo.fs`.  Si noterà che il codice è già in non esiste. Andare avanti ed eliminare la definizione di classe, ma assicurarsi di lasciare il [ `namespace` ](../language-reference/namespaces.md) dichiarazione nella parte superiore.

Successivamente, creare una nuova [ `module` ](../language-reference/modules.md) chiamato `PigLatin` e copiare il `toPigLatin` funzione al suo interno di conseguenza:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Successivamente, aprire il `Script.fsx` nuovamente file ed eliminare l'intero `toPigLatin` funzionare, ma occorre assicurarsi di mantenere le due righe seguenti nel file:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

La prima riga è necessaria per FSI scripting per caricare `ClassLibraryDemo.fs`. La seconda riga è utile: omettendola è facoltativo, ma è necessario digitare `open ClassLibraryDemo` in una finestra FSI se si vuole trasferire il `ToPigLatin` modulo nell'ambito.

Successivamente, nella finestra di FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Operazione completata Ottengono gli stessi risultati come prima, ma ora caricata da un file di implementazione F#. La differenza principale è che i file di origine F# sono compilati in assembly che può essere eseguito ovunque, non solo in FSI.

## <a name="summary"></a>Riepilogo

In questo articolo, si è appreso:

1. Come configurare Visual Studio Code con Ionide.
2. Come creare il primo progetto F# con Ionide.
3. Come usare script F# per scrivere la prima funzione F# in Ionide e quindi eseguire il comando della FSI.
4. Come migrare il codice script F# origine e quindi richiamare il codice dagli FSI.

Sta ora riesce a scrivere molto più codice F# con Visual Studio Code e Ionide.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Ecco alcuni modi, che è possibile risolvere alcuni problemi che si verificano:

1. Per ottenere le funzionalità di Ionide modifica del codice, i file F# devono essere salvati su disco e all'interno di una cartella in cui è aperta nell'area di lavoro di Visual Studio Code.
2. Se è stato apportato modifiche al sistema o installato Ionide prerequisiti con Visual Studio Code aprire, riavviare Visual Studio Code.
3. Verificare che è possibile usare il compilatore F# e F# interactive dalla riga di comando senza un percorso completo. È possibile farlo digitando `fsc` in una riga di comando per il compilatore F#, e `fsi` o `fsharpi` per il Visual F# tools in Windows e Mono in Mac/Linux, rispettivamente.
4. Se le directory di progetto contiene caratteri non validi, Ionide potrebbe non funzionare.  In questo caso, rinominare la directory di progetto.
5. Se nessuno dei comandi Ionide lavora, verificare i [tasti di scelta rapida Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per vedere se si sta eseguendone l'override accidentale.
6. Se viene interrotto Ionide nel computer e nessuna delle precedenti ha risolto il problema, provare a rimuovere il `ionide-fsharp` directory nel computer e reinstallare il plug-in gruppo.

Ionide è un progetto open source compilato e gestito da membri della community di F#. Per segnalare problemi ed è possibile aggiungere il proprio contributo nel [Ionide VSCode: repository GitHub di FSharp](https://github.com/ionide/ionide-vscode-fsharp).

Se si dispone di un problema al report, seguire [le istruzioni per ottenere i log da utilizzare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

È anche possibile richiedere ulteriore assistenza dagli sviluppatori Ionide e community di F# nel [Ionide Gitter canale](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni su F# e le funzionalità del linguaggio, consultare [Panoramica di F#](../tour.md).
