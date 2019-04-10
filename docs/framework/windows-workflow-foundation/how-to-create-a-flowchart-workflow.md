---
title: 'Procedura: Creare un flusso di lavoro del diagramma di flusso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 15cf94d5ea191435723f754f35e43d65632142e2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311201"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="fe379-102">Procedura: Creare un flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="fe379-102">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="fe379-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="fe379-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="fe379-104">In questo argomento illustra la creazione di un flusso di lavoro che vengono usate sia attività incorporate, ad esempio la <xref:System.Activities.Statements.Flowchart> attività e le attività personalizzate dal precedente [come: Creare un'attività](how-to-create-an-activity.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="fe379-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="fe379-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="fe379-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe379-106">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="fe379-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="fe379-107">Per completare questo argomento, è necessario completare prima [come: Creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="fe379-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe379-108">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="fe379-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="fe379-109">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe379-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="fe379-110">Fare doppio clic su **NumberGuessWorkflowActivities** nelle **Esplora soluzioni** e selezionare **Add**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fe379-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="fe379-111">Nel **Installed**, **elementi comuni** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="fe379-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="fe379-112">Selezionare **impegno** dalle **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="fe379-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="fe379-113">Tipo di `FlowchartNumberGuessWorkflow` nella **Name** casella e fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="fe379-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="fe379-114">Trascinare un **diagramma di flusso** attività dal **diagramma di flusso** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe379-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="fe379-115">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe379-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="fe379-116">Fare doppio clic su **Flowchartnumberguessworkflow** nelle **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="fe379-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="fe379-117">Fare clic su **argomenti** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="fe379-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="fe379-118">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="fe379-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="fe379-119">Tipo `MaxNumber` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="fe379-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="fe379-120">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="fe379-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="fe379-121">Tipo `Turns` nella **Name** finestra che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** dall'elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="fe379-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="fe379-122">Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="fe379-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="fe379-123">Fare clic su **variabili** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="fe379-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="fe379-124">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="fe379-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="fe379-125">Se nessun **Crea variabile** verrà visualizzata la finestra, fare clic su di <xref:System.Activities.Statements.Flowchart> attività nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="fe379-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="fe379-126">Tipo di `Guess` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="fe379-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="fe379-127">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="fe379-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="fe379-128">Tipo di `Target` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="fe379-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="fe379-129">Fare clic su **variabili** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="fe379-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="fe379-130">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe379-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="fe379-131">Trascinare un' **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e passarla sul **avviare** nodo, ovvero all'inizio del diagramma di flusso.</span><span class="sxs-lookup"><span data-stu-id="fe379-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="fe379-132">Quando la **assegnare** attività è posizionato sulle **avviare** nodo, verranno visualizzati tre triangoli intorno al **avviare** nodo.</span><span class="sxs-lookup"><span data-stu-id="fe379-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="fe379-133">Eliminare il **assegnare** attività sul triangolo che si trova direttamente sotto il **avviare** nodo.</span><span class="sxs-lookup"><span data-stu-id="fe379-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="fe379-134">Questo verrà collegare i due elementi e designa il **assegnare** attività come la prima attività nel diagramma di flusso.</span><span class="sxs-lookup"><span data-stu-id="fe379-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe379-135">È possibile designare le attività come attività iniziali nel diagramma di flusso anche collegandole manualmente al nodo iniziale.</span><span class="sxs-lookup"><span data-stu-id="fe379-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="fe379-136">A tale scopo, posizionare il mouse sopra il **avviare** nodo, fare clic su uno dei rettangoli visualizzati quando il mouse è posizionato sopra il **avviare** nodo e quindi trascinare la connessione di riga sull'attività desiderata e rilasciarla su uno dei i rettangoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="fe379-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="fe379-137">È inoltre possibile specificare un'attività come attività iniziale facendo clic su it e scegliendo **imposta come StartNode**.</span><span class="sxs-lookup"><span data-stu-id="fe379-137">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="fe379-138">Tipo `Target` nella **al** finestra e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="fe379-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="fe379-139">Se il **casella degli strumenti** finestra non viene visualizzata, selezionare **della casella degli strumenti** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="fe379-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="fe379-140">Trascinare un **dei messaggi di richiesta** attività dalle **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti**, rilasciarla sotto il **assegnare** attività dal precedente passaggio e connettere il **dei messaggi di richiesta** attività per il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="fe379-141">Esistono tre modi per connettere le due attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="fe379-142">Il primo modo consiste nel connetterle quando si rilascia il **dei messaggi di richiesta** attività del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe379-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="fe379-143">Mentre si trascina il **dei messaggi di richiesta** attività al flusso di lavoro, passarlo sulle **assegnare** attività e rilasciarlo su uno dei quattro triangoli visualizzati quando il **Prompt** attività è tramite il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="fe379-144">Il secondo modo consiste nell'eliminare la **dei messaggi di richiesta** attività sul flusso di lavoro nella posizione desiderata.</span><span class="sxs-lookup"><span data-stu-id="fe379-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="fe379-145">Quindi, posizionare il mouse sopra il **assegnare** attività e trascinare uno dei rettangoli visualizzati fino al **dei messaggi di richiesta** attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="fe379-146">Trascinare il puntatore del mouse in modo che la linea di connessione dal **assegnare** attività si connette a uno dei rettangoli delle **dei messaggi di richiesta** attività e quindi rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="fe379-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="fe379-147">Il terzo modo è molto simile al primo modo, con la differenza che invece di trascinare il **dei messaggi di richiesta** attività dalle **della casella degli strumenti**, si trascina dalla relativa posizione nell'area di progettazione del flusso di lavoro, passarlo sul  **Assegnare** attività e rilasciarlo su uno dei triangoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="fe379-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="fe379-148">Nel **finestra delle proprietà** per il **dei messaggi di richiesta** attività, digitare `"EnterGuess"` incluse le virgolette nella **BookmarkName** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="fe379-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="fe379-149">Tipo di `Guess` nella **risultato** casella del valore proprietà e digitare l'espressione seguente nella **testo** finestra delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="fe379-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="fe379-150">Se il **finestra delle proprietà** non è visualizzato, selezionare **finestra delle proprietà** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="fe379-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="fe379-151">Trascinare un' **assegnare** attività dalle **primitive** sezione del **della casella degli strumenti** e connetterla usando uno dei metodi descritti nel passaggio precedente in modo che si trovi sotto il  **Messaggio di richiesta** attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="fe379-152">Tipo `Turns` nella **al** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="fe379-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="fe379-153">Trascinare un **FlowDecision** dalle **diagramma di flusso** sezione del **della casella degli strumenti** e connetterla sotto il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="fe379-154">Nel **finestra delle proprietà**, digitare l'espressione seguente nella **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="fe379-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="fe379-155">Trascinare un'altra **FlowDecision** attività dalle **della casella degli strumenti** e rilasciarlo sotto il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="fe379-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="fe379-156">Connettere le due attività trascinando dal rettangolo con etichetta **False** in alto **FlowDecision** attività per il rettangolo nella parte superiore della seconda **FlowDecision**attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="fe379-157">Se non viene visualizzato il **True** e **False** etichette nel **FlowDecision**, posizionare il mouse sopra il **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="fe379-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="fe379-158">Fare clic sul secondo **FlowDecision** attività per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="fe379-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="fe379-159">Nel **finestra delle proprietà**, digitare l'espressione seguente nella **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="fe379-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
10. <span data-ttu-id="fe379-160">Trascinare due **WriteLine** le attività eseguite dal **primitive** sezione la **della casella degli strumenti** e rilasciarle in modo che siano affiancate sotto le due **FlowDecision**  attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="fe379-161">Connettere il **True** azione della parte inferiore **FlowDecision** attività più a sinistra **WriteLine** attività e il **False** azione per il all'estrema destra **WriteLine** attività.</span><span class="sxs-lookup"><span data-stu-id="fe379-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="fe379-162">Fare clic su più a sinistra **WriteLine** attività per selezionarla e digitare l'espressione seguente nel **testo** casella di valore della proprietà di **finestra proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fe379-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="fe379-163">Connettere il **WriteLine** a sinistra del **dei messaggi di richiesta** attività che si trova.</span><span class="sxs-lookup"><span data-stu-id="fe379-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="fe379-164">Fare clic all'estrema destra **WriteLine** attività per selezionarla e digitare l'espressione seguente nella **testo** casella di valore della proprietà il **finestra proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fe379-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="fe379-165">Connettere il **WriteLine** attività sul lato destro delle **dei messaggi di richiesta** attività sopra di esso.</span><span class="sxs-lookup"><span data-stu-id="fe379-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="fe379-166">Nell'esempio seguente viene illustrato il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="fe379-166">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="fe379-167">![Windows Workflow Foundation completato](./media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span><span class="sxs-lookup"><span data-stu-id="fe379-167">![Completed Windows Workflow Foundation](./media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="fe379-168">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe379-168">To build the workflow</span></span>  
  
1. <span data-ttu-id="fe379-169">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="fe379-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="fe379-170">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="fe379-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="fe379-171">Se sono già state completate le [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md) passaggio con uno stile diverso del flusso di lavoro e si desidera eseguirlo tramite il flusso di lavoro del diagramma di flusso da questo passaggio, andare direttamente al [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sezione [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="fe379-171">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe379-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe379-172">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="fe379-173">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="fe379-173">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="fe379-174">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe379-174">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="fe379-175">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="fe379-175">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="fe379-176">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="fe379-176">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="fe379-177">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe379-177">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
