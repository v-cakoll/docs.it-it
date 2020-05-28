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
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="4ef5f-103">Esercitazione: eseguire il debug di un'applicazione console .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4ef5f-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="4ef5f-104">Questa esercitazione presenta gli strumenti di debug disponibili in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ef5f-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4ef5f-105">Prerequisites</span></span>

- <span data-ttu-id="4ef5f-106">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4ef5f-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="4ef5f-107">Debug della configurazione della build</span><span class="sxs-lookup"><span data-stu-id="4ef5f-107">Debug build configuration</span></span>

<span data-ttu-id="4ef5f-108">Le modalità *Debug* e *Rilascio* sono due configurazioni di compilazione predefinite di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="4ef5f-109">La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="4ef5f-110">La seguente immagine della barra degli strumenti Mostra che Visual Studio è configurato per compilare la versione di debug dell'app:</span><span class="sxs-lookup"><span data-stu-id="4ef5f-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![Barra degli strumenti di Visual Studio con debug evidenziato](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="4ef5f-112">Iniziare eseguendo la versione di debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-112">Begin by running the Debug version of the app.</span></span> <span data-ttu-id="4ef5f-113">La configurazione della build di debug Disattiva la maggior parte delle ottimizzazioni del compilatore e offre informazioni più complete durante il processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="4ef5f-114">Imposta punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="4ef5f-114">Set a breakpoint</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="4ef5f-115">Impostare un punto di *interruzione* nella riga in cui vengono visualizzati il nome, la data e l'ora facendo clic sul margine sinistro della finestra del codice nella riga.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-115">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="4ef5f-116">Un altro modo per impostare un punto di interruzione consiste nel posizionare il cursore nella riga di codice e quindi premere **F9** o scegliere **debug**  >  **Imposta/Rimuovi** punto di interruzione dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-116">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="4ef5f-117">Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-117">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="4ef5f-118">Come illustrato nell'immagine seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando il punto e visualizzando un punto rosso nel margine sinistro.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-118">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="4ef5f-120">Eseguire il programma in modalità di debug selezionando il pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-120">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span> <span data-ttu-id="4ef5f-121">Altri modi per avviare il debug sono premendo **F5** o scegliendo **debug**  >  **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-121">Other ways to start debugging are by pressing **F5** or by choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="4ef5f-122">Immettere una stringa nella finestra della console quando il programma richiede un nome e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-122">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="4ef5f-123">L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-123">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="4ef5f-124">Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-124">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Screenshot di un punto di interruzione in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="4ef5f-126">La finestra **controllo immediato** consente di interagire con l'applicazione di cui si sta eseguendo il debug.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-126">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="4ef5f-127">È possibile modificare in modo interattivo il valore delle variabili per vedere come influiscono sul programma.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-127">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="4ef5f-128">Se la finestra di **controllo immediato** non è visibile, visualizzarla scegliendo **debug**  >  **Windows**  >  **immediate**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-128">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="4ef5f-129">Immettere `name = "Gracie"` nella finestra di **controllo immediato** e premere il tasto **invio** .</span><span class="sxs-lookup"><span data-stu-id="4ef5f-129">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="4ef5f-130">Immettere `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` nella finestra di **controllo immediato** e premere il tasto **invio** .</span><span class="sxs-lookup"><span data-stu-id="4ef5f-130">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="4ef5f-131">Nella finestra di **controllo immediato** vengono visualizzati il valore della variabile stringa e le proprietà del <xref:System.DateTime> valore.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-131">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="4ef5f-132">Inoltre, i valori delle variabili vengono aggiornati nella finestra variabili **locali** .</span><span class="sxs-lookup"><span data-stu-id="4ef5f-132">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Variabili locali e finestre immediate in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="4ef5f-134">Continuare l'esecuzione del programma selezionando il pulsante **continua** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-134">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="4ef5f-135">Un altro modo per continuare è scegliere **debug**  >  **continua**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-135">Another way to continue is by choosing **Debug** > **Continue**.</span></span>

   <span data-ttu-id="4ef5f-136">I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella finestra di **controllo immediato** .</span><span class="sxs-lookup"><span data-stu-id="4ef5f-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![Finestra della console che mostra i valori immessi](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="4ef5f-138">Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-138">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="4ef5f-139">Impostare un punto di interruzione condizionale</span><span class="sxs-lookup"><span data-stu-id="4ef5f-139">Set a conditional breakpoint</span></span>

<span data-ttu-id="4ef5f-140">Il programma Visualizza la stringa che l'utente immette.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-140">The program displays the string that the user enters.</span></span> <span data-ttu-id="4ef5f-141">Ma cosa succede se l'utente non immette alcuna stringa?</span><span class="sxs-lookup"><span data-stu-id="4ef5f-141">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="4ef5f-142">È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*, che interrompe l'esecuzione del programma quando vengono soddisfatte una o più condizioni.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-142">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="4ef5f-143">Per impostare un punto di interruzione condizionale e verificare cosa succede quando l'utente non immette una stringa, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="4ef5f-143">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

1. <span data-ttu-id="4ef5f-144">Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-144">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="4ef5f-145">Scegliere **condizioni** dal menu di scelta rapida per aprire la finestra di dialogo impostazioni punto di **interruzione** .</span><span class="sxs-lookup"><span data-stu-id="4ef5f-145">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="4ef5f-146">Selezionare la casella per le **condizioni** , se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-146">Select the box for **Conditions** if it's not already selected.</span></span>

   ![Editor con il pannello Impostazioni punto di interruzione - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="4ef5f-148">Per l' **espressione condizionale**, immettere il codice seguente nel campo che mostra il codice di esempio che verifica se `x` è 5.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-148">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="4ef5f-149">Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-149">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="4ef5f-150">Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="4ef5f-150">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="4ef5f-151">Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*, che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte o una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-151">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="4ef5f-152">Selezionare **Chiudi** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-152">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="4ef5f-153">Avviare il programma con il debug premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-153">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="4ef5f-154">Nella finestra della console premere il tasto **invio** quando viene richiesto di immettere il nome.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-154">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="4ef5f-155">Poiché la condizione specificata ( `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima dell' `Console.WriteLine` esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-155">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="4ef5f-156">Selezionare la finestra variabili **locali** , che mostra i valori delle variabili locali per il metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-156">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="4ef5f-157">In questo caso, `Main` è il metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-157">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="4ef5f-158">Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-158">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="4ef5f-159">Verificare che il valore sia una stringa vuota immettendo l'istruzione seguente nella finestra di **controllo immediato** e premendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-159">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="4ef5f-160">Il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-160">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="4ef5f-161">Il punto interrogativo indirizza la finestra di controllo immediato per la [valutazione di un'espressione](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="4ef5f-161">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="4ef5f-163">Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-163">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="4ef5f-164">Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-164">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="4ef5f-165">Cancellare il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-165">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="4ef5f-166">Un altro modo per cancellare un punto di interruzione è scegliere **Debug > Imposta/Rimuovi** punto di interruzione mentre è selezionata la riga di codice.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-166">Another way to clear a breakpoint is by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="4ef5f-167">Scorrere un programma</span><span class="sxs-lookup"><span data-stu-id="4ef5f-167">Step through a program</span></span>

<span data-ttu-id="4ef5f-168">Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-168">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="4ef5f-169">In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-169">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="4ef5f-170">Poiché il programma è di piccole dimensioni, è possibile eseguire l'intero programma.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-170">Since your program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="4ef5f-171">Scegliere **debug**  >  **Esegui istruzione**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-171">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="4ef5f-172">Un altro modo per eseguire il debug di un'istruzione alla volta è premere **F11**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-172">Another way to debug one statement at a time is by pressing **F11**.</span></span>

   <span data-ttu-id="4ef5f-173">Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-173">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="4ef5f-174">C#</span><span class="sxs-lookup"><span data-stu-id="4ef5f-174">C#</span></span>

   ![Metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="4ef5f-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ef5f-176">Visual Basic</span></span>

   ![Metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="4ef5f-178">A questo punto, nella finestra **variabili locali** viene indicato che la `args` matrice è vuota e che i `name` `date` valori predefiniti sono e.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-178">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="4ef5f-179">Visual Studio, inoltre, ha aperto una finestra della console vuota.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-179">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="4ef5f-180">Premere **F11**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-180">Press **F11**.</span></span> <span data-ttu-id="4ef5f-181">Visual Studio evidenzia ora la riga dell'esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-181">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="4ef5f-182">La finestra **variabili locali** è invariata e la finestra della console rimane vuota.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-182">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="4ef5f-183">C#</span><span class="sxs-lookup"><span data-stu-id="4ef5f-183">C#</span></span>

   ![Origine metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="4ef5f-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ef5f-185">Visual Basic</span></span>

   ![Origine metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="4ef5f-187">Premere **F11**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-187">Press **F11**.</span></span> <span data-ttu-id="4ef5f-188">Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-188">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="4ef5f-189">La finestra **variabili locali** Mostra che `name` è `null` e la finestra della console Visualizza la stringa "Qual è il nome?".</span><span class="sxs-lookup"><span data-stu-id="4ef5f-189">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="4ef5f-190">Per rispondere alla richiesta, immettere una stringa nella finestra della console e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-190">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="4ef5f-191">La console non risponde e la stringa immessa non viene visualizzata nella finestra della console, ma il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> Metodo acquisirà comunque l'input.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-191">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="4ef5f-192">Premere **F11**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-192">Press **F11**.</span></span> <span data-ttu-id="4ef5f-193">Visual Studio evidenzia l'istruzione che include l' `date` assegnazione di variabili ( `currentDate` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4ef5f-193">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="4ef5f-194">Nella finestra **variabili locali** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-194">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4ef5f-195">La finestra della console Visualizza anche la stringa immessa al prompt.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-195">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="4ef5f-196">Premere **F11**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-196">Press **F11**.</span></span> <span data-ttu-id="4ef5f-197">Nella finestra variabili **locali** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-197">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4ef5f-198">La finestra della console rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-198">The console window is unchanged.</span></span>

1. <span data-ttu-id="4ef5f-199">Premere **F11**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-199">Press **F11**.</span></span> <span data-ttu-id="4ef5f-200">Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-200">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4ef5f-201">Nella finestra della console viene visualizzata la stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-201">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="4ef5f-202">Scegliere **debug**Esci  >  **da istruzione/uscita**. Un altro modo per arrestare l'esecuzione dettagliata consiste nel premere **MAIUSC** + **F11**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-202">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing **Shift**+**F11**.</span></span>

   <span data-ttu-id="4ef5f-203">La finestra della console visualizza un messaggio e attende che venga premuto un tasto.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-203">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="4ef5f-204">Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-204">Press any key to close the console window and stop debugging.</span></span>

## <a name="build-a-release-version"></a><span data-ttu-id="4ef5f-205">Compilare una versione di rilascio</span><span class="sxs-lookup"><span data-stu-id="4ef5f-205">Build a Release version</span></span>

<span data-ttu-id="4ef5f-206">Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-206">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="4ef5f-207">La versione di rilascio integra le ottimizzazioni del compilatore che possono talvolta influire negativamente sul comportamento di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-207">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="4ef5f-208">Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-208">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="4ef5f-209">Per compilare e testare la versione di rilascio dell'applicazione console, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-209">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![Barra degli strumenti predefinita di Visual Studio con Debug evidenziata](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="4ef5f-211">Quando si preme **F5** o si sceglie **Compila soluzione** dal menu **Compila** , Visual Studio compila la versione di rilascio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-211">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="4ef5f-212">È possibile eseguirne il test con la versione di debug.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-212">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ef5f-213">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4ef5f-213">Next steps</span></span>

<span data-ttu-id="4ef5f-214">In questa esercitazione sono stati usati gli strumenti di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-214">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="4ef5f-215">Nell'esercitazione successiva si pubblica una versione distribuibile dell'app.</span><span class="sxs-lookup"><span data-stu-id="4ef5f-215">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4ef5f-216">Pubblicare un'applicazione console .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4ef5f-216">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
