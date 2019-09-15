---
title: 'Procedura: Creare un flusso di lavoro sequenziale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 61e3f01b1259536ff15d71526e91aef42069722e
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989700"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="81885-102">Procedura: Creare un flusso di lavoro sequenziale</span><span class="sxs-lookup"><span data-stu-id="81885-102">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="81885-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="81885-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="81885-104">Questo argomento illustra la creazione di un flusso di lavoro che usa sia attività predefinite, ad <xref:System.Activities.Statements.Sequence> esempio l'attività, che le attività personalizzate della [procedura precedente: Creare un argomento](how-to-create-an-activity.md) di attività.</span><span class="sxs-lookup"><span data-stu-id="81885-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="81885-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="81885-105">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="81885-106">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="81885-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="81885-107">Per completare questo argomento, è necessario completare [prima di tutto come: Creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="81885-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="81885-108">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="81885-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="81885-109">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="81885-109">To create the workflow</span></span>

1. <span data-ttu-id="81885-110">Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowActivities** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="81885-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="81885-111">Nel nodo **elementi comuni** **installati**selezionare **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="81885-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="81885-112">Selezionare **attività** dall'elenco **flusso di lavoro** .</span><span class="sxs-lookup"><span data-stu-id="81885-112">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="81885-113">Digitare `SequentialNumberGuessWorkflow` nella casella **nome** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="81885-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="81885-114">Trascinare un'attività **Sequence** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla sull'etichetta rilasciare l' **attività** nell'area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="81885-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="81885-115">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="81885-115">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="81885-116">Fare doppio clic su **SequentialNumberGuessWorkflow. XAML** in **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="81885-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="81885-117">Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **argomenti** .</span><span class="sxs-lookup"><span data-stu-id="81885-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="81885-118">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="81885-118">Click **Create Argument**.</span></span>

4. <span data-ttu-id="81885-119">Digitare `MaxNumber` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **Int32** dall'elenco a discesa tipo di **argomento** , quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="81885-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="81885-120">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="81885-120">Click **Create Argument**.</span></span>

6. <span data-ttu-id="81885-121">Digitare `Turns` nella casella **nome** che si trova sotto l'argomento appena `MaxNumber` aggiunto, selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="81885-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="81885-122">Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere il riquadro **argomenti** .</span><span class="sxs-lookup"><span data-stu-id="81885-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="81885-123">Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **variabili** .</span><span class="sxs-lookup"><span data-stu-id="81885-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="81885-124">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="81885-124">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="81885-125">Se non viene visualizzata la casella **Crea variabile** , fare clic sull'attività **Sequence** nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="81885-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="81885-126">Digitare `Guess` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="81885-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="81885-127">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="81885-127">Click **Create Variable**.</span></span>

12. <span data-ttu-id="81885-128">Digitare `Target` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="81885-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="81885-129">Fare clic su **variabili** nel lato inferiore sinistro dell'ActivityDesigner per chiudere il riquadro **variabili** .</span><span class="sxs-lookup"><span data-stu-id="81885-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="81885-130">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="81885-130">To add the workflow activities</span></span>

1. <span data-ttu-id="81885-131">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="81885-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="81885-132">Digitare `Target` nella casella **a** e l'espressione seguente nella casella **immettere un' C# espressione** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="81885-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="81885-133">Se la finestra **casella degli strumenti** non è visualizzata, scegliere **casella degli strumenti** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="81885-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="81885-134">Trascinare un'attività **DoWhile** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nel flusso di lavoro in modo che si trovi sotto l'attività **assign** .</span><span class="sxs-lookup"><span data-stu-id="81885-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="81885-135">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **DoWhile** .</span><span class="sxs-lookup"><span data-stu-id="81885-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="81885-136">Un'attività <xref:System.Activities.Statements.DoWhile> esegue le proprie attività figlio e successivamente valuta <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="81885-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="81885-137">Se <xref:System.Activities.Statements.DoWhile.Condition%2A> dà come risultato `True`, le attività in <xref:System.Activities.Statements.DoWhile> vengono eseguite nuovamente.</span><span class="sxs-lookup"><span data-stu-id="81885-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="81885-138">In questo esempio, viene valutata l'ipotesi dell'utente e <xref:System.Activities.Statements.DoWhile> continua finché l'ipotesi non è corretta.</span><span class="sxs-lookup"><span data-stu-id="81885-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="81885-139">Trascinare un'attività **prompt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti** e rilasciarla nell'attività **DoWhile** del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="81885-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="81885-140">Nella **finestra Proprietà**Digitare `"EnterGuess"` includendo le virgolette nella casella del valore della proprietà **BookmarkName** per l'attività **prompt** .</span><span class="sxs-lookup"><span data-stu-id="81885-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="81885-141">Digitare `Guess` nella casella valore proprietà **risultato** e digitare l'espressione seguente nella casella della proprietà **testo** .</span><span class="sxs-lookup"><span data-stu-id="81885-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="81885-142">Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="81885-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="81885-143">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nell'attività **DoWhile** in modo che segua l'attività **prompt** .</span><span class="sxs-lookup"><span data-stu-id="81885-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81885-144">Quando si rilascia l'attività **assign** , si noti come la finestra di progettazione del flusso di lavoro aggiunge automaticamente un'attività **Sequence** in modo che contenga sia l'attività **prompt** che l'attività **assign** appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="81885-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="81885-145">Digitare `Turns` nella casella **a** e `Turns + 1` nella casella **immettere un' C# espressione** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="81885-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="81885-146">Trascinare un'attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** in modo che segua l'attività **assign** appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="81885-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="81885-147">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** .</span><span class="sxs-lookup"><span data-stu-id="81885-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="81885-148">Trascinare un'altra attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nella sezione **then** della prima attività **if** .</span><span class="sxs-lookup"><span data-stu-id="81885-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="81885-149">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="81885-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="81885-150">Trascinare due attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarle in modo che una si trovi nella sezione **then** dell'attività **if** appena aggiunta e una si trovi nella sezione **else** .</span><span class="sxs-lookup"><span data-stu-id="81885-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="81885-151">Fare clic sull'attività **WriteLine** nella sezione **then** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .</span><span class="sxs-lookup"><span data-stu-id="81885-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="81885-152">Fare clic sull'attività **WriteLine** nella sezione **else** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .</span><span class="sxs-lookup"><span data-stu-id="81885-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="81885-153">Nell'esempio seguente viene illustrato il flusso di lavoro completato:</span><span class="sxs-lookup"><span data-stu-id="81885-153">The following example illustrates the completed workflow:</span></span>

     ![Screenshot che illustra il flusso di lavoro sequenziale completato.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="81885-155">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="81885-155">To build the workflow</span></span>

1. <span data-ttu-id="81885-156">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="81885-156">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="81885-157">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [procedura: Eseguire un flusso](how-to-run-a-workflow.md)di lavoro.</span><span class="sxs-lookup"><span data-stu-id="81885-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="81885-158">Se è già stata completata la [procedura: Eseguire un passaggio](how-to-run-a-workflow.md) del flusso di lavoro con uno stile di flusso di lavoro diverso e desidera eseguirlo tramite il flusso di lavoro sequenziale da questo passaggio, passare alla sezione [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) di [procedura: Eseguire un flusso](how-to-run-a-workflow.md)di lavoro.</span><span class="sxs-lookup"><span data-stu-id="81885-158">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="81885-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81885-159">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="81885-160">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="81885-160">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="81885-161">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="81885-161">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="81885-162">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="81885-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="81885-163">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="81885-163">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="81885-164">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="81885-164">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
