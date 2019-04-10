---
title: 'Procedura: Creare un flusso di lavoro della macchina a stati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 654621ab7dd74c26a7fddbd985559a713c0e9df3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294808"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="9a62b-102">Procedura: Creare un flusso di lavoro della macchina a stati</span><span class="sxs-lookup"><span data-stu-id="9a62b-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="9a62b-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9a62b-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="9a62b-104">In questo argomento illustra la creazione di un flusso di lavoro che vengono usate sia attività incorporate, ad esempio la <xref:System.Activities.Statements.StateMachine> attività e le attività personalizzate dal precedente [come: Creare un'attività](how-to-create-an-activity.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="9a62b-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="9a62b-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="9a62b-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a62b-106">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="9a62b-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="9a62b-107">Per completare questo argomento, è necessario completare prima [come: Creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="9a62b-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a62b-108">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="9a62b-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="9a62b-109">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a62b-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="9a62b-110">Fare doppio clic su **NumberGuessWorkflowActivities** nelle **Esplora soluzioni** e selezionare **Add**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="9a62b-111">Nel **Installed**, **elementi comuni** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="9a62b-112">Selezionare **impegno** dalle **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="9a62b-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="9a62b-113">Tipo di `StateMachineNumberGuessWorkflow` nella **Name** casella e fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="9a62b-114">Trascinare un **StateMachine** attività dal **macchina a stati** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="9a62b-115">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a62b-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="9a62b-116">Fare doppio clic su **Statemachinenumberguessworkflow** nelle **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="9a62b-117">Fare clic su **argomenti** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="9a62b-118">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="9a62b-119">Tipo `MaxNumber` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="9a62b-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="9a62b-120">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="9a62b-121">Tipo `Turns` nella **Name** finestra che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** dall'elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="9a62b-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="9a62b-122">Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="9a62b-123">Fare clic su **variabili** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="9a62b-124">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="9a62b-125">Se nessun **Crea variabile** verrà visualizzata la finestra, fare clic su di <xref:System.Activities.Statements.StateMachine> attività nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="9a62b-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="9a62b-126">Tipo di `Guess` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="9a62b-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="9a62b-127">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="9a62b-128">Tipo di `Target` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="9a62b-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="9a62b-129">Fare clic su **variabili** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="9a62b-130">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a62b-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="9a62b-131">Fare clic su **State1** per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="9a62b-131">Click **State1** to select it.</span></span> <span data-ttu-id="9a62b-132">Nel **finestra delle proprietà**, modificare il **DisplayName** a `Initialize Target`.</span><span class="sxs-lookup"><span data-stu-id="9a62b-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="9a62b-133">Se il **finestra delle proprietà** non è visualizzato, selezionare **finestra delle proprietà** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="9a62b-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="9a62b-134">Fare doppio clic su appena rinominata **Initialize Target** stato nella finestra di progettazione del flusso di lavoro per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="9a62b-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="9a62b-135">Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **voce** sezione dello stato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="9a62b-136">Tipo `Target` nella **al** finestra e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="9a62b-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="9a62b-137">Se il **casella degli strumenti** finestra non viene visualizzata, selezionare **della casella degli strumenti** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="9a62b-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="9a62b-138">Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="9a62b-139">Trascinare un **lo stato** attività dalle **macchina a stati** sezione del **della casella degli strumenti** nella finestra di progettazione del flusso di lavoro e passarla sul **Initialize Target** lo stato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="9a62b-140">Si noti che verranno visualizzati quattro triangoli intorno al **Initialize Target** lo stato quando il nuovo stato viene posizionato sopra di essa.</span><span class="sxs-lookup"><span data-stu-id="9a62b-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="9a62b-141">Rilasciare il nuovo stato sul triangolo che si trova immediatamente sotto il **Initialize Target** dello stato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="9a62b-142">Questo posizionare il nuovo stato sul flusso di lavoro e crea una transizione dal **Initialize Target** stato al nuovo stato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="9a62b-143">Fare clic su **State1** per selezionarlo, modificare il **DisplayName** a `Enter Guess`, quindi fare doppio clic sullo stato nella finestra di progettazione del flusso di lavoro per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="9a62b-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="9a62b-144">Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **voce** sezione dello stato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="9a62b-145">Digitare l'espressione seguente nella **testo** finestra proprietà delle **WriteLine**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="9a62b-146">Trascinare un' **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **uscita** sezione dello stato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="9a62b-147">Tipo `Turns` nella **al** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="9a62b-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="9a62b-148">Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="9a62b-149">Trascinare un **FinalState** attività dal **macchina a stati** sezione del **della casella degli strumenti**, passarla sul **Enter Guess** sullo stato, quindi rilasciarla nel triangolo che viene visualizzato a destra del **Enter Guess** lo stato in modo che una transizione viene creata tra **Enter Guess** e **FinalState**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="9a62b-150">È il nome predefinito della transizione **T2**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="9a62b-151">Fare clic sulla transizione nella finestra di progettazione del flusso di lavoro per selezionarla e impostare relativi **DisplayName** al **Guess Correct**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="9a62b-152">Quindi fare clic e selezionare il **FinalState**e trascinarla a destra in modo che ci sia spazio per il nome completo della transizione da visualizzare senza sovrapporre uno dei due stati.</span><span class="sxs-lookup"><span data-stu-id="9a62b-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="9a62b-153">Ciò faciliterà il completamento dei passaggi rimanenti nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="9a62b-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="9a62b-154">Fare doppio clic su appena rinominata **Guess Correct** transizione nella finestra di progettazione del flusso di lavoro per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="9a62b-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="9a62b-155">Trascinare un **ReadInt** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti** e rilasciarla nel **Trigger** sezione della transizione.</span><span class="sxs-lookup"><span data-stu-id="9a62b-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="9a62b-156">Nel **finestra delle proprietà** per il **ReadInt** attività, digitare `"EnterGuess"` incluse le virgolette nella **BookmarkName** finestra proprietà di valore e tipo `Guess`nel **risultato** casella del valore proprietà</span><span class="sxs-lookup"><span data-stu-id="9a62b-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="9a62b-157">Digitare l'espressione seguente nella **Guess Correct** della transizione **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="9a62b-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="9a62b-158">Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a62b-159">La transizione si verifica quando viene ricevuto un evento trigger e <xref:System.Activities.Statements.Transition.Condition%2A>, se presente, restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="9a62b-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="9a62b-160">Per questa transizione, se l'utente `Guess` corrispondente generato casualmente `Target`, quindi il controllo passa al **FinalState** e completa il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="9a62b-161">A seconda del fatto che il valore indicato è corretto, il flusso di lavoro deve eseguire la transizione al **FinalState** oppure tornare il **Enter Guess** dello stato per un altro tentativo.</span><span class="sxs-lookup"><span data-stu-id="9a62b-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="9a62b-162">Entrambe le transizioni condividono lo stesso trigger di attesa per il tentativo dell'utente sia ricevuta tramite il **ReadInt** attività.</span><span class="sxs-lookup"><span data-stu-id="9a62b-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="9a62b-163">Questa transizione è denominata transizione condivisa.</span><span class="sxs-lookup"><span data-stu-id="9a62b-163">This is called a shared transition.</span></span> <span data-ttu-id="9a62b-164">Per creare una transizione condivisa, fare clic sul cerchio che indica l'inizio del **Guess Correct** transizione e trascinarlo nello stato desiderato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="9a62b-165">In questo caso la transizione è una transizione automatica, quindi trascinare il punto iniziale del **Guess Correct** transizione e rilasciarlo indietro nella parte inferiore della **Enter Guess** dello stato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="9a62b-166">Dopo aver creato la transizione, selezionarla nella finestra di progettazione del flusso di lavoro e impostare relativi **DisplayName** proprietà **Guess Incorrect**.</span><span class="sxs-lookup"><span data-stu-id="9a62b-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a62b-167">Le transizioni condivise possono anche essere create da all'interno di progettazione della transizione facendo **Aggiungi transizione del trigger condivisa** nella parte inferiore della finestra di progettazione di transizione e quindi selezionando lo stato di destinazione desiderato dal  **Gli stati disponibili per la connessione** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9a62b-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a62b-168">Si noti che se <xref:System.Activities.Statements.Transition.Condition%2A> di una transizione restituisce `false` (o tutti gli stati di una transizione trigger condivisa restituiscono `false`), la transizione non si verificherà e tutti i trigger per tutte le transizioni dallo stato verranno rinviati.</span><span class="sxs-lookup"><span data-stu-id="9a62b-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="9a62b-169">In questa esercitazione, questa situazione non può verificarsi a causa della modalità con cui le condizioni vengono configurate (esistono azioni specifiche per verificare se il valore indicato è corretto o errato).</span><span class="sxs-lookup"><span data-stu-id="9a62b-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="9a62b-170">Fare doppio clic il **Guess Incorrect** transizione nella finestra di progettazione del flusso di lavoro per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="9a62b-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="9a62b-171">Si noti che il **Trigger** è già impostato allo stesso **ReadInt** attività che è stata utilizzata per il **Guess Correct** transizione.</span><span class="sxs-lookup"><span data-stu-id="9a62b-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="9a62b-172">Digitare l'espressione seguente nella **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="9a62b-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="9a62b-173">Trascinare un' **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla nel **azione** sezione della transizione.</span><span class="sxs-lookup"><span data-stu-id="9a62b-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="9a62b-174">Digitare l'espressione seguente nella **se** dell'attività **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="9a62b-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="9a62b-175">Trascinare due **WriteLine** le attività eseguite dal **primitive** sezione del **della casella degli strumenti** e rilasciarle in modo che uno è il **quindi** sezione di il **se** attività e l'altro è nel **Else** sezione.</span><span class="sxs-lookup"><span data-stu-id="9a62b-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="9a62b-176">Fare clic sui **WriteLine** attività nel **quindi** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="9a62b-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="9a62b-177">Fare clic sui **WriteLine** attività nel **Else** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="9a62b-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="9a62b-178">Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9a62b-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="9a62b-179">Nell'esempio seguente viene illustrato il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="9a62b-179">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="9a62b-180">![Flusso di lavoro macchina a stati completo](./media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="9a62b-180">![Completed State Machine Workflow](./media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="9a62b-181">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a62b-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="9a62b-182">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="9a62b-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="9a62b-183">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9a62b-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="9a62b-184">Se sono già state completate le [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md) passaggio con uno stile diverso del flusso di lavoro e si desidera eseguirlo tramite il lavoro macchina a stati da questo passaggio, andare direttamente al [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sezione [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9a62b-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a62b-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a62b-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="9a62b-186">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="9a62b-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="9a62b-187">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a62b-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="9a62b-188">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="9a62b-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="9a62b-189">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="9a62b-189">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="9a62b-190">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a62b-190">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
