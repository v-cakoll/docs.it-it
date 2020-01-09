---
title: Eseguire il debug dell'applicazione Hello World .NET Core con Visual Studio
description: Informazioni su come eseguire il debug di un'app C# Hello World scritta in o Visual Basic con Visual Studio.
ms.date: 12/05/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bc2736165ec827c1f2670605f23f549ceed4e83a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714048"
---
# <a name="debug-your-c-or-visual-basic-net-core-hello-world-application-using-visual-studio"></a>Eseguire il C# debug dell'applicazione .net core Hello World o Visual Basic con Visual Studio

Fino a questo momento, è stata seguita la procedura descritta in [creare la prima applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md) per creare ed eseguire una semplice applicazione console. Dopo aver scritto e compilato l'applicazione, è possibile iniziare a testarla. Visual Studio include un set completo di strumenti di debug che è possibile usare per risolvere i problemi dell'applicazione.

## <a name="debug-build-configuration"></a>Debug della configurazione della build

Le modalità *Debug* e *Rilascio* sono due configurazioni di compilazione predefinite di Visual Studio. La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti. La seguente immagine della barra degli strumenti Mostra che Visual Studio è configurato per compilare la versione di debug dell'app:

![Barra degli strumenti di Visual Studio con debug evidenziato](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

Iniziare eseguendo la versione di debug dell'app. La configurazione della build di debug Disattiva la maggior parte delle ottimizzazioni del compilatore e offre informazioni più complete durante il processo di compilazione.

## <a name="set-a-breakpoint"></a>Imposta punto di interruzione

Eseguire il programma e provare alcune funzionalità di debug:

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Impostare un punto di *interruzione* sulla riga che legge `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` facendo clic sul margine sinistro della finestra del codice nella riga. È anche possibile impostare un punto di interruzione posizionando il cursore nella riga di codice e premendo **F9** o scegliendo **debug** > **Imposta/Rimuovi** punto di interruzione dalla barra dei menu.

   Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.

   Come illustrato nell'immagine seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando e visualizzando un cerchio rosso nel margine sinistro.

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. Eseguire il programma in modalità di debug selezionando il pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti, premendo **F5**o scegliendo **debug** > **avviare il debug**.

1. Immettere una stringa nella finestra della console quando il programma richiede un nome e quindi premere **invio**.

1. L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito. Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.

   ![Screenshot di un punto di interruzione in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. La finestra **controllo immediato** consente di interagire con l'applicazione di cui si sta eseguendo il debug. È possibile modificare in modo interattivo il valore delle variabili per vedere come influiscono sul programma.

   1. Se la finestra di **controllo immediato** non è visibile, visualizzarla scegliendo **Debug** > **Windows** > **immediate**.

   1. Immettere `name = "Gracie"` nella finestra di **controllo immediato** e premere il tasto **invio** .

   1. Immettere `date = DateTime.Parse("11/16/2019 5:25 PM")` nella finestra di **controllo immediato** e premere il tasto **invio** .

   Nella finestra di **controllo immediato** vengono visualizzati il valore della variabile stringa e le proprietà del valore <xref:System.DateTime>. Inoltre, i valori delle variabili vengono aggiornati nella finestra variabili **locali** .

   ![Variabili locali e finestre immediate in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. Continuare l'esecuzione del programma selezionando il pulsante **continua** sulla barra degli strumenti oppure selezionando **debug** > **continua**. I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella finestra di **controllo immediato** .

   ![Finestra della console che mostra i valori immessi](./media/debugging-with-visual-studio/console-window.png)

1. Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Impostare un punto di *interruzione* sulla riga che legge `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")` facendo clic sul margine sinistro della finestra del codice nella riga. È anche possibile impostare un punto di interruzione posizionando il cursore sulla riga desiderata e scegliendo **Debug** > **Imposta/Rimuovi** punto di interruzione dalla barra dei menu.

   Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.
   
   Come mostrato nella figura seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando tale riga e visualizzando un cerchio rosso sul margine sinistro della finestra.

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/vb/set-breakpoint-in-editor.png)

1. Eseguire il programma in modalità di debug selezionando il pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti, premendo **F5**o scegliendo **debug** > **avviare il debug**.

1. Immettere una stringa nella finestra della console quando il programma richiede un nome e premere **invio**.

1. L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito. Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.

1. La finestra **controllo immediato** consente di interagire con l'applicazione di cui si sta eseguendo il debug. È possibile modificare in modo interattivo il valore delle variabili per vedere come influiscono sul programma.

   1. Se la finestra di **controllo immediato** non è visibile, visualizzarla scegliendo **Debug** > **Windows** > **immediate**.

   1. Immettere `name = "Gracie"` nella finestra di **controllo immediato** e premere il tasto **invio** .

   1. Immettere `date = DateTime.Parse("11/16/2019 5:25 PM")` nella finestra di **controllo immediato** e premere il tasto **invio** .

   I valori delle variabili vengono aggiornati nella finestra variabili **locali** .

1. Continuare l'esecuzione del programma scegliendo il pulsante **Continua** sulla barra degli strumenti oppure scegliendo la voce di menu **Debug** > **Continua**. I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella finestra di **controllo immediato** .

   ![Finestra della console che mostra i valori immessi](./media/debugging-with-visual-studio/console-window.png)

1. Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.

---

## <a name="set-a-conditional-breakpoint"></a>Impostare un punto di interruzione condizionale

Il programma visualizza la stringa immessa dall'utente. Ma cosa succede se l'utente non immette alcuna stringa? È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*, che interrompe l'esecuzione del programma quando vengono soddisfatte una o più condizioni.

Per impostare un punto di interruzione condizionale e verificare cosa succede quando l'utente non immette una stringa, seguire questa procedura:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione. Scegliere **Condizioni** dal menu di scelta rapida per aprire la finestra di dialogo **Impostazioni del punto di interruzione**. Selezionare la casella per le **condizioni** se non è già selezionata.

   ![Editor con il pannello Impostazioni punto di interruzione - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. Per l' **espressione condizionale**sostituire "e.g. x = = 5" con quanto segue:

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   Si sta testando una condizione di codice, che la chiamata al metodo `String.IsNullOrEmpty(name)` è `true` perché a `name` non è stato assegnato un valore o perché il relativo valore è una stringa vuota (""). Anziché un'espressione condizionale, è anche possibile specificare un numero di *passaggi*, che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte o una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.

1. Selezionare **Chiudi** per chiudere la finestra di dialogo.

1. Avviare il programma con il debug premendo **F5**.

1. Nella finestra della console premere il tasto **invio** quando viene richiesto di immettere il nome.

1. Poiché la condizione specificata `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType>, è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima dell'esecuzione del metodo `Console.WriteLine`.

1. Selezionare la finestra variabili **locali** , che mostra i valori delle variabili locali per il metodo attualmente in esecuzione. In questo caso, `Main` è il metodo attualmente in esecuzione. Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Verificare che il valore sia una stringa vuota immettendo l'istruzione seguente nella finestra di **controllo immediato** e premendo **invio**. Il risultato è `true`.

   ```csharp
   ? name == String.Empty
   ```

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.

1. Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.

1. Deselezionare il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice oppure scegliendo **Debug > Imposta/Rimuovi** punto di interruzione mentre è selezionata la riga di codice.

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione. Scegliere **Condizioni** dal menu di scelta rapida per aprire la finestra di dialogo **Impostazioni del punto di interruzione**. Selezionare la casella per **Condizioni**.

   ![Editor con il pannello Impostazioni del punto di interruzione - Visual Basic](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. Per l'**Espressione condizionale** sostituire "e.g. x = 5" con quanto segue:

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Si sta testando una condizione di codice, che la chiamata al metodo `String.IsNullOrEmpty(name)` è `true` perché a `name` non è stato assegnato un valore o perché il relativo valore è una stringa vuota (""). Anziché un'espressione condizionale, è anche possibile specificare un numero di *passaggi*, che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte o una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.

1. Selezionare **Chiudi** per chiudere la finestra di dialogo.

1. Avviare il programma con il debug premendo **F5**.

1. Nella finestra della console premere il tasto **invio** quando viene richiesto di immettere il nome.

1. Poiché la condizione specificata `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType>, è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima dell'esecuzione del metodo `Console.WriteLine`.

1. Selezionare la finestra variabili **locali** , che mostra i valori delle variabili locali per il metodo attualmente in esecuzione. In questo caso, `Main` è il metodo attualmente in esecuzione. Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Verificare che il valore sia una stringa vuota immettendo l'istruzione seguente nella finestra di **controllo immediato** e premendo **invio**. Il risultato è `true`.

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione - Visual Basic](./media/debugging-with-visual-studio/vb/immediate-window-output.png)

1. Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.

1. Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.

1. Rimuovere il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice oppure scegliendo la voce di menu **Debug > Imposta/Rimuovi punto di interruzione** per la riga selezionata.

---
## <a name="step-through-a-program"></a>Scorrere un programma

Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione. In genere si imposta un punto di interruzione e si usa questa funzionalità per seguire il flusso del programma attraverso una piccola parte del codice. Poiché il programma è di piccole dimensioni, è possibile eseguire l'intero programma:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Nella barra dei menu scegliere **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   ![Metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-method.png)

   A questo punto, nella finestra **variabili locali** viene indicato che il programma ha definito una sola variabile, `args`. Poiché al programma non è stato passato alcun argomento della riga di comando, il relativo valore è una matrice di stringhe vuota. Visual Studio, inoltre, ha aperto una finestra della console vuota.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia ora la riga dell'esecuzione successiva. Come illustrato nell'immagine, l'esecuzione del codice tra l'ultima istruzione e l'altra è stata eseguita in meno di un millisecondo. `args` rimane l'unica variabile dichiarata e la finestra della console resta vuota.

   ![Origine metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`. La finestra **variabili locali** mostra che `name` è `null`e nella finestra della console viene visualizzata la stringa "Qual è il nome?".

1. Per rispondere alla richiesta, immettere una stringa nella finestra della console e premere **invio**. La console non risponde e la stringa immessa non viene visualizzata nella finestra della console, ma il metodo <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> acquisisce comunque l'input.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `date`. Nella finestra **variabili locali** viene visualizzato il valore restituito dalla chiamata al metodo <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. La finestra della console Visualizza anche la stringa immessa al prompt.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Nella finestra variabili **locali** viene visualizzato il valore della variabile `date` dopo l'assegnazione dalla proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>. La finestra della console rimane invariata.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Nella finestra della console viene visualizzata la stringa formattata.

1. Selezionare **Debug** > **Esci da istruzione/uscita** o premere **MAIUSC**+**F11**. Questa operazione arresta l'esecuzione passo passo. La finestra della console visualizza un messaggio e attende che venga premuto un tasto.

1. Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Nella barra dei menu scegliere **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   ![Metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   A questo punto, nella finestra **variabili locali** viene indicato che il programma ha definito una sola variabile, `args`. Poiché al programma non è stato passato alcun argomento della riga di comando, il relativo valore è una matrice di stringhe vuota. Visual Studio, inoltre, ha aperto una finestra della console vuota.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia ora la riga dell'esecuzione successiva. Come illustrato nella figura, l'esecuzione del codice tra l'ultima istruzione e questa ha richiesto 3 millisecondi. `args` rimane l'unica variabile dichiarata e la finestra della console resta vuota.

   ![Origine metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`. La finestra **variabili locali** mostra che `name` è `Nothing`e nella finestra della console viene visualizzata la stringa "Qual è il nome?".

1. Per rispondere alla richiesta, immettere una stringa nella finestra della console e premere **invio**. La console non risponde e la stringa immessa non viene visualizzata nella finestra della console. Il metodo <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>, tuttavia, acquisirà l'input.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `currentDate`. Nella finestra **variabili locali** viene visualizzato il valore restituito dalla chiamata al metodo <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. Nella finestra della console viene visualizzata anche la stringa immessa quando la console ha richiesto un input.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. La finestra della console rimane invariata.

1. Selezionare **Debug** > **Esegui istruzione** o premere **F11**. Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Nella finestra della console viene visualizzata la stringa formattata.

1. Selezionare **Debug** > **Esci da istruzione/uscita** o premere **MAIUSC**+**F11**. Questa operazione arresta l'esecuzione passo passo. La finestra della console visualizza un messaggio e attende che venga premuto un tasto.

1. Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.

---

## <a name="build-a-release-version"></a>Compilare una versione di rilascio

Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio. La versione di rilascio integra le ottimizzazioni del compilatore che possono talvolta influire negativamente sul comportamento di un'applicazione. Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.

Per compilare e testare la versione di rilascio dell'applicazione console, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

![Barra degli strumenti predefinita di Visual Studio con Debug evidenziata](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

Quando si preme **F5** o si sceglie **Compila soluzione** dal menu **Compila** , Visual Studio compila la versione di rilascio dell'applicazione. È possibile eseguirne il test con la versione di debug.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver eseguito il debug dell'applicazione, il passaggio successivo consiste nel pubblicare una versione distribuibile dell'app. Per informazioni su come eseguire questa operazione, vedere [pubblicare un'applicazione .NET Core Hello World con Visual Studio](publishing-with-visual-studio.md).
