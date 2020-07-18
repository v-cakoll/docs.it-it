---
title: Eseguire il debug di un'applicazione console .NET Core usando Visual Studio per Mac
description: Informazioni su come eseguire il debug di un'app console .NET Core usando Visual Studio Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 7e2a25266fab40b5ef1d0a38b8bbf06a6843746b
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416019"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="27daf-103">Esercitazione: eseguire il debug di un'applicazione console .NET Core usando Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="27daf-103">Tutorial: Debug a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="27daf-104">In questa esercitazione sono stati introdotti gli strumenti di debug disponibili in Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="27daf-104">This tutorial introduces the debugging tools available in Visual Studio for Mac.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27daf-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="27daf-105">Prerequisites</span></span>

- <span data-ttu-id="27daf-106">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio per Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="27daf-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="27daf-107">Usa configurazione build di debug</span><span class="sxs-lookup"><span data-stu-id="27daf-107">Use Debug build configuration</span></span>

<span data-ttu-id="27daf-108">Il *debug* e la *versione* sono configurazioni di compilazione predefinite di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="27daf-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="27daf-109">Usare la configurazione della build di debug per il debug e la configurazione di rilascio per la distribuzione finale della versione.</span><span class="sxs-lookup"><span data-stu-id="27daf-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="27daf-110">Nella configurazione di debug, un programma viene compilato con informazioni di debug simboliche complete e senza ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="27daf-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="27daf-111">L'ottimizzazione rende più difficile il debug perché la relazione tra il codice sorgente e le istruzioni generate è più complessa.</span><span class="sxs-lookup"><span data-stu-id="27daf-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="27daf-112">La configurazione di rilascio di un programma non dispone di informazioni di debug simboliche ed è completamente ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="27daf-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="27daf-113">Per impostazione predefinita, Visual Studio usa la configurazione della build di debug, pertanto non è necessario modificarla prima del debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="27daf-114">Avviare Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="27daf-114">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="27daf-115">Aprire il progetto creato in [creare un'applicazione console .NET Core in Visual Studio per Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="27daf-115">Open the project that you created in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

   <span data-ttu-id="27daf-116">La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="27daf-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="27daf-117">La seguente immagine della barra degli strumenti Mostra che Visual Studio è configurato per compilare la versione di debug dell'app:</span><span class="sxs-lookup"><span data-stu-id="27daf-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-debug.png" alt-text="Barra degli strumenti di Visual Studio con debug evidenziato":::

## <a name="set-a-breakpoint"></a><span data-ttu-id="27daf-119">Imposta punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="27daf-119">Set a breakpoint</span></span>

<span data-ttu-id="27daf-120">Un punto di *interruzione* interrompe temporaneamente l'esecuzione dell'applicazione prima che venga eseguita la riga con il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="27daf-121">Impostare un punto di interruzione nella riga in cui vengono visualizzati il nome, la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="27daf-121">Set a breakpoint on the line that displays the name, date, and time.</span></span> <span data-ttu-id="27daf-122">A tale scopo, posizionare il cursore nella riga di codice e premere <kbd>⌘</kbd> <kbd>\\</kbd> (<kbd>comando</kbd> + <kbd>\\</kbd> ).</span><span class="sxs-lookup"><span data-stu-id="27daf-122">To do that, place the cursor in the line of code and press <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>command</kbd>+<kbd>\\</kbd>).</span></span> <span data-ttu-id="27daf-123">Un altro modo per impostare un punto di interruzione consiste nel selezionare **Esegui**  >  **/Rimuovi** punto di interruzione dal menu.</span><span class="sxs-lookup"><span data-stu-id="27daf-123">Another way to set a breakpoint is by selecting **Run** > **Toggle Breakpoint** from the menu.</span></span>

   <span data-ttu-id="27daf-124">Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando il punto e visualizzando un punto rosso nel margine sinistro.</span><span class="sxs-lookup"><span data-stu-id="27daf-124">Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/set-breakpoint-in-editor.png" alt-text="Finestra del programma in Visual Studio con punto di interruzione impostato":::

1. <span data-ttu-id="27daf-126">Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per avviare il programma in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-126">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start the program in debugging mode.</span></span> <span data-ttu-id="27daf-127">Un altro modo per avviare il debug è scegliere **Esegui**  >  **Avvia debug** dal menu.</span><span class="sxs-lookup"><span data-stu-id="27daf-127">Another way to start debugging is by choosing **Run** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="27daf-128">Immettere una stringa nella finestra del terminale quando il programma richiede un nome e quindi premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="27daf-128">Enter a string in the terminal window when the program prompts for a name, and then press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="27daf-129">L'esecuzione del programma si interrompe quando raggiunge il punto di interruzione, prima dell' `Console.WriteLine` esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="27daf-129">Program execution stops when it reaches the breakpoint, before the `Console.WriteLine` method executes.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-hit.png" alt-text="Screenshot di un punto di interruzione in Visual Studio":::

## <a name="use-the-immediate-window"></a><span data-ttu-id="27daf-131">Utilizzare la finestra controllo immediato</span><span class="sxs-lookup"><span data-stu-id="27daf-131">Use the Immediate window</span></span>

<span data-ttu-id="27daf-132">La finestra **controllo immediato** consente di interagire con l'applicazione di cui si sta eseguendo il debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-132">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="27daf-133">È possibile modificare in modo interattivo il valore delle variabili per vedere come influiscono sul programma.</span><span class="sxs-lookup"><span data-stu-id="27daf-133">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="27daf-134">Se la finestra di **controllo immediato** non è visibile, visualizzarla scegliendo **Visualizza**i  >  **rilievi di debug**  >  **immediato**.</span><span class="sxs-lookup"><span data-stu-id="27daf-134">If the **Immediate** window is not visible, display it by choosing **View** > **Debug Pads** > **Immediate**.</span></span>

1. <span data-ttu-id="27daf-135">Immettere `name = "Gracie"` nella finestra di **controllo immediato** e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="27daf-135">Enter `name = "Gracie"` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="27daf-136">Immettere `date = date.AddDays(1)` nella finestra di **controllo immediato** e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="27daf-136">Enter `date = date.AddDays(1)` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

   <span data-ttu-id="27daf-137">Nella finestra di **controllo immediato** vengono visualizzati il nuovo valore della variabile stringa e le proprietà del <xref:System.DateTime> valore.</span><span class="sxs-lookup"><span data-stu-id="27daf-137">The **Immediate** window displays the new value of the string variable and the properties of the <xref:System.DateTime> value.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window.png" alt-text="Finestra di controllo immediato in Visual Studio":::

   <span data-ttu-id="27daf-139">Nella finestra **Variabili locali** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-139">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span> <span data-ttu-id="27daf-140">I valori delle variabili appena modificate vengono aggiornati nella finestra variabili **locali** .</span><span class="sxs-lookup"><span data-stu-id="27daf-140">The values of the variables that you just changed are updated in the **Locals** window.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/locals-window.png" alt-text="Finestra variabili locali in Visual Studio":::

1. <span data-ttu-id="27daf-142">Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per continuare il debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-142">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

   <span data-ttu-id="27daf-143">I valori visualizzati nel terminale corrispondono alle modifiche apportate nella finestra di **controllo immediato** .</span><span class="sxs-lookup"><span data-stu-id="27daf-143">The values displayed in the terminal correspond to the changes you made in the **Immediate** window.</span></span>

   <span data-ttu-id="27daf-144">Se il terminale non è visibile, selezionare **Terminal-HelloWorld** nella barra di spostamento inferiore.</span><span class="sxs-lookup"><span data-stu-id="27daf-144">If you don't see the Terminal, select **Terminal - HelloWorld** in the bottom navigation bar.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/terminal-hello-world.png" alt-text="Hello World terminali nella barra di spostamento inferiore":::

1. <span data-ttu-id="27daf-146">Premere un tasto qualsiasi per uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="27daf-146">Press any key to exit the program.</span></span>

1. <span data-ttu-id="27daf-147">Chiudere la finestra del terminale.</span><span class="sxs-lookup"><span data-stu-id="27daf-147">Close the terminal window.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="27daf-148">Impostare un punto di interruzione condizionale</span><span class="sxs-lookup"><span data-stu-id="27daf-148">Set a conditional breakpoint</span></span>

<span data-ttu-id="27daf-149">Il programma visualizza una stringa immessa dall'utente.</span><span class="sxs-lookup"><span data-stu-id="27daf-149">The program displays a string that the user enters.</span></span> <span data-ttu-id="27daf-150">Ma cosa succede se l'utente non immette alcuna stringa?</span><span class="sxs-lookup"><span data-stu-id="27daf-150">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="27daf-151">È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*.</span><span class="sxs-lookup"><span data-stu-id="27daf-151">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="27daf-152">fare clic con il <kbd>pulsante destro del</kbd>mouse sul punto rosso che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-152"><kbd>ctrl</kbd>-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="27daf-153">Nel menu di scelta rapida selezionare **modifica**punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-153">In the context menu, select **Edit Breakpoint**.</span></span>

1. <span data-ttu-id="27daf-154">Nella finestra di dialogo Modifica punto di **interruzione** immettere il codice seguente nel campo seguente **e la condizione seguente è true**e selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="27daf-154">In the **Edit Breakpoint** dialog, enter the following code in the field that follows **And the following condition is true**, and select **Apply**.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-settings.png" alt-text="Editor che mostra il pannello impostazioni del punto di interruzione":::

   <span data-ttu-id="27daf-156">Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="27daf-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="27daf-157">Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte.</span><span class="sxs-lookup"><span data-stu-id="27daf-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span>

1. <span data-ttu-id="27daf-158">Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per avviare il debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-158">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

1. <span data-ttu-id="27daf-159">Nella finestra del terminale premere <kbd>invio</kbd> quando viene richiesto di immettere il nome.</span><span class="sxs-lookup"><span data-stu-id="27daf-159">In the terminal window, press <kbd>enter</kbd> when prompted to enter your name.</span></span>

   <span data-ttu-id="27daf-160">Poiché la condizione specificata ( `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-160">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint.</span></span>

1. <span data-ttu-id="27daf-161">Selezionare la finestra variabili **locali** , che mostra i valori delle variabili locali per il metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-161">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="27daf-162">In questo caso, `Main` è il metodo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-162">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="27daf-163">Si noti che il valore della `name` variabile è `""` , ovvero <xref:System.String.Empty?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="27daf-163">Observe that the value of the `name` variable is `""`, that is, <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="27daf-164">È anche possibile notare che il valore è una stringa vuota immettendo il `name` nome della variabile nella finestra di **controllo immediato** e premendo <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="27daf-164">You can also see that the value is an empty string by entering the `name` variable name in the **Immediate** window and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window-output.png" alt-text="La finestra di controllo immediato che mostra il nome è una stringa vuota":::

1. <span data-ttu-id="27daf-166">Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per continuare il debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-166">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

1. <span data-ttu-id="27daf-167">Nella finestra del terminale premere un tasto qualsiasi per uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="27daf-167">In the terminal window, press any key to exit the program.</span></span>

1. <span data-ttu-id="27daf-168">Chiudere la finestra del terminale.</span><span class="sxs-lookup"><span data-stu-id="27daf-168">Close the terminal window.</span></span>

1. <span data-ttu-id="27daf-169">Deselezionare il punto di interruzione facendo clic sul punto rosso nel margine sinistro della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="27daf-169">Clear the breakpoint by clicking on the red dot in the left margin of the code window.</span></span> <span data-ttu-id="27daf-170">Un altro modo per cancellare un punto di interruzione è scegliere **esegui > Imposta/Rimuovi** punto di interruzione mentre è selezionata la riga di codice.</span><span class="sxs-lookup"><span data-stu-id="27daf-170">Another way to clear a breakpoint is by choosing **Run > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="27daf-171">Scorrere un programma</span><span class="sxs-lookup"><span data-stu-id="27daf-171">Step through a program</span></span>

<span data-ttu-id="27daf-172">Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-172">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="27daf-173">In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma.</span><span class="sxs-lookup"><span data-stu-id="27daf-173">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="27daf-174">Poiché questo programma è di piccole dimensioni, è possibile eseguire l'intero programma.</span><span class="sxs-lookup"><span data-stu-id="27daf-174">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="27daf-175">Impostare un punto di interruzione sulla parentesi graffa che contrassegna l'inizio del `Main` Metodo (premere <kbd>comando</kbd> + <kbd>\\</kbd> ).</span><span class="sxs-lookup"><span data-stu-id="27daf-175">Set a breakpoint on the curly brace that marks the start of the `Main` method (press <kbd>command</kbd>+<kbd>\\</kbd>).</span></span>

1. <span data-ttu-id="27daf-176">Premere <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>comando</kbd> + <kbd>invio</kbd>) per avviare il debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-176">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

   <span data-ttu-id="27daf-177">Visual Studio si interrompe in corrispondenza della riga con il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="27daf-177">Visual Studio stops on the line with the breakpoint.</span></span>

1. <span data-ttu-id="27daf-178">Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>MAIUSC</kbd> + <kbd>comando</kbd> + <kbd>i</kbd>) o selezionare **Esegui**  >  **istruzione** per avanzare di una riga.</span><span class="sxs-lookup"><span data-stu-id="27daf-178">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>) or select **Run** > **Step Into** to advance one line.</span></span>

   <span data-ttu-id="27daf-179">Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="27daf-179">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/step-into-method.png" alt-text="Metodo Esegui istruzione di Visual Studio":::

   <span data-ttu-id="27daf-181">A questo punto, nella finestra **variabili locali** viene indicato che la `args` matrice è vuota e che i `name` `date` valori predefiniti sono e.</span><span class="sxs-lookup"><span data-stu-id="27daf-181">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="27daf-182">Inoltre, Visual Studio ha aperto un terminale vuoto.</span><span class="sxs-lookup"><span data-stu-id="27daf-182">In addition, Visual Studio has opened a blank terminal.</span></span>

1. <span data-ttu-id="27daf-183">Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).</span><span class="sxs-lookup"><span data-stu-id="27daf-183">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="27daf-184">Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`.</span><span class="sxs-lookup"><span data-stu-id="27daf-184">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="27daf-185">La finestra **variabili locali** Mostra che `name` è `null` e il terminale Visualizza la stringa "Qual è il nome?".</span><span class="sxs-lookup"><span data-stu-id="27daf-185">The **Locals** window shows that `name` is `null`, and the terminal displays the string "What is your name?".</span></span>

1. <span data-ttu-id="27daf-186">Per rispondere alla richiesta, immettere una stringa nella finestra della console e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="27daf-186">Respond to the prompt by entering a string in the console window and pressing <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="27daf-187">Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).</span><span class="sxs-lookup"><span data-stu-id="27daf-187">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="27daf-188">Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `date`.</span><span class="sxs-lookup"><span data-stu-id="27daf-188">Visual Studio highlights the statement that includes the `date` variable assignment.</span></span> <span data-ttu-id="27daf-189">Nella finestra **variabili locali** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="27daf-189">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="27daf-190">Il terminale Visualizza la stringa immessa al prompt.</span><span class="sxs-lookup"><span data-stu-id="27daf-190">The terminal displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="27daf-191">Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).</span><span class="sxs-lookup"><span data-stu-id="27daf-191">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="27daf-192">Nella finestra variabili **locali** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="27daf-192">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="27daf-193">Il terminale non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="27daf-193">The terminal is unchanged.</span></span>

1. <span data-ttu-id="27daf-194">Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>i</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>i</kbd>).</span><span class="sxs-lookup"><span data-stu-id="27daf-194">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="27daf-195">Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27daf-195">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="27daf-196">Il terminale Visualizza la stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="27daf-196">The terminal displays the formatted string.</span></span>

1. <span data-ttu-id="27daf-197">Premere <kbd>⇧</kbd><kbd>⌘</kbd><kbd>u</kbd> (<kbd>shift</kbd> + <kbd>comando</kbd>MAIUSC + <kbd>u</kbd>) o selezionare **Esegui**  >  **istruzione/uscita**.</span><span class="sxs-lookup"><span data-stu-id="27daf-197">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>U</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>U</kbd>) or select **Run** > **Step Out**.</span></span>

   <span data-ttu-id="27daf-198">Il terminale Visualizza un messaggio e attende che venga premuto un tasto.</span><span class="sxs-lookup"><span data-stu-id="27daf-198">The terminal displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="27daf-199">Premere un tasto qualsiasi per uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="27daf-199">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="27daf-200">Usa configurazione build di rilascio</span><span class="sxs-lookup"><span data-stu-id="27daf-200">Use Release build configuration</span></span>

<span data-ttu-id="27daf-201">Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="27daf-201">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="27daf-202">La versione di rilascio incorpora le ottimizzazioni del compilatore che possono influire negativamente sul comportamento di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27daf-202">The Release version incorporates compiler optimizations that can negatively affect the behavior of an application.</span></span> <span data-ttu-id="27daf-203">Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.</span><span class="sxs-lookup"><span data-stu-id="27daf-203">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="27daf-204">Per compilare e testare la versione di rilascio dell'applicazione console, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="27daf-204">To build and test the Release version of the console application, do the following steps:</span></span>

1. <span data-ttu-id="27daf-205">Modificare la configurazione della build sulla barra degli strumenti da **debug** a **versione**.</span><span class="sxs-lookup"><span data-stu-id="27daf-205">Change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra degli strumenti predefinita di Visual Studio con Debug evidenziata":::

1. <span data-ttu-id="27daf-207">Premere <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opzione</kbd> + <kbd>comando</kbd> + <kbd>invio</kbd>) per eseguire senza debug.</span><span class="sxs-lookup"><span data-stu-id="27daf-207">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run without debugging.</span></span>

## <a name="next-steps"></a><span data-ttu-id="27daf-208">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="27daf-208">Next steps</span></span>

<span data-ttu-id="27daf-209">In questa esercitazione sono stati usati gli strumenti di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="27daf-209">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="27daf-210">Nell'esercitazione successiva si pubblica una versione distribuibile dell'app.</span><span class="sxs-lookup"><span data-stu-id="27daf-210">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="27daf-211">Pubblicare un'applicazione console .NET Core con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="27daf-211">Publish a .NET Core console application with Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
