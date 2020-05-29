---
title: Eseguire il debug di un'applicazione console .NET Core con Visual Studio Code
description: Informazioni su come eseguire il debug di un'app console .NET Core con Visual Studio Code.
ms.date: 05/26/2020
ms.openlocfilehash: eaeb97f54442006d2f0e29483a68dc3de89b5778
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202589"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="86107-103">Esercitazione: eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="86107-103">Tutorial: Debug a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="86107-104">Questa esercitazione introduce gli strumenti di debug disponibili in Visual Studio Code per l'uso con le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="86107-104">This tutorial introduces the debugging tools available in Visual Studio Code for working with .NET Core apps.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86107-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="86107-105">Prerequisites</span></span>

- <span data-ttu-id="86107-106">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="86107-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="86107-107">Usa configurazione build di debug</span><span class="sxs-lookup"><span data-stu-id="86107-107">Use Debug build configuration</span></span>

<span data-ttu-id="86107-108">Il *debug* e la *versione* sono due delle configurazioni della build di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="86107-108">*Debug* and *release* are two of .NET Core's build configurations.</span></span> <span data-ttu-id="86107-109">Usare la configurazione della build di debug per il debug e la configurazione di rilascio per la distribuzione finale della versione.</span><span class="sxs-lookup"><span data-stu-id="86107-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="86107-110">Nella configurazione di debug, un programma viene compilato con informazioni di debug simboliche complete e senza ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="86107-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="86107-111">L'ottimizzazione rende più difficile il debug perché la relazione tra il codice sorgente e le istruzioni generate è più complessa.</span><span class="sxs-lookup"><span data-stu-id="86107-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="86107-112">La configurazione di rilascio di un programma non dispone di informazioni di debug simboliche ed è completamente ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="86107-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="86107-113">Per impostazione predefinita, Visual Studio Code Usa la configurazione della build di debug, pertanto non è necessario modificarla prima del debug.</span><span class="sxs-lookup"><span data-stu-id="86107-113">By default, Visual Studio Code uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="86107-114">Imposta punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="86107-114">Set a breakpoint</span></span>

<span data-ttu-id="86107-115">Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="86107-115">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="86107-116">In *Program.cs*, impostare un punto di *interruzione* sulla riga in cui vengono visualizzati il nome, la data e l'ora facendo clic sul margine sinistro della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="86107-116">In *Program.cs*, set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window.</span></span> <span data-ttu-id="86107-117">Il margine sinistro è a sinistra dei numeri di riga.</span><span class="sxs-lookup"><span data-stu-id="86107-117">The left margin is to the left of the line numbers.</span></span> <span data-ttu-id="86107-118">Un altro modo per impostare un punto di interruzione consiste nel posizionare il cursore nella riga di codice e quindi premere <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-118">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing <kbd>F9</kbd>.</span></span>

   <span data-ttu-id="86107-119">Come illustrato nell'immagine seguente, Visual Studio Code indica la riga in cui è impostato il punto di interruzione visualizzando un punto rosso nel margine sinistro.</span><span class="sxs-lookup"><span data-stu-id="86107-119">As the following image shows, Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="Set di punti di interruzione":::

## <a name="set-up-for-terminal-input"></a><span data-ttu-id="86107-121">Configurare per l'input del terminale</span><span class="sxs-lookup"><span data-stu-id="86107-121">Set up for terminal input</span></span>

<span data-ttu-id="86107-122">Il punto di interruzione si trova dopo una `Console.ReadLine` chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="86107-122">The breakpoint is located after a `Console.ReadLine` method call.</span></span> <span data-ttu-id="86107-123">Il **console di debug** non accetta l'input del terminale per un programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="86107-123">The **Debug Console** doesn't accept terminal input for a running program.</span></span> <span data-ttu-id="86107-124">Per gestire l'input del terminale durante il debug, è possibile usare il terminale integrato (uno dei Visual Studio Code Windows) o un terminale esterno.</span><span class="sxs-lookup"><span data-stu-id="86107-124">To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal.</span></span> <span data-ttu-id="86107-125">Per questa esercitazione si userà il terminale integrato.</span><span class="sxs-lookup"><span data-stu-id="86107-125">For this tutorial, you use the integrated terminal.</span></span>

1. <span data-ttu-id="86107-126">Aprire *. VSCODE/Launch. JSON*.</span><span class="sxs-lookup"><span data-stu-id="86107-126">Open *.vscode/launch.json*.</span></span>

1. <span data-ttu-id="86107-127">Modificare l' `console` impostazione in `integratedTerminal` .</span><span class="sxs-lookup"><span data-stu-id="86107-127">Change the `console` setting to `integratedTerminal`.</span></span>

   <span data-ttu-id="86107-128">Da:</span><span class="sxs-lookup"><span data-stu-id="86107-128">From:</span></span>

   ```
   "console": "internalConsole",
   ```

   <span data-ttu-id="86107-129">Con:</span><span class="sxs-lookup"><span data-stu-id="86107-129">To:</span></span>

   ```
   "console": "integratedTerminal",
   ```

1. <span data-ttu-id="86107-130">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="86107-130">Save your changes.</span></span>

## <a name="start-debugging"></a><span data-ttu-id="86107-131">Consente di iniziare il debug</span><span class="sxs-lookup"><span data-stu-id="86107-131">Start debugging</span></span>

1. <span data-ttu-id="86107-132">Aprire la visualizzazione debug selezionando l'icona debug nel menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="86107-132">Open the Debug view by selecting the Debugging icon on the left side menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Aprire la scheda Debug in Visual Studio Code":::

1. <span data-ttu-id="86107-134">Avviare il debug selezionando la freccia verde nella parte superiore del riquadro, accanto a **.NET Core Launch (console)**.</span><span class="sxs-lookup"><span data-stu-id="86107-134">Start debugging by selecting the green arrow at the top of the pane, next to **.NET Core Launch (console)**.</span></span>  <span data-ttu-id="86107-135">Un altro modo per avviare il debug è premere <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-135">Another way to start debugging is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="Consente di iniziare il debug":::

1. <span data-ttu-id="86107-137">Selezionare la scheda **terminale** per visualizzare il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="86107-137">Select the **Terminal** tab to see the "What is your name?"</span></span> <span data-ttu-id="86107-138">richiede che il programma venga visualizzato prima dell'attesa di una risposta.</span><span class="sxs-lookup"><span data-stu-id="86107-138">prompt that the program displays before waiting for a response.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="Selezionare la scheda terminale":::

1. <span data-ttu-id="86107-140">Immettere una stringa nella finestra del **terminale** in risposta alla richiesta di un nome, quindi premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-140">Enter a string in the **Terminal** window in response to the prompt for a name, and then press <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="86107-141">L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="86107-141">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="86107-142">Nella sezione variabili **locali** della finestra **variabili** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="86107-142">The **Locals** section of the **Variables** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="Raggiunto punto di interruzione, che Mostra variabili locali":::

## <a name="change-variable-values"></a><span data-ttu-id="86107-144">Modificare i valori delle variabili</span><span class="sxs-lookup"><span data-stu-id="86107-144">Change variable values</span></span>

<span data-ttu-id="86107-145">La finestra di **console di debug** consente di interagire con l'applicazione di cui si sta eseguendo il debug.</span><span class="sxs-lookup"><span data-stu-id="86107-145">The **Debug Console** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="86107-146">È possibile modificare il valore delle variabili per vedere come influiscono sul programma.</span><span class="sxs-lookup"><span data-stu-id="86107-146">You can change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="86107-147">Selezionare la scheda **console di debug** .</span><span class="sxs-lookup"><span data-stu-id="86107-147">Select the **Debug Console** tab.</span></span>

1. <span data-ttu-id="86107-148">Immettere `name = "Gracie"` al prompt nella parte inferiore della finestra **console di debug** e premere il tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="86107-148">Enter `name = "Gracie"` at the prompt at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="Modificare i valori delle variabili":::

1. <span data-ttu-id="86107-150">Immettere `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` nella parte inferiore della finestra di **console di debug** e premere il tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="86107-150">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="86107-151">Nella finestra **variabili** vengono visualizzati i nuovi valori delle `name` `date` variabili e.</span><span class="sxs-lookup"><span data-stu-id="86107-151">The **Variables** window displays the new values of the `name` and `date` variables.</span></span>

1. <span data-ttu-id="86107-152">Continuare l'esecuzione del programma selezionando il pulsante **continua** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="86107-152">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="86107-153">Un altro modo per continuare è premere <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-153">Another way to continue is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="Continua debug":::

1. <span data-ttu-id="86107-155">Selezionare di nuovo la scheda **terminale** .</span><span class="sxs-lookup"><span data-stu-id="86107-155">Select the **Terminal** tab again.</span></span>

   <span data-ttu-id="86107-156">I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nel **console di debug**.</span><span class="sxs-lookup"><span data-stu-id="86107-156">The values displayed in the console window correspond to the changes you made in the **Debug Console**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="Terminale che mostra i valori immessi":::

1. <span data-ttu-id="86107-158">Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="86107-158">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="86107-159">Impostare un punto di interruzione condizionale</span><span class="sxs-lookup"><span data-stu-id="86107-159">Set a conditional breakpoint</span></span>

<span data-ttu-id="86107-160">Il programma Visualizza la stringa che l'utente immette.</span><span class="sxs-lookup"><span data-stu-id="86107-160">The program displays the string that the user enters.</span></span> <span data-ttu-id="86107-161">Ma cosa succede se l'utente non immette alcuna stringa?</span><span class="sxs-lookup"><span data-stu-id="86107-161">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="86107-162">È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*.</span><span class="sxs-lookup"><span data-stu-id="86107-162">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="86107-163">Fare clic con il pulsante destro del mouse (<kbd>CTRL</kbd>+ clic su MacOS) sul punto rosso che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="86107-163">Right-click (<kbd>Ctrl</kbd>+click on macOS) on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="86107-164">Nel menu di scelta rapida selezionare **modifica** punto di interruzione per aprire una finestra di dialogo che consente di immettere un'espressione condizionale.</span><span class="sxs-lookup"><span data-stu-id="86107-164">In the context menu, select **Edit Breakpoint** to open a dialog that lets you enter a conditional expression.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="Menu di scelta rapida Punto di interruzione":::

1. <span data-ttu-id="86107-166">Selezionare `Expression` nell'elenco a discesa, immettere l'espressione condizionale seguente e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-166">Select `Expression` in the drop-down, enter the following conditional expression, and press <kbd>Enter</kbd>.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="Immettere un'espressione condizionale":::

   <span data-ttu-id="86107-168">Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="86107-168">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="86107-169">Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*, che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte o una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.</span><span class="sxs-lookup"><span data-stu-id="86107-169">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="86107-170">Avviare il programma con il debug premendo <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-170">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="86107-171">Nella scheda **terminale** premere il tasto <kbd>invio</kbd> quando viene richiesto di immettere il nome.</span><span class="sxs-lookup"><span data-stu-id="86107-171">In the **Terminal** tab, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

   <span data-ttu-id="86107-172">Poiché la condizione specificata ( `name` is `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima che venga eseguito il `Console.WriteLine` metodo.</span><span class="sxs-lookup"><span data-stu-id="86107-172">Because the condition you specified (`name` is `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

   <span data-ttu-id="86107-173">La finestra **variabili** Mostra che il valore della `name` variabile è `""` o <xref:System.String.Empty?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="86107-173">The **Variables** window shows that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="86107-174">Confermare che il valore è una stringa vuota immettendo l'istruzione seguente al prompt dei **console di debug** e premendo <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-174">Confirm the value is an empty string by entering the following statement at the **Debug Console** prompt and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="86107-175">Il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="86107-175">The result is `true`.</span></span>

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="Console di debug la restituzione di un valore true dopo l'esecuzione dell'istruzione":::

1. <span data-ttu-id="86107-177">Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="86107-177">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="86107-178">Selezionare la scheda **terminale** e premere un tasto qualsiasi per uscire dal programma e arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="86107-178">Select the **Terminal** tab, and press any key to exit the program and stop debugging.</span></span>

1. <span data-ttu-id="86107-179">Cancellare il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="86107-179">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="86107-180">Un altro modo per cancellare un punto di interruzione consiste nel premere <kbd>F9</kbd> mentre è selezionata la riga di codice.</span><span class="sxs-lookup"><span data-stu-id="86107-180">Another way to clear a breakpoint is by pressing <kbd>F9</kbd> while the line of code is selected.</span></span>

1. <span data-ttu-id="86107-181">Se viene visualizzato un avviso che indica che la condizione del punto di interruzione andrà persa, selezionare Rimuovi punto di **interruzione**.</span><span class="sxs-lookup"><span data-stu-id="86107-181">If you get a warning that the breakpoint condition will be lost, select **Remove Breakpoint**.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="86107-182">Scorrere un programma</span><span class="sxs-lookup"><span data-stu-id="86107-182">Step through a program</span></span>

<span data-ttu-id="86107-183">Visual Studio Code consente inoltre di passare riga per riga attraverso un programma e monitorarne l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="86107-183">Visual Studio Code also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="86107-184">In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma.</span><span class="sxs-lookup"><span data-stu-id="86107-184">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="86107-185">Poiché questo programma è di piccole dimensioni, è possibile eseguire l'intero programma.</span><span class="sxs-lookup"><span data-stu-id="86107-185">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="86107-186">Impostare un punto di interruzione sulla parentesi graffa di apertura del `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="86107-186">Set a breakpoint on the opening curly brace of the `Main` method.</span></span>

1. <span data-ttu-id="86107-187">Premere <kbd>F5</kbd> per avviare il debug.</span><span class="sxs-lookup"><span data-stu-id="86107-187">Press <kbd>F5</kbd> to start debugging.</span></span>

   <span data-ttu-id="86107-188">Visual Studio Code evidenzia la riga del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="86107-188">Visual Studio Code highlights the breakpoint line.</span></span>

   <span data-ttu-id="86107-189">A questo punto, nella finestra **variabili** viene indicato che la `args` matrice è vuota e `name` e `date` hanno valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="86107-189">At this point, the **Variables** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span>

1. <span data-ttu-id="86107-190">Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-190">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="Pulsante Esegui istruzione":::

   <span data-ttu-id="86107-192">Visual Studio Code evidenzia la riga successiva.</span><span class="sxs-lookup"><span data-stu-id="86107-192">Visual Studio Code highlights the next line.</span></span>

1. <span data-ttu-id="86107-193">Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-193">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="86107-194">Visual Studio Code esegue `Console.WriteLine` per la richiesta del nome ed evidenzia la riga successiva di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="86107-194">Visual Studio Code executes the `Console.WriteLine` for the name prompt and highlights the next line of execution.</span></span> <span data-ttu-id="86107-195">La riga successiva è `Console.ReadLine` per `name` .</span><span class="sxs-lookup"><span data-stu-id="86107-195">The next line is the `Console.ReadLine` for the `name`.</span></span> <span data-ttu-id="86107-196">La finestra **variabili** è invariata e la scheda **terminale** Mostra "Qual è il nome?"</span><span class="sxs-lookup"><span data-stu-id="86107-196">The **Variables** window is unchanged, and the **Terminal** tab shows the "What is your name?"</span></span> <span data-ttu-id="86107-197">prompt.</span><span class="sxs-lookup"><span data-stu-id="86107-197">prompt.</span></span>

1. <span data-ttu-id="86107-198">Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-198">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="86107-199">Visual Studio evidenzia l' `name` assegnazione della variabile.</span><span class="sxs-lookup"><span data-stu-id="86107-199">Visual Studio highlights the `name` variable assignment.</span></span> <span data-ttu-id="86107-200">La finestra **variabili** Mostra che `name` è ancora `null` .</span><span class="sxs-lookup"><span data-stu-id="86107-200">The **Variables** window shows that `name` is still `null`.</span></span>

1. <span data-ttu-id="86107-201">Per rispondere alla richiesta, immettere una stringa nella scheda terminale e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-201">Respond to the prompt by entering a string in the Terminal tab and pressing <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="86107-202">La scheda **terminale** potrebbe non visualizzare la stringa immessa durante l'immissione, ma il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> Metodo acquisirà l'input.</span><span class="sxs-lookup"><span data-stu-id="86107-202">The **Terminal** tab might not display the string you enter while you're entering it, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will capture your input.</span></span>

1. <span data-ttu-id="86107-203">Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-203">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="86107-204">Visual Studio Code evidenzia l' `date` assegnazione della variabile.</span><span class="sxs-lookup"><span data-stu-id="86107-204">Visual Studio Code highlights the `date` variable assignment.</span></span> <span data-ttu-id="86107-205">Nella finestra **variabili** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="86107-205">The **Variables** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="86107-206">Nella scheda **terminale** viene visualizzata la stringa immessa al prompt.</span><span class="sxs-lookup"><span data-stu-id="86107-206">The **Terminal** tab displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="86107-207">Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-207">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="86107-208">Nella finestra **variabili** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="86107-208">The **Variables** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span>

1. <span data-ttu-id="86107-209">Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-209">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="86107-210">Visual Studio Code chiama il <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="86107-210">Visual Studio Code calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="86107-211">Nella finestra della console viene visualizzata la stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="86107-211">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="86107-212">Selezionare **Esci da istruzione/uscita** o premere <kbd>MAIUSC</kbd> + <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="86107-212">Select **Step Out** or press <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="Pulsante Esci da istruzione/uscita":::

1. <span data-ttu-id="86107-214">Selezionare la scheda **terminale** .</span><span class="sxs-lookup"><span data-stu-id="86107-214">Select the **Terminal** tab.</span></span>

   <span data-ttu-id="86107-215">Il terminale Visualizza "premere un tasto qualsiasi per uscire..."</span><span class="sxs-lookup"><span data-stu-id="86107-215">The terminal displays "Press any key to exit..."</span></span>

1. <span data-ttu-id="86107-216">Premere un tasto qualsiasi per uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="86107-216">Press any key to exit the program.</span></span>

## <a name="select-release-build-configuration"></a><span data-ttu-id="86107-217">Selezionare la configurazione della build di rilascio</span><span class="sxs-lookup"><span data-stu-id="86107-217">Select Release build configuration</span></span>

<span data-ttu-id="86107-218">Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="86107-218">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="86107-219">La versione di rilascio incorpora le ottimizzazioni del compilatore che possono influire sul comportamento di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86107-219">The Release version incorporates compiler optimizations that can affect the behavior of an application.</span></span> <span data-ttu-id="86107-220">Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.</span><span class="sxs-lookup"><span data-stu-id="86107-220">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="86107-221">Per compilare e testare la versione di rilascio dell'applicazione console, aprire il **terminale** ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="86107-221">To build and test the Release version of your console application, open the **Terminal** and run the following command:</span></span>

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a><span data-ttu-id="86107-222">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86107-222">Additional resources</span></span>

* [<span data-ttu-id="86107-223">Debugging in Visual Studio Code (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="86107-223">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a><span data-ttu-id="86107-224">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="86107-224">Next steps</span></span>

<span data-ttu-id="86107-225">In questa esercitazione sono stati usati Visual Studio Code strumenti di debug.</span><span class="sxs-lookup"><span data-stu-id="86107-225">In this tutorial, you used Visual Studio Code debugging tools.</span></span> <span data-ttu-id="86107-226">Per informazioni su come pubblicare una versione distribuibile dell'app, vedere [pubblicare l'app](cli-create-console-app.md#publish-your-app).</span><span class="sxs-lookup"><span data-stu-id="86107-226">To learn how to publish a deployable version of the app, see [Publish your app](cli-create-console-app.md#publish-your-app).</span></span>

<!--In the next tutorial, you publish a deployable version of the app.

> [!div class="nextstepaction"]
> [Publish a .NET Core console application with Visual Studio Code](publishing-with-visual-studio-code.md)
-->
