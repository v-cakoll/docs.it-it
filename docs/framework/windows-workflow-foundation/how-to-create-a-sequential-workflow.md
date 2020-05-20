---
title: 'Procedura: creare un flusso di lavoro sequenziale'
description: Questo articolo crea un flusso di lavoro che usa sia le attività predefinite, ad esempio l'attività Sequence, che le attività personalizzate.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: f80ac471fdcc425504b11b5fb17effa888aa9590
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419694"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="acabe-103">Procedura: creare un flusso di lavoro sequenziale</span><span class="sxs-lookup"><span data-stu-id="acabe-103">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="acabe-104">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="acabe-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="acabe-105">Questo argomento illustra la creazione di un flusso di lavoro che usa sia attività predefinite, ad esempio l' <xref:System.Activities.Statements.Sequence> attività, che le attività personalizzate dell'argomento [procedura: creare un'attività](how-to-create-an-activity.md) precedente.</span><span class="sxs-lookup"><span data-stu-id="acabe-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="acabe-106">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="acabe-106">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="acabe-107">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="acabe-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="acabe-108">Per completare questo argomento, è necessario completare prima di tutto [procedura: creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="acabe-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="acabe-109">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="acabe-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="acabe-110">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="acabe-110">To create the workflow</span></span>

1. <span data-ttu-id="acabe-111">Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowActivities** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="acabe-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="acabe-112">Nel nodo **elementi comuni** **installati**selezionare **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="acabe-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="acabe-113">Selezionare l'**attività** dall'elenco **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="acabe-113">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="acabe-114">Digitare `SequentialNumberGuessWorkflow` nella casella **nome** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="acabe-114">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="acabe-115">Trascinare un'attività **Sequence** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla sull'etichetta rilasciare l' **attività** nell'area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="acabe-115">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="acabe-116">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="acabe-116">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="acabe-117">Fare doppio clic su **SequentialNumberGuessWorkflow. XAML** in **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="acabe-117">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="acabe-118">Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **argomenti** .</span><span class="sxs-lookup"><span data-stu-id="acabe-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="acabe-119">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="acabe-119">Click **Create Argument**.</span></span>

4. <span data-ttu-id="acabe-120">Digitare `MaxNumber` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **Int32** dall'elenco a discesa tipo di **argomento** , quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="acabe-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="acabe-121">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="acabe-121">Click **Create Argument**.</span></span>

6. <span data-ttu-id="acabe-122">Digitare `Turns` nella casella **nome** che si trova sotto l'argomento appena aggiunto `MaxNumber` , selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="acabe-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="acabe-123">Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Argomenti**.</span><span class="sxs-lookup"><span data-stu-id="acabe-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="acabe-124">Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **variabili** .</span><span class="sxs-lookup"><span data-stu-id="acabe-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="acabe-125">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="acabe-125">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="acabe-126">Se non viene visualizzata la casella **Crea variabile** , fare clic sull'attività **Sequence** nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="acabe-126">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="acabe-127">Digitare `Guess` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="acabe-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="acabe-128">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="acabe-128">Click **Create Variable**.</span></span>

12. <span data-ttu-id="acabe-129">Digitare `Target` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="acabe-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="acabe-130">Fare clic su **Variabili** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Variabili**.</span><span class="sxs-lookup"><span data-stu-id="acabe-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="acabe-131">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="acabe-131">To add the workflow activities</span></span>

1. <span data-ttu-id="acabe-132">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="acabe-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="acabe-133">Digitare `Target` nella casella **a** e l'espressione seguente nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="acabe-133">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="acabe-134">Se la finestra **Casella degli strumenti** non è visualizzata, selezionare **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="acabe-134">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="acabe-135">Trascinare un'attività **DoWhile** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nel flusso di lavoro in modo che si trovi sotto l'attività **assign** .</span><span class="sxs-lookup"><span data-stu-id="acabe-135">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="acabe-136">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **DoWhile** .</span><span class="sxs-lookup"><span data-stu-id="acabe-136">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="acabe-137">Un'attività <xref:System.Activities.Statements.DoWhile> esegue le proprie attività figlio e successivamente valuta <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="acabe-137">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="acabe-138">Se <xref:System.Activities.Statements.DoWhile.Condition%2A> dà come risultato `True`, le attività in <xref:System.Activities.Statements.DoWhile> vengono eseguite nuovamente.</span><span class="sxs-lookup"><span data-stu-id="acabe-138">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="acabe-139">In questo esempio, viene valutata l'ipotesi dell'utente e <xref:System.Activities.Statements.DoWhile> continua finché l'ipotesi non è corretta.</span><span class="sxs-lookup"><span data-stu-id="acabe-139">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="acabe-140">Trascinare un'attività **prompt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti** e rilasciarla nell'attività **DoWhile** del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="acabe-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="acabe-141">Nella **finestra Proprietà**Digitare `"EnterGuess"` includendo le virgolette nella casella del valore della proprietà **BookmarkName** per l'attività **prompt** .</span><span class="sxs-lookup"><span data-stu-id="acabe-141">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="acabe-142">Digitare `Guess` nella casella valore proprietà **risultato** e digitare l'espressione seguente nella casella della proprietà **testo** .</span><span class="sxs-lookup"><span data-stu-id="acabe-142">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="acabe-143">Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="acabe-143">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="acabe-144">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nell'attività **DoWhile** in modo che segua l'attività **prompt** .</span><span class="sxs-lookup"><span data-stu-id="acabe-144">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="acabe-145">Quando si rilascia l'attività **assign** , si noti come la finestra di progettazione del flusso di lavoro aggiunge automaticamente un'attività **Sequence** in modo che contenga sia l'attività **prompt** che l'attività **assign** appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="acabe-145">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="acabe-146">Digitare `Turns` nella casella **a** e `Turns + 1` nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="acabe-146">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="acabe-147">Trascinare un'attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** in modo che segua l'attività **assign** appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="acabe-147">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="acabe-148">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** .</span><span class="sxs-lookup"><span data-stu-id="acabe-148">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="acabe-149">Trascinare un'altra attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nella sezione **then** della prima attività **if** .</span><span class="sxs-lookup"><span data-stu-id="acabe-149">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="acabe-150">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="acabe-150">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="acabe-151">Trascinare due attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarle in modo che una si trovi nella sezione **then** dell'attività **if** appena aggiunta e una si trovi nella sezione **else** .</span><span class="sxs-lookup"><span data-stu-id="acabe-151">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="acabe-152">Fare clic sull'attività **WriteLine** nella sezione **then** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .</span><span class="sxs-lookup"><span data-stu-id="acabe-152">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="acabe-153">Fare clic sull'attività **WriteLine** nella sezione **else** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .</span><span class="sxs-lookup"><span data-stu-id="acabe-153">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="acabe-154">Nell'esempio seguente viene illustrato il flusso di lavoro completato:</span><span class="sxs-lookup"><span data-stu-id="acabe-154">The following example illustrates the completed workflow:</span></span>

     ![Screenshot che illustra il flusso di lavoro sequenziale completato.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="acabe-156">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="acabe-156">To build the workflow</span></span>

1. <span data-ttu-id="acabe-157">Premere CTRL+MAIUSC+B per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="acabe-157">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="acabe-158">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="acabe-158">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="acabe-159">Se è già stato completato il passaggio [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md) con uno stile di flusso di lavoro diverso e si desidera eseguirlo tramite il flusso di lavoro sequenziale da questo passaggio, passare alla sezione [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) di [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="acabe-159">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="acabe-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acabe-160">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="acabe-161">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="acabe-161">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="acabe-162">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="acabe-162">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="acabe-163">Esercitazione Introduzione</span><span class="sxs-lookup"><span data-stu-id="acabe-163">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="acabe-164">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="acabe-164">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="acabe-165">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="acabe-165">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
