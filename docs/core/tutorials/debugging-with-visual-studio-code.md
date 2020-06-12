---
title: Eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code
description: Informazioni su come eseguire il debug di un'app console .NET Core usando Visual Studio Code.
ms.date: 05/26/2020
ms.openlocfilehash: 40e9b114df1bd12fb05bfb773781d6009d087a06
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702127"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="a0070-103">Esercitazione: eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a0070-103">Tutorial: Debug a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="a0070-104">Questa esercitazione introduce gli strumenti di debug disponibili in Visual Studio Code per l'uso con le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a0070-104">This tutorial introduces the debugging tools available in Visual Studio Code for working with .NET Core apps.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0070-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a0070-105">Prerequisites</span></span>

- <span data-ttu-id="a0070-106">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="a0070-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="a0070-107">Usa configurazione build di debug</span><span class="sxs-lookup"><span data-stu-id="a0070-107">Use Debug build configuration</span></span>

<span data-ttu-id="a0070-108">Il *debug* e la *versione* sono configurazioni di compilazione predefinite di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a0070-108">*Debug* and *Release* are .NET Core's built-in build configurations.</span></span> <span data-ttu-id="a0070-109">Usare la configurazione della build di debug per il debug e la configurazione di rilascio per la distribuzione finale della versione.</span><span class="sxs-lookup"><span data-stu-id="a0070-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="a0070-110">Nella configurazione di debug, un programma viene compilato con informazioni di debug simboliche complete e senza ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0070-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="a0070-111">L'ottimizzazione rende più difficile il debug perché la relazione tra il codice sorgente e le istruzioni generate è più complessa.</span><span class="sxs-lookup"><span data-stu-id="a0070-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="a0070-112">La configurazione di rilascio di un programma non dispone di informazioni di debug simboliche ed è completamente ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="a0070-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="a0070-113">Per impostazione predefinita, Visual Studio Code impostazioni di avvio usano la configurazione della build di debug, pertanto non è necessario modificarla prima del debug.</span><span class="sxs-lookup"><span data-stu-id="a0070-113">By default, Visual Studio Code launch settings use the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="a0070-114">Avviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a0070-114">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="a0070-115">Aprire la cartella del progetto creato in [creare un'applicazione console .NET Core in Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="a0070-115">Open the folder of the project that you created in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="a0070-116">Imposta punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="a0070-116">Set a breakpoint</span></span>

<span data-ttu-id="a0070-117">Un punto di *interruzione* interrompe temporaneamente l'esecuzione dell'applicazione prima che venga eseguita la riga con il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="a0070-117">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="a0070-118">Aprire il file *Program.cs* .</span><span class="sxs-lookup"><span data-stu-id="a0070-118">Open the *Program.cs* file.</span></span>

1. <span data-ttu-id="a0070-119">Impostare un punto di *interruzione* nella riga in cui vengono visualizzati il nome, la data e l'ora facendo clic sul margine sinistro della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="a0070-119">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window.</span></span> <span data-ttu-id="a0070-120">Il margine sinistro è a sinistra dei numeri di riga.</span><span class="sxs-lookup"><span data-stu-id="a0070-120">The left margin is to the left of the line numbers.</span></span> <span data-ttu-id="a0070-121">Altri modi per impostare un punto di interruzione sono premendo <kbd>F9</kbd> o selezionando **Esegui**  >  **Imposta/Rimuovi** punto di interruzione dal menu mentre è selezionata la riga di codice.</span><span class="sxs-lookup"><span data-stu-id="a0070-121">Other ways to set a breakpoint are by pressing <kbd>F9</kbd> or selecting **Run** > **Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

   <span data-ttu-id="a0070-122">Visual Studio Code indica la riga in cui è impostato il punto di interruzione visualizzando un punto rosso nel margine sinistro.</span><span class="sxs-lookup"><span data-stu-id="a0070-122">Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="Set di punti di interruzione":::

## <a name="set-up-for-terminal-input"></a><span data-ttu-id="a0070-124">Configurare per l'input del terminale</span><span class="sxs-lookup"><span data-stu-id="a0070-124">Set up for terminal input</span></span>

<span data-ttu-id="a0070-125">Il punto di interruzione si trova dopo una `Console.ReadLine` chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="a0070-125">The breakpoint is located after a `Console.ReadLine` method call.</span></span> <span data-ttu-id="a0070-126">Il **console di debug** non accetta l'input del terminale per un programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0070-126">The **Debug Console** doesn't accept terminal input for a running program.</span></span> <span data-ttu-id="a0070-127">Per gestire l'input del terminale durante il debug, è possibile usare il terminale integrato (uno dei Visual Studio Code Windows) o un terminale esterno.</span><span class="sxs-lookup"><span data-stu-id="a0070-127">To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal.</span></span> <span data-ttu-id="a0070-128">Per questa esercitazione si userà il terminale integrato.</span><span class="sxs-lookup"><span data-stu-id="a0070-128">For this tutorial, you use the integrated terminal.</span></span>

1. <span data-ttu-id="a0070-129">Aprire *. VSCODE/launch.js*.</span><span class="sxs-lookup"><span data-stu-id="a0070-129">Open *.vscode/launch.json*.</span></span>

1. <span data-ttu-id="a0070-130">Modificare l' `console` impostazione in `integratedTerminal` .</span><span class="sxs-lookup"><span data-stu-id="a0070-130">Change the `console` setting to `integratedTerminal`.</span></span>

   <span data-ttu-id="a0070-131">Da:</span><span class="sxs-lookup"><span data-stu-id="a0070-131">From:</span></span>

   ```
   "console": "internalConsole",
   ```

   <span data-ttu-id="a0070-132">Con:</span><span class="sxs-lookup"><span data-stu-id="a0070-132">To:</span></span>

   ```
   "console": "integratedTerminal",
   ```

1. <span data-ttu-id="a0070-133">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a0070-133">Save your changes.</span></span>

## <a name="start-debugging"></a><span data-ttu-id="a0070-134">Consente di iniziare il debug</span><span class="sxs-lookup"><span data-stu-id="a0070-134">Start debugging</span></span>

1. <span data-ttu-id="a0070-135">Aprire la visualizzazione debug selezionando l'icona debug nel menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="a0070-135">Open the Debug view by selecting the Debugging icon on the left side menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Aprire la scheda Debug in Visual Studio Code":::

1. <span data-ttu-id="a0070-137">Selezionare la freccia verde nella parte superiore del riquadro accanto a **.NET Core Launch (console)**.</span><span class="sxs-lookup"><span data-stu-id="a0070-137">Select the green arrow at the top of the pane, next to **.NET Core Launch (console)**.</span></span> <span data-ttu-id="a0070-138">Un altro modo per avviare il programma in modalità di debug è scegliere **Esegui**  >  **Avvia debug** dal menu.</span><span class="sxs-lookup"><span data-stu-id="a0070-138">Another way to start the program in debugging mode is by choosing **Run** > **Start Debugging** from the menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="Consente di iniziare il debug":::

1. <span data-ttu-id="a0070-140">Selezionare la scheda **terminale** per visualizzare il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0070-140">Select the **Terminal** tab to see the "What is your name?"</span></span> <span data-ttu-id="a0070-141">richiede che il programma venga visualizzato prima dell'attesa di una risposta.</span><span class="sxs-lookup"><span data-stu-id="a0070-141">prompt that the program displays before waiting for a response.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="Selezionare la scheda terminale":::

1. <span data-ttu-id="a0070-143">Immettere una stringa nella finestra del **terminale** in risposta alla richiesta di un nome, quindi premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-143">Enter a string in the **Terminal** window in response to the prompt for a name, and then press <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="a0070-144">L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="a0070-144">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="a0070-145">Nella sezione variabili **locali** della finestra **variabili** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0070-145">The **Locals** section of the **Variables** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="Raggiunto punto di interruzione, che Mostra variabili locali":::

## <a name="use-the-debug-console"></a><span data-ttu-id="a0070-147">Usare il Console di debug</span><span class="sxs-lookup"><span data-stu-id="a0070-147">Use the Debug Console</span></span>

<span data-ttu-id="a0070-148">La finestra di **console di debug** consente di interagire con l'applicazione di cui si sta eseguendo il debug.</span><span class="sxs-lookup"><span data-stu-id="a0070-148">The **Debug Console** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="a0070-149">È possibile modificare il valore delle variabili per vedere come influiscono sul programma.</span><span class="sxs-lookup"><span data-stu-id="a0070-149">You can change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="a0070-150">Selezionare la scheda **console di debug** .</span><span class="sxs-lookup"><span data-stu-id="a0070-150">Select the **Debug Console** tab.</span></span>

1. <span data-ttu-id="a0070-151">Immettere `name = "Gracie"` al prompt nella parte inferiore della finestra **console di debug** e premere il tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="a0070-151">Enter `name = "Gracie"` at the prompt at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="Modificare i valori delle variabili":::

1. <span data-ttu-id="a0070-153">Immettere `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` nella parte inferiore della finestra di **console di debug** e premere il tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="a0070-153">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="a0070-154">Nella finestra **variabili** vengono visualizzati i nuovi valori delle `name` `date` variabili e.</span><span class="sxs-lookup"><span data-stu-id="a0070-154">The **Variables** window displays the new values of the `name` and `date` variables.</span></span>

1. <span data-ttu-id="a0070-155">Continuare l'esecuzione del programma selezionando il pulsante **continua** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="a0070-155">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="a0070-156">Un altro modo per continuare è premere <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-156">Another way to continue is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="Continua debug":::

1. <span data-ttu-id="a0070-158">Selezionare di nuovo la scheda **terminale** .</span><span class="sxs-lookup"><span data-stu-id="a0070-158">Select the **Terminal** tab again.</span></span>

   <span data-ttu-id="a0070-159">I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nel **console di debug**.</span><span class="sxs-lookup"><span data-stu-id="a0070-159">The values displayed in the console window correspond to the changes you made in the **Debug Console**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="Terminale che mostra i valori immessi":::

1. <span data-ttu-id="a0070-161">Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="a0070-161">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="a0070-162">Impostare un punto di interruzione condizionale</span><span class="sxs-lookup"><span data-stu-id="a0070-162">Set a conditional breakpoint</span></span>

<span data-ttu-id="a0070-163">Il programma Visualizza la stringa che l'utente immette.</span><span class="sxs-lookup"><span data-stu-id="a0070-163">The program displays the string that the user enters.</span></span> <span data-ttu-id="a0070-164">Ma cosa succede se l'utente non immette alcuna stringa?</span><span class="sxs-lookup"><span data-stu-id="a0070-164">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="a0070-165">È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*.</span><span class="sxs-lookup"><span data-stu-id="a0070-165">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="a0070-166">Fare clic con il pulsante destro del mouse (<kbd>CTRL +</kbd>clic su MacOS) sul punto rosso che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="a0070-166">Right-click (<kbd>Ctrl</kbd>-click on macOS) on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="a0070-167">Nel menu di scelta rapida selezionare **modifica** punto di interruzione per aprire una finestra di dialogo che consente di immettere un'espressione condizionale.</span><span class="sxs-lookup"><span data-stu-id="a0070-167">In the context menu, select **Edit Breakpoint** to open a dialog that lets you enter a conditional expression.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="Menu di scelta rapida Punto di interruzione":::

1. <span data-ttu-id="a0070-169">Selezionare `Expression` nell'elenco a discesa, immettere l'espressione condizionale seguente e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-169">Select `Expression` in the drop-down, enter the following conditional expression, and press <kbd>Enter</kbd>.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="Immettere un'espressione condizionale":::

   <span data-ttu-id="a0070-171">Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="a0070-171">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="a0070-172">Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte.</span><span class="sxs-lookup"><span data-stu-id="a0070-172">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="a0070-173">Un'altra opzione consiste nello specificare una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.</span><span class="sxs-lookup"><span data-stu-id="a0070-173">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="a0070-174">Avviare il programma con il debug premendo <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-174">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="a0070-175">Nella scheda **terminale** premere il tasto <kbd>invio</kbd> quando viene richiesto di immettere il nome.</span><span class="sxs-lookup"><span data-stu-id="a0070-175">In the **Terminal** tab, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

   <span data-ttu-id="a0070-176">Poiché la condizione specificata ( `name` is `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima che venga eseguito il `Console.WriteLine` metodo.</span><span class="sxs-lookup"><span data-stu-id="a0070-176">Because the condition you specified (`name` is `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

   <span data-ttu-id="a0070-177">La finestra **variabili** Mostra che il valore della `name` variabile è `""` o <xref:System.String.Empty?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a0070-177">The **Variables** window shows that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="a0070-178">Confermare che il valore è una stringa vuota immettendo l'istruzione seguente al prompt dei **console di debug** e premendo <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-178">Confirm the value is an empty string by entering the following statement at the **Debug Console** prompt and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="a0070-179">Il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="a0070-179">The result is `true`.</span></span>

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="Console di debug la restituzione di un valore true dopo l'esecuzione dell'istruzione":::

1. <span data-ttu-id="a0070-181">Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="a0070-181">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="a0070-182">Selezionare la scheda **terminale** e premere un tasto qualsiasi per uscire dal programma e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="a0070-182">Select the **Terminal** tab, and press any key to exit the program and stop debugging.</span></span>

1. <span data-ttu-id="a0070-183">Cancellare il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="a0070-183">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="a0070-184">Altre modalità di cancellazione di un punto di interruzione sono premendo <kbd>F9</kbd> o scegliendo **Esegui > Imposta/Rimuovi** punto di interruzione dal menu mentre è selezionata la riga di codice.</span><span class="sxs-lookup"><span data-stu-id="a0070-184">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Run > Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

1. <span data-ttu-id="a0070-185">Se viene visualizzato un avviso che indica che la condizione del punto di interruzione andrà persa, selezionare Rimuovi punto di **interruzione**.</span><span class="sxs-lookup"><span data-stu-id="a0070-185">If you get a warning that the breakpoint condition will be lost, select **Remove Breakpoint**.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="a0070-186">Scorrere un programma</span><span class="sxs-lookup"><span data-stu-id="a0070-186">Step through a program</span></span>

<span data-ttu-id="a0070-187">Visual Studio Code consente inoltre di passare riga per riga attraverso un programma e monitorarne l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0070-187">Visual Studio Code also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="a0070-188">In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma.</span><span class="sxs-lookup"><span data-stu-id="a0070-188">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="a0070-189">Poiché questo programma è di piccole dimensioni, è possibile eseguire l'intero programma.</span><span class="sxs-lookup"><span data-stu-id="a0070-189">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="a0070-190">Impostare un punto di interruzione sulla parentesi graffa di apertura del `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="a0070-190">Set a breakpoint on the opening curly brace of the `Main` method.</span></span>

1. <span data-ttu-id="a0070-191">Premere <kbd>F5</kbd> per avviare il debug.</span><span class="sxs-lookup"><span data-stu-id="a0070-191">Press <kbd>F5</kbd> to start debugging.</span></span>

   <span data-ttu-id="a0070-192">Visual Studio Code evidenzia la riga del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="a0070-192">Visual Studio Code highlights the breakpoint line.</span></span>

   <span data-ttu-id="a0070-193">A questo punto, nella finestra **variabili** viene indicato che la `args` matrice è vuota e `name` e `date` hanno valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a0070-193">At this point, the **Variables** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span>

1. <span data-ttu-id="a0070-194">Selezionare **Esegui**  >  **istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-194">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="Pulsante Esegui istruzione":::

   <span data-ttu-id="a0070-196">Visual Studio Code evidenzia la riga successiva.</span><span class="sxs-lookup"><span data-stu-id="a0070-196">Visual Studio Code highlights the next line.</span></span>

1. <span data-ttu-id="a0070-197">Selezionare **Esegui**  >  **istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-197">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a0070-198">Visual Studio Code esegue `Console.WriteLine` per la richiesta del nome ed evidenzia la riga successiva di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0070-198">Visual Studio Code executes the `Console.WriteLine` for the name prompt and highlights the next line of execution.</span></span> <span data-ttu-id="a0070-199">La riga successiva è `Console.ReadLine` per `name` .</span><span class="sxs-lookup"><span data-stu-id="a0070-199">The next line is the `Console.ReadLine` for the `name`.</span></span> <span data-ttu-id="a0070-200">La finestra **variabili** è invariata e la scheda **terminale** Mostra "Qual è il nome?"</span><span class="sxs-lookup"><span data-stu-id="a0070-200">The **Variables** window is unchanged, and the **Terminal** tab shows the "What is your name?"</span></span> <span data-ttu-id="a0070-201">prompt.</span><span class="sxs-lookup"><span data-stu-id="a0070-201">prompt.</span></span>

1. <span data-ttu-id="a0070-202">Selezionare **Esegui**  >  **istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-202">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a0070-203">Visual Studio evidenzia l' `name` assegnazione della variabile.</span><span class="sxs-lookup"><span data-stu-id="a0070-203">Visual Studio highlights the `name` variable assignment.</span></span> <span data-ttu-id="a0070-204">La finestra **variabili** Mostra che `name` è ancora `null` .</span><span class="sxs-lookup"><span data-stu-id="a0070-204">The **Variables** window shows that `name` is still `null`.</span></span>

1. <span data-ttu-id="a0070-205">Per rispondere alla richiesta, immettere una stringa nella scheda terminale e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-205">Respond to the prompt by entering a string in the Terminal tab and pressing <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="a0070-206">La scheda **terminale** potrebbe non visualizzare la stringa immessa durante l'immissione, ma il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> Metodo acquisirà l'input.</span><span class="sxs-lookup"><span data-stu-id="a0070-206">The **Terminal** tab might not display the string you enter while you're entering it, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will capture your input.</span></span>

1. <span data-ttu-id="a0070-207">Selezionare **Esegui**  >  **istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-207">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a0070-208">Visual Studio Code evidenzia l' `date` assegnazione della variabile.</span><span class="sxs-lookup"><span data-stu-id="a0070-208">Visual Studio Code highlights the `date` variable assignment.</span></span> <span data-ttu-id="a0070-209">Nella finestra **variabili** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="a0070-209">The **Variables** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a0070-210">Nella scheda **terminale** viene visualizzata la stringa immessa al prompt.</span><span class="sxs-lookup"><span data-stu-id="a0070-210">The **Terminal** tab displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="a0070-211">Selezionare **Esegui**  >  **istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-211">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a0070-212">Nella finestra **variabili** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a0070-212">The **Variables** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span>

1. <span data-ttu-id="a0070-213">Selezionare **Esegui**  >  **istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-213">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a0070-214">Visual Studio Code chiama il <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="a0070-214">Visual Studio Code calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a0070-215">Nella finestra della console viene visualizzata la stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="a0070-215">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="a0070-216">Selezionare **Esegui**  >  **istruzione/uscita** o premere <kbd>MAIUSC</kbd> + <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a0070-216">Select **Run** > **Step Out** or press <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="Pulsante Esci da istruzione/uscita":::

1. <span data-ttu-id="a0070-218">Selezionare la scheda **terminale** .</span><span class="sxs-lookup"><span data-stu-id="a0070-218">Select the **Terminal** tab.</span></span>

   <span data-ttu-id="a0070-219">Il terminale Visualizza "premere un tasto qualsiasi per uscire..."</span><span class="sxs-lookup"><span data-stu-id="a0070-219">The terminal displays "Press any key to exit..."</span></span>

1. <span data-ttu-id="a0070-220">Premere un tasto qualsiasi per uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="a0070-220">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="a0070-221">Usa configurazione build di rilascio</span><span class="sxs-lookup"><span data-stu-id="a0070-221">Use Release build configuration</span></span>

<span data-ttu-id="a0070-222">Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="a0070-222">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="a0070-223">La versione di rilascio incorpora le ottimizzazioni del compilatore che possono influire sul comportamento di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a0070-223">The Release version incorporates compiler optimizations that can affect the behavior of an application.</span></span> <span data-ttu-id="a0070-224">Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.</span><span class="sxs-lookup"><span data-stu-id="a0070-224">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="a0070-225">Per compilare e testare la versione di rilascio dell'applicazione console, aprire il **terminale** ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a0070-225">To build and test the Release version of your console application, open the **Terminal** and run the following command:</span></span>

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a><span data-ttu-id="a0070-226">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a0070-226">Additional resources</span></span>

* [<span data-ttu-id="a0070-227">Debugging in Visual Studio Code (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="a0070-227">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a><span data-ttu-id="a0070-228">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a0070-228">Next steps</span></span>

<span data-ttu-id="a0070-229">In questa esercitazione sono stati usati Visual Studio Code strumenti di debug.</span><span class="sxs-lookup"><span data-stu-id="a0070-229">In this tutorial, you used Visual Studio Code debugging tools.</span></span> <span data-ttu-id="a0070-230">Nell'esercitazione successiva si pubblica una versione distribuibile dell'app.</span><span class="sxs-lookup"><span data-stu-id="a0070-230">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a0070-231">Pubblicare un'applicazione console .NET Core con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a0070-231">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
