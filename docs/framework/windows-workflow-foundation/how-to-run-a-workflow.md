---
title: 'Procedura: eseguire un flusso di lavoro'
description: Questo articolo illustra come creare un host del flusso di lavoro ed eseguire il flusso di lavoro definito in un articolo precedente in questa serie di esercitazioni Windows Workflow Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 86062dd5147e6e354833928fd98bd1f6b5de9114
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421501"
---
# <a name="how-to-run-a-workflow"></a><span data-ttu-id="36e59-103">Procedura: eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-103">How to: Run a Workflow</span></span>
<span data-ttu-id="36e59-104">Questo argomento è una continuazione dell'esercitazione introduttiva di Windows Workflow Foundation e illustra come creare un host di flusso di lavoro ed eseguire il flusso di lavoro definito nell'argomento [How to: Create a Workflow](how-to-create-a-workflow.md) precedente.</span><span class="sxs-lookup"><span data-stu-id="36e59-104">This topic is a continuation of the Windows Workflow Foundation Getting Started tutorial and discusses how to create a workflow host and run the workflow defined in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="36e59-105">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="36e59-105">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="36e59-106">Per completare questo argomento, è necessario completare prima [How to: Create an Activity](how-to-create-an-activity.md) e [How to: Create a Workflow](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="36e59-106">To complete this topic you must first complete [How to: Create an Activity](how-to-create-an-activity.md) and [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36e59-107">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="36e59-107">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow-host-project"></a><span data-ttu-id="36e59-108">Per creare il progetto host del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-108">To create the workflow host project</span></span>  
  
1. <span data-ttu-id="36e59-109">Aprire la soluzione dall'argomento [procedura: creare un'attività](how-to-create-an-activity.md) con Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="36e59-109">Open the solution from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic by using Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="36e59-110">Fare clic con il pulsante destro del mouse sulla soluzione **WF45GettingStartedTutorial** in **Esplora soluzioni** e scegliere **Aggiungi**, **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="36e59-110">Right-click the **WF45GettingStartedTutorial** solution in **Solution Explorer** and select **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="36e59-111">Se la finestra **Esplora soluzioni** non è visualizzata, selezionare **Esplora soluzioni** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="36e59-111">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="36e59-112">Nel nodo **Modelli installati** selezionare **Visual C#**, **Flusso di lavoro** (oppure **Visual Basic**, **Flusso di lavoro**).</span><span class="sxs-lookup"><span data-stu-id="36e59-112">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="36e59-113">A seconda del linguaggio di programmazione configurato come principale in Visual Studio, il nodo **Visual C#** o **Visual Basic** potrebbe trovarsi all'interno del nodo **Altri linguaggi** nel nodo **Installati**.</span><span class="sxs-lookup"><span data-stu-id="36e59-113">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="36e59-114">Assicurarsi che nell'elenco a discesa della versione di .NET Framework sia selezionato **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="36e59-114">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="36e59-115">Selezionare **Applicazione console flusso di lavoro** dall'elenco **Flusso di lavoro** .</span><span class="sxs-lookup"><span data-stu-id="36e59-115">Select **Workflow Console Application** from the **Workflow** list.</span></span> <span data-ttu-id="36e59-116">Digitare `NumberGuessWorkflowHost` nella casella **Nome** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36e59-116">Type `NumberGuessWorkflowHost` into the **Name** box and click **OK**.</span></span> <span data-ttu-id="36e59-117">In questo modo verrà creata un'applicazione flusso di lavoro iniziale con supporto per l'hosting del flusso di lavoro di base.</span><span class="sxs-lookup"><span data-stu-id="36e59-117">This creates a starter workflow application with basic workflow hosting support.</span></span> <span data-ttu-id="36e59-118">Il codice host di base viene modificato e usato per eseguire l'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-118">This basic hosting code is modified and used to run the workflow application.</span></span>

4. <span data-ttu-id="36e59-119">Fare clic con il pulsante destro del mouse sul progetto **NumberGuessWorkflowHost** appena aggiunto in **Esplora soluzioni** e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="36e59-119">Right-click the newly added **NumberGuessWorkflowHost** project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="36e59-120">Scegliere **Soluzione** nell'elenco **Aggiungi riferimento** , selezionare la casella di controllo accanto a **NumberGuessWorkflowActivities**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="36e59-120">Select **Solution** from the **Add Reference** list, check the checkbox beside **NumberGuessWorkflowActivities**, and then click **OK**.</span></span>

5. <span data-ttu-id="36e59-121">Fare clic con il pulsante destro del mouse su **Workflow1.xaml** in **Esplora soluzioni** e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="36e59-121">Right-click **Workflow1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="36e59-122">Fare clic su **OK** per confermare.</span><span class="sxs-lookup"><span data-stu-id="36e59-122">Click **OK** to confirm.</span></span>

### <a name="to-modify-the-workflow-hosting-code"></a><span data-ttu-id="36e59-123">Per modificare il codice host del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-123">To modify the workflow hosting code</span></span>

1. <span data-ttu-id="36e59-124">Fare doppio clic su **Program.cs** o **Module1.vb** in **Esplora soluzioni** per visualizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="36e59-124">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to display the code.</span></span>

    > [!TIP]
    > <span data-ttu-id="36e59-125">Se la finestra **Esplora soluzioni** non è visualizzata, selezionare **Esplora soluzioni** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="36e59-125">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

     <span data-ttu-id="36e59-126">Poiché questo progetto viene creato usando il modello **Applicazione console flusso di lavoro** , **Program.cs** o **Module1.vb** contiene il seguente codice host del flusso di lavoro di base.</span><span class="sxs-lookup"><span data-stu-id="36e59-126">Because this project was created by using the **Workflow Console Application** template, **Program.cs** or **Module1.vb** contains the following basic workflow hosting code.</span></span>

    ```vb
    ' Create and cache the workflow definition.
    Dim workflow1 As Activity = New Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition.
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     <span data-ttu-id="36e59-127">Questo codice host generato usa <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="36e59-127">This generated hosting code uses <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="36e59-128"><xref:System.Activities.WorkflowInvoker> offre un modo semplice per richiamare un flusso di lavoro come se fosse una chiamata a un metodo e può essere usato solo per i flussi di lavoro che non usano la persistenza.</span><span class="sxs-lookup"><span data-stu-id="36e59-128"><xref:System.Activities.WorkflowInvoker> provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <span data-ttu-id="36e59-129"><xref:System.Activities.WorkflowApplication> fornisce un modello più dettagliato per l'esecuzione di flussi di lavoro che include la notifica degli eventi del ciclo di vita, il controllo di esecuzione, la ripresa del segnalibro e la persistenza.</span><span class="sxs-lookup"><span data-stu-id="36e59-129"><xref:System.Activities.WorkflowApplication> provides a richer model for executing workflows that includes notification of life-cycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="36e59-130">In questo esempio vengono usati i segnalibri e l'oggetto <xref:System.Activities.WorkflowApplication> viene usato per ospitare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-130">This example uses bookmarks and <xref:System.Activities.WorkflowApplication> is used for hosting the workflow.</span></span> <span data-ttu-id="36e59-131">Aggiungere la seguente istruzione `using` o **Imports** all'inizio del file **Program.cs** o **Module1.vb** dopo le istruzioni **using** o **Imports** esistenti.</span><span class="sxs-lookup"><span data-stu-id="36e59-131">Add the following `using` or **Imports** statement at the top of **Program.cs** or **Module1.vb** below the existing **using** or **Imports** statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     <span data-ttu-id="36e59-132">Sostituire le righe di codice che usano l'oggetto <xref:System.Activities.WorkflowInvoker> con il seguente codice host <xref:System.Activities.WorkflowApplication> di base.</span><span class="sxs-lookup"><span data-stu-id="36e59-132">Replace the lines of code that use <xref:System.Activities.WorkflowInvoker> with the following basic <xref:System.Activities.WorkflowApplication> hosting code.</span></span> <span data-ttu-id="36e59-133">In questo codice host di esempio vengono illustrati i passaggi di base per ospitare e richiamare un flusso di lavoro, ma non è contenuta ancora la funzionalità per eseguire correttamente il flusso di lavoro da questo argomento.</span><span class="sxs-lookup"><span data-stu-id="36e59-133">This sample hosting code demonstrates the basic steps for hosting and invoking a workflow, but does not yet contain the functionality to successfully run the workflow from this topic.</span></span> <span data-ttu-id="36e59-134">Nei seguenti passaggi il codice di base viene modificato e vengono aggiunte funzionalità aggiuntive fino a quando l'applicazione non viene completata.</span><span class="sxs-lookup"><span data-stu-id="36e59-134">In the following steps, this basic code is modified and additional features are added until the application is complete.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36e59-135">Sostituire `Workflow1` in questi esempi con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda del flusso di lavoro completato nel passaggio precedente [How to: Create a Workflow](how-to-create-a-workflow.md) .</span><span class="sxs-lookup"><span data-stu-id="36e59-135">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="36e59-136">Se non si sostituisce `Workflow1` , si verificheranno degli errori di compilazione quando si tenterà di compilare o eseguire il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-136">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     <span data-ttu-id="36e59-137">Questo codice crea un oggetto <xref:System.Activities.WorkflowApplication>, sottoscrive tre eventi del ciclo di vita del flusso di lavoro, avvia il flusso di lavoro con una chiamata al metodo <xref:System.Activities.WorkflowApplication.Run%2A>, quindi attende il completamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-137">This code creates a <xref:System.Activities.WorkflowApplication>, subscribes to three workflow life-cycle events, starts the workflow with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then waits for the workflow to complete.</span></span> <span data-ttu-id="36e59-138">Quando il flusso di lavoro viene completato, l'oggetto <xref:System.Threading.AutoResetEvent> viene impostato e l'applicazione host viene completata.</span><span class="sxs-lookup"><span data-stu-id="36e59-138">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application completes.</span></span>

### <a name="to-set-input-arguments-of-a-workflow"></a><span data-ttu-id="36e59-139">Per impostare gli argomenti di input di un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-139">To set input arguments of a workflow</span></span>

1. <span data-ttu-id="36e59-140">Aggiungere la seguente istruzione all'inizio del file **Program.cs** o **Module1.vb** dopo le istruzioni `using` o `Imports` esistenti.</span><span class="sxs-lookup"><span data-stu-id="36e59-140">Add the following statement at the top of **Program.cs** or **Module1.vb** below the existing `using` or `Imports` statements.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. <span data-ttu-id="36e59-141">Sostituire la riga di codice che crea il nuovo oggetto <xref:System.Activities.WorkflowApplication> con il codice seguente che crea e passa un dizionario di parametri al flusso di lavoro quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="36e59-141">Replace the line of code that creates the new <xref:System.Activities.WorkflowApplication> with the following code that creates and passes a dictionary of parameters to the workflow when it is created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36e59-142">Sostituire `Workflow1` in questi esempi con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda del flusso di lavoro completato nel passaggio precedente [How to: Create a Workflow](how-to-create-a-workflow.md) .</span><span class="sxs-lookup"><span data-stu-id="36e59-142">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="36e59-143">Se non si sostituisce `Workflow1` , si verificheranno degli errori di compilazione quando si tenterà di compilare o eseguire il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-143">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="36e59-144">Questo dizionario contiene un elemento con una chiave di `MaxNumber`.</span><span class="sxs-lookup"><span data-stu-id="36e59-144">This dictionary contains one element with a key of `MaxNumber`.</span></span> <span data-ttu-id="36e59-145">Le chiavi nel dizionario di input corrispondono agli argomenti di input sull'attività radice del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-145">Keys in the input dictionary correspond to input arguments on the root activity of the workflow.</span></span> <span data-ttu-id="36e59-146">`MaxNumber` viene usato dal flusso di lavoro per determinare il limite superiore del numero generato casualmente.</span><span class="sxs-lookup"><span data-stu-id="36e59-146">`MaxNumber` is used by the workflow to determine the upper bound for the randomly generated number.</span></span>

### <a name="to-retrieve-output-arguments-of-a-workflow"></a><span data-ttu-id="36e59-147">Per recuperare gli argomenti di output di un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-147">To retrieve output arguments of a workflow</span></span>

1. <span data-ttu-id="36e59-148">Modificare il gestore <xref:System.Activities.WorkflowApplication.Completed%2A> per recuperare e visualizzare il numero di turni usati dal flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-148">Modify the <xref:System.Activities.WorkflowApplication.Completed%2A> handler to retrieve and display the number of turns used by the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a><span data-ttu-id="36e59-149">Per riprendere un segnalibro</span><span class="sxs-lookup"><span data-stu-id="36e59-149">To resume a bookmark</span></span>

1. <span data-ttu-id="36e59-150">Aggiungere il seguente codice all'inizio del metodo `Main` subito dopo la dichiarazione <xref:System.Threading.AutoResetEvent> esistente.</span><span class="sxs-lookup"><span data-stu-id="36e59-150">Add the following code at the top of the `Main` method just after the existing <xref:System.Threading.AutoResetEvent> declaration.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. <span data-ttu-id="36e59-151">Aggiungere il seguente gestore <xref:System.Activities.WorkflowApplication.Idle%2A> subito dopo i tre gestori del ciclo di vita del flusso di lavoro esistenti in `Main`.</span><span class="sxs-lookup"><span data-stu-id="36e59-151">Add the following <xref:System.Activities.WorkflowApplication.Idle%2A> handler just below the existing three workflow life-cycle handlers in `Main`.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     <span data-ttu-id="36e59-152">Ogni volta che il flusso di lavoro diventa inattivo in attesa del tentativo successivo, questo gestore viene chiamato e l'oggetto `idleAction` <xref:System.Threading.AutoResetEvent> viene impostato.</span><span class="sxs-lookup"><span data-stu-id="36e59-152">Each time the workflow becomes idle waiting for the next guess, this handler is called and the `idleAction` <xref:System.Threading.AutoResetEvent> is set.</span></span> <span data-ttu-id="36e59-153">Il codice nel passaggio seguente usa `idleEvent` e `syncEvent` per determinare se il flusso di lavoro è in attesa della prossimo tentativo o viene completato.</span><span class="sxs-lookup"><span data-stu-id="36e59-153">The code in the following step uses `idleEvent` and `syncEvent` to determine whether the workflow is waiting for the next guess or is complete.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36e59-154">In questo esempio l'applicazione host usa eventi di reimpostazione automatica nei gestori <xref:System.Activities.WorkflowApplication.Completed%2A> e <xref:System.Activities.WorkflowApplication.Idle%2A> per sincronizzare l'applicazione host con lo stato di avanzamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-154">In this example, the host application uses auto-reset events in the <xref:System.Activities.WorkflowApplication.Completed%2A> and <xref:System.Activities.WorkflowApplication.Idle%2A> handlers to synchronize the host application with the progress of the workflow.</span></span> <span data-ttu-id="36e59-155">Non è necessario bloccare e attendere l'inattività del flusso di lavoro prima di riprendere un segnalibro, ma in questo esempio gli eventi di sincronizzazione sono obbligatori affinché l'host sappia se il flusso di lavoro viene completato o se è in attesa di più input dell'utente usando l'oggetto <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="36e59-155">It is not necessary to block and wait for the workflow to become idle before resuming a bookmark, but in this example the synchronization events are required so the host knows whether the workflow is complete or whether it is waiting on more user input by using the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="36e59-156">Per ulteriori informazioni, vedere [segnalibri](bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="36e59-156">For more information, see [Bookmarks](bookmarks.md).</span></span>

3. <span data-ttu-id="36e59-157">Rimuovere la chiamata al metodo `WaitOne`e sostituirla con codice per raccogliere l'input dell'utente e riprendere l'oggetto <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="36e59-157">Remove the call to `WaitOne`, and replace it with code to gather input from the user and resume the <xref:System.Activities.Bookmark>.</span></span>

     <span data-ttu-id="36e59-158">Rimuovere la seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="36e59-158">Remove the following line of code.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     <span data-ttu-id="36e59-159">Sostituirla con l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="36e59-159">Replace it with the following example.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="to-build-and-run-the-application"></a><a name="BKMK_ToRunTheApplication"></a><span data-ttu-id="36e59-160">Per compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="36e59-160">To build and run the application</span></span>

1. <span data-ttu-id="36e59-161">Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e selezionare **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="36e59-161">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="36e59-162">Premere CTRL+F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="36e59-162">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="36e59-163">Provare a determinare il numero con meno tentativi possibili.</span><span class="sxs-lookup"><span data-stu-id="36e59-163">Try to guess the number in as few turns as possible.</span></span>

     <span data-ttu-id="36e59-164">Per provare l'applicazione con uno degli altri stili del flusso di lavoro, sostituire `Workflow1` nel codice che crea <xref:System.Activities.WorkflowApplication> con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda dello stile del flusso di lavoro desiderato.</span><span class="sxs-lookup"><span data-stu-id="36e59-164">To try the application with one of the other styles of workflow, replace `Workflow1` in the code that creates the <xref:System.Activities.WorkflowApplication> with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow style you desire.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="36e59-165">Per istruzioni sull'aggiunta di persistenza a un'applicazione flusso di lavoro, vedere l'argomento successivo, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="36e59-165">For instructions about how to add persistence to a workflow application, see the next topic, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span></span>

## <a name="example"></a><span data-ttu-id="36e59-166">Esempio</span><span class="sxs-lookup"><span data-stu-id="36e59-166">Example</span></span>
 <span data-ttu-id="36e59-167">L'esempio seguente è l'elenco di codice per il metodo `Main` .</span><span class="sxs-lookup"><span data-stu-id="36e59-167">The following example is the complete code listing for the `Main` method.</span></span>

> [!NOTE]
> <span data-ttu-id="36e59-168">Sostituire `Workflow1` in questi esempi con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda del flusso di lavoro completato nel passaggio precedente [How to: Create a Workflow](how-to-create-a-workflow.md) .</span><span class="sxs-lookup"><span data-stu-id="36e59-168">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="36e59-169">Se non si sostituisce `Workflow1` , si verificheranno degli errori di compilazione quando si tenterà di compilare o eseguire il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36e59-169">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a><span data-ttu-id="36e59-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36e59-170">See also</span></span>

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [<span data-ttu-id="36e59-171">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="36e59-171">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="36e59-172">Esercitazione Introduzione</span><span class="sxs-lookup"><span data-stu-id="36e59-172">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="36e59-173">Procedura: Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-173">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="36e59-174">Procedura: Creare ed eseguire un flusso di lavoro con esecuzione prolungata</span><span class="sxs-lookup"><span data-stu-id="36e59-174">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)
- [<span data-ttu-id="36e59-175">Attesa per l'input in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-175">Waiting for Input in a Workflow</span></span>](waiting-for-input-in-a-workflow.md)
- [<span data-ttu-id="36e59-176">Hosting dei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e59-176">Hosting Workflows</span></span>](hosting-workflows.md)
