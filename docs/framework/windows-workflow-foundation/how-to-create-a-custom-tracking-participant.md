---
title: 'Procedura: creare un partecipante del rilevamento personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
ms.openlocfilehash: ea7a598a73f131d8ee33e285a39173fbf84a97f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182915"
---
# <a name="how-to-create-a-custom-tracking-participant"></a><span data-ttu-id="24a00-102">Procedura: creare un partecipante del rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="24a00-102">How to: Create a Custom Tracking Participant</span></span>
<span data-ttu-id="24a00-103">Il rilevamento del flusso di lavoro fornisce la visibilità nello stato dell'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24a00-103">Workflow tracking provides visibility into the status of workflow execution.</span></span> <span data-ttu-id="24a00-104">Il runtime del flusso di lavoro genera i record di rilevamento che descrivono gli eventi del ciclo di vita di flusso del lavoro, gli eventi del ciclo di vita delle attività, le riprese dei segnalibri e gli errori.</span><span class="sxs-lookup"><span data-stu-id="24a00-104">The workflow runtime emits tracking records that describe workflow lifecycle events, activity lifecycle events, bookmark resumptions, and faults.</span></span> <span data-ttu-id="24a00-105">Tali record di rilevamento vengono usati dai partecipanti del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="24a00-105">These tracking records are consumed by tracking participants.</span></span> <span data-ttu-id="24a00-106">Windows Workflow Foundation (WF) include un partecipante di rilevamento standard che scrive i record di rilevamento come eventi ETW (Event Tracing for Windows).</span><span class="sxs-lookup"><span data-stu-id="24a00-106">Windows Workflow Foundation (WF) includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="24a00-107">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="24a00-107">If that does not meet your requirements, you can also write a custom tracking participant.</span></span> <span data-ttu-id="24a00-108">In questo passaggio dell'esercitazione viene illustrato come creare un profilo di rilevamento e un partecipante di rilevamento personalizzati che acquisiscono l'output delle attività di `WriteLine` per renderlo visibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="24a00-108">This tutorial step describes how to create a custom tracking participant and tracking profile that capture the output of `WriteLine` activities so that they can be displayed to the user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24a00-109">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="24a00-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="24a00-110">Per completare questo argomento, è necessario completare prima gli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="24a00-110">To complete this topic, you must first complete the previous topics.</span></span> <span data-ttu-id="24a00-111">Per scaricare una versione completata o visualizzare una procedura dettagliata video dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - Esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="24a00-111">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="to-create-the-custom-tracking-participant"></a><span data-ttu-id="24a00-112">Per creare un partecipante di rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="24a00-112">To create the custom tracking participant</span></span>  
  
1. <span data-ttu-id="24a00-113">Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e scegliere **Aggiungi**, **Classe**.</span><span class="sxs-lookup"><span data-stu-id="24a00-113">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="24a00-114">Digitare `StatusTrackingParticipant` nella casella **Nome** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="24a00-114">Type `StatusTrackingParticipant` into the **Name** box, and click **Add**.</span></span>  
  
2. <span data-ttu-id="24a00-115">Aggiungere le seguenti istruzioni `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="24a00-115">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3. <span data-ttu-id="24a00-116">Modificare la classe `StatusTrackingParticipant` per fare in modo che erediti da `TrackingParticipant`.</span><span class="sxs-lookup"><span data-stu-id="24a00-116">Modify the `StatusTrackingParticipant` class so that it inherits from `TrackingParticipant`.</span></span>  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4. <span data-ttu-id="24a00-117">Aggiungere il seguente override del metodo `Track`.</span><span class="sxs-lookup"><span data-stu-id="24a00-117">Add the following `Track` method override.</span></span> <span data-ttu-id="24a00-118">Esistono vari tipi di record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="24a00-118">There are several different types of tracking records.</span></span> <span data-ttu-id="24a00-119">In questo caso, si usa l'output delle attività di `WriteLine` contenute nei record di rilevamento delle attività.</span><span class="sxs-lookup"><span data-stu-id="24a00-119">We are interested in the output of `WriteLine` activities, which are contained in activity tracking records.</span></span> <span data-ttu-id="24a00-120">Se `TrackingRecord` è un `ActivityTrackingRecord` di un'attività `WriteLine`, `Text` di `WriteLine` viene aggiunto a un file denominato dopo l'elemento `InstanceId` del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24a00-120">If the `TrackingRecord` is an `ActivityTrackingRecord` for a `WriteLine` activity, the `Text` of the `WriteLine` is appended to a file named after the `InstanceId` of the workflow.</span></span> <span data-ttu-id="24a00-121">In questa esercitazione, il file viene salvato nella cartella corrente dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="24a00-121">In this tutorial, the file is saved to the current folder of the host application.</span></span>  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="24a00-122">Se non è specificato alcun profilo di rilevamento, viene usato il profilo di rilevamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="24a00-122">When no tracking profile is specified, the default tracking profile is used.</span></span> <span data-ttu-id="24a00-123">Quando viene usato il profilo di rilevamento predefinito, i record di rilevamento vengono generati per tutti gli elementi `ActivityStates`.</span><span class="sxs-lookup"><span data-stu-id="24a00-123">When the default tracking profile is used, tracking records are emitted for all `ActivityStates`.</span></span> <span data-ttu-id="24a00-124">Dal momento che è necessario acquisire il testo solo una volta durante il ciclo di vita dell'attività `WriteLine`, si estrae solo il testo dello stato `ActivityStates.Executing`.</span><span class="sxs-lookup"><span data-stu-id="24a00-124">Because we only need to capture the text one time during the lifecycle of the `WriteLine` activity, we only extract the text from the `ActivityStates.Executing` state.</span></span> <span data-ttu-id="24a00-125">In Per creare il profilo di [rilevamento e registrare il partecipante di rilevamento,](#to-create-the-tracking-profile-and-register-the-tracking-participant)viene creato un profilo di rilevamento che specifica che vengono generati solo `WriteLine` `ActivityStates.Executing` i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="24a00-125">In [To create the tracking profile and register the tracking participant](#to-create-the-tracking-profile-and-register-the-tracking-participant), a tracking profile is created that specifies that only `WriteLine` `ActivityStates.Executing` tracking records are emitted.</span></span>  
  
## <a name="to-create-the-tracking-profile-and-register-the-tracking-participant"></a><span data-ttu-id="24a00-126">Per creare il profilo di rilevamento e registrare il partecipante di rilevamento</span><span class="sxs-lookup"><span data-stu-id="24a00-126">To create the tracking profile and register the tracking participant</span></span>  
  
1. <span data-ttu-id="24a00-127">Fare clic con il pulsante destro del mouse su **WorkflowHostForm** in **Esplora soluzioni** e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="24a00-127">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="24a00-128">Aggiungere la seguente istruzione `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="24a00-128">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3. <span data-ttu-id="24a00-129">Aggiungere il codice seguente a `ConfigureWorkflowApplication` immediatamente dopo il codice che aggiunge `StringWriter` alle estensioni del flusso di lavoro e prima dei gestori del ciclo di vita del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24a00-129">Add the following code to `ConfigureWorkflowApplication` just after the code that adds the `StringWriter` to the workflow extensions and before the workflow lifecycle handlers.</span></span>  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     <span data-ttu-id="24a00-130">Questo profilo di rilevamento specifica che vengono generati solo i record di stato dell'attività per le attività `WriteLine` nello stato `Executing` per il partecipante di rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="24a00-130">This tracking profile specifies that only activity state records for `WriteLine` activities in the `Executing` state are emitted to the custom tracking participant.</span></span>  
  
     <span data-ttu-id="24a00-131">Dopo aver aggiunto il codice, l'inizio di `ConfigureWorkflowApplication` risulterà analogo al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="24a00-131">After adding the code, the start of `ConfigureWorkflowApplication` will look like the following example.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
## <a name="to-display-the-tracking-information"></a><span data-ttu-id="24a00-132">Per visualizzare le informazioni di rilevamento</span><span class="sxs-lookup"><span data-stu-id="24a00-132">To display the tracking information</span></span>  
  
1. <span data-ttu-id="24a00-133">Fare clic con il pulsante destro del mouse su **WorkflowHostForm** in **Esplora soluzioni** e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="24a00-133">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="24a00-134">Nel gestore `InstanceId_SelectedIndexChanged`, aggiungere il codice seguente subito dopo il codice che cancella la finestra di stato.</span><span class="sxs-lookup"><span data-stu-id="24a00-134">In the `InstanceId_SelectedIndexChanged` handler, add the following code immediately after the code that clears the status window.</span></span>  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     <span data-ttu-id="24a00-135">Quando viene selezionato un nuovo flusso di lavoro nell'elenco dei flusso di lavoro, i record di rilevamento del flusso di lavoro vengono caricati e visualizzati nella finestra di stato.</span><span class="sxs-lookup"><span data-stu-id="24a00-135">When a new workflow is selected in the workflow list, the tracking records for that workflow are loaded and displayed in the status window.</span></span> <span data-ttu-id="24a00-136">Nell'esempio seguente viene mostrato il gestore `InstanceId_SelectedIndexChanged` completato.</span><span class="sxs-lookup"><span data-stu-id="24a00-136">The following example is the completed `InstanceId_SelectedIndexChanged` handler.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
        'Get the workflow version and display it.  
        'If the workflow is just starting then this info will not  
        'be available in the persistence store so do not try and retrieve it.  
        If Not WorkflowStarting Then  
            Dim instance As WorkflowApplicationInstance = _  
                WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
            WorkflowVersion.Text = _  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
            'Unload the instance.  
            instance.Abandon()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
        // Get the workflow version and display it.  
        // If the workflow is just starting then this info will not  
        // be available in the persistence store so do not try and retrieve it.  
        if (!WorkflowStarting)  
        {  
            WorkflowApplicationInstance instance =  
                WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
            WorkflowVersion.Text =  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
            // Unload the instance.  
            instance.Abandon();  
        }  
    }  
    ```  
  
## <a name="to-build-and-run-the-application"></a><span data-ttu-id="24a00-137">Per compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="24a00-137">To build and run the application</span></span>  
  
1. <span data-ttu-id="24a00-138">Premere CTRL+MAIUSC+B per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24a00-138">Press Ctrl+Shift+B to build the application.</span></span>  
  
2. <span data-ttu-id="24a00-139">Premere CTRL+F5 per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24a00-139">Press Ctrl+F5 to start the application.</span></span>  
  
3. <span data-ttu-id="24a00-140">Selezionare un intervallo per il gioco di indovinare e il tipo di flusso di lavoro da avviare e fare clic su **Nuova partita**.</span><span class="sxs-lookup"><span data-stu-id="24a00-140">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="24a00-141">Inserisci un'ipotesi nella casella **Indovina** e fai clic su **Vai** per inviare la tua ipotesi.</span><span class="sxs-lookup"><span data-stu-id="24a00-141">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="24a00-142">Si noti che lo stato del flusso di lavoro viene visualizzato nella finestra di stato.</span><span class="sxs-lookup"><span data-stu-id="24a00-142">Note that the status of the workflow is displayed in the status window.</span></span> <span data-ttu-id="24a00-143">Questo output viene acquisito dalle attività `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="24a00-143">This output is captured from the `WriteLine` activities.</span></span> <span data-ttu-id="24a00-144">Passare a un flusso di lavoro diverso selezionandone uno dalla casella combinata **ID istanza flusso di** lavoro e notare che lo stato del flusso di lavoro corrente viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="24a00-144">Switch to a different workflow by selecting one from the **Workflow Instance Id** combo box and note that the status of the current workflow is removed.</span></span> <span data-ttu-id="24a00-145">Passare di nuovo al flusso di lavoro precedente. Notare che lo stato viene ripristinato, in modo simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="24a00-145">Switch back to the previous workflow and note that the status is restored, similar to the following example.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="24a00-146">Se si passa a un flusso di lavoro che è stato avviato prima dell'abilitazione del rilevamento non viene visualizzato alcuno stato.</span><span class="sxs-lookup"><span data-stu-id="24a00-146">If you switch to a workflow that was started before tracking was enabled no status is displayed.</span></span> <span data-ttu-id="24a00-147">Tuttavia se si creano tentativi aggiuntivi, lo stato viene salvato in quanto il rilevamento viene così abilitato.</span><span class="sxs-lookup"><span data-stu-id="24a00-147">However if you make additional guesses, their status is saved because tracking is now enabled.</span></span>  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    > [!NOTE]
    > <span data-ttu-id="24a00-148">Queste informazioni sono utili per la scelta dell'intervallo del numero casuale, ma non contiene alcuna informazione sui tentativi effettuati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="24a00-148">This information is useful for determining the range of the random number, but it does not contain any information about what guesses have been previously made.</span></span> <span data-ttu-id="24a00-149">Queste informazioni sono nel passaggio successivo, [Procedura: ospitare più versioni di un flusso di lavoro side-by-side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="24a00-149">This information is in the next step, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    <span data-ttu-id="24a00-150">Annotare l'ID istanza del flusso di lavoro e giocare fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="24a00-150">Make a note of the workflow instance id, and play the game through to its completion.</span></span>
  
4. <span data-ttu-id="24a00-151">Aprire Esplora risorse e passare alla cartella **NumberGuessWorkflowHost,bin,debug** (o **bin-release** a seconda delle impostazioni del progetto).</span><span class="sxs-lookup"><span data-stu-id="24a00-151">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="24a00-152">Si noti che oltre ai file eseguibili di progetto, sono presenti file con nomi file GUID.</span><span class="sxs-lookup"><span data-stu-id="24a00-152">Note that in addition to the project executable files there are files with guid filenames.</span></span> <span data-ttu-id="24a00-153">Identificare quello corrispondente all'ID istanza del flusso di lavoro dal flusso di lavoro completato nel passaggio precedente e aprirlo in Blocco Note.</span><span class="sxs-lookup"><span data-stu-id="24a00-153">Identify the one that corresponds to the workflow instance id from the completed workflow in the previous step and open it in Notepad.</span></span> <span data-ttu-id="24a00-154">Le informazioni sul rilevamento contengono dati simili al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="24a00-154">The tracking information contains information similar to the following.</span></span>  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    <span data-ttu-id="24a00-155">Oltre all'assenza dei tentativi dell'utente, questi dati di rilevamento non contengono informazioni sul tentativo finale del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24a00-155">In addition to the absence of the user's guesses, this tracking data does not contain information about the final guess of the workflow.</span></span> <span data-ttu-id="24a00-156">Ciò accade perché le informazioni di rilevamento sono costituite solo dall'output di `WriteLine` restituito dal flusso di lavoro e il messaggio finale visualizzato viene in tal modo creato dal gestore `Completed` dopo il completamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24a00-156">That is because the tracking information consists only of the `WriteLine` output from the workflow, and the final message that is displayed is done so from the `Completed` handler after the workflow completes.</span></span> <span data-ttu-id="24a00-157">Nel passaggio successivo dell'esercitazione, procedura: ospitare più versioni di `WriteLine` un flusso di lavoro [side-by-side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), le attività esistenti vengono modificate per visualizzare le ipotesi dell'utente e viene aggiunta un'attività aggiuntiva `WriteLine` che visualizza i risultati finali.</span><span class="sxs-lookup"><span data-stu-id="24a00-157">In next step of the tutorial, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), the existing `WriteLine` activities are modified to display the user's guesses, and an additional `WriteLine` activity is added that displays the final results.</span></span> <span data-ttu-id="24a00-158">Dopo aver integrato queste modifiche, procedura: ospitare più versioni di un flusso di lavoro [side-by-side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) viene illustrato come ospitare più versioni di un flusso di lavoro contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="24a00-158">After these changes are integrated, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) demonstrates how to host multiple versions of a workflow at the same time.</span></span>
