---
title: 'Procedura: creare un flusso di lavoro del diagramma di flusso'
description: Questo articolo descrive la creazione di un flusso di lavoro che usa sia attività predefinite che le attività personalizzate dell'articolo precedente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 6b3fa423200f5c5cfece60f07372ce9678fc0072
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419707"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="3b860-103">Procedura: creare un flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="3b860-103">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="3b860-104">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3b860-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="3b860-105">Questo argomento illustra la creazione di un flusso di lavoro che usa sia attività predefinite, ad esempio l' <xref:System.Activities.Statements.Flowchart> attività, che le attività personalizzate dell'argomento [procedura: creare un'attività](how-to-create-an-activity.md) precedente.</span><span class="sxs-lookup"><span data-stu-id="3b860-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="3b860-106">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="3b860-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b860-107">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="3b860-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="3b860-108">Per completare questo argomento, è necessario completare prima di tutto [procedura: creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="3b860-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b860-109">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="3b860-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="3b860-110">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b860-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="3b860-111">Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowActivities** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3b860-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="3b860-112">Nel nodo **elementi comuni** **installati**selezionare **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3b860-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="3b860-113">Selezionare l'**attività** dall'elenco **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="3b860-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="3b860-114">Digitare `FlowchartNumberGuessWorkflow` nella casella **nome** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3b860-114">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="3b860-115">Trascinare un'attività **Flowchart** dalla sezione **diagramma** di flusso della **casella degli strumenti** e rilasciarla sull'etichetta **rilasciare l'attività** nell'area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b860-115">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="3b860-116">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b860-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="3b860-117">Fare doppio clic su **FlowchartNumberGuessWorkflow. XAML** in **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3b860-117">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="3b860-118">Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **argomenti** .</span><span class="sxs-lookup"><span data-stu-id="3b860-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="3b860-119">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="3b860-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="3b860-120">Digitare `MaxNumber` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **Int32** dall'elenco a discesa tipo di **argomento** , quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="3b860-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="3b860-121">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="3b860-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="3b860-122">Digitare `Turns` nella casella **nome** che si trova sotto l'argomento appena aggiunto `MaxNumber` , selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="3b860-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="3b860-123">Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Argomenti**.</span><span class="sxs-lookup"><span data-stu-id="3b860-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="3b860-124">Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **variabili** .</span><span class="sxs-lookup"><span data-stu-id="3b860-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="3b860-125">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="3b860-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="3b860-126">Se non viene visualizzata la casella **Crea variabile** , fare clic sull' <xref:System.Activities.Statements.Flowchart> attività nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="3b860-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="3b860-127">Digitare `Guess` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="3b860-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="3b860-128">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="3b860-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="3b860-129">Digitare `Target` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="3b860-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="3b860-130">Fare clic su **Variabili** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Variabili**.</span><span class="sxs-lookup"><span data-stu-id="3b860-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="3b860-131">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b860-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="3b860-132">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e posizionarla sul nodo **iniziale** , che si trova nella parte superiore del diagramma di flusso.</span><span class="sxs-lookup"><span data-stu-id="3b860-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="3b860-133">Quando l'attività **assign** è sul nodo **iniziale** , vengono visualizzati tre triangoli intorno al nodo **iniziale** .</span><span class="sxs-lookup"><span data-stu-id="3b860-133">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="3b860-134">Rilasciare l'attività **assign** sul triangolo che si trova direttamente sotto il nodo **iniziale** .</span><span class="sxs-lookup"><span data-stu-id="3b860-134">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="3b860-135">In questo modo i due elementi vengono collegati insieme e l'attività **assign** viene designata come prima attività del diagramma di flusso.</span><span class="sxs-lookup"><span data-stu-id="3b860-135">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3b860-136">È possibile designare le attività come attività iniziali nel diagramma di flusso anche collegandole manualmente al nodo iniziale.</span><span class="sxs-lookup"><span data-stu-id="3b860-136">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="3b860-137">A tale scopo, passare il puntatore del mouse sul nodo **iniziale** , fare clic su uno dei rettangoli visualizzati quando il mouse si trova sul nodo **iniziale** e trascinare la linea di connessione fino all'attività desiderata e rilasciarla su uno dei rettangoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="3b860-137">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="3b860-138">È anche possibile designare un'attività come attività iniziale facendo clic con il pulsante destro del mouse su di essa e scegliendo **Imposta come nodo iniziale**.</span><span class="sxs-lookup"><span data-stu-id="3b860-138">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="3b860-139">Digitare `Target` nella casella **a** e l'espressione seguente nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="3b860-139">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="3b860-140">Se la finestra **Casella degli strumenti** non è visualizzata, selezionare **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="3b860-140">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="3b860-141">Trascinare un'attività **prompt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti**, rilasciarla sotto l'attività **assign** del passaggio precedente e connettere l'attività **prompt** all'attività **assign** .</span><span class="sxs-lookup"><span data-stu-id="3b860-141">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="3b860-142">Esistono tre modi per connettere le due attività.</span><span class="sxs-lookup"><span data-stu-id="3b860-142">There are three ways to connect the two activities.</span></span> <span data-ttu-id="3b860-143">Il primo consiste nel connetterli quando si rilascia l'attività **prompt** sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b860-143">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="3b860-144">Quando si trascina l'attività **prompt** sul flusso di lavoro, passare il mouse sull'attività **assign** e rilasciarla su uno dei quattro triangoli visualizzati quando l'attività **prompt** è sull'attività **assign** .</span><span class="sxs-lookup"><span data-stu-id="3b860-144">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="3b860-145">Il secondo modo consiste nell'eliminare l'attività **prompt** sul flusso di lavoro nella posizione desiderata.</span><span class="sxs-lookup"><span data-stu-id="3b860-145">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="3b860-146">Posizionare quindi il puntatore del mouse sull'attività **assign** e trascinare uno dei rettangoli visualizzati fino all'attività **prompt** .</span><span class="sxs-lookup"><span data-stu-id="3b860-146">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="3b860-147">Trascinare il mouse in modo che la linea di connessione dall'attività **assign** si connetta a uno dei rettangoli dell'attività **prompt** , quindi rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="3b860-147">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="3b860-148">Il terzo modo è molto simile al primo, ad eccezione del fatto che anziché trascinare l'attività **prompt** dalla **casella degli strumenti**, trascinarla dalla relativa posizione nell'area di progettazione del flusso di lavoro, posizionarla sull'attività **assign** e rilasciarla su uno dei triangoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="3b860-148">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="3b860-149">Nella **finestra Proprietà** per l'attività **prompt** digitare, `"EnterGuess"` incluse le virgolette, nella casella del valore della proprietà **BookmarkName** .</span><span class="sxs-lookup"><span data-stu-id="3b860-149">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="3b860-150">Digitare `Guess` nella casella valore proprietà **risultato** e digitare l'espressione seguente nella casella della proprietà **testo** .</span><span class="sxs-lookup"><span data-stu-id="3b860-150">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="3b860-151">Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="3b860-151">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="3b860-152">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e connetterla usando uno dei metodi descritti nel passaggio precedente, in modo che si trovi sotto l'attività **prompt** .</span><span class="sxs-lookup"><span data-stu-id="3b860-152">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="3b860-153">Digitare `Turns` nella casella **a** e `Turns + 1` nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="3b860-153">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="3b860-154">Trascinare un **FlowDecision** dalla sezione **diagramma di flusso** della **casella degli strumenti** e connetterlo sotto l'attività **assign** .</span><span class="sxs-lookup"><span data-stu-id="3b860-154">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="3b860-155">Nella **finestra Proprietà**Digitare l'espressione seguente nella casella valore proprietà **condizione** .</span><span class="sxs-lookup"><span data-stu-id="3b860-155">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="3b860-156">Trascinare un'altra attività **FlowDecision** dalla **casella degli strumenti** e rilasciarla sotto la prima.</span><span class="sxs-lookup"><span data-stu-id="3b860-156">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="3b860-157">Connettere le due attività trascinando dal rettangolo con etichetta **false** nella parte superiore dell'attività **FlowDecision** al rettangolo nella parte superiore della seconda attività **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="3b860-157">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="3b860-158">Se non vengono visualizzate le etichette **true** e **false** in **FlowDecision**, passare il puntatore del mouse sul **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="3b860-158">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="3b860-159">Fare clic sulla seconda attività **FlowDecision** per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="3b860-159">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="3b860-160">Nella **finestra Proprietà**Digitare l'espressione seguente nella casella valore proprietà **condizione** .</span><span class="sxs-lookup"><span data-stu-id="3b860-160">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="3b860-161">Trascinare due attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarle in modo che siano affiancate al di sotto delle due attività **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="3b860-161">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="3b860-162">Connettere la **vera** azione dell'attività **FlowDecision** inferiore all'attività **WriteLine** più a sinistra e l'azione **false** all'attività **WriteLine** più a destra.</span><span class="sxs-lookup"><span data-stu-id="3b860-162">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="3b860-163">Fare clic sull'attività **WriteLine** più a sinistra per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** nella **finestra Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3b860-163">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="3b860-164">Connettere il **WriteLine** al lato sinistro dell'attività **prompt** sopra.</span><span class="sxs-lookup"><span data-stu-id="3b860-164">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="3b860-165">Fare clic sull'attività **WriteLine** più a destra per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** nella **finestra Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3b860-165">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="3b860-166">Connettere l'attività **WriteLine** al lato destro dell'attività **prompt** sopra.</span><span class="sxs-lookup"><span data-stu-id="3b860-166">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="3b860-167">Nell'esempio seguente viene illustrato il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="3b860-167">The following example illustrates the completed workflow.</span></span>  
  
     ![Diagramma che mostra un diagramma di flusso Windows Workflow Foundation completato.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="3b860-169">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b860-169">To build the workflow</span></span>  
  
1. <span data-ttu-id="3b860-170">Premere CTRL+MAIUSC+B per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="3b860-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="3b860-171">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="3b860-171">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="3b860-172">Se è già stato completato il passaggio [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md) con uno stile di flusso di lavoro diverso e si desidera eseguirlo tramite il flusso di lavoro diagramma di flusso da questo passaggio, passare alla sezione [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) di [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="3b860-172">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b860-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b860-173">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="3b860-174">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="3b860-174">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="3b860-175">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b860-175">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="3b860-176">Esercitazione Introduzione</span><span class="sxs-lookup"><span data-stu-id="3b860-176">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="3b860-177">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="3b860-177">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="3b860-178">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b860-178">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
