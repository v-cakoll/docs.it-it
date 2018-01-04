---
title: 'Procedura: creare un flusso di lavoro del diagramma di flusso'
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
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b7a8eab16b089597eecc03896f86827aae1ad85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="99131-102">Procedura: creare un flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="99131-102">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="99131-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="99131-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="99131-104">Passaggi in questo argomento per la creazione di un flusso di lavoro che utilizza entrambe le attività predefinite, ad esempio il <xref:System.Activities.Statements.Flowchart> attività e le attività personalizzate dal precedente [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="99131-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="99131-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="99131-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99131-106">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="99131-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="99131-107">Per completare questo argomento, è necessario prima completare [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="99131-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99131-108">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="99131-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="99131-109">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99131-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="99131-110">Fare doppio clic su **NumberGuessWorkflowActivities** in **Esplora** e selezionare **Aggiungi**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="99131-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="99131-111">Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="99131-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="99131-112">Selezionare **attività** dal **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="99131-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="99131-113">Tipo `FlowchartNumberGuessWorkflow` nel **nome** casella e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="99131-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="99131-114">Trascinare un **diagramma di flusso** attività dal **diagramma di flusso** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99131-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="99131-115">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99131-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="99131-116">Fare doppio clic su **Flowchartnumberguessworkflow** in **Esplora** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="99131-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="99131-117">Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99131-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="99131-118">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="99131-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="99131-119">Tipo `MaxNumber` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="99131-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="99131-120">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="99131-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="99131-121">Tipo `Turns` nel **nome** casella che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** -elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="99131-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="99131-122">Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99131-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="99131-123">Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99131-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="99131-124">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="99131-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="99131-125">Se non **Crea variabile** viene visualizzata, fare clic su di <xref:System.Activities.Statements.Flowchart> attività nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="99131-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="99131-126">Tipo `Guess` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="99131-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="99131-127">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="99131-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="99131-128">Tipo `Target` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="99131-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="99131-129">Fare clic su **variabili** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99131-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="99131-130">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99131-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="99131-131">Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e passarla sul **avviare** nodo, nella parte superiore del diagramma di flusso.</span><span class="sxs-lookup"><span data-stu-id="99131-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="99131-132">Quando il **assegnare** attività è posizionato il **avviare** nodo, verranno visualizzati tre triangoli intorno il **avviare** nodo.</span><span class="sxs-lookup"><span data-stu-id="99131-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="99131-133">Eliminare il **assegnare** attività sul triangolo che si trova direttamente sotto il **avviare** nodo.</span><span class="sxs-lookup"><span data-stu-id="99131-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="99131-134">Questo verrà collegare i due elementi e designa il **assegnare** attività come la prima attività nel diagramma di flusso.</span><span class="sxs-lookup"><span data-stu-id="99131-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99131-135">È possibile designare le attività come attività iniziali nel diagramma di flusso anche collegandole manualmente al nodo iniziale.</span><span class="sxs-lookup"><span data-stu-id="99131-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="99131-136">A tale scopo, posizionare il mouse sopra il **avviare** nodo, fare clic su uno dei rettangoli visualizzati quando il mouse è posizionato il **avviare** nodo e trascinare la connessione di riga sull'attività desiderata e rilasciarla su uno di i rettangoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="99131-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="99131-137">È inoltre possibile designare e attività come attività iniziale facendo clic it e scegliendo **imposta come StartNode**.</span><span class="sxs-lookup"><span data-stu-id="99131-137">You can also designate and activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2.  <span data-ttu-id="99131-138">Tipo `Target` nel **a** casella e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="99131-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="99131-139">Se il **della casella degli strumenti** non verrà visualizzata la finestra, selezionare **della casella degli strumenti** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="99131-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="99131-140">Trascinare un **prompt dei comandi** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti**, rilasciarlo di sotto di **assegnare** attività dal precedente passaggio e collegare il **Prompt** attività per il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="99131-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="99131-141">Esistono tre modi per connettere le due attività.</span><span class="sxs-lookup"><span data-stu-id="99131-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="99131-142">La prima consiste nel connetterle quando si elimina il **Prompt** attività del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99131-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="99131-143">Mentre si trascina il **prompt dei comandi** attività al flusso di lavoro, posizionarla sopra il **assegnare** attività e rilasciarla su uno dei quattro triangoli visualizzati quando il **Prompt** attività è posizionato il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="99131-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="99131-144">Il secondo modo consiste nel rilasciare il **Prompt** attività sul flusso di lavoro nella posizione desiderata.</span><span class="sxs-lookup"><span data-stu-id="99131-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="99131-145">Quindi, posizionare il mouse sopra il **assegnare** attività e trascinare uno dei rettangoli visualizzati fino al **prompt dei comandi** attività.</span><span class="sxs-lookup"><span data-stu-id="99131-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="99131-146">Trascinare il mouse in modo che la linea di connessione dal **assegnare** attività si connette a uno dei rettangoli del **Prompt** attività e quindi rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="99131-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="99131-147">Il terzo modo è molto simile al primo, tranne il fatto che invece di trascinare il **Prompt** attività dal **della casella degli strumenti**, si trascina dalla relativa posizione nell'area di progettazione del flusso di lavoro, posizionarla sopra il  **Assegnare** , attività e rilasciarlo su uno dei triangoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="99131-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4.  <span data-ttu-id="99131-148">Nel **finestra proprietà** per il **Prompt** attività, digitare `"EnterGuess"` incluse le virgolette nel **BookmarkName** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="99131-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="99131-149">Tipo `Guess` nel **risultato** casella valore di proprietà e digitare l'espressione seguente nella **testo** casella della proprietà.</span><span class="sxs-lookup"><span data-stu-id="99131-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="99131-150">Se il **finestra proprietà** non è visualizzata, selezionare **finestra proprietà** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="99131-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="99131-151">Trascinare un **assegnare** attività dal **primitive** sezione il **della casella degli strumenti** e connetterla usando uno dei metodi descritti nel passaggio precedente, in modo che si trovi sotto il  **Prompt dei comandi** attività.</span><span class="sxs-lookup"><span data-stu-id="99131-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6.  <span data-ttu-id="99131-152">Tipo `Turns` nel **a** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="99131-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7.  <span data-ttu-id="99131-153">Trascinare un **FlowDecision** dal **diagramma di flusso** sezione il **della casella degli strumenti** e connetterla sotto il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="99131-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="99131-154">Nel **finestra proprietà**, digitare l'espressione seguente nella **condizione** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="99131-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  <span data-ttu-id="99131-155">Trascinare un'altra **FlowDecision** attività di **della casella degli strumenti** e rilasciarlo sotto il primo.</span><span class="sxs-lookup"><span data-stu-id="99131-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="99131-156">Connettere le due attività trascinando dal rettangolo con etichetta **False** in alto **FlowDecision** attività per il rettangolo nella parte superiore del secondo **FlowDecision**attività.</span><span class="sxs-lookup"><span data-stu-id="99131-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="99131-157">Se non viene visualizzato il **True** e **False** etichette del **FlowDecision**, posizionare il mouse sopra il **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="99131-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="99131-158">Fare clic sul secondo **FlowDecision** attività per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="99131-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="99131-159">Nel **finestra proprietà**, digitare l'espressione seguente nella **condizione** casella valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="99131-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
10. <span data-ttu-id="99131-160">Trascinare due **WriteLine** le attività dal **primitive** sezione la **della casella degli strumenti** e rilasciarle in modo che siano affiancate sotto le due **FlowDecision**  attività.</span><span class="sxs-lookup"><span data-stu-id="99131-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="99131-161">Connettere il **True** azione della parte inferiore **FlowDecision** attività più a sinistra **WriteLine** attività e il **False** azione per il all'estrema destra **WriteLine** attività.</span><span class="sxs-lookup"><span data-stu-id="99131-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="99131-162">Fare clic su quello all'estrema sinistra **WriteLine** attività per selezionarla e digitare l'espressione seguente nella **testo** nella casella valore della proprietà di **finestra proprietà**.</span><span class="sxs-lookup"><span data-stu-id="99131-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="99131-163">Connettere il **WriteLine** sul lato sinistro del **prompt dei comandi** attività sopra di esso.</span><span class="sxs-lookup"><span data-stu-id="99131-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="99131-164">Fare clic su all'estrema destra **WriteLine** attività per selezionarla e digitare l'espressione seguente nella **testo** nella casella valore della proprietà di **finestra proprietà**.</span><span class="sxs-lookup"><span data-stu-id="99131-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="99131-165">Connettere il **WriteLine** attività sul lato destro del **prompt dei comandi** attività sopra di esso.</span><span class="sxs-lookup"><span data-stu-id="99131-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="99131-166">Nell'esempio seguente viene illustrato il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="99131-166">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="99131-167">![Windows Workflow Foundation completato](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span><span class="sxs-lookup"><span data-stu-id="99131-167">![Completed Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="99131-168">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99131-168">To build the workflow</span></span>  
  
1.  <span data-ttu-id="99131-169">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="99131-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="99131-170">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="99131-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="99131-171">Se è già stata completata la [come: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) spostarsi con uno stile diverso del flusso di lavoro e desidera eseguirlo tramite il flusso di lavoro di diagramma di flusso tramite questo passaggio, ignorare il [per compilare ed eseguire l'applicazione](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)sezione [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="99131-171">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99131-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99131-172">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="99131-173">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="99131-173">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="99131-174">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="99131-174">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="99131-175">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="99131-175">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="99131-176">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="99131-176">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="99131-177">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99131-177">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
