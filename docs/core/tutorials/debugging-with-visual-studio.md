---
title: Eseguire il debug dell'applicazione Hello World .NET Core con Visual Studio
description: Informazioni su come eseguire il debug di un'app Hello World scritta in Visual Basic o in Visual Basic.
ms.date: 12/05/2019
ms.custom: vs-dotnet
ms.openlocfilehash: b2ee1401fc89f990c5f930d80d1a510a117e63a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156673"
---
# <a name="debug-your-c-or-visual-basic-net-core-hello-world-application-using-visual-studio"></a>Eseguire il debug dell'applicazione Hello World di Visual Basic .NET Core o Visual Basic .NET utilizzando Visual Studio

Finora, sono stati eseguiti i passaggi descritti in [Creare la prima applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md) per creare ed eseguire una semplice applicazione console. Dopo aver scritto e compilato l'applicazione, è possibile iniziare a testarla. Visual Studio include un set completo di strumenti di debug che è possibile usare per risolvere i problemi dell'applicazione.

## <a name="debug-build-configuration"></a>Configurazione della build di debugDebug build configuration

Le modalità *Debug* e *Rilascio* sono due configurazioni di compilazione predefinite di Visual Studio. La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti. L'immagine della barra degli strumenti seguente mostra che Visual Studio è configurato per compilare la versione di debug dell'app:

![Barra degli strumenti di Visual Studio con il debug evidenziato](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

Inizia eseguendo la versione di debug dell'app. La configurazione di debug della build disattiva la maggior parte delle ottimizzazioni del compilatore e fornisce informazioni più dettagliate durante il processo di compilazione.

## <a name="set-a-breakpoint"></a>Imposta punto di interruzione

Eseguire il programma e provare alcune funzionalità di debug:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C #](#tab/csharp)

1. Impostare un *punto di* `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` interruzione sulla riga che legge facendo clic sul margine sinistro della finestra del codice su tale riga. È inoltre possibile impostare un punto di interruzione posizionando il punto di inserimento nella riga di codice e quindi premendo **F9** o scegliendo **Debug** > **Toggle Breakpoint** dalla barra dei menu.

   Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.

   Come illustrato nell'immagine seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziandolo e visualizzando un cerchio rosso nel margine sinistro.

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. Eseguire il programma in modalità Debug selezionando il pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti, premendo **F5**o scegliendo **Debug** > **Start Debugging**.

1. Immettere una stringa nella finestra della console quando il programma richiede un nome e quindi premere **INVIO.**

1. L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito. Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.

   ![Screenshot di un punto di interruzione in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. La finestra **Immediata** consente di interagire con l'applicazione di cui si sta eseguendo il debug. È possibile modificare in modo interattivo il valore delle variabili per vedere come influisce sul programma.

   1. Se la finestra **di controllo immediato** non è visibile, visualizzarla scegliendo **Debug** > di**Windows** > **Immediata**.

   1. Invio `name = "Gracie"` nella finestra **Immediata** e premere il tasto **Invio.**

   1. Invio `date = DateTime.Parse("11/16/2019 5:25 PM")` nella finestra **Immediata** e premere il tasto **Invio.**

   Nella finestra **Immediata** vengono visualizzati il valore <xref:System.DateTime> della variabile stringa e le proprietà del valore. Inoltre, i valori delle variabili vengono aggiornati nella finestra **Variabili locali.**

   ![Locali e Windows immediati in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. Continuare l'esecuzione del programma selezionando il pulsante **Continua** nella barra degli strumenti o selezionando**Continuazione** **debug** > . I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella finestra **Immediata.**

   ![Finestra della console che mostra i valori immessi](./media/debugging-with-visual-studio/console-window.png)

1. Premere un tasto qualsiasi per uscire dall'applicazione e interrompere il debug.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Impostare un *punto di* `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")` interruzione sulla riga che legge facendo clic sul margine sinistro della finestra del codice su tale riga. È inoltre possibile impostare un punto di interruzione posizionando il punto di inserimento nella riga desiderata e quindi scegliendo **Debug** > **Toggle Breakpoint** dalla barra dei menu.

   Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.

   Come mostrato nella figura seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando tale riga e visualizzando un cerchio rosso sul margine sinistro della finestra.

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/vb/set-breakpoint-in-editor.png)

1. Eseguire il programma in modalità Debug selezionando il pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti, premendo **F5**o scegliendo **Debug** > **Start Debugging**.

1. Immettere una stringa nella finestra della console quando il programma richiede un nome e premere **INVIO**.

1. L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito. Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.

1. La finestra **Immediata** consente di interagire con l'applicazione di cui si sta eseguendo il debug. È possibile modificare in modo interattivo il valore delle variabili per vedere come influisce sul programma.

   1. Se la finestra **di controllo immediato** non è visibile, visualizzarla scegliendo **Debug** > di**Windows** > **Immediata**.

   1. Invio `name = "Gracie"` nella finestra **Immediata** e premere il tasto **Invio.**

   1. Invio `date = DateTime.Parse("11/16/2019 5:25 PM")` nella finestra **Immediata** e premere il tasto **Invio.**

   I valori delle variabili vengono aggiornati nella finestra **Variabili locali.**

1. Continuare l'esecuzione del programma scegliendo il pulsante **Continua** sulla barra degli strumenti oppure scegliendo la voce di menu **Debug** > **Continua**. I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella finestra **Immediata.**

   ![Finestra della console che mostra i valori immessi](./media/debugging-with-visual-studio/console-window.png)

1. Premere un tasto qualsiasi per uscire dall'applicazione e interrompere il debug.

---

## <a name="set-a-conditional-breakpoint"></a>Impostare un punto di interruzione condizionaleSet a conditional breakpoint

Il programma visualizza la stringa immessa dall'utente. Ma cosa succede se l'utente non immette alcuna stringa? È possibile verificarlo con un'utile funzionalità di debug denominata *punto di interruzione condizionale*, che interrompe l'esecuzione del programma quando vengono soddisfatte una o più condizioni.

Per impostare un punto di interruzione condizionale e verificare cosa succede quando l'utente non immette una stringa, seguire questa procedura:

# <a name="c"></a>[C #](#tab/csharp)

1. Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione. Scegliere **Condizioni** dal menu di scelta rapida per aprire la finestra di dialogo **Impostazioni del punto di interruzione**. Seleziona la casella **Condizioni** se non è già selezionata.

   ![Editor con il pannello Impostazioni punto di interruzione - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. Per **l'espressione condizionale**, sostituire "es. x " 5" con quanto segue:

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   Si sta verificando una condizione `String.IsNullOrEmpty(name)` del codice, che la chiamata al metodo è `true` perché `name` non è stato assegnato un valore o perché il relativo valore è una stringa vuota (""). Invece di un'espressione condizionale, è anche possibile specificare un numero di *passaggi,* che interrompe l'esecuzione del programma prima dell'esecuzione di un'istruzione un numero specificato di volte, o una condizione di *filtro*, che interrompe l'esecuzione del programma in base ad attributi quali un identificatore di thread, un nome di processo o un nome di thread.

1. Selezionare **Chiudi** per chiudere la finestra di dialogo.

1. Avviare il programma con il debug premendo **F5**.

1. Nella finestra della console, premere **INVIO** quando viene richiesto di immettere il proprio nome.

1. Poiché la condizione `name` specificata `null` <xref:System.String.Empty?displayProperty=nameWithType>è o , è stata soddisfatta, l'esecuzione `Console.WriteLine` del programma si interrompe quando raggiunge il punto di interruzione e prima dell'esecuzione del metodo.

1. Selezionare la finestra **Variabili locali,** che mostra i valori delle variabili locali al metodo attualmente in esecuzione. In questo `Main` caso, è il metodo attualmente in esecuzione. Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Verificare che il valore sia una stringa vuota immettendo l'istruzione seguente nella finestra **Immediata** e premendo **INVIO**. Il risultato è `true`.

   ```csharp
   ? name == String.Empty
   ```

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.

1. Premere un tasto qualsiasi per chiudere la finestra della console e interrompere il debug.

1. Cancellare il punto di interruzione facendo clic sul punto nel margine sinistro della finestra del codice o scegliendo **Debug > Attiva/disattiva punto di interruzione** mentre la riga di codice è selezionata.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione. Scegliere **Condizioni** dal menu di scelta rapida per aprire la finestra di dialogo **Impostazioni del punto di interruzione**. Selezionare la casella per **Condizioni**.

   ![Editor con il pannello Impostazioni del punto di interruzione - Visual Basic](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. Per **l'espressione condizionale** sostituire "ad es. x x 5" con quanto segue:

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Si sta verificando una condizione `String.IsNullOrEmpty(name)` del codice, che la chiamata al metodo è `true` perché `name` non è stato assegnato un valore o perché il relativo valore è una stringa vuota (""). Invece di un'espressione condizionale, è anche possibile specificare un numero di *passaggi,* che interrompe l'esecuzione del programma prima dell'esecuzione di un'istruzione un numero specificato di volte, o una condizione di *filtro*, che interrompe l'esecuzione del programma in base ad attributi quali un identificatore di thread, un nome di processo o un nome di thread.

1. Selezionare **Chiudi** per chiudere la finestra di dialogo.

1. Avviare il programma con il debug premendo **F5**.

1. Nella finestra della console, premere **INVIO** quando viene richiesto di immettere il proprio nome.

1. Poiché la condizione `name` specificata `null` <xref:System.String.Empty?displayProperty=nameWithType>è o , è stata soddisfatta, l'esecuzione `Console.WriteLine` del programma si interrompe quando raggiunge il punto di interruzione e prima dell'esecuzione del metodo.

1. Selezionare la finestra **Variabili locali,** che mostra i valori delle variabili locali al metodo attualmente in esecuzione. In questo `Main` caso, è il metodo attualmente in esecuzione. Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Verificare che il valore sia una stringa vuota immettendo l'istruzione seguente nella finestra **Immediata** e premendo **INVIO**. Il risultato è `true`.

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione - Visual Basic](./media/debugging-with-visual-studio/vb/immediate-window-output.png)

1. Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.

1. Premere un tasto qualsiasi per chiudere la finestra della console e interrompere il debug.

1. Rimuovere il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice oppure scegliendo la voce di menu **Debug > Imposta/Rimuovi punto di interruzione** per la riga selezionata.

---
## <a name="step-through-a-program"></a>Eseguire un programma

Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione. In genere si imposta un punto di interruzione e si usa questa funzionalità per seguire il flusso del programma attraverso una piccola parte del codice. Poiché il programma è piccolo, è possibile scorrere l'intero programma:

# <a name="c"></a>[C #](#tab/csharp)

1. Nella barra dei menu scegliere **Esegui debug** > **istruzione** istruzione oppure premere **F11.** Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   ![Metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-method.png)

   A questo punto, la finestra **Variabili locali** mostra che `args`il programma ha definito una sola variabile, . Poiché al programma non è stato passato alcun argomento della riga di comando, il relativo valore è una matrice di stringhe vuota. Visual Studio, inoltre, ha aperto una finestra della console vuota.

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio evidenzia ora la riga dell'esecuzione successiva. Come illustrato nell'immagine, è stato impiegato meno di un millisecondo per eseguire il codice tra l'ultima istruzione e questa. `args` rimane l'unica variabile dichiarata e la finestra della console resta vuota.

   ![Origine metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`. Nella finestra **Variabili** `name` locali `null`viene illustrato che è e nella finestra della console viene visualizzata la stringa "Qual è il proprio nome?".

1. Rispondere al prompt immettendo una stringa nella finestra della console e premendo **INVIO**. La console non risponde e la stringa immessa non viene visualizzata <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> nella finestra della console, ma il metodo acquisirà comunque l'input.

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `date`. Nella finestra **Variabili locali** viene visualizzato il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> valore restituito dalla chiamata al metodo. Nella finestra della console viene inoltre visualizzata la stringa immessa al prompt.

1. Selezionare **Esegui debug** > **in** o premere **F11**. Nella finestra **Variabili locali** viene `date` visualizzato il valore <xref:System.DateTime.Now?displayProperty=nameWithType> della variabile dopo l'assegnazione dalla proprietà. La finestra della console rimane invariata.

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Nella finestra della console viene visualizzata la stringa formattata.

1. Selezionare **Estratto** > **di** debug o premere **Maiusc**+**F11**. Questa operazione arresta l'esecuzione passo passo. La finestra della console visualizza un messaggio e attende che venga premuto un tasto.

1. Premere un tasto qualsiasi per chiudere la finestra della console e interrompere il debug.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Nella barra dei menu scegliere **Esegui debug** > **istruzione** istruzione oppure premere **F11.** Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   ![Metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   A questo punto, la finestra **Variabili locali** mostra che `args`il programma ha definito una sola variabile, . Poiché al programma non è stato passato alcun argomento della riga di comando, il relativo valore è una matrice di stringhe vuota. Visual Studio, inoltre, ha aperto una finestra della console vuota.

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio evidenzia ora la riga dell'esecuzione successiva. Come illustrato nella figura, l'esecuzione del codice tra l'ultima istruzione e questa ha richiesto 3 millisecondi. `args` rimane l'unica variabile dichiarata e la finestra della console resta vuota.

   ![Origine metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`. Nella finestra **Variabili** `name` locali `Nothing`viene illustrato che è e nella finestra della console viene visualizzata la stringa "Qual è il proprio nome?".

1. Rispondere al prompt immettendo una stringa nella finestra della console e premendo **INVIO**. La console non risponde e la stringa immessa non viene visualizzata nella finestra della console. Il metodo <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>, tuttavia, acquisirà l'input.

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `currentDate`. Nella finestra **Variabili locali** viene visualizzato il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> valore restituito dalla chiamata al metodo. Nella finestra della console viene visualizzata anche la stringa immessa quando la console ha richiesto un input.

1. Selezionare **Esegui debug** > **in** o premere **F11**. La finestra della console rimane invariata.

1. Selezionare **Esegui debug** > **in** o premere **F11**. Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Nella finestra della console viene visualizzata la stringa formattata.

1. Selezionare **Estratto** > **di** debug o premere **Maiusc**+**F11**. Questa operazione arresta l'esecuzione passo passo. La finestra della console visualizza un messaggio e attende che venga premuto un tasto.

1. Premere un tasto qualsiasi per chiudere la finestra della console e interrompere il debug.

---

## <a name="build-a-release-version"></a>Compilare una versione di rilascioBuild a Release version

Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare la versione di rilascio. La versione di rilascio integra le ottimizzazioni del compilatore che possono talvolta influire negativamente sul comportamento di un'applicazione. Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithreading.

Per compilare e testare la versione di rilascio dell'applicazione console, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

![Barra degli strumenti predefinita di Visual Studio con Debug evidenziata](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

Quando si preme **F5** o si sceglie **Compila soluzione** dal menu **Compila** , Visual Studio compila la versione di rilascio dell'applicazione. È possibile testarlo come è stata emessa la versione di debug.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver eseguito il debug dell'applicazione, il passaggio successivo consiste nel pubblicare una versione distribuibile dell'app. Per informazioni su come eseguire questa operazione, vedere [Pubblicare l'applicazione Hello World di .NET Core con Visual Studio](publishing-with-visual-studio.md).
