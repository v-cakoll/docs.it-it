---
title: "Procedura: creare un'attività"
description: 'Questo articolo illustra come creare due attività in Workflow Foundation: una che usa il codice per implementare la logica e una definita tramite altre attività.'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: dae099d102b0c85d09a1ef8bcce56e8a9096bd20
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419590"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="c8344-103">Procedura: creare un'attività</span><span class="sxs-lookup"><span data-stu-id="c8344-103">How to: Create an Activity</span></span>

<span data-ttu-id="c8344-104">Le attività sono l'unità principale del comportamento in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8344-104">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="c8344-105">La logica di esecuzione di un'attività può essere implementata nel codice gestito oppure tramite altre attività.</span><span class="sxs-lookup"><span data-stu-id="c8344-105">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="c8344-106">In questo argomento viene illustrato come creare due attività.</span><span class="sxs-lookup"><span data-stu-id="c8344-106">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="c8344-107">La prima è un'attività semplice che usa il codice per implementare la propria logica di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c8344-107">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="c8344-108">L'implementazione della seconda attività viene definita tramite altre attività.</span><span class="sxs-lookup"><span data-stu-id="c8344-108">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="c8344-109">Queste attività vengono usate nei seguenti passaggi dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="c8344-109">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="c8344-110">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="c8344-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="c8344-111">Creare il progetto di libreria di attività</span><span class="sxs-lookup"><span data-stu-id="c8344-111">Create the activity library project</span></span>

1. <span data-ttu-id="c8344-112">Aprire Visual Studio e scegliere **nuovo**  >  **progetto** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="c8344-112">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="c8344-113">Nella finestra di dialogo **nuovo progetto** , sotto la categoria **installato** , selezionare flusso di lavoro di **Visual C#**  >  **Workflow** (o **Visual Basic**  >  **flusso di lavoro**).</span><span class="sxs-lookup"><span data-stu-id="c8344-113">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c8344-114">Se non viene visualizzata la categoria del modello di **flusso di lavoro** , potrebbe essere necessario installare il componente **Windows Workflow Foundation** di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8344-114">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="c8344-115">Scegliere il collegamento **apri programma di installazione di Visual Studio** sulla parte sinistra della finestra di dialogo **nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="c8344-115">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="c8344-116">In Programma di installazione di Visual Studio selezionare la scheda **singoli componenti** . Quindi, nella categoria **attività di sviluppo** selezionare il componente **Windows Workflow Foundation** .</span><span class="sxs-lookup"><span data-stu-id="c8344-116">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="c8344-117">Scegliere **modifica** per installare il componente.</span><span class="sxs-lookup"><span data-stu-id="c8344-117">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="c8344-118">Selezionare il modello di progetto **libreria attività** .</span><span class="sxs-lookup"><span data-stu-id="c8344-118">Select the **Activity Library** project template.</span></span> <span data-ttu-id="c8344-119">Digitare `NumberGuessWorkflowActivities` nella casella **Nome** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8344-119">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="c8344-120">Fare clic con il pulsante destro del mouse su **Activity1.xaml** in **Esplora soluzioni** e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c8344-120">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="c8344-121">Fare clic su **OK** per confermare.</span><span class="sxs-lookup"><span data-stu-id="c8344-121">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="c8344-122">Creare l'attività ReadInt</span><span class="sxs-lookup"><span data-stu-id="c8344-122">Create the ReadInt activity</span></span>

1. <span data-ttu-id="c8344-123">Scegliere **Aggiungi nuovo elemento** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="c8344-123">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="c8344-124">Nel nodo **Installed**  >  **elementi comuni** installati selezionare flusso di **lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c8344-124">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="c8344-125">Selezionare **attività codice** dall'elenco **flusso di lavoro** .</span><span class="sxs-lookup"><span data-stu-id="c8344-125">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="c8344-126">Digitare `ReadInt` nella casella **Nome** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c8344-126">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="c8344-127">Sostituire la definizione dell'attività `ReadInt` esistente con la definizione seguente.</span><span class="sxs-lookup"><span data-stu-id="c8344-127">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="c8344-128">L'attività `ReadInt` deriva da <xref:System.Activities.NativeActivity%601> anziché <xref:System.Activities.CodeActivity>, che è l'attività predefinita per il modello di attività codice.</span><span class="sxs-lookup"><span data-stu-id="c8344-128">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="c8344-129">L'oggetto <xref:System.Activities.CodeActivity%601> può essere usato se l'attività fornisce un singolo risultato, che viene esposto tramite l'argomento <xref:System.Activities.Activity%601.Result%2A>, ma <xref:System.Activities.CodeActivity%601> non supporta l'uso dei segnalibri, quindi viene usato l'oggetto <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="c8344-129"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="c8344-130">Creare l'attività prompt</span><span class="sxs-lookup"><span data-stu-id="c8344-130">Create the Prompt activity</span></span>

1. <span data-ttu-id="c8344-131">Premere **CTRL** + **MAIUSC** + **B** per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="c8344-131">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="c8344-132">Nella compilazione del progetto, l'attività `ReadInt` in questo progetto può essere usata per compilare l'attività personalizzata tramite questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="c8344-132">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="c8344-133">Scegliere **Aggiungi nuovo elemento** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="c8344-133">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="c8344-134">Nel nodo **Installed**  >  **elementi comuni** installati selezionare flusso di **lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c8344-134">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="c8344-135">Selezionare l'**attività** dall'elenco **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="c8344-135">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="c8344-136">Digitare `Prompt` nella casella **Nome** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c8344-136">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="c8344-137">Fare doppio clic su **prompt. XAML** in **Esplora soluzioni** per visualizzarlo nella finestra di progettazione se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c8344-137">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="c8344-138">Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per visualizzare il riquadro **Argomenti**.</span><span class="sxs-lookup"><span data-stu-id="c8344-138">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="c8344-139">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="c8344-139">Click **Create Argument**.</span></span>

8. <span data-ttu-id="c8344-140">Digitare `BookmarkName` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **stringa** dall'elenco a discesa tipo di **argomento** , quindi premere **invio** per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="c8344-140">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="c8344-141">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="c8344-141">Click **Create Argument**.</span></span>

10. <span data-ttu-id="c8344-142">Digitare `Result` nella casella **nome** che si trova sotto l'argomento appena aggiunto `BookmarkName` , selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="c8344-142">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="c8344-143">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="c8344-143">Click **Create Argument**.</span></span>

12. <span data-ttu-id="c8344-144">Digitare `Text` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **stringa** dall'elenco a discesa tipo di **argomento** , quindi premere **invio** per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="c8344-144">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="c8344-145">Questi tre argomenti vengono associati agli argomenti corrispondenti delle attività <xref:System.Activities.Statements.WriteLine> e `ReadInt` aggiunte all'attività `Prompt` nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="c8344-145">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="c8344-146">Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Argomenti**.</span><span class="sxs-lookup"><span data-stu-id="c8344-146">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="c8344-147">Trascinare un'attività **Sequence** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla sull'etichetta **rilasciare** l'attività dell'ActivityDesigner **prompt** .</span><span class="sxs-lookup"><span data-stu-id="c8344-147">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="c8344-148">Se la finestra **Casella degli strumenti** non è visualizzata, selezionare **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c8344-148">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="c8344-149">Trascinare un'attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla sull'etichetta **Drop Activity here** dell'attività **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="c8344-149">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="c8344-150">Associare l'argomento **Text** dell'attività **WriteLine** all'argomento **Text** dell'attività **prompt** digitando nella `Text` casella **immettere un'espressione C#** o **immettere un'espressione VB** nella finestra **Proprietà** , quindi premere il tasto **Tab** due volte.</span><span class="sxs-lookup"><span data-stu-id="c8344-150">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="c8344-151">Ciò consente di chiudere la finestra dei membri dell'elenco IntelliSense e salva il valore della proprietà spostando la selezione dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="c8344-151">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="c8344-152">Questa proprietà può essere impostata anche digitando `Text` nella casella **immettere un'espressione C#** o **immettere un'espressione VB** nell'attività stessa.</span><span class="sxs-lookup"><span data-stu-id="c8344-152">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="c8344-153">Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="c8344-153">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="c8344-154">Trascinare un'attività **ReadInt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** in modo che segua l'attività **WriteLine** .</span><span class="sxs-lookup"><span data-stu-id="c8344-154">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="c8344-155">Associare l'argomento **BookmarkName** dell'attività **ReadInt** all'argomento **BookmarkName** dell'attività **prompt** digitando `BookmarkName` nella casella **immettere un'espressione VB** a destra dell'argomento **BookmarkName** nella **finestra Proprietà**, quindi premere il tasto **Tab** due volte per chiudere la finestra elenco IntelliSense membri e salvare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="c8344-155">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="c8344-156">Associare l'argomento **result** dell'attività **ReadInt** all'argomento **result** dell'attività **prompt** digitando `Result` nella casella **immettere un'espressione VB** a destra dell'argomento **result** nella **finestra Proprietà**, quindi premere il tasto **Tab** due volte.</span><span class="sxs-lookup"><span data-stu-id="c8344-156">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="c8344-157">Premere **CTRL** + **MAIUSC** + **B** per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="c8344-157">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8344-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c8344-158">Next steps</span></span>

<span data-ttu-id="c8344-159">Per istruzioni su come creare un flusso di lavoro usando queste attività, vedere il passaggio successivo dell'esercitazione [procedura: creare un flusso di lavoro](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="c8344-159">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8344-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8344-160">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="c8344-161">Progettazione e implementazione di attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="c8344-161">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="c8344-162">Esercitazione Introduzione</span><span class="sxs-lookup"><span data-stu-id="c8344-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="c8344-163">Procedura: Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c8344-163">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="c8344-164">Uso di ExpressionTextBox in un ActivityDesigner personalizzato</span><span class="sxs-lookup"><span data-stu-id="c8344-164">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
