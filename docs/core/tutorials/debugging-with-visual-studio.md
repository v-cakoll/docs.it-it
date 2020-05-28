---
title: Eseguire il debug di un'applicazione console .NET Core con Visual Studio
description: Informazioni su come eseguire il debug di un'app console .NET Core con Visual Studio.
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4bd2a8a0e4b3cea55e209306dd3788552e4b61f3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005414"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a>Esercitazione: eseguire il debug di un'applicazione console .NET Core con Visual Studio

Questa esercitazione presenta gli strumenti di debug disponibili in Visual Studio.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md).

## <a name="debug-build-configuration"></a>Debug della configurazione della build

Le modalità *Debug* e *Rilascio* sono due configurazioni di compilazione predefinite di Visual Studio. La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti. La seguente immagine della barra degli strumenti Mostra che Visual Studio è configurato per compilare la versione di debug dell'app:

![Barra degli strumenti di Visual Studio con debug evidenziato](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

Iniziare eseguendo la versione di debug dell'app. La configurazione della build di debug Disattiva la maggior parte delle ottimizzazioni del compilatore e offre informazioni più complete durante il processo di compilazione.

## <a name="set-a-breakpoint"></a>Imposta punto di interruzione

<!-- markdownlint-disable MD025 -->

1. Impostare un punto di *interruzione* nella riga in cui vengono visualizzati il nome, la data e l'ora facendo clic sul margine sinistro della finestra del codice nella riga. Un altro modo per impostare un punto di interruzione consiste nel posizionare il cursore nella riga di codice e quindi premere **F9** o scegliere **debug**  >  **Imposta/Rimuovi** punto di interruzione dalla barra dei menu.

   Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.

   Come illustrato nell'immagine seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando il punto e visualizzando un punto rosso nel margine sinistro.

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. Eseguire il programma in modalità di debug selezionando il pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti. Altri modi per avviare il debug sono premendo **F5** o scegliendo **debug**  >  **Avvia debug**.

1. Immettere una stringa nella finestra della console quando il programma richiede un nome e quindi premere **invio**.

1. L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito. Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.

   ![Screenshot di un punto di interruzione in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. La finestra **controllo immediato** consente di interagire con l'applicazione di cui si sta eseguendo il debug. È possibile modificare in modo interattivo il valore delle variabili per vedere come influiscono sul programma.

   1. Se la finestra di **controllo immediato** non è visibile, visualizzarla scegliendo **debug**  >  **Windows**  >  **immediate**.

   1. Immettere `name = "Gracie"` nella finestra di **controllo immediato** e premere il tasto **invio** .

   1. Immettere `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` nella finestra di **controllo immediato** e premere il tasto **invio** .

   Nella finestra di **controllo immediato** vengono visualizzati il valore della variabile stringa e le proprietà del <xref:System.DateTime> valore. Inoltre, i valori delle variabili vengono aggiornati nella finestra variabili **locali** .

   ![Variabili locali e finestre immediate in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. Continuare l'esecuzione del programma selezionando il pulsante **continua** sulla barra degli strumenti. Un altro modo per continuare è scegliere **debug**  >  **continua**.

   I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella finestra di **controllo immediato** .

   ![Finestra della console che mostra i valori immessi](./media/debugging-with-visual-studio/console-window.png)

1. Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.

## <a name="set-a-conditional-breakpoint"></a>Impostare un punto di interruzione condizionale

Il programma Visualizza la stringa che l'utente immette. Ma cosa succede se l'utente non immette alcuna stringa? È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*, che interrompe l'esecuzione del programma quando vengono soddisfatte una o più condizioni.

Per impostare un punto di interruzione condizionale e verificare cosa succede quando l'utente non immette una stringa, seguire questa procedura:

1. Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione. Scegliere **condizioni** dal menu di scelta rapida per aprire la finestra di dialogo impostazioni punto di **interruzione** . Selezionare la casella per le **condizioni** , se non è già selezionata.

   ![Editor con il pannello Impostazioni punto di interruzione - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. Per l' **espressione condizionale**, immettere il codice seguente nel campo che mostra il codice di esempio che verifica se `x` è 5. Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .

   Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*, che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte o una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.

1. Selezionare **Chiudi** per chiudere la finestra di dialogo.

1. Avviare il programma con il debug premendo **F5**.

1. Nella finestra della console premere il tasto **invio** quando viene richiesto di immettere il nome.

1. Poiché la condizione specificata ( `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima dell' `Console.WriteLine` esecuzione del metodo.

1. Selezionare la finestra variabili **locali** , che mostra i valori delle variabili locali per il metodo attualmente in esecuzione. In questo caso, `Main` è il metodo attualmente in esecuzione. Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Verificare che il valore sia una stringa vuota immettendo l'istruzione seguente nella finestra di **controllo immediato** e premendo **invio**. Il risultato è `true`.

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   Il punto interrogativo indirizza la finestra di controllo immediato per la [valutazione di un'espressione](/visualstudio/ide/reference/immediate-window#enter-commands).

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.

1. Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.

1. Cancellare il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice. Un altro modo per cancellare un punto di interruzione è scegliere **Debug > Imposta/Rimuovi** punto di interruzione mentre è selezionata la riga di codice.

## <a name="step-through-a-program"></a>Scorrere un programma

Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione. In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma. Poiché il programma è di piccole dimensioni, è possibile eseguire l'intero programma.

1. Scegliere **debug**  >  **Esegui istruzione**. Un altro modo per eseguire il debug di un'istruzione alla volta è premere **F11**.

   Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   C#

   ![Metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-method.png)

   Visual Basic

   ![Metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   A questo punto, nella finestra **variabili locali** viene indicato che la `args` matrice è vuota e che i `name` `date` valori predefiniti sono e. Visual Studio, inoltre, ha aperto una finestra della console vuota.

1. Premere **F11**. Visual Studio evidenzia ora la riga dell'esecuzione successiva. La finestra **variabili locali** è invariata e la finestra della console rimane vuota.

   C#

   ![Origine metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   Visual Basic

   ![Origine metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. Premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`. La finestra **variabili locali** Mostra che `name` è `null` e la finestra della console Visualizza la stringa "Qual è il nome?".

1. Per rispondere alla richiesta, immettere una stringa nella finestra della console e premere **invio**. La console non risponde e la stringa immessa non viene visualizzata nella finestra della console, ma il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> Metodo acquisirà comunque l'input.

1. Premere **F11**. Visual Studio evidenzia l'istruzione che include l' `date` assegnazione di variabili ( `currentDate` in Visual Basic). Nella finestra **variabili locali** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo. La finestra della console Visualizza anche la stringa immessa al prompt.

1. Premere **F11**. Nella finestra variabili **locali** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà. La finestra della console rimane invariata.

1. Premere **F11**. Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Nella finestra della console viene visualizzata la stringa formattata.

1. Scegliere **debug**Esci  >  **da istruzione/uscita**. Un altro modo per arrestare l'esecuzione dettagliata consiste nel premere **MAIUSC** + **F11**.

   La finestra della console visualizza un messaggio e attende che venga premuto un tasto.

1. Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.

## <a name="build-a-release-version"></a>Compilare una versione di rilascio

Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio. La versione di rilascio integra le ottimizzazioni del compilatore che possono talvolta influire negativamente sul comportamento di un'applicazione. Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.

Per compilare e testare la versione di rilascio dell'applicazione console, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

![Barra degli strumenti predefinita di Visual Studio con Debug evidenziata](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

Quando si preme **F5** o si sceglie **Compila soluzione** dal menu **Compila** , Visual Studio compila la versione di rilascio dell'applicazione. È possibile eseguirne il test con la versione di debug.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono stati usati gli strumenti di debug di Visual Studio. Nell'esercitazione successiva si pubblica una versione distribuibile dell'app.

> [!div class="nextstepaction"]
> [Pubblicare un'applicazione console .NET Core con Visual Studio](publishing-with-visual-studio.md)
