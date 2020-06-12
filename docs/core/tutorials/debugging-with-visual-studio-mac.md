---
title: Eseguire il debug di un'applicazione console .NET Core usando Visual Studio per Mac
description: Informazioni su come eseguire il debug di un'app console .NET Core usando Visual Studio Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 4941605923a9897d481aca4ec31408ab62e873f3
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713819"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-for-mac"></a>Esercitazione: eseguire il debug di un'applicazione console .NET Core usando Visual Studio per Mac

In questa esercitazione sono stati introdotti gli strumenti di debug disponibili in Visual Studio per Mac.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio per Mac](using-on-mac-vs.md).

## <a name="use-debug-build-configuration"></a>Usa configurazione build di debug

Il *debug* e la *versione* sono configurazioni di compilazione predefinite di Visual Studio. Usare la configurazione della build di debug per il debug e la configurazione di rilascio per la distribuzione finale della versione.

Nella configurazione di debug, un programma viene compilato con informazioni di debug simboliche complete e senza ottimizzazione. L'ottimizzazione rende più difficile il debug perché la relazione tra il codice sorgente e le istruzioni generate è più complessa. La configurazione di rilascio di un programma non dispone di informazioni di debug simboliche ed è completamente ottimizzata.

Per impostazione predefinita, Visual Studio usa la configurazione della build di debug, pertanto non è necessario modificarla prima del debug.

1. Avviare Visual Studio per Mac.

1. Aprire il progetto creato in [creare un'applicazione console .NET Core in Visual Studio per Mac](using-on-mac-vs.md).

   La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti. La seguente immagine della barra degli strumenti Mostra che Visual Studio è configurato per compilare la versione di debug dell'app:

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-debug.png" alt-text="Barra degli strumenti di Visual Studio con debug evidenziato":::

## <a name="set-a-breakpoint"></a>Imposta punto di interruzione

Un punto di *interruzione* interrompe temporaneamente l'esecuzione dell'applicazione prima che venga eseguita la riga con il punto di interruzione.

1. Impostare un punto di interruzione nella riga in cui vengono visualizzati il nome, la data e l'ora. A tale scopo, posizionare il cursore nella riga di codice e premere <kbd>⌘</kbd> <kbd>\\</kbd> (<kbd>comando</kbd> + <kbd>\\</kbd> ). Un altro modo per impostare un punto di interruzione consiste nel selezionare **Esegui**  >  **/Rimuovi** punto di interruzione dal menu.

   Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando il punto e visualizzando un punto rosso nel margine sinistro.

   :::image type="content" source="media/debugging-with-visual-studio-mac/set-breakpoint-in-editor.png" alt-text="Finestra del programma in Visual Studio con punto di interruzione impostato":::

1. Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per avviare il programma in modalità di debug. Un altro modo per avviare il debug è scegliere **Esegui**  >  **Avvia debug** dal menu.

1. Immettere una stringa nella finestra del terminale quando il programma richiede un nome e quindi premere <kbd>invio</kbd>.

1. L'esecuzione del programma si interrompe quando raggiunge il punto di interruzione, prima dell' `Console.WriteLine` esecuzione del metodo.

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-hit.png" alt-text="Screenshot di un punto di interruzione in Visual Studio":::

## <a name="use-the-immediate-window"></a>Utilizzare la finestra controllo immediato

La finestra **controllo immediato** consente di interagire con l'applicazione di cui si sta eseguendo il debug. È possibile modificare in modo interattivo il valore delle variabili per vedere come influiscono sul programma.

1. Se la finestra di **controllo immediato** non è visibile, visualizzarla scegliendo **Visualizza**i  >  **rilievi di debug**  >  **immediato**.

1. Immettere `name = "Gracie"` nella finestra di **controllo immediato** e premere <kbd>invio</kbd>.

1. Immettere `date = date.AddDays(1)` nella finestra di **controllo immediato** e premere <kbd>invio</kbd>.

   Nella finestra di **controllo immediato** vengono visualizzati il nuovo valore della variabile stringa e le proprietà del <xref:System.DateTime> valore.

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window.png" alt-text="Finestra di controllo immediato in Visual Studio":::

   Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione. I valori delle variabili appena modificate vengono aggiornati nella finestra variabili **locali** .

   :::image type="content" source="media/debugging-with-visual-studio-mac/locals-window.png" alt-text="Finestra variabili locali in Visual Studio":::

1. Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per continuare il debug.

   I valori visualizzati nel terminale corrispondono alle modifiche apportate nella finestra di **controllo immediato** .

   Se il terminale non è visibile, selezionare **Terminal-HelloWorld** nella barra di spostamento inferiore.

   :::image type="content" source="media/debugging-with-visual-studio-mac/terminal-hello-world.png" alt-text="Hello World terminali nella barra di spostamento inferiore":::

1. Premere un tasto qualsiasi per uscire dal programma.

1. Chiudere la finestra del terminale.

## <a name="set-a-conditional-breakpoint"></a>Impostare un punto di interruzione condizionale

Il programma visualizza una stringa immessa dall'utente. Ma cosa succede se l'utente non immette alcuna stringa? È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*.

1. fare clic con il <kbd>pulsante destro del</kbd>mouse sul punto rosso che rappresenta il punto di interruzione. Nel menu di scelta rapida selezionare **modifica**punto di interruzione.

1. Nella finestra di dialogo Modifica punto di **interruzione** immettere il codice seguente nel campo seguente **e la condizione seguente è true**e selezionare **applica**.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-settings.png" alt-text="Editor che mostra il pannello impostazioni del punto di interruzione":::

   Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .

   Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte.

1. Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per avviare il debug.

1. Nella finestra del terminale premere <kbd>invio</kbd> quando viene richiesto di immettere il nome.

   Poiché la condizione specificata ( `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione.

1. Selezionare la finestra variabili **locali** , che mostra i valori delle variabili locali per il metodo attualmente in esecuzione. In questo caso, `Main` è il metodo attualmente in esecuzione. Si noti che il valore della `name` variabile è `""` , ovvero <xref:System.String.Empty?displayProperty=nameWithType> .

1. È anche possibile notare che il valore è una stringa vuota immettendo il `name` nome della variabile nella finestra di **controllo immediato** e premendo <kbd>invio</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window-output.png" alt-text="La finestra di controllo immediato che mostra il nome è una stringa vuota":::

1. Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per continuare il debug.

1. Nella finestra del terminale premere un tasto qualsiasi per uscire dal programma.

1. Chiudere la finestra del terminale.

1. Deselezionare il punto di interruzione facendo clic sul punto rosso nel margine sinistro della finestra del codice. Un altro modo per cancellare un punto di interruzione è scegliere **esegui > Imposta/Rimuovi** punto di interruzione mentre è selezionata la riga di codice.

## <a name="step-through-a-program"></a>Scorrere un programma

Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione. In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma. Poiché questo programma è di piccole dimensioni, è possibile eseguire l'intero programma.

1. Impostare un punto di interruzione sulla parentesi graffa che contrassegna l'inizio del `Main` Metodo (premere <kbd>comando</kbd> + <kbd>\\</kbd> ).

1. Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per avviare il debug.

   Visual Studio si interrompe in corrispondenza della riga con il punto di interruzione.

1. Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>MAIUSC</kbd> + <kbd>comando</kbd> + <kbd>i</kbd>) o selezionare **Esegui**  >  **istruzione** per avanzare di una riga.

   Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   :::image type="content" source="media/debugging-with-visual-studio-mac/step-into-method.png" alt-text="Metodo Esegui istruzione di Visual Studio":::

   A questo punto, nella finestra **variabili locali** viene indicato che la `args` matrice è vuota e che i `name` `date` valori predefiniti sono e. Inoltre, Visual Studio ha aperto un terminale vuoto.

1. Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).

   Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`. La finestra **variabili locali** Mostra che `name` è `null` e il terminale Visualizza la stringa "Qual è il nome?".

1. Per rispondere alla richiesta, immettere una stringa nella finestra della console e premere <kbd>invio</kbd>.

1. Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).

   Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `date`. Nella finestra **variabili locali** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo. Il terminale Visualizza la stringa immessa al prompt.

1. Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).

   Nella finestra variabili **locali** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà. Il terminale non è stato modificato.

1. Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).

   Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Il terminale Visualizza la stringa formattata.

1. Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>u</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>u</kbd>) o selezionare **Esegui**  >  **istruzione/uscita**.

   Il terminale Visualizza un messaggio e attende che venga premuto un tasto.

1. Premere un tasto qualsiasi per uscire dal programma.

## <a name="use-release-build-configuration"></a>Usa configurazione build di rilascio

Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio. La versione di rilascio incorpora le ottimizzazioni del compilatore che possono influire negativamente sul comportamento di un'applicazione. Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.

Per compilare e testare la versione di rilascio dell'applicazione console, seguire questa procedura:

1. Modificare la configurazione della build sulla barra degli strumenti da **debug** a **versione**.

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra degli strumenti predefinita di Visual Studio con Debug evidenziata":::

1. Premere <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opzione</kbd> + <kbd>comando</kbd> + <kbd>invio</kbd>) per eseguire senza debug.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono stati usati gli strumenti di debug di Visual Studio. Nell'esercitazione successiva si pubblica una versione distribuibile dell'app.

> [!div class="nextstepaction"]
> [Pubblicare un'applicazione console .NET Core con Visual Studio per Mac](publishing-with-visual-studio-mac.md)
