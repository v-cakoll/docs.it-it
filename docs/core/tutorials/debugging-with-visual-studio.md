---
title: Eseguire il debug di un'applicazione console .NET Core con Visual Studio
description: Informazioni su come eseguire il debug di un'app console .NET Core usando Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 743603cb037406948190c7090ca3527bfc40db18
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702067"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="d6c99-103">Esercitazione: eseguire il debug di un'applicazione console .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d6c99-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="d6c99-104">Questa esercitazione presenta gli strumenti di debug disponibili in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6c99-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6c99-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d6c99-105">Prerequisites</span></span>

- <span data-ttu-id="d6c99-106">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d6c99-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="d6c99-107">Usa configurazione build di debug</span><span class="sxs-lookup"><span data-stu-id="d6c99-107">Use Debug build configuration</span></span>

<span data-ttu-id="d6c99-108">Il *debug* e la *versione* sono configurazioni di compilazione predefinite di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6c99-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="d6c99-109">Usare la configurazione della build di debug per il debug e la configurazione di rilascio per la distribuzione finale della versione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="d6c99-110">Nella configurazione di debug, un programma viene compilato con informazioni di debug simboliche complete e senza ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="d6c99-111">L'ottimizzazione rende più difficile il debug perché la relazione tra il codice sorgente e le istruzioni generate è più complessa.</span><span class="sxs-lookup"><span data-stu-id="d6c99-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="d6c99-112">La configurazione di rilascio di un programma non dispone di informazioni di debug simboliche ed è completamente ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="d6c99-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="d6c99-113">Per impostazione predefinita, Visual Studio Code Usa la configurazione della build di debug, pertanto non è necessario modificarla prima del debug.</span><span class="sxs-lookup"><span data-stu-id="d6c99-113">By default, Visual Studio Code uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="d6c99-114">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6c99-114">Start Visual Studio.</span></span>

1. <span data-ttu-id="d6c99-115">Aprire il progetto creato in [creare un'applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d6c99-115">Open the project that you created in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

   <span data-ttu-id="d6c99-116">La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="d6c99-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="d6c99-117">La seguente immagine della barra degli strumenti Mostra che Visual Studio è configurato per compilare la versione di debug dell'app:</span><span class="sxs-lookup"><span data-stu-id="d6c99-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   ![Barra degli strumenti di Visual Studio con debug evidenziato](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

## <a name="set-a-breakpoint"></a><span data-ttu-id="d6c99-119">Imposta punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="d6c99-119">Set a breakpoint</span></span>

<span data-ttu-id="d6c99-120">Un punto di *interruzione* interrompe temporaneamente l'esecuzione dell'applicazione prima che venga eseguita la riga con il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="d6c99-121">Impostare un punto di *interruzione* nella riga in cui vengono visualizzati il nome, la data e l'ora facendo clic sul margine sinistro della finestra del codice nella riga.</span><span class="sxs-lookup"><span data-stu-id="d6c99-121">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="d6c99-122">Il margine sinistro è a sinistra dei numeri di riga.</span><span class="sxs-lookup"><span data-stu-id="d6c99-122">The left margin is to the left of the line numbers.</span></span>  <span data-ttu-id="d6c99-123">Un altro modo per impostare un punto di interruzione consiste nel posizionare il cursore nella riga di codice e quindi scegliere **debug**  >  **Imposta/Rimuovi** punto di interruzione dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="d6c99-123">Another way to set a breakpoint is by placing the cursor in the line of code and then choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="d6c99-124">Come illustrato nell'immagine seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando il punto e visualizzando un punto rosso nel margine sinistro.</span><span class="sxs-lookup"><span data-stu-id="d6c99-124">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="d6c99-126">Premere <kbd>F5</kbd> per eseguire il programma in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="d6c99-126">Press <kbd>F5</kbd> to run the program in Debug mode.</span></span> <span data-ttu-id="d6c99-127">Un altro modo per avviare il debug consiste nel scegliere **debug**  >  **Avvia debug** dal menu.</span><span class="sxs-lookup"><span data-stu-id="d6c99-127">Another way to start debugging is by choosing **Debug** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="d6c99-128">Immettere una stringa nella finestra della console quando il programma richiede un nome e quindi premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-128">Enter a string in the console window when the program prompts for a name, and then press <kbd>Enter</kbd>.</span></span>

1. <span data-ttu-id="d6c99-129">L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="d6c99-129">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="d6c99-130">Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-130">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Screenshot di un punto di interruzione in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

## <a name="use-the-immediate-window"></a><span data-ttu-id="d6c99-132">Utilizzare la finestra controllo immediato</span><span class="sxs-lookup"><span data-stu-id="d6c99-132">Use the Immediate window</span></span>

<span data-ttu-id="d6c99-133">La finestra **controllo immediato** consente di interagire con l'applicazione di cui si sta eseguendo il debug.</span><span class="sxs-lookup"><span data-stu-id="d6c99-133">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="d6c99-134">È possibile modificare in modo interattivo il valore delle variabili per vedere come influiscono sul programma.</span><span class="sxs-lookup"><span data-stu-id="d6c99-134">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="d6c99-135">Se la finestra di **controllo immediato** non è visibile, visualizzarla scegliendo **debug**  >  **Windows**  >  **immediate**.</span><span class="sxs-lookup"><span data-stu-id="d6c99-135">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

1. <span data-ttu-id="d6c99-136">Immettere `name = "Gracie"` nella finestra di **controllo immediato** e premere il tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="d6c99-136">Enter `name = "Gracie"` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

1. <span data-ttu-id="d6c99-137">Immettere `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` nella finestra di **controllo immediato** e premere il tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="d6c99-137">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="d6c99-138">Nella finestra di **controllo immediato** vengono visualizzati il valore della variabile stringa e le proprietà del <xref:System.DateTime> valore.</span><span class="sxs-lookup"><span data-stu-id="d6c99-138">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="d6c99-139">Inoltre, i valori delle variabili vengono aggiornati nella finestra variabili **locali** .</span><span class="sxs-lookup"><span data-stu-id="d6c99-139">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Variabili locali e finestre immediate in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="d6c99-141">Premere <kbd>F5</kbd> per continuare l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="d6c99-141">Press <kbd>F5</kbd> to continue program execution.</span></span> <span data-ttu-id="d6c99-142">Un altro modo per continuare è scegliere **debug**  >  **continua** dal menu.</span><span class="sxs-lookup"><span data-stu-id="d6c99-142">Another way to continue is by choosing **Debug** > **Continue** from the menu.</span></span>

   <span data-ttu-id="d6c99-143">I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella finestra di **controllo immediato** .</span><span class="sxs-lookup"><span data-stu-id="d6c99-143">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![Finestra della console che mostra i valori immessi](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="d6c99-145">Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="d6c99-145">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="d6c99-146">Impostare un punto di interruzione condizionale</span><span class="sxs-lookup"><span data-stu-id="d6c99-146">Set a conditional breakpoint</span></span>

<span data-ttu-id="d6c99-147">Il programma Visualizza la stringa che l'utente immette.</span><span class="sxs-lookup"><span data-stu-id="d6c99-147">The program displays the string that the user enters.</span></span> <span data-ttu-id="d6c99-148">Ma cosa succede se l'utente non immette alcuna stringa?</span><span class="sxs-lookup"><span data-stu-id="d6c99-148">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="d6c99-149">È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*.</span><span class="sxs-lookup"><span data-stu-id="d6c99-149">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="d6c99-150">Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-150">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="d6c99-151">Scegliere **condizioni** dal menu di scelta rapida per aprire la finestra di dialogo impostazioni punto di **interruzione** .</span><span class="sxs-lookup"><span data-stu-id="d6c99-151">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="d6c99-152">Selezionare la casella per le **condizioni** , se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="d6c99-152">Select the box for **Conditions** if it's not already selected.</span></span>

   ![Editor con il pannello Impostazioni punto di interruzione - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="d6c99-154">Per l' **espressione condizionale**, immettere il codice seguente nel campo che mostra il codice di esempio che verifica se `x` è 5.</span><span class="sxs-lookup"><span data-stu-id="d6c99-154">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="d6c99-155">Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="d6c99-155">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="d6c99-156">Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="d6c99-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="d6c99-157">Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte.</span><span class="sxs-lookup"><span data-stu-id="d6c99-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="d6c99-158">Un'altra opzione consiste nello specificare una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.</span><span class="sxs-lookup"><span data-stu-id="d6c99-158">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="d6c99-159">Selezionare **Chiudi** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d6c99-159">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="d6c99-160">Avviare il programma con il debug premendo <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-160">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="d6c99-161">Nella finestra della console premere il tasto <kbd>invio</kbd> quando viene richiesto di immettere il nome.</span><span class="sxs-lookup"><span data-stu-id="d6c99-161">In the console window, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

1. <span data-ttu-id="d6c99-162">Poiché la condizione specificata ( `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima dell' `Console.WriteLine` esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="d6c99-162">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="d6c99-163">Selezionare la finestra variabili **locali** , che mostra i valori delle variabili locali per il metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-163">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="d6c99-164">In questo caso, `Main` è il metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-164">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="d6c99-165">Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-165">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="d6c99-166">Verificare che il valore sia una stringa vuota immettendo l'istruzione seguente nella finestra di **controllo immediato** e premendo <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-166">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="d6c99-167">Il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="d6c99-167">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="d6c99-168">Il punto interrogativo indirizza la finestra di controllo immediato per la [valutazione di un'espressione](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="d6c99-168">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="d6c99-170">Premere <kbd>F5</kbd> per continuare l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="d6c99-170">Press <kbd>F5</kbd> to continue program execution.</span></span>

1. <span data-ttu-id="d6c99-171">Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="d6c99-171">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="d6c99-172">Cancellare il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="d6c99-172">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="d6c99-173">Un altro modo per cancellare un punto di interruzione è scegliere **Debug > Imposta/Rimuovi** punto di interruzione mentre è selezionata la riga di codice.</span><span class="sxs-lookup"><span data-stu-id="d6c99-173">Another way to clear a breakpoint is by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="d6c99-174">Scorrere un programma</span><span class="sxs-lookup"><span data-stu-id="d6c99-174">Step through a program</span></span>

<span data-ttu-id="d6c99-175">Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-175">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="d6c99-176">In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma.</span><span class="sxs-lookup"><span data-stu-id="d6c99-176">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="d6c99-177">Poiché questo programma è di piccole dimensioni, è possibile eseguire l'intero programma.</span><span class="sxs-lookup"><span data-stu-id="d6c99-177">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="d6c99-178">Scegliere **debug**  >  **Esegui istruzione**.</span><span class="sxs-lookup"><span data-stu-id="d6c99-178">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="d6c99-179">Un altro modo per eseguire il debug di un'istruzione alla volta è premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-179">Another way to debug one statement at a time is by pressing <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="d6c99-180">Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="d6c99-180">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="d6c99-181">C#</span><span class="sxs-lookup"><span data-stu-id="d6c99-181">C#</span></span>

   ![Metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="d6c99-183">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6c99-183">Visual Basic</span></span>

   ![Metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="d6c99-185">A questo punto, nella finestra **variabili locali** viene indicato che la `args` matrice è vuota e che i `name` `date` valori predefiniti sono e.</span><span class="sxs-lookup"><span data-stu-id="d6c99-185">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="d6c99-186">Visual Studio, inoltre, ha aperto una finestra della console vuota.</span><span class="sxs-lookup"><span data-stu-id="d6c99-186">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="d6c99-187">Premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-187">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6c99-188">Visual Studio evidenzia ora la riga dell'esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="d6c99-188">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="d6c99-189">La finestra **variabili locali** è invariata e la finestra della console rimane vuota.</span><span class="sxs-lookup"><span data-stu-id="d6c99-189">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="d6c99-190">C#</span><span class="sxs-lookup"><span data-stu-id="d6c99-190">C#</span></span>

   ![Origine metodo Esegui istruzione di Visual Studio - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="d6c99-192">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6c99-192">Visual Basic</span></span>

   ![Origine metodo Esegui istruzione di Visual Studio - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="d6c99-194">Premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-194">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6c99-195">Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`.</span><span class="sxs-lookup"><span data-stu-id="d6c99-195">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="d6c99-196">La finestra **variabili locali** Mostra che `name` è `null` e la finestra della console Visualizza la stringa "Qual è il nome?".</span><span class="sxs-lookup"><span data-stu-id="d6c99-196">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="d6c99-197">Per rispondere alla richiesta, immettere una stringa nella finestra della console e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-197">Respond to the prompt by entering a string in the console window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="d6c99-198">La console non risponde e la stringa immessa non viene visualizzata nella finestra della console, ma il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> Metodo acquisirà comunque l'input.</span><span class="sxs-lookup"><span data-stu-id="d6c99-198">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="d6c99-199">Premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-199">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6c99-200">Visual Studio evidenzia l'istruzione che include l' `date` assegnazione di variabili ( `currentDate` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d6c99-200">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="d6c99-201">Nella finestra **variabili locali** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="d6c99-201">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d6c99-202">La finestra della console Visualizza anche la stringa immessa al prompt.</span><span class="sxs-lookup"><span data-stu-id="d6c99-202">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="d6c99-203">Premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-203">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6c99-204">Nella finestra variabili **locali** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="d6c99-204">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d6c99-205">La finestra della console rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="d6c99-205">The console window is unchanged.</span></span>

1. <span data-ttu-id="d6c99-206">Premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-206">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6c99-207">Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-207">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d6c99-208">Nella finestra della console viene visualizzata la stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="d6c99-208">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="d6c99-209">Scegliere **debug**Esci  >  **da istruzione/uscita**. Un altro modo per arrestare l'esecuzione dettagliata consiste nel premere <kbd>MAIUSC</kbd> + <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6c99-209">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   <span data-ttu-id="d6c99-210">La finestra della console visualizza un messaggio e attende che venga premuto un tasto.</span><span class="sxs-lookup"><span data-stu-id="d6c99-210">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="d6c99-211">Premere un tasto qualsiasi per chiudere la finestra della console e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="d6c99-211">Press any key to close the console window and stop debugging.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="d6c99-212">Usa configurazione build di rilascio</span><span class="sxs-lookup"><span data-stu-id="d6c99-212">Use Release build configuration</span></span>

<span data-ttu-id="d6c99-213">Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="d6c99-213">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="d6c99-214">La versione di rilascio integra le ottimizzazioni del compilatore che possono talvolta influire negativamente sul comportamento di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-214">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="d6c99-215">Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.</span><span class="sxs-lookup"><span data-stu-id="d6c99-215">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="d6c99-216">Per compilare e testare la versione di rilascio dell'applicazione console, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="d6c99-216">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![Barra degli strumenti predefinita di Visual Studio con Debug evidenziata](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="d6c99-218">Quando si preme <kbd>F5</kbd> o si sceglie **Compila soluzione** dal menu **Compila** , Visual Studio compila la versione di rilascio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6c99-218">When you press <kbd>F5</kbd> or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="d6c99-219">È possibile eseguirne il test con la versione di debug.</span><span class="sxs-lookup"><span data-stu-id="d6c99-219">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6c99-220">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d6c99-220">Next steps</span></span>

<span data-ttu-id="d6c99-221">In questa esercitazione sono stati usati gli strumenti di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6c99-221">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="d6c99-222">Nell'esercitazione successiva si pubblica una versione distribuibile dell'app.</span><span class="sxs-lookup"><span data-stu-id="d6c99-222">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d6c99-223">Pubblicare un'applicazione console .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d6c99-223">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
