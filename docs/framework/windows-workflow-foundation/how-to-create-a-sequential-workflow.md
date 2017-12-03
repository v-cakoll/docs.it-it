---
title: 'Procedura: creare un flusso di lavoro sequenziale'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 285450f3c9e724bcf449f638ee1922751c9cebaf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="dcd53-102">Procedura: creare un flusso di lavoro sequenziale</span><span class="sxs-lookup"><span data-stu-id="dcd53-102">How to: Create a Sequential Workflow</span></span>
<span data-ttu-id="dcd53-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="dcd53-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="dcd53-104">Passaggi in questo argomento per la creazione di un flusso di lavoro che utilizza entrambe le attività predefinite, ad esempio il <xref:System.Activities.Statements.Sequence> attività e le attività personalizzate dal precedente [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="dcd53-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="dcd53-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="dcd53-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcd53-106">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="dcd53-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="dcd53-107">Per completare questo argomento, è necessario prima completare [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="dcd53-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcd53-108">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="dcd53-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="dcd53-109">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dcd53-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="dcd53-110">Fare doppio clic su **NumberGuessWorkflowActivities** in **Esplora** e selezionare **Aggiungi**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="dcd53-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="dcd53-111">Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="dcd53-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="dcd53-112">Selezionare **attività** dal **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="dcd53-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="dcd53-113">Tipo `SequentialNumberGuessWorkflow` nel **nome** casella e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="dcd53-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="dcd53-114">Trascinare un **sequenza** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dcd53-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="dcd53-115">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dcd53-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="dcd53-116">Fare doppio clic su **Sequentialnumberguessworkflow** in **Esplora** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="dcd53-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="dcd53-117">Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="dcd53-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="dcd53-118">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="dcd53-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="dcd53-119">Tipo `MaxNumber` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="dcd53-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="dcd53-120">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="dcd53-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="dcd53-121">Tipo `Turns` nel **nome** casella che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** -elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="dcd53-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="dcd53-122">Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="dcd53-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="dcd53-123">Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="dcd53-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="dcd53-124">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="dcd53-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="dcd53-125">Se non **Crea variabile** viene visualizzata, fare clic su di **sequenza** attività nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="dcd53-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="dcd53-126">Tipo `Guess` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="dcd53-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="dcd53-127">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="dcd53-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="dcd53-128">Tipo `Target` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="dcd53-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="dcd53-129">Fare clic su **variabili** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="dcd53-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="dcd53-130">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dcd53-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="dcd53-131">Trascinare un **assegnare** attività dal **primitive** sezione il **della casella degli strumenti** e rilasciarla il **sequenza** attività.</span><span class="sxs-lookup"><span data-stu-id="dcd53-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="dcd53-132">Tipo `Target` nel **a** casella e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="dcd53-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="dcd53-133">Se il **della casella degli strumenti** non verrà visualizzata la finestra, selezionare **della casella degli strumenti** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="dcd53-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="dcd53-134">Trascinare un **DoWhile** attività dal **flusso di controllo** sezione il **della casella degli strumenti** e rilasciarla sul flusso di lavoro in modo che si trovi sotto il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="dcd53-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>  
  
3.  <span data-ttu-id="dcd53-135">Digitare l'espressione seguente nella **DoWhile** dell'attività **condizione** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dcd53-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <span data-ttu-id="dcd53-136">Un'attività <xref:System.Activities.Statements.DoWhile> esegue le proprie attività figlio e successivamente valuta <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="dcd53-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="dcd53-137">Se <xref:System.Activities.Statements.DoWhile.Condition%2A> dà come risultato `True`, le attività in <xref:System.Activities.Statements.DoWhile> vengono eseguite nuovamente.</span><span class="sxs-lookup"><span data-stu-id="dcd53-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="dcd53-138">In questo esempio, viene valutata l'ipotesi dell'utente e <xref:System.Activities.Statements.DoWhile> continua finché l'ipotesi non è corretta.</span><span class="sxs-lookup"><span data-stu-id="dcd53-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>  
  
4.  <span data-ttu-id="dcd53-139">Trascinare un **Prompt** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti** e rilasciarlo nel **DoWhile** attività nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="dcd53-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>  
  
5.  <span data-ttu-id="dcd53-140">Nel **finestra proprietà**, tipo `"EnterGuess"` incluse le virgolette nel **BookmarkName** casella valore della proprietà per il **Prompt** attività.</span><span class="sxs-lookup"><span data-stu-id="dcd53-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="dcd53-141">Tipo `Guess` nel **risultato** casella valore di proprietà e digitare l'espressione seguente nella **testo** casella della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dcd53-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="dcd53-142">Se il **finestra proprietà** non è visualizzata, selezionare **finestra proprietà** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="dcd53-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
6.  <span data-ttu-id="dcd53-143">Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarlo nel **DoWhile** attività in modo che segua il **Prompt** attività.</span><span class="sxs-lookup"><span data-stu-id="dcd53-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dcd53-144">Quando si trascina il **assegnare** attività, nota come finestra di progettazione del flusso di lavoro aggiunge automaticamente un **sequenza** attività per contenere sia il **Prompt** appena aggiunta e attività **Assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="dcd53-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>  
  
7.  <span data-ttu-id="dcd53-145">Tipo `Turns` nel **a** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="dcd53-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
8.  <span data-ttu-id="dcd53-146">Trascinare un **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarlo nel **sequenza** attività in modo che segua il aggiunta di **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="dcd53-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>  
  
9. <span data-ttu-id="dcd53-147">Digitare l'espressione seguente nella **se** dell'attività **condizione** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dcd53-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. <span data-ttu-id="dcd53-148">Trascinare un'altra **se** attività dal **flusso di controllo** sezione il **della casella degli strumenti** e rilasciarlo nel **quindi** sezione del primo **Se** attività.</span><span class="sxs-lookup"><span data-stu-id="dcd53-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>  
  
11. <span data-ttu-id="dcd53-149">Digitare l'espressione seguente in appena aggiunta **se** dell'attività **condizione** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dcd53-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
12. <span data-ttu-id="dcd53-150">Trascinare due **WriteLine** le attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarle in modo che uno è il **quindi** sezione di appena aggiunta **se** attività e l'altro è il **Else** sezione.</span><span class="sxs-lookup"><span data-stu-id="dcd53-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>  
  
13. <span data-ttu-id="dcd53-151">Fare clic sul **WriteLine** attività di **quindi** sezione per selezionarlo, quindi digitare l'espressione seguente nel **testo** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dcd53-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. <span data-ttu-id="dcd53-152">Fare clic sul **WriteLine** attività di **Else** sezione per selezionarlo, quindi digitare l'espressione seguente nel **testo** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dcd53-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     <span data-ttu-id="dcd53-153">Nell'esempio seguente viene illustrato il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="dcd53-153">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="dcd53-154">![Flusso di lavoro sequenza completato](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="dcd53-154">![Completed Sequential Workflow](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="dcd53-155">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dcd53-155">To build the workflow</span></span>  
  
1.  <span data-ttu-id="dcd53-156">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="dcd53-156">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="dcd53-157">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="dcd53-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="dcd53-158">Se è già stata completata la [come: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) spostarsi con uno stile diverso del flusso di lavoro e desidera eseguirlo tramite il flusso di lavoro sequenza da questo passaggio, ignorare il [per compilare ed eseguire l'applicazione](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)sezione [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="dcd53-158">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd53-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcd53-159">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="dcd53-160">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="dcd53-160">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="dcd53-161">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="dcd53-161">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="dcd53-162">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="dcd53-162">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="dcd53-163">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="dcd53-163">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="dcd53-164">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dcd53-164">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
