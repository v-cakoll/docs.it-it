---
title: "Procedura: ospitare più versioni di un flusso di lavoro side-by-side"
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
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0f6fa267e6400672328714f016a5823d8f1311aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="e3294-102">Procedura: ospitare più versioni di un flusso di lavoro side-by-side</span><span class="sxs-lookup"><span data-stu-id="e3294-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
<span data-ttu-id="e3294-103">`WorkflowIdentity` offre agli sviluppatori di applicazioni flusso di lavoro un modo per associare un nome e una versione a una definizione del flusso di lavoro. Consente inoltre di associare queste informazioni a un'istanza persistente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3294-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="e3294-104">Queste informazioni di identità possono essere usate dagli sviluppatori di applicazioni flusso di lavoro per scenari quali l'esecuzione affiancata di più versioni di una definizione del flusso di lavoro e costituiscono un elemento fondamentale per altre funzionalità come l'aggiornamento dinamico.</span><span class="sxs-lookup"><span data-stu-id="e3294-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="e3294-105">In questo passaggio dell'esercitazione viene illustrato come usare `WorkflowIdentity` per ospitare più versioni di un flusso di lavoro contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e3294-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3294-106">Per scaricare una versione completa o visualizzare una procedura dettagliata video dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="e3294-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="e3294-107">Contenuto dell'argomento</span><span class="sxs-lookup"><span data-stu-id="e3294-107">In this topic</span></span>  
 <span data-ttu-id="e3294-108">In questo passaggio dell'esercitazione, le attività di `WriteLine` nel flusso di lavoro vengono modificate per fornire informazioni aggiuntive e viene aggiunta una nuova attività `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="e3294-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="e3294-109">Una copia dell'assembly originale del flusso di lavoro viene archiviata e l'applicazione host viene aggiornata in modo da poter eseguire il flusso di lavoro originale e aggiornato contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e3294-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="e3294-110">Per creare una copia del progetto NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="e3294-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="e3294-111">Per aggiornare i flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="e3294-111">To update the workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="e3294-112">Per aggiornare il flusso di lavoro StateMachine</span><span class="sxs-lookup"><span data-stu-id="e3294-112">To update the StateMachine workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="e3294-113">Per aggiornare il flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="e3294-113">To update the Flowchart workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="e3294-114">Per aggiornare il flusso di lavoro sequenza</span><span class="sxs-lookup"><span data-stu-id="e3294-114">To update the Sequential workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="e3294-115">Per aggiornare WorkflowVersionMap in modo da includere le versioni precedenti di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e3294-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="e3294-116">Per compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="e3294-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="e3294-117">Prima di effettuare i passaggi di questo argomento, eseguire l'applicazione, avviare diversi flussi di lavoro di ogni tipo ed effettuare uno o due tentativi per ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="e3294-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="e3294-118">Questi flussi di lavoro persistente vengono utilizzati in questo passaggio e il passaggio seguente, [procedura: aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="e3294-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3294-119">Ogni passaggio nell'Esercitazione introduttiva dipende dai passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="e3294-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="e3294-120">Se non è completato i passaggi precedenti è possibile scaricare una versione completa dell'esercitazione da [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="e3294-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
###  <a name="BKMK_BackupCopy"></a><span data-ttu-id="e3294-121">Per creare una copia del progetto NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="e3294-121">To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1.  <span data-ttu-id="e3294-122">Aprire il **WF45GettingStartedTutorial** soluzione in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] se non è aperto.</span><span class="sxs-lookup"><span data-stu-id="e3294-122">Open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] if it is not open.</span></span>  
  
2.  <span data-ttu-id="e3294-123">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="e3294-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="e3294-124">Chiudi il **WF45GettingStartedTutorial** soluzione.</span><span class="sxs-lookup"><span data-stu-id="e3294-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4.  <span data-ttu-id="e3294-125">Aprire Esplora risorse e passare alla cartella in cui si trova il file della soluzione di esercitazione e le cartelle del progetto.</span><span class="sxs-lookup"><span data-stu-id="e3294-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5.  <span data-ttu-id="e3294-126">Creare una nuova cartella denominata **PreviousVersions** nella stessa cartella **NumberGuessWorkflowHost** e **NumberGuessWorkflowActivities**.</span><span class="sxs-lookup"><span data-stu-id="e3294-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="e3294-127">Questa cartella è usata per contenere gli assembly che includono le diverse versioni dei flussi di lavoro usate nei passaggi successivi dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="e3294-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6.  <span data-ttu-id="e3294-128">Passare il **NumberGuessWorkflowActivities\bin\debug** cartella (o **bin\release** a seconda delle impostazioni di progetto).</span><span class="sxs-lookup"><span data-stu-id="e3294-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="e3294-129">Copia **NumberGuessWorkflowActivities.dll** e incollarlo il **PreviousVersions** cartella.</span><span class="sxs-lookup"><span data-stu-id="e3294-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7.  <span data-ttu-id="e3294-130">Rinominare **NumberGuessWorkflowActivities.dll** nel **PreviousVersions** cartella **NumberGuessWorkflowActivities_v1.dll**.</span><span class="sxs-lookup"><span data-stu-id="e3294-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3294-131">Nei passaggi di questo argomento viene illustrato un modo per gestire gli assembly usati per contenere più versioni dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3294-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="e3294-132">È anche possibile usare altri metodi, come l'assegnazione dei nomi sicuri agli assembly e la registrazione degli assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="e3294-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>  
  
8.  <span data-ttu-id="e3294-133">Creare una nuova cartella denominata **NumberGuessWorkflowActivities_du** nella stessa cartella **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**e il nuovo aggiunto **PreviousVersions** cartella e copiare tutti i file e le sottocartelle dal **NumberGuessWorkflowActivities** cartella nel nuovo  **NumberGuessWorkflowActivities_du** cartella.</span><span class="sxs-lookup"><span data-stu-id="e3294-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="e3294-134">Questa copia di backup del progetto per la versione iniziale delle attività viene utilizzata [procedura: aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="e3294-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
9. <span data-ttu-id="e3294-135">Aprire nuovamente la **WF45GettingStartedTutorial** soluzione in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3294-135">Re-open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
###  <a name="BKMK_UpdateWorkflows"></a><span data-ttu-id="e3294-136">Per aggiornare i flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="e3294-136">To update the workflows</span></span>  
 <span data-ttu-id="e3294-137">Questa sezione aggiorna le definizioni di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3294-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="e3294-138">Le due attività `WriteLine` che forniscono il feedback sul tentativo dell'utente vengono aggiornate e viene aggiunta una nuova attività `WriteLine` che fornisce informazioni aggiuntive sul gioco una volta determinato il numero.</span><span class="sxs-lookup"><span data-stu-id="e3294-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>  
  
####  <a name="BKMK_UpdateStateMachine"></a><span data-ttu-id="e3294-139">Per aggiornare il flusso di lavoro StateMachine</span><span class="sxs-lookup"><span data-stu-id="e3294-139">To update the StateMachine workflow</span></span>  
  
1.  <span data-ttu-id="e3294-140">In **Esplora**, sotto il **NumberGuessWorkflowActivities** progetto, fare doppio clic su **Statemachinenumberguessworkflow**.</span><span class="sxs-lookup"><span data-stu-id="e3294-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="e3294-141">Fare doppio clic su di **Guess Incorrect** transizione nella macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="e3294-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>  
  
3.  <span data-ttu-id="e3294-142">Aggiornare l'oggetto `Text` di `WriteLine` all'estrema sinistra dell'attività `If`.</span><span class="sxs-lookup"><span data-stu-id="e3294-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
4.  <span data-ttu-id="e3294-143">Aggiornare l'oggetto `Text` di `WriteLine` all'estrema destra dell'attività `If`.</span><span class="sxs-lookup"><span data-stu-id="e3294-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
5.  <span data-ttu-id="e3294-144">Tornare a generale dello stato di visualizzazione nella finestra di progettazione del flusso di lavoro della macchina, fare clic su **StateMachine** della barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3294-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
6.  <span data-ttu-id="e3294-145">Fare doppio clic su di **Guess Correct** transizione nella macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="e3294-145">Double-click the **Guess Correct** transition on the state machine.</span></span>  
  
7.  <span data-ttu-id="e3294-146">Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla sul **rilascia l'attività Action qui** etichetta del transizione.</span><span class="sxs-lookup"><span data-stu-id="e3294-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>  
  
8.  <span data-ttu-id="e3294-147">Digitare l'espressione seguente nella casella della proprietà `Text`.</span><span class="sxs-lookup"><span data-stu-id="e3294-147">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateFlowchart"></a><span data-ttu-id="e3294-148">Per aggiornare il flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="e3294-148">To update the Flowchart workflow</span></span>  
  
1.  <span data-ttu-id="e3294-149">In **Esplora**, sotto il **NumberGuessWorkflowActivities** progetto, fare doppio clic su **Flowchartnumberguessworkflow**.</span><span class="sxs-lookup"><span data-stu-id="e3294-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="e3294-150">Aggiornare l'oggetto `Text` dell'attività `WriteLine` all'estrema sinistra.</span><span class="sxs-lookup"><span data-stu-id="e3294-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="e3294-151">Aggiornare l'oggetto `Text` dell'attività `WriteLine` all'estrema destra.</span><span class="sxs-lookup"><span data-stu-id="e3294-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="e3294-152">Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla sul punto di rilascio del `True` azione di livello più alto `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="e3294-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="e3294-153">L'attività di `WriteLine` viene aggiunta al diagramma di flusso e collegata all'azione `True` di `FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="e3294-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>  
  
5.  <span data-ttu-id="e3294-154">Digitare l'espressione seguente nella casella della proprietà `Text`.</span><span class="sxs-lookup"><span data-stu-id="e3294-154">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateSequential"></a><span data-ttu-id="e3294-155">Per aggiornare il flusso di lavoro sequenza</span><span class="sxs-lookup"><span data-stu-id="e3294-155">To update the Sequential workflow</span></span>  
  
1.  <span data-ttu-id="e3294-156">In **Esplora**, sotto il **NumberGuessWorkflowActivities** progetto, fare doppio clic su **Sequentialnumberguessworkflow**.</span><span class="sxs-lookup"><span data-stu-id="e3294-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="e3294-157">Aggiornare l'oggetto `Text` di `WriteLine` all'estrema sinistra dell'attività `If`.</span><span class="sxs-lookup"><span data-stu-id="e3294-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="e3294-158">Aggiornare l'oggetto `Text` dell'attività `WriteLine` all'estrema destra dell'attività `If`.</span><span class="sxs-lookup"><span data-stu-id="e3294-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="e3294-159">Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla dopo il **DoWhile** attività in modo che il  **WriteLine** è l'attività finale nella radice `Sequence` attività.</span><span class="sxs-lookup"><span data-stu-id="e3294-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>  
  
5.  <span data-ttu-id="e3294-160">Digitare l'espressione seguente nella casella della proprietà `Text`.</span><span class="sxs-lookup"><span data-stu-id="e3294-160">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
###  <a name="BKMK_UpdateWorkflowVersionMap"></a><span data-ttu-id="e3294-161">Per aggiornare WorkflowVersionMap in modo da includere le versioni precedenti di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e3294-161">To update WorkflowVersionMap to include the previous workflow versions</span></span>  
  
1.  <span data-ttu-id="e3294-162">Fare doppio clic su **workflowversionmap. cs** (o **workflowversionmap. vb**) sotto il **NumberGuessWorkflowHost** per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="e3294-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>  
  
2.  <span data-ttu-id="e3294-163">Aggiungere le seguenti istruzioni `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="e3294-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Reflection  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Reflection;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="e3294-164">Aggiungere tre nuove identità del flusso di lavoro subito dopo le tre dichiarazioni di identità del flusso di lavoro esistenti.</span><span class="sxs-lookup"><span data-stu-id="e3294-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="e3294-165">Queste nuove identità del flusso di lavoro `v1` verranno usate per fornire la definizione corretta del flusso di lavoro ai flussi di lavoro avviati prima dell'applicazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e3294-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>  
  
    ```vb  
    'Current version identities.  
    Public StateMachineNumberGuessIdentity As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity As WorkflowIdentity  
    Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
    'v1 Identities.  
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
    ```  
  
    ```csharp  
    // Current version identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity;  
    static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
    // v1 identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
    ```  
  
4.  <span data-ttu-id="e3294-166">Nel costruttore `WorkflowVersionMap`, aggiornare la proprietà `Version` delle tre identità correnti del flusso di lavoro a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="e3294-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>  
  
    ```vb  
    'Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
    ```  
  
    ```csharp  
    // Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
    ```  
  
     <span data-ttu-id="e3294-167">Il codice che aggiunge le versioni correnti dei flussi di lavoro al dizionario usa le versioni correnti a cui si fa riferimento nel progetto, in modo che il codice che inizializza le definizioni dei flusso di lavoro non deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="e3294-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>  
  
5.  <span data-ttu-id="e3294-168">Aggiungere il seguente codice nel costruttore immediatamente dopo il codice che aggiunge le versioni correnti al dizionario.</span><span class="sxs-lookup"><span data-stu-id="e3294-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>  
  
    ```vb  
    'Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
    ```  
  
    ```csharp  
    // Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
    ```  
  
     <span data-ttu-id="e3294-169">Queste identità del flusso di lavoro sono associate alle versioni iniziali delle corrispondenti definizioni di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3294-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>  
  
6.  <span data-ttu-id="e3294-170">Quindi, caricare l'assembly contenente la versione iniziale delle definizioni di flusso di lavoro e creare e aggiungere le definizioni corrispondenti di flusso di lavoro al dizionario.</span><span class="sxs-lookup"><span data-stu-id="e3294-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>  
  
    ```vb  
    'Add the previous version workflow identities to the dictionary along with  
    'the corresponding workflow definitions loaded from the v1 assembly.  
    'Assembly.LoadFile requires an absolute path so convert this relative path  
    'to an absolute path.  
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
    ```  
  
    ```csharp  
    // Add the previous version workflow identities to the dictionary along with  
    // the corresponding workflow definitions loaded from the v1 assembly.  
    // Assembly.LoadFile requires an absolute path so convert this relative path  
    // to an absolute path.  
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
    ```  
  
     <span data-ttu-id="e3294-171">L'esempio seguente è l'elenco di codice per la classe `WorkflowVersionMap` aggiornata.</span><span class="sxs-lookup"><span data-stu-id="e3294-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        'v1 Identities.  
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
  
            'Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            'Add the previous version workflow identities to the dictionary along with  
            'the corresponding workflow definitions loaded from the v1 assembly.  
            'Assembly.LoadFile requires an absolute path so convert this relative path  
            'to an absolute path.  
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        // v1 identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
  
            // Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            // Add the previous version workflow identities to the dictionary along with  
            // the corresponding workflow definitions loaded from the v1 assembly.  
            // Assembly.LoadFile requires an absolute path so convert this relative path  
            // to an absolute path.  
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {  
            return identity.ToString();  
        }  
    }  
    ```  
  
###  <a name="BKMK_BuildAndRun"></a><span data-ttu-id="e3294-172">Per compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="e3294-172">To build and run the application</span></span>  
  
1.  <span data-ttu-id="e3294-173">Premere CTRL+MAIUSC+B per compilare l'applicazione, quindi premere CTRL+F5 per avviarla.</span><span class="sxs-lookup"><span data-stu-id="e3294-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>  
  
2.  <span data-ttu-id="e3294-174">Avviare un nuovo flusso di lavoro facendo **nuova partita**.</span><span class="sxs-lookup"><span data-stu-id="e3294-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="e3294-175">La versione del flusso di lavoro viene visualizzata nella finestra di stato e riflette la versione aggiornata dall'oggetto `WorkflowIdentity` associato.</span><span class="sxs-lookup"><span data-stu-id="e3294-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="e3294-176">Prendere nota di `InstanceId` in modo da poter visualizzare il file di traccia per il flusso di lavoro quando viene completato e quindi immettere i tentativi fino al termine del gioco.</span><span class="sxs-lookup"><span data-stu-id="e3294-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="e3294-177">Si noti in che modo la stima dell'utente viene visualizzata tra le informazioni riportate nella finestra di stato in base agli aggiornamenti alle attività `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="e3294-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>  
  
 <span data-ttu-id="e3294-178">**Immettere un numero compreso tra 1 e 10**</span><span class="sxs-lookup"><span data-stu-id="e3294-178">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="e3294-179">**5 è troppo alto.** </span><span class="sxs-lookup"><span data-stu-id="e3294-179">**5 is too high.** </span></span>  
<span data-ttu-id="e3294-180">**Immettere un numero compreso tra 1 e 10** </span><span class="sxs-lookup"><span data-stu-id="e3294-180">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="e3294-181">**3 è troppo alto.** </span><span class="sxs-lookup"><span data-stu-id="e3294-181">**3 is too high.** </span></span>  
<span data-ttu-id="e3294-182">**Immettere un numero compreso tra 1 e 10** </span><span class="sxs-lookup"><span data-stu-id="e3294-182">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="e3294-183">**1 è troppo basso.** </span><span class="sxs-lookup"><span data-stu-id="e3294-183">**1 is too low.** </span></span>  
<span data-ttu-id="e3294-184">**Immettere un numero compreso tra 1 e 10** </span><span class="sxs-lookup"><span data-stu-id="e3294-184">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="e3294-185">**Complimenti, il numero è decifrate a sua 4 volta.**</span><span class="sxs-lookup"><span data-stu-id="e3294-185">**Congratulations, you guessed the number in 4 turns.**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="e3294-186">Viene visualizzato il testo aggiornato dalle attività `WriteLine`, ma non l'output dell'attività finale `WriteLine` aggiunta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e3294-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="e3294-187">Ciò accade perché la finestra di stato viene aggiornata dal gestore `PersistableIdle`.</span><span class="sxs-lookup"><span data-stu-id="e3294-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="e3294-188">Poiché il flusso di lavoro viene completato e non risulta inattivo dopo l'attività finale, il gestore `PersistableIdle` non viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="e3294-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="e3294-189">Tuttavia, viene visualizzato un messaggio simile nella finestra di stato dal gestore `Completed`.</span><span class="sxs-lookup"><span data-stu-id="e3294-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="e3294-190">Se necessario, è possibile aggiungere il codice al gestore `Completed` per estrarre il testo da `StringWriter` e per visualizzarlo nella finestra di stato.</span><span class="sxs-lookup"><span data-stu-id="e3294-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>  
  
3.  <span data-ttu-id="e3294-191">Aprire Esplora risorse e passare al **NumberGuessWorkflowHost\bin\debug** cartella (o **bin\release** a seconda delle impostazioni di progetto) e aprire il file di rilevamento mediante blocco note corrispondente per il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="e3294-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="e3294-192">Se invece non hai apportato annotare il `InstanceId`, è possibile identificare il file di rilevamento corretto usando il **data modificata** informazioni in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="e3294-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>  
  
 <span data-ttu-id="e3294-193">**Immettere un numero compreso tra 1 e 10**</span><span class="sxs-lookup"><span data-stu-id="e3294-193">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="e3294-194">**5 è troppo alto.** </span><span class="sxs-lookup"><span data-stu-id="e3294-194">**5 is too high.** </span></span>  
<span data-ttu-id="e3294-195">**Immettere un numero compreso tra 1 e 10** </span><span class="sxs-lookup"><span data-stu-id="e3294-195">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="e3294-196">**3 è troppo alto.** </span><span class="sxs-lookup"><span data-stu-id="e3294-196">**3 is too high.** </span></span>  
<span data-ttu-id="e3294-197">**Immettere un numero compreso tra 1 e 10** </span><span class="sxs-lookup"><span data-stu-id="e3294-197">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="e3294-198">**1 è troppo basso.** </span><span class="sxs-lookup"><span data-stu-id="e3294-198">**1 is too low.** </span></span>  
<span data-ttu-id="e3294-199">**Immettere un numero compreso tra 1 e 10** </span><span class="sxs-lookup"><span data-stu-id="e3294-199">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="e3294-200">**2 è corretto. Esatto a sua 4 volta.**</span><span class="sxs-lookup"><span data-stu-id="e3294-200">**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="e3294-201">L'output di `WriteLine` aggiornato è contenuto nel file di rilevamento, incluso l'output di `WriteLine` aggiornato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e3294-201">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>  
  
4.  <span data-ttu-id="e3294-202">Passare di nuovo all'applicazione per determinare il numero e selezionare uno dei flussi di lavoro avviato prima dell'applicazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e3294-202">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="e3294-203">È possibile identificare la versione del flusso di lavoro attualmente selezionato esaminando le informazioni sulla versione visualizzate nella finestra di stato.</span><span class="sxs-lookup"><span data-stu-id="e3294-203">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="e3294-204">Immettere alcuni tentativi e notare che gli aggiornamenti di stato corrispondono all'output dell'attività `WriteLine` della versione precedente e non includono il tentativo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e3294-204">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="e3294-205">Questo perché questi flussi di lavoro usano la definizione precedente del flusso di lavoro che non presenta gli aggiornamenti di `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="e3294-205">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>  
  
     <span data-ttu-id="e3294-206">Nel passaggio successivo, [procedura: aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), l'esecuzione `v1` le istanze del flusso di lavoro vengono aggiornate in modo che contengono le nuove funzionalità come il `v2` istanze.</span><span class="sxs-lookup"><span data-stu-id="e3294-206">In the next step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
