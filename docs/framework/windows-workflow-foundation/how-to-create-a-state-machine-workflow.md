---
title: 'Procedura: Creare un flusso di lavoro della macchina a stati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 451f9581ae997ad86fee968fa978713db2049455
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044393"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="760e3-102">Procedura: Creare un flusso di lavoro della macchina a stati</span><span class="sxs-lookup"><span data-stu-id="760e3-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="760e3-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="760e3-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="760e3-104">Questo argomento illustra la creazione di un flusso di lavoro che usa sia attività predefinite, ad <xref:System.Activities.Statements.StateMachine> esempio l'attività, che le attività personalizzate della [procedura precedente: Creare un argomento](how-to-create-an-activity.md) di attività.</span><span class="sxs-lookup"><span data-stu-id="760e3-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="760e3-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="760e3-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="760e3-106">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="760e3-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="760e3-107">Per completare questo argomento, è necessario completare [prima di tutto come: Creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="760e3-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="760e3-108">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="760e3-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="760e3-109">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="760e3-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="760e3-110">Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowActivities** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="760e3-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="760e3-111">Nel nodo **elementi comuni** **installati**selezionare **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="760e3-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="760e3-112">Selezionare **attività** dall'elenco **flusso di lavoro** .</span><span class="sxs-lookup"><span data-stu-id="760e3-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="760e3-113">Digitare `StateMachineNumberGuessWorkflow` nella casella **nome** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="760e3-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="760e3-114">Trascinare un'attività **StateMachine** dalla sezione **macchina a stati** della **casella degli strumenti** e rilasciarla sull'etichetta rilasciare l' **attività** nell'area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="760e3-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="760e3-115">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="760e3-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="760e3-116">Fare doppio clic su **StateMachineNumberGuessWorkflow. XAML** in **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="760e3-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="760e3-117">Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **argomenti** .</span><span class="sxs-lookup"><span data-stu-id="760e3-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="760e3-118">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="760e3-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="760e3-119">Digitare `MaxNumber` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **Int32** dall'elenco a discesa tipo di **argomento** , quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="760e3-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="760e3-120">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="760e3-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="760e3-121">Digitare `Turns` nella casella **nome** che si trova sotto l'argomento appena `MaxNumber` aggiunto, selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="760e3-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="760e3-122">Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere il riquadro **argomenti** .</span><span class="sxs-lookup"><span data-stu-id="760e3-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="760e3-123">Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **variabili** .</span><span class="sxs-lookup"><span data-stu-id="760e3-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="760e3-124">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="760e3-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="760e3-125">Se non viene visualizzata la casella **Crea variabile** , fare <xref:System.Activities.Statements.StateMachine> clic sull'attività nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="760e3-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="760e3-126">Digitare `Guess` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="760e3-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="760e3-127">Fare clic su **Crea variabile**.</span><span class="sxs-lookup"><span data-stu-id="760e3-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="760e3-128">Digitare `Target` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="760e3-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="760e3-129">Fare clic su **variabili** nel lato inferiore sinistro dell'ActivityDesigner per chiudere il riquadro **variabili** .</span><span class="sxs-lookup"><span data-stu-id="760e3-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="760e3-130">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="760e3-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="760e3-131">Fare clic su **state1** per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="760e3-131">Click **State1** to select it.</span></span> <span data-ttu-id="760e3-132">Nella **finestra Proprietà**modificare `Initialize Target` **DisplayName** in.</span><span class="sxs-lookup"><span data-stu-id="760e3-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="760e3-133">Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="760e3-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="760e3-134">Fare doppio clic sullo stato **Initialize Target** appena rinominato nella finestra di progettazione del flusso di lavoro per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="760e3-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="760e3-135">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nella sezione **entry** dello stato.</span><span class="sxs-lookup"><span data-stu-id="760e3-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="760e3-136">Digitare `Target` nella casella **a** e l'espressione seguente nella casella **immettere un' C# espressione** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="760e3-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="760e3-137">Se la finestra **casella degli strumenti** non è visualizzata, scegliere **casella degli strumenti** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="760e3-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="760e3-138">Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="760e3-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="760e3-139">Trascinare un'attività **stato** dalla sezione **macchina a stati** della **casella degli strumenti** nella finestra di progettazione del flusso di lavoro e posizionarla sullo stato di destinazione dell' **inizializzazione** .</span><span class="sxs-lookup"><span data-stu-id="760e3-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="760e3-140">Si noti che quattro triangoli verranno visualizzati intorno allo stato di inizializzazione della **destinazione** quando il nuovo stato si trova su di esso.</span><span class="sxs-lookup"><span data-stu-id="760e3-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="760e3-141">Rilasciare il nuovo stato sul triangolo immediatamente sotto lo stato di inizializzazione della **destinazione** .</span><span class="sxs-lookup"><span data-stu-id="760e3-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="760e3-142">In questo modo il nuovo stato viene posizionato sul flusso di lavoro e viene creata una transizione dallo stato di **destinazione** dell'inizializzazione al nuovo stato.</span><span class="sxs-lookup"><span data-stu-id="760e3-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="760e3-143">Fare clic su **state1** per selezionarlo, impostare DisplayName `Enter Guess`su, quindi fare doppio clic sullo stato nella finestra di progettazione del flusso di lavoro per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="760e3-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="760e3-144">Trascinare un'attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nella sezione **entry** dello stato.</span><span class="sxs-lookup"><span data-stu-id="760e3-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="760e3-145">Digitare l'espressione seguente nella casella della proprietà **Text** di **WriteLine**.</span><span class="sxs-lookup"><span data-stu-id="760e3-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="760e3-146">Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nella sezione **uscita** dello stato.</span><span class="sxs-lookup"><span data-stu-id="760e3-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="760e3-147">Digitare `Turns` nella casella **a** e `Turns + 1` nella casella **immettere un' C# espressione** o **immettere un'espressione VB** .</span><span class="sxs-lookup"><span data-stu-id="760e3-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="760e3-148">Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="760e3-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="760e3-149">Trascinare un'attività **FinalState** dalla sezione **macchina a stati** della **casella degli strumenti**, posizionarla sopra lo stato **Enter Guess** e rilasciarla sul triangolo visualizzato a destra dello stato **Enter Guess** in modo che una transizione sia creato tra **Enter Guess** e **FinalState**.</span><span class="sxs-lookup"><span data-stu-id="760e3-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="760e3-150">Il nome predefinito della transizione è **T2**.</span><span class="sxs-lookup"><span data-stu-id="760e3-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="760e3-151">Fare clic sulla transizione nella finestra di progettazione del flusso di lavoro per selezionarla e impostare il relativo **DisplayName** su **Guess Correct**.</span><span class="sxs-lookup"><span data-stu-id="760e3-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="760e3-152">Quindi fare clic e selezionare il **FinalState**e trascinarlo a destra in modo che sia disponibile spazio per il nome di transizione completo da visualizzare senza sovrapporre uno dei due Stati.</span><span class="sxs-lookup"><span data-stu-id="760e3-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="760e3-153">Ciò faciliterà il completamento dei passaggi rimanenti nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="760e3-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="760e3-154">Fare doppio clic sulla transizione **Guess Correct** appena rinominata nella finestra di progettazione del flusso di lavoro per espanderla.</span><span class="sxs-lookup"><span data-stu-id="760e3-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="760e3-155">Trascinare un'attività **ReadInt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti** e rilasciarla nella sezione **trigger** della transizione.</span><span class="sxs-lookup"><span data-stu-id="760e3-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="760e3-156">Nella **finestra Proprietà** per l'attività **ReadInt** `"EnterGuess"` , digitare, incluse le virgolette, nella casella del valore della proprietà BookmarkName `Guess` e digitare nella casella valore proprietà **risultato**</span><span class="sxs-lookup"><span data-stu-id="760e3-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="760e3-157">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** della transizione **Guess Correct** .</span><span class="sxs-lookup"><span data-stu-id="760e3-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="760e3-158">Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="760e3-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="760e3-159">La transizione si verifica quando viene ricevuto un evento trigger e <xref:System.Activities.Statements.Transition.Condition%2A>, se presente, restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="760e3-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="760e3-160">Per questa transizione, se l'utente `Guess` corrisponde a generato `Target`in modo casuale, il controllo passa a **FinalState** e il flusso di lavoro viene completato.</span><span class="sxs-lookup"><span data-stu-id="760e3-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="760e3-161">A seconda del fatto che l'ipotesi sia corretta, il flusso di lavoro deve eseguire la transizione a **FinalState** o di nuovo allo stato **Enter Guess** per un altro tentativo.</span><span class="sxs-lookup"><span data-stu-id="760e3-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="760e3-162">Entrambe le transizioni condividono lo stesso trigger di attesa per la ricezione dell'ipotesi dell'utente tramite l'attività **ReadInt** .</span><span class="sxs-lookup"><span data-stu-id="760e3-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="760e3-163">Questa transizione è denominata transizione condivisa.</span><span class="sxs-lookup"><span data-stu-id="760e3-163">This is called a shared transition.</span></span> <span data-ttu-id="760e3-164">Per creare una transizione condivisa, fare clic sul cerchio che indica l'inizio della transizione **Guess Correct** e trascinarlo nello stato desiderato.</span><span class="sxs-lookup"><span data-stu-id="760e3-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="760e3-165">In questo caso la transizione è una transizione automatica, quindi trascinare il punto iniziale della transizione **Guess Correct** e rilasciarlo nella parte inferiore dello stato **Enter Guess** .</span><span class="sxs-lookup"><span data-stu-id="760e3-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="760e3-166">Dopo aver creato la transizione, selezionarla nella finestra di progettazione del flusso di lavoro e impostarne la proprietà **DisplayName** su **Guess uncorrect**.</span><span class="sxs-lookup"><span data-stu-id="760e3-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="760e3-167">È anche possibile creare transizioni condivise dall'interno della finestra di progettazione della transizione facendo clic su **Aggiungi transizione del trigger condiviso** nella parte inferiore della finestra di progettazione della transizione e quindi selezionando lo stato di destinazione desiderato dagli **stati disponibili per la connessione** . elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="760e3-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="760e3-168">Si noti che se <xref:System.Activities.Statements.Transition.Condition%2A> di una transizione restituisce `false` (o tutti gli stati di una transizione trigger condivisa restituiscono `false`), la transizione non si verificherà e tutti i trigger per tutte le transizioni dallo stato verranno rinviati.</span><span class="sxs-lookup"><span data-stu-id="760e3-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="760e3-169">In questa esercitazione, questa situazione non può verificarsi a causa della modalità con cui le condizioni vengono configurate (esistono azioni specifiche per verificare se il valore indicato è corretto o errato).</span><span class="sxs-lookup"><span data-stu-id="760e3-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="760e3-170">Fare doppio clic sulla transizione Guess errata nella finestra di progettazione del flusso di lavoro per espanderla.</span><span class="sxs-lookup"><span data-stu-id="760e3-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="760e3-171">Si noti che il **trigger** è già impostato sulla stessa attività **ReadInt** utilizzata dalla transizione Guess **Correct** .</span><span class="sxs-lookup"><span data-stu-id="760e3-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="760e3-172">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** .</span><span class="sxs-lookup"><span data-stu-id="760e3-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="760e3-173">Trascinare un'attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nella sezione **azione** della transizione.</span><span class="sxs-lookup"><span data-stu-id="760e3-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="760e3-174">Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** .</span><span class="sxs-lookup"><span data-stu-id="760e3-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="760e3-175">Trascinare due attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarle in modo che una si trovi nella sezione **then** dell'attività **if** e una si trovi nella sezione **else** .</span><span class="sxs-lookup"><span data-stu-id="760e3-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="760e3-176">Fare clic sull'attività **WriteLine** nella sezione **then** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .</span><span class="sxs-lookup"><span data-stu-id="760e3-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="760e3-177">Fare clic sull'attività **WriteLine** nella sezione **else** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .</span><span class="sxs-lookup"><span data-stu-id="760e3-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="760e3-178">Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="760e3-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="760e3-179">Nell'esempio seguente viene illustrato il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="760e3-179">The following example illustrates the completed workflow.</span></span>  
  
     ![Illustrazione che mostra il flusso di lavoro della macchina a stati completato.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="760e3-181">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="760e3-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="760e3-182">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="760e3-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="760e3-183">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [procedura: Eseguire un flusso](how-to-run-a-workflow.md)di lavoro.</span><span class="sxs-lookup"><span data-stu-id="760e3-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="760e3-184">Se è già stata completata la [procedura: Eseguire un passaggio](how-to-run-a-workflow.md) del flusso di lavoro con uno stile di flusso di lavoro diverso e desidera eseguirlo tramite il flusso di lavoro della macchina a stati da questo passaggio, passare alla sezione [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) di [procedura: Eseguire un flusso](how-to-run-a-workflow.md)di lavoro.</span><span class="sxs-lookup"><span data-stu-id="760e3-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760e3-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="760e3-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="760e3-186">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="760e3-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="760e3-187">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="760e3-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="760e3-188">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="760e3-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="760e3-189">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="760e3-189">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="760e3-190">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="760e3-190">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
