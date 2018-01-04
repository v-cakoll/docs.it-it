---
title: "Procedura: creare un'attività"
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
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a3b9698d6a060120addff52e6600916a2de19fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="d3afb-102">Procedura: creare un'attività</span><span class="sxs-lookup"><span data-stu-id="d3afb-102">How to: Create an Activity</span></span>
<span data-ttu-id="d3afb-103">Le attività sono l'unità principale del comportamento in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3afb-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="d3afb-104">La logica di esecuzione di un'attività può essere implementata nel codice gestito oppure tramite altre attività.</span><span class="sxs-lookup"><span data-stu-id="d3afb-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="d3afb-105">In questo argomento viene illustrato come creare due attività.</span><span class="sxs-lookup"><span data-stu-id="d3afb-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="d3afb-106">La prima è un'attività semplice che usa il codice per implementare la propria logica di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d3afb-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="d3afb-107">L'implementazione della seconda attività viene definita tramite altre attività.</span><span class="sxs-lookup"><span data-stu-id="d3afb-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="d3afb-108">Queste attività vengono usate nei seguenti passaggi dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="d3afb-108">These activities are used in following steps in the tutorial.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3afb-109">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="d3afb-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-activity-library-project"></a><span data-ttu-id="d3afb-110">Per creare il progetto di libreria di attività</span><span class="sxs-lookup"><span data-stu-id="d3afb-110">To create the activity library project</span></span>  
  
1.  <span data-ttu-id="d3afb-111">Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] e scegliere **New**, **progetto** dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="d3afb-111">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and choose **New**,  **Project** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="d3afb-112">Espandere il **altri tipi di progetto** nodo il **installato**, **modelli** elenco e selezionare **soluzioni di Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-112">Expand the **Other Project Types** node in the **Installed**, **Templates** list and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="d3afb-113">Selezionare **soluzione vuota** dal **soluzioni di Visual Studio** elenco.</span><span class="sxs-lookup"><span data-stu-id="d3afb-113">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="d3afb-114">Assicurarsi che nell'elenco a discesa della versione di .NET Framework sia selezionata l'opzione **.NET Framework 4.5** .</span><span class="sxs-lookup"><span data-stu-id="d3afb-114">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="d3afb-115">Tipo `WF45GettingStartedTutorial` nel **nome** casella e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-115">Type `WF45GettingStartedTutorial` in the **Name** box and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d3afb-116">Fare doppio clic su **WF45GettingStartedTutorial** in **Esplora** e scegliere **Aggiungi**, **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-116">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="d3afb-117">Se la finestra **Esplora soluzioni** non è visualizzata, scegliere **Esplora soluzioni** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="d3afb-117">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="d3afb-118">Nel nodo **Modelli installati** selezionare **Visual C#**, **Flusso di lavoro** (oppure **Visual Basic**, **Flusso di lavoro**).</span><span class="sxs-lookup"><span data-stu-id="d3afb-118">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span> <span data-ttu-id="d3afb-119">Verificare che **.NET Framework 4.5** è selezionata nel [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] elenco a discesa della versione.</span><span class="sxs-lookup"><span data-stu-id="d3afb-119">Ensure that **.NET Framework 4.5** is selected in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version drop-down list.</span></span> <span data-ttu-id="d3afb-120">Selezionare **libreria attività** dal **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="d3afb-120">Select **Activity Library** from the **Workflow** list.</span></span> <span data-ttu-id="d3afb-121">Tipo `NumberGuessWorkflowActivities` nel **nome** casella e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-121">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3afb-122">A seconda del linguaggio di programmazione configurato come linguaggio principale in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], **Visual c#** o **Visual Basic** nodo può trovarsi sotto il **altri linguaggi**nodo il **installato** nodo.</span><span class="sxs-lookup"><span data-stu-id="d3afb-122">Depending on which programming language is configured as the primary language in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>  
  
6.  <span data-ttu-id="d3afb-123">Fare doppio clic su **Activity1** in **Esplora** e scegliere **eliminare**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-123">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="d3afb-124">Per confermare scegliere **OK** .</span><span class="sxs-lookup"><span data-stu-id="d3afb-124">Click **OK** to confirm.</span></span>  
  
### <a name="to-create-the-readint-activity"></a><span data-ttu-id="d3afb-125">Per creare l'attività ReadInt</span><span class="sxs-lookup"><span data-stu-id="d3afb-125">To create the ReadInt activity</span></span>  
  
1.  <span data-ttu-id="d3afb-126">Scegliere **Aggiungi nuovo elemento** dal **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="d3afb-126">Choose **Add New Item** from the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="d3afb-127">Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-127">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="d3afb-128">Selezionare **attività codice** dal **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="d3afb-128">Select **Code Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="d3afb-129">Tipo `ReadInt` nel **nome** casella e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-129">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="d3afb-130">Sostituire la definizione dell'attività `ReadInt` esistente con la definizione seguente.</span><span class="sxs-lookup"><span data-stu-id="d3afb-130">Replace the existing `ReadInt` definition with the following definition.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="d3afb-131">L'attività `ReadInt` deriva da <xref:System.Activities.NativeActivity%601> anziché <xref:System.Activities.CodeActivity>, che è l'attività predefinita per il modello di attività codice.</span><span class="sxs-lookup"><span data-stu-id="d3afb-131">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="d3afb-132">L'oggetto <xref:System.Activities.CodeActivity%601> può essere usato se l'attività fornisce un singolo risultato, che viene esposto tramite l'argomento <xref:System.Activities.Activity%601.Result%2A>, ma <xref:System.Activities.CodeActivity%601> non supporta l'uso dei segnalibri, quindi viene usato l'oggetto <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="d3afb-132"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>  
  
### <a name="to-create-the-prompt-activity"></a><span data-ttu-id="d3afb-133">Per creare l'attività Prompt</span><span class="sxs-lookup"><span data-stu-id="d3afb-133">To create the Prompt activity</span></span>  
  
1.  <span data-ttu-id="d3afb-134">Premere CTRL+MAIUSC+B per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="d3afb-134">Press CTRL+SHIFT+B to build the project.</span></span> <span data-ttu-id="d3afb-135">Nella compilazione del progetto, l'attività `ReadInt` in questo progetto può essere usata per compilare l'attività personalizzata tramite questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d3afb-135">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>  
  
2.  <span data-ttu-id="d3afb-136">Scegliere **Aggiungi nuovo elemento** dal **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="d3afb-136">Choose **Add New Item** from the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="d3afb-137">Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-137">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="d3afb-138">Selezionare **attività** dal **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="d3afb-138">Select **Activity** from the **Workflow** list.</span></span>  
  
4.  <span data-ttu-id="d3afb-139">Tipo `Prompt` nel **nome** casella e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-139">Type `Prompt` into the **Name** box and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="d3afb-140">Fare doppio clic su **prompt** in **Esplora** da visualizzare nella finestra di progettazione se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d3afb-140">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>  
  
6.  <span data-ttu-id="d3afb-141">Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione di attività per visualizzare il **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="d3afb-141">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>  
  
7.  <span data-ttu-id="d3afb-142">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-142">Click **Create Argument**.</span></span>  
  
8.  <span data-ttu-id="d3afb-143">Tipo `BookmarkName` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **stringa** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="d3afb-143">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
9. <span data-ttu-id="d3afb-144">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-144">Click **Create Argument**.</span></span>  
  
10. <span data-ttu-id="d3afb-145">Tipo `Result` nel **nome** casella che si trova sotto appena aggiunta `BookmarkName` argomento, selezionare **Out** dal **direzione** elenco a discesa, seleziona **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="d3afb-145">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
11. <span data-ttu-id="d3afb-146">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="d3afb-146">Click **Create Argument**.</span></span>  
  
12. <span data-ttu-id="d3afb-147">Tipo `Text` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **stringa** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="d3afb-147">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
     <span data-ttu-id="d3afb-148">Questi tre argomenti vengono associati agli argomenti corrispondenti delle attività <xref:System.Activities.Statements.WriteLine> e `ReadInt` aggiunte all'attività `Prompt` nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d3afb-148">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>  
  
13. <span data-ttu-id="d3afb-149">Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="d3afb-149">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
14. <span data-ttu-id="d3afb-150">Trascinare un **sequenza** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta del **Prompt** ActivityDesigner.</span><span class="sxs-lookup"><span data-stu-id="d3afb-150">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="d3afb-151">Se il **della casella degli strumenti** non verrà visualizzata la finestra, selezionare **della casella degli strumenti** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="d3afb-151">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
15. <span data-ttu-id="d3afb-152">Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta del **Sequenza** attività.</span><span class="sxs-lookup"><span data-stu-id="d3afb-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>  
  
16. <span data-ttu-id="d3afb-153">Associare il **testo** argomento del **WriteLine** attività per il **testo** argomento del **Prompt** attività digitando `Text` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella il **proprietà** finestra e quindi la scheda tasto due volte.</span><span class="sxs-lookup"><span data-stu-id="d3afb-153">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the TAB key two times.</span></span> <span data-ttu-id="d3afb-154">Ciò consente di chiudere la finestra dei membri dell'elenco IntelliSense e salva il valore della proprietà spostando la selezione dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3afb-154">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="d3afb-155">Questa proprietà può essere impostata anche digitando `Text` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella nell'attività stessa.</span><span class="sxs-lookup"><span data-stu-id="d3afb-155">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="d3afb-156">Se il **finestra proprietà** non è visualizzata, selezionare **finestra proprietà** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="d3afb-156">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
17. <span data-ttu-id="d3afb-157">Trascinare un **ReadInt** attività dal **NumberGuessWorkflowActivities** sezione il **della casella degli strumenti** e rilasciarlo nel **sequenza** attività in modo che segua il **WriteLine** attività.</span><span class="sxs-lookup"><span data-stu-id="d3afb-157">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>  
  
18. <span data-ttu-id="d3afb-158">Associare il **BookmarkName** argomento del **ReadInt** attività per il **BookmarkName** argomento del **Prompt** attività digitando `BookmarkName` nel **immettere un'espressione VB** casella a destra del **BookmarkName** argomento in di **finestra proprietà**e quindi premere il tasto TAB due a volte per chiudere la finestra di IntelliSense elenco membri e salvare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3afb-158">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the TAB key two times to close the IntelliSense list members window and save the property.</span></span>  
  
19. <span data-ttu-id="d3afb-159">Associare il **risultato** argomento del **ReadInt** attività per il **risultato** argomento del **Prompt** attività digitando `Result` nel **immettere un'espressione VB** casella a destra del **risultato** argomento in di **finestra proprietà**e quindi premere il tasto TAB due volte.</span><span class="sxs-lookup"><span data-stu-id="d3afb-159">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the TAB key two times.</span></span>  
  
20. <span data-ttu-id="d3afb-160">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="d3afb-160">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="d3afb-161">Per istruzioni su come creare un flusso di lavoro utilizzando queste attività, vedere il passaggio successivo dell'esercitazione, [procedura: creare un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d3afb-161">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3afb-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3afb-162">See Also</span></span>  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [<span data-ttu-id="d3afb-163">Progettazione e implementazione di attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="d3afb-163">Designing and Implementing Custom Activities</span></span>](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [<span data-ttu-id="d3afb-164">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="d3afb-164">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="d3afb-165">Procedura: Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d3afb-165">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [<span data-ttu-id="d3afb-166">Uso di ExpressionTextBox in un ActivityDesigner personalizzato</span><span class="sxs-lookup"><span data-stu-id="d3afb-166">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
