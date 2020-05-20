---
title: Come creare ed eseguire un flusso di lavoro a esecuzione prolungata
description: Questo articolo illustra come creare un'applicazione host Windows Forms che supporta l'avvio e la ripresa di più istanze del flusso di lavoro e la persistenza del flusso di lavoro.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 557b3512e534198d47c0c6f6b0a7c5f92bb71739
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419551"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a>Come creare ed eseguire un flusso di lavoro a esecuzione prolungata

Una delle principali funzionalità di Windows Workflow Foundation (WF) è la capacità del runtime di salvare in modo permanente e scaricare flussi di lavoro inattivi in un database. I passaggi in [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md) hanno illustrato le nozioni di base dell'hosting del flusso di lavoro tramite un'applicazione console. Sono stati mostrati esempi relativi all'avvio di flussi di lavoro, di gestori del ciclo di vita del flusso di lavoro e di ripresa dei segnalibri. Per illustrare la persistenza del flusso di lavoro in modo efficace, è necessario un host del flusso di lavoro più complesso che supporta l'avvio e la ripresa di più istanze del flusso di lavoro. In questo passaggio dell'esercitazione viene illustrato come creare un'applicazione host Windows Form che supporta l'avvio e la ripresa di più istanze del flusso di lavoro e la persistenza del flusso di lavoro e vengono fornite informazioni di base per le funzionalità avanzate, ad esempio il rilevamento e il controllo delle versioni illustrati nei passaggi successivi dell'esercitazione.

> [!NOTE]
> Questo passaggio dell'esercitazione e i passaggi successivi usano tutti e tre i tipi di flusso di lavoro di [procedura: creare un flusso di lavoro](how-to-create-a-workflow.md). Se non sono stati completati tutti e tre i tipi, è possibile scaricare una versione completa dei passaggi da [Windows Workflow Foundation (WF45)-Introduzione esercitazione](https://go.microsoft.com/fwlink/?LinkID=248976).

> [!NOTE]
> Per scaricare una versione completa o visualizzare una procedura dettagliata del video dell'esercitazione, vedere [Windows Workflow Foundation (WF45)-Introduzione esercitazione](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="to-create-the-persistence-database"></a>Per creare il database di persistenza

1. Aprire SQL Server Management Studio e connettersi al server locale, ad esempio **.\SQLEXPRESS**. Fare clic con il pulsante destro del mouse sul nodo **database** nel server locale e selezionare **nuovo database**. Assegnare al nuovo database il nome **WF45GettingStartedTutorial**, accettare tutti gli altri valori e selezionare **OK**.

    > [!NOTE]
    > Assicurarsi di disporre dell'autorizzazione **create database** nel server locale prima di creare il database.

2. Scegliere **Apri**dal **menu** **file** . Passare alla cartella seguente: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*

    Selezionare i due file seguenti e fare clic su **Apri**.

    - *SqlWorkflowInstanceStoreLogic.sql*

    - *SqlWorkflowInstanceStoreSchema.sql*

3. Scegliere **SqlWorkflowInstanceStoreSchema. SQL** dal menu **finestra** . Verificare che **WF45GettingStartedTutorial** sia selezionato nell'elenco a discesa **database disponibili** e scegliere **Esegui** dal menu **query** .

4. Scegliere **SqlWorkflowInstanceStoreLogic. SQL** dal menu **finestra** . Verificare che **WF45GettingStartedTutorial** sia selezionato nell'elenco a discesa **database disponibili** e scegliere **Esegui** dal menu **query** .

    > [!WARNING]
    > È importante eseguire i due passaggi precedenti nell'ordine corretto. Se le query vengono eseguite senza rispettare l'ordine, si verificano degli errori e il database di persistenza non viene configurato correttamente.

## <a name="to-add-the-reference-to-the-durableinstancing-assemblies"></a>Per aggiungere il riferimento agli assembly DurableInstancing

1. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e scegliere **Aggiungi riferimento**.

2. Selezionare **assembly** dall'elenco **Aggiungi riferimento** e digitare `DurableInstancing` nella casella **Cerca assembly** . In questo modo gli assembly vengono filtrati ed è più semplice selezionare i riferimenti desiderati.

3. Selezionare la casella di controllo accanto a **System. Activities. DurableInstancing** e **System. Runtime. DurableInstancing** dall'elenco **dei risultati della ricerca** , quindi fare clic su **OK**.

## <a name="to-create-the-workflow-host-form"></a>Per creare il form host del flusso di lavoro

> [!NOTE]
> Nei passaggi di questa procedura viene descritto come aggiungere e configurare manualmente il form. Se si desidera, è possibile scaricare i file della soluzione per l'esercitazione e aggiungere il form completato al progetto. Per scaricare i file dell'esercitazione, vedere [Windows Workflow Foundation (WF45)-Introduzione esercitazione](https://go.microsoft.com/fwlink/?LinkID=248976). Una volta scaricati i file, fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** e scegliere **Aggiungi riferimento**. Aggiungere un riferimento a **System. Windows. Forms** e **System. Drawing**. Questi riferimenti vengono aggiunti automaticamente se si aggiunge un nuovo modulo dal menu **Aggiungi**, **nuovo elemento** , ma è necessario aggiungerlo manualmente durante l'importazione di un modulo. Una volta aggiunti i riferimenti, fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e scegliere **Aggiungi**, **elemento esistente**. Passare alla `Form` cartella nei file di progetto, selezionare **WorkflowHostForm.cs** (o **WorkflowHostForm. vb**) e fare clic su **Aggiungi**. Se si sceglie di importare il form, è possibile passare alla sezione successiva [per aggiungere le proprietà e i metodi helper del modulo](#to-add-the-properties-and-helper-methods-of-the-form).

1. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.

2. Nell'elenco modelli **installati** scegliere **Windows Form**, digitare `WorkflowHostForm` nella casella **nome** e fare clic su **Aggiungi**.

3. Configurare le seguenti proprietà nel form.

    |Proprietà|Value|
    |--------------|-----------|
    |FormBorderStyle|FixedSingle|
    |MaximizeBox|False|
    |Dimensione|400, 420|

4. Aggiungere i controlli seguenti al form nell'ordine specificato e configurare le proprietà come indicato.

    |Controllo|Proprietà: valore|
    |-------------|---------------------|
    |**Button**|Nome: NewGame<br /><br /> Località: 13, 13<br /><br /> Dimensioni: 75, 23<br /><br /> Testo: nuovo gioco|
    |**Etichetta**|Località: 94, 18<br /><br /> Testo: indovinare un numero compreso tra 1 e|
    |**ComboBox**|Nome: NumberRange<br /><br /> DropDownStyle: DropDownList<br /><br /> Elementi: 10, 100, 1000<br /><br /> Località: 228, 12<br /><br /> Dimensioni: 143, 21|
    |**Etichetta**|Località: 13, 43<br /><br /> Testo: tipo di flusso di lavoro|
    |**ComboBox**|Nome: WorkflowType<br /><br /> DropDownStyle: DropDownList<br /><br /> Elementi: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow<br /><br /> Località: 94, 40<br /><br /> Dimensioni: 277, 21|
    |**Etichetta**|Nome: WorkflowVersion<br /><br /> Località: 13, 362<br /><br /> Testo: versione del flusso di lavoro|
    |**GroupBox**|Località: 13, 67<br /><br /> Dimensioni: 358, 287<br /><br /> Testo: gioco|

    > [!NOTE]
    > Quando si aggiungono i seguenti controlli, inserirli nel GroupBox.

    |Controllo|Proprietà: valore|
    |-------------|---------------------|
    |**Etichetta**|Località: 7, 20<br /><br /> Testo: ID istanza del flusso di lavoro|
    |**ComboBox**|Nome: InstanceId<br /><br /> DropDownStyle: DropDownList<br /><br /> Località: 121, 17<br /><br /> Dimensioni: 227, 21|
    |**Etichetta**|Località: 7, 47<br /><br /> Testo: ipotesi|
    |**TextBox**|Nome: indovinare<br /><br /> Località: 50, 44<br /><br /> Dimensioni: 65, 20|
    |**Button**|Nome: EnterGuess<br /><br /> Località: 121, 42<br /><br /> Dimensioni: 75, 23<br /><br /> Testo: immettere Guess|
    |**Button**|Nome: QuitGame<br /><br /> Località: 274, 42<br /><br /> Dimensioni: 75, 23<br /><br /> Testo: Quit|
    |**TextBox**|Nome: WorkflowStatus<br /><br /> Località: 10, 73<br /><br /> Più righe: true<br /><br /> ReadOnly: true<br /><br /> Barre di scorrimento: verticali<br /><br /> Dimensioni: 338, 208|

5. Impostare la proprietà **AcceptButton** del form su **EnterGuess**.

 Nell'esempio seguente viene illustrato il form completato.

 ![Screenshot di un modulo host del flusso di lavoro Windows Workflow Foundation.](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

## <a name="to-add-the-properties-and-helper-methods-of-the-form"></a>Per aggiungere proprietà e metodi di supporto del form

Tramite i passaggi di questa sezione vengono aggiunti proprietà e metodi di supporto alla classe del form tramite cui viene configurata l'interfaccia utente del form per supportare l'esecuzione e la ripresa dei flussi di lavoro per determinare un numero.

1. Fare clic con il pulsante destro del mouse su **WorkflowHostForm** in **Esplora soluzioni** e scegliere **Visualizza codice**.

2. Aggiungere le seguenti istruzioni `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).

    ```vb
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    Imports System.Data.SqlClient
    Imports System.IO
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DurableInstancing;
    using System.Data.SqlClient;
    using System.IO;
    using System.Windows.Forms;
    ```

3. Aggiungere le seguenti dichiarazioni di membro alla classe **WorkflowHostForm** .

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    Dim store As SqlWorkflowInstanceStore
    Dim workflowStarting As Boolean
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    SqlWorkflowInstanceStore store;
    bool workflowStarting;
    ```

    > [!NOTE]
    > Se la stringa di connessione è diversa, aggiornare `connectionString` per fare riferimento al database.

4. Aggiungere una proprietà `WorkflowInstanceId` alla classe `WorkflowFormHost`.

    ```vb
    Public ReadOnly Property WorkflowInstanceId() As Guid
        Get
            If InstanceId.SelectedIndex = -1 Then
                Return Guid.Empty
            Else
                Return New Guid(InstanceId.SelectedItem.ToString())
            End If
        End Get
    End Property
    ```

    ```csharp
    public Guid WorkflowInstanceId
    {
        get
        {
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;
        }
    }
    ```

    La `InstanceId` casella combinata Visualizza un elenco di ID di istanze del flusso di lavoro permanente e la `WorkflowInstanceId` proprietà restituisce il flusso di lavoro attualmente selezionato.

5. Aggiungere un gestore per l'evento `Load` del form. Per aggiungere il gestore, passare alla **visualizzazione progettazione** per il modulo, fare clic sull'icona **eventi** nella parte superiore della finestra **proprietà** , quindi fare doppio clic su **carica**.

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. Aggiungere il seguente codice a `WorkflowHostForm_Load`.

    ```vb
    ' Initialize the store and configure it so that it can be used for
    ' multiple WorkflowApplication instances.
    store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    ' Set default ComboBox selections.
    NumberRange.SelectedIndex = 0
    WorkflowType.SelectedIndex = 0

    ListPersistedWorkflows()
    ```

    ```csharp
    // Initialize the store and configure it so that it can be used for
    // multiple WorkflowApplication instances.
    store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    // Set default ComboBox selections.
    NumberRange.SelectedIndex = 0;
    WorkflowType.SelectedIndex = 0;

    ListPersistedWorkflows();
    ```

    Durante il caricamento del form, viene configurato `SqlWorkflowInstanceStore`, le caselle combinate dell'intervallo e del tipo di flusso di lavoro vengono impostate sui valori predefiniti e le istanze del flusso di lavoro persistente vengono aggiunte alla casella combinata `InstanceId`.

7. Aggiungere un gestore `SelectedIndexChanged` per `InstanceId`. Per aggiungere il gestore, passare alla **visualizzazione progettazione** per il modulo, selezionare la `InstanceId` casella combinata, fare clic sull'icona **eventi** nella parte superiore della finestra **Proprietà** , quindi fare doppio clic su **SelectedIndexChanged**.

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. Aggiungere il seguente codice a `InstanceId_SelectedIndexChanged`. Ogni volta che l'utente seleziona un flusso di lavoro usando la casella combinata, tramite questo gestore viene aggiornata la finestra di stato.

    ```vb
    If InstanceId.SelectedIndex = -1 Then
        Return
    End If

    ' Clear the status window.
    WorkflowStatus.Clear()

    ' Get the workflow version and display it.
    ' If the workflow is just starting then this info will not
    ' be available in the persistence store so do not try and retrieve it.
    If Not workflowStarting Then
        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        WorkflowVersion.Text = _
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)

        ' Unload the instance.
        instance.Abandon()
    End If
    ```

    ```csharp
    if (InstanceId.SelectedIndex == -1)
    {
        return;
    }

    // Clear the status window.
    WorkflowStatus.Clear();

    // Get the workflow version and display it.
    // If the workflow is just starting then this info will not
    // be available in the persistence store so do not try and retrieve it.
    if (!workflowStarting)
    {
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);

        WorkflowVersion.Text =
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);

        // Unload the instance.
        instance.Abandon();
    }
    ```

9. Aggiungere il seguente metodo `ListPersistedWorkflows` alla classe del form.

    ```vb
    Private Sub ListPersistedWorkflows()
        Using localCon As New SqlConnection(connectionString)
            Dim localCmd As String = _
                "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]"

            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)

                While (reader.Read())
                    ' Get the InstanceId of the persisted Workflow.
                    Dim id As Guid = Guid.Parse(reader(0).ToString())
                    InstanceId.Items.Add(id)
                End While
            End Using
        End Using
    End Sub
    ```

    ```csharp
    using (var localCon = new SqlConnection(connectionString))
    {
        string localCmd =
            "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]";

        SqlCommand cmd = localCon.CreateCommand();
        cmd.CommandText = localCmd;
        localCon.Open();
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
        {
            while (reader.Read())
            {
                // Get the InstanceId of the persisted Workflow.
                Guid id = Guid.Parse(reader[0].ToString());
                InstanceId.Items.Add(id);
            }
        }
    }
    ```

    Tramite `ListPersistedWorkflows` viene eseguita una query sull'archivio di istanze per le istanze del flusso di lavoro persistente, quindi vengono aggiunti gli ID istanza alla casella combinata `cboInstanceId`.

10. Aggiungere il seguente metodo `UpdateStatus` e il delegato corrispondente alla classe del form. Tramite questo metodo viene aggiornata la finestra di stato nel form con lo stato del flusso di lavoro attualmente in esecuzione.

    ```vb
    Private Delegate Sub UpdateStatusDelegate(msg As String)
    Public Sub UpdateStatus(msg As String)
        ' We may be on a different thread so we need to
        ' make this call using BeginInvoke.
        If InvokeRequired Then
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)
        Else
            If Not msg.EndsWith(vbCrLf) Then
                msg = msg & vbCrLf
            End If

            WorkflowStatus.AppendText(msg)

            ' Ensure that the newly added status is visible.
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length
            WorkflowStatus.ScrollToCaret()
        End If
    End Sub
    ```

    ```csharp
    private delegate void UpdateStatusDelegate(string msg);
    public void UpdateStatus(string msg)
    {
        // We may be on a different thread so we need to
        // make this call using BeginInvoke.
        if (InvokeRequired)
        {
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);
        }
        else
        {
            if (!msg.EndsWith("\r\n"))
            {
                msg += "\r\n";
            }
            WorkflowStatus.AppendText(msg);

            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;
            WorkflowStatus.ScrollToCaret();
        }
    }
    ```

11. Aggiungere il seguente metodo `GameOver` e il delegato corrispondente alla classe del form. Quando un flusso di lavoro viene completato, questo metodo aggiorna l'interfaccia utente del form rimuovendo l'ID istanza del flusso di lavoro completato dalla casella combinata **InstanceID** .

    ```vb
    Private Delegate Sub GameOverDelegate()
    Private Sub GameOver()
        If InvokeRequired Then
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))
        Else
            ' Remove this instance from the InstanceId combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem)
            InstanceId.SelectedIndex = -1
        End If
    End Sub
    ```

    ```csharp
    private delegate void GameOverDelegate();
    private void GameOver()
    {
        if (InvokeRequired)
        {
            BeginInvoke(new GameOverDelegate(GameOver));
        }
        else
        {
            // Remove this instance from the combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem);
            InstanceId.SelectedIndex = -1;
        }
    }
    ```

## <a name="to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a>Per configurare l'archivio di istanze, i gestori del ciclo di vita del flusso di lavoro e le estensioni

1. Aggiungere un metodo `ConfigureWorkflowApplication` alla classe del form.

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    Tramite questo metodo viene configurata l'istanza `WorkflowApplication` e vengono aggiunti le estensioni desiderate e i gestori per gli eventi del ciclo di vita del flusso di lavoro.

2. In `ConfigureWorkflowApplication` specificare `SqlWorkflowInstanceStore` per l'istanza `WorkflowApplication`.

    ```vb
    ' Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. Successivamente, creare un'istanza `StringWriter` e aggiungerla alla raccolta `Extensions` dell'istanza `WorkflowApplication`. Quando un oggetto `StringWriter` viene aggiunto alle estensioni, acquisisce tutto l' `WriteLine` output dell'attività. Quando il flusso di lavoro diventa inattivo, l'output `WriteLine` può essere estratto da `StringWriter` e visualizzato nel form.

    ```vb
    ' Add a StringWriter to the extensions. This captures the output
    ' from the WriteLine activities so we can display it in the form.
    Dim sw As New StringWriter()
    wfApp.Extensions.Add(sw)
    ```

    ```csharp
    // Add a StringWriter to the extensions. This captures the output
    // from the WriteLine activities so we can display it in the form.
    var sw = new StringWriter();
    wfApp.Extensions.Add(sw);
    ```

4. Aggiungere il gestore seguente per l'evento `Completed`. Quando un flusso di lavoro è stato completato, il numero di tentativi effettuati per determinare il numero viene visualizzato nella finestra di stato. Se il flusso di lavoro viene terminato, vengono visualizzate le informazioni sull'eccezione che ha provocato l'interruzione. Alla fine del gestore viene chiamato il metodo `GameOver` tramite cui il flusso di lavoro completato viene rimosso dall'elenco di flussi di lavoro.

    ```vb
    wfApp.Completed = _
        Sub(e As WorkflowApplicationCompletedEventArgs)
            If e.CompletionState = ActivityInstanceState.Faulted Then
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                UpdateStatus("Workflow Canceled.")
            Else
                Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
            End If
            GameOver()
        End Sub
    ```

    ```csharp
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
    {
        if (e.CompletionState == ActivityInstanceState.Faulted)
        {
            UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
        }
        else if (e.CompletionState == ActivityInstanceState.Canceled)
        {
            UpdateStatus("Workflow Canceled.");
        }
        else
        {
            int turns = Convert.ToInt32(e.Outputs["Turns"]);
            UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
        }
        GameOver();
    };
    ```

5. Aggiungere i seguenti gestori `Aborted` e `OnUnhandledException`. Il metodo `GameOver` non viene chiamato dal gestore `Aborted` perché quando un'istanza del flusso di lavoro viene interrotta, non viene terminata ed è possibile riprenderla in un secondo momento.

    ```vb
    wfApp.Aborted = _
        Sub(e As WorkflowApplicationAbortedEventArgs)
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
        End Sub

    wfApp.OnUnhandledException = _
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
            GameOver()
            Return UnhandledExceptionAction.Terminate
        End Function
    ```

    ```csharp
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
    {
        UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
    };

    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
    {
        UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
        GameOver();
        return UnhandledExceptionAction.Terminate;
    };
    ```

6. Aggiungere il seguente gestore `PersistableIdle`. Tramite questo gestore viene recuperata l'estensione `StringWriter` che era stata aggiunta, viene estratto l'output dalle attività `WriteLine` che, successivamente, viene visualizzato nella finestra di stato.

    ```vb
    wfApp.PersistableIdle = _
        Function(e As WorkflowApplicationIdleEventArgs)
            ' Send the current WriteLine outputs to the status window.
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()
            For Each writer In writers
                UpdateStatus(writer.ToString())
            Next
            Return PersistableIdleAction.Unload
        End Function
    ```

    ```csharp
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
    {
        // Send the current WriteLine outputs to the status window.
        var writers = e.GetInstanceExtensions<StringWriter>();
        foreach (var writer in writers)
        {
            UpdateStatus(writer.ToString());
        }
        return PersistableIdleAction.Unload;
    };
    ```

    L'enumerazione <xref:System.Activities.PersistableIdleAction> ha tre valori:<xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist> e <xref:System.Activities.PersistableIdleAction.Unload>. Tramite il campo <xref:System.Activities.PersistableIdleAction.Persist> il flusso di lavoro viene reso persistente, ma non scaricato. <xref:System.Activities.PersistableIdleAction.Unload> rende il flusso di lavoro persistente e lo scarica.

    Nell'esempio seguente viene mostrato il metodo `ConfigureWorkflowApplication` completato.

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)
        ' Configure the persistence store.
        wfApp.InstanceStore = store

        ' Add a StringWriter to the extensions. This captures the output
        ' from the WriteLine activities so we can display it in the form.
        Dim sw As New StringWriter()
        wfApp.Extensions.Add(sw)

        wfApp.Completed = _
            Sub(e As WorkflowApplicationCompletedEventArgs)
                If e.CompletionState = ActivityInstanceState.Faulted Then
                    UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                    UpdateStatus("Workflow Canceled.")
                Else
                    Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                    UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
                End If
                GameOver()
            End Sub

        wfApp.Aborted = _
            Sub(e As WorkflowApplicationAbortedEventArgs)
                UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
            End Sub

        wfApp.OnUnhandledException = _
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
                UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
                GameOver()
                Return UnhandledExceptionAction.Terminate
            End Function

        wfApp.PersistableIdle = _
            Function(e As WorkflowApplicationIdleEventArgs)
                ' Send the current WriteLine outputs to the status window.
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()
                For Each writer In writers
                    UpdateStatus(writer.ToString())
                Next
                Return PersistableIdleAction.Unload
            End Function
    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
        // Configure the persistence store.
        wfApp.InstanceStore = store;

        // Add a StringWriter to the extensions. This captures the output
        // from the WriteLine activities so we can display it in the form.
        var sw = new StringWriter();
        wfApp.Extensions.Add(sw);

        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
        {
            if (e.CompletionState == ActivityInstanceState.Faulted)
            {
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
            }
            else if (e.CompletionState == ActivityInstanceState.Canceled)
            {
                UpdateStatus("Workflow Canceled.");
            }
            else
            {
                int turns = Convert.ToInt32(e.Outputs["Turns"]);
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
            }
            GameOver();
        };

        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
        {
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
        };

        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
        {
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
            GameOver();
            return UnhandledExceptionAction.Terminate;
        };

        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
        {
            // Send the current WriteLine outputs to the status window.
            var writers = e.GetInstanceExtensions<StringWriter>();
            foreach (var writer in writers)
            {
                UpdateStatus(writer.ToString());
            }
            return PersistableIdleAction.Unload;
        };
    }
    ```

## <a name="to-enable-starting-and-resuming-multiple-workflow-types"></a>Per abilitare l'avvio e la ripresa di più tipi di flussi di lavoro

Per riprendere un'istanza del flusso di lavoro, tramite l'host deve essere fornita la definizione del flusso di lavoro. In questa esercitazione sono disponibili tre tipi di flussi di lavoro e nei passaggi successivi dell'esercitazione vengono introdotte più versioni di questi tipi. Tramite `WorkflowIdentity` viene fornito un modo per un'applicazione host per associare le informazioni di identificazione con un'istanza del flusso di lavoro persistente. Nei passaggi di questa sezione viene illustrato come creare una classe di utilità per consentire il mapping dell'identità del flusso di lavoro da un'istanza del flusso di lavoro persistente alla definizione del flusso di lavoro corrispondente. Per altre informazioni su `WorkflowIdentity` e sul controllo delle versioni, vedere [uso di WorkflowIdentity e controllo delle versioni](using-workflowidentity-and-versioning.md).

1. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e scegliere **Aggiungi**, **classe**. Digitare `WorkflowVersionMap` nella casella **nome** e fare clic su **Aggiungi**.

2. Aggiungere le seguenti istruzioni `using` o `Imports` nella parte superiore del file con le altre istruzioni `using` o `Imports`.

    ```vb
    Imports System.Activities
    Imports NumberGuessWorkflowActivities
    ```

    ```csharp
    using System.Activities;
    using NumberGuessWorkflowActivities;
    ```

3. Sostituire la dichiarazione di classe `WorkflowVersionMap` con la dichiarazione seguente.

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        ' Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            ' Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
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

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
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

    In `WorkflowVersionMap` sono contenute tre identità del flusso di lavoro tramite cui viene eseguito il mapping alle tre definizioni del flusso di lavoro di questa esercitazione e viene usato nelle sezioni seguenti quando i flussi di lavoro vengono avviati e ripresi.

## <a name="to-start-a-new-workflow"></a>Per avviare un nuovo flusso di lavoro

1. Aggiungere un gestore `Click` per `NewGame`. Per aggiungere il gestore, passare alla **visualizzazione progettazione** per il form e fare doppio clic su `NewGame` . Viene aggiunto un gestore `NewGame_Click` e si passa alla visualizzazione codice per il form. Ogni volta che l'utente fa clic sul pulsante, viene avviato un nuovo flusso di lavoro.

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. Aggiungere il codice seguente al gestore di eventi Click. Tramite questo codice viene creato un dizionario di argomenti di input per il flusso di lavoro, con chiave basata sul nome dell'argomento. Nel dizionario è contenuta una voce in cui è incluso l'intervallo del numero generato casualmente, recuperato dalla casella combinata dell'intervallo.

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. Successivamente, aggiungere il codice seguente tramite cui viene avviato il flusso di lavoro. `WorkflowIdentity` e la definizione del flusso di lavoro corrispondente al tipo di flusso di lavoro selezionato vengono recuperati usando la classe di supporto `WorkflowVersionMap`. Successivamente, viene creata una nuova istanza `WorkflowApplication` usando la definizione del flusso di lavoro, `WorkflowIdentity` e il dizionario degli argomenti di input.

    ```vb
    Dim identity As WorkflowIdentity = Nothing
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
    End Select

    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

    Dim wfApp = New WorkflowApplication(wf, inputs, identity)
    ```

    ```csharp
    WorkflowIdentity identity = null;
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;
    };

    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);
    ```

4. Successivamente, aggiungere il codice seguente tramite cui viene aggiunto il flusso di lavoro al relativo elenco e vengono visualizzate le informazioni sulla versione del flusso di lavoro nel form.

    ```vb
    ' Add the workflow to the list and display the version information.
    workflowStarting = True
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
    WorkflowVersion.Text = identity.ToString()
    workflowStarting = False
    ```

    ```csharp
    // Add the workflow to the list and display the version information.
    workflowStarting = true;
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
    WorkflowVersion.Text = identity.ToString();
    workflowStarting = false;
    ```

5. Chiamare `ConfigureWorkflowApplication` per configurare l'archivio di istanze, le estensioni e i gestori del ciclo di vita del flusso di lavoro per questa istanza `WorkflowApplication`.

    ```vb
    ' Configure the instance store, extensions, and
    ' workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)
    ```

    ```csharp
    // Configure the instance store, extensions, and
    // workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp);
    ```

6. Infine, viene chiamato `Run`.

    ```vb
    ' Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     Nell'esempio seguente viene mostrato il gestore `NewGame_Click` completato.

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click
        ' Start a new workflow.
        Dim inputs As New Dictionary(Of String, Object)()
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))

        Dim identity As WorkflowIdentity = Nothing
        Select Case WorkflowType.SelectedItem.ToString()
            Case "SequentialNumberGuessWorkflow"
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity

            Case "StateMachineNumberGuessWorkflow"
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

            Case "FlowchartNumberGuessWorkflow"
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
        End Select

        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

        Dim wfApp = New WorkflowApplication(wf, inputs, identity)

        ' Add the workflow to the list and display the version information.
        workflowStarting = True
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
        WorkflowVersion.Text = identity.ToString()
        workflowStarting = False

        ' Configure the instance store, extensions, and
        ' workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp)

        ' Start the workflow.
        wfApp.Run()
    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {
        var inputs = new Dictionary<string, object>();
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));

        WorkflowIdentity identity = null;
        switch (WorkflowType.SelectedItem.ToString())
        {
            case "SequentialNumberGuessWorkflow":
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
                break;

            case "StateMachineNumberGuessWorkflow":
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
                break;

            case "FlowchartNumberGuessWorkflow":
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
                break;
        };

        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

        var wfApp = new WorkflowApplication(wf, inputs, identity);

        // Add the workflow to the list and display the version information.
        workflowStarting = true;
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
        WorkflowVersion.Text = identity.ToString();
        workflowStarting = false;

        // Configure the instance store, extensions, and
        // workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp);

        // Start the workflow.
        wfApp.Run();
    }
    ```

## <a name="to-resume-a-workflow"></a>Per riprendere un flusso di lavoro

1. Aggiungere un gestore `Click` per `EnterGuess`. Per aggiungere il gestore, passare alla **visualizzazione progettazione** per il form e fare doppio clic su `EnterGuess` . Ogni volta che l'utente fa clic sul pulsante, viene ripreso un flusso di lavoro.

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. Aggiungere il codice seguente per assicurarsi che un flusso di lavoro venga selezionato nell'elenco di flussi di lavoro e che il tentativo dell'utente sia valido.

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim userGuess As Integer
    If Not Int32.TryParse(Guess.Text, userGuess) Then
        MessageBox.Show("Please enter an integer.")
        Guess.SelectAll()
        Guess.Focus()
        Return
    End If
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    int guess;
    if (!Int32.TryParse(Guess.Text, out guess))
    {
        MessageBox.Show("Please enter an integer.");
        Guess.SelectAll();
        Guess.Focus();
        return;
    }
    ```

3. Successivamente, recuperare l'istanza `WorkflowApplicationInstance` dell'istanza del flusso di lavoro persistente. Un'istanza `WorkflowApplicationInstance` rappresenta un'istanza del flusso di lavoro persistente che non è ancora stata associata a una definizione del flusso di lavoro. In `DefinitionIdentity` dell'istanza `WorkflowApplicationInstance` è contenuto `WorkflowIdentity` dell'istanza del flusso di lavoro persistente. In questa esercitazione la classe di utilità `WorkflowVersionMap` viene usata per eseguire il mapping di `WorkflowIdentity` alla definizione del flusso di lavoro corretta. Una volta recuperata la definizione del flusso di lavoro, viene creata un'istanza `WorkflowApplication` usando la definizione del flusso di lavoro corretta.

    ```vb
    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = _
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)
    ```

    ```csharp
    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf =
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);
    ```

4. Una volta creata l'istanza `WorkflowApplication`, configurare l'archivio di istanze, i gestori del ciclo di vita del flusso di lavoro e le estensioni chiamando `ConfigureWorkflowApplication`. Questi passaggi devono essere effettuati ogni volta che viene creata una nuova istanza `WorkflowApplication` e prima che l'istanza del flusso di lavoro venga caricata nell'istanza `WorkflowApplication`. Una volta caricato il flusso di lavoro, viene ripreso con il tentativo dell'utente.

    ```vb
    ' Configure the extensions and lifecycle handlers.
    ' Do this before the instance is loaded. Once the instance is
    ' loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", userGuess)
    ```

    ```csharp
    // Configure the extensions and lifecycle handlers.
    // Do this before the instance is loaded. Once the instance is
    // loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", guess);
    ```

5. Infine, deselezionare la casella di testo del tentativo e preparare il form per accettare un altro tentativo.

    ```vb
    ' Clear the Guess textbox.
    Guess.Clear()
    Guess.Focus()
    ```

    ```csharp
    // Clear the Guess textbox.
    Guess.Clear();
    Guess.Focus();
    ```

    Nell'esempio seguente viene mostrato il gestore `EnterGuess_Click` completato.

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click
        If WorkflowInstanceId = Guid.Empty Then
            MessageBox.Show("Please select a workflow.")
            Return
        End If

        Dim userGuess As Integer
        If Not Int32.TryParse(Guess.Text, userGuess) Then
            MessageBox.Show("Please enter an integer.")
            Guess.SelectAll()
            Guess.Focus()
            Return
        End If

        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        ' Use the persisted WorkflowIdentity to retrieve the correct workflow
        ' definition from the dictionary.
        Dim wf As Activity = _
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

        ' Associate the WorkflowApplication with the correct definition
        Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

        ' Configure the extensions and lifecycle handlers.
        ' Do this before the instance is loaded. Once the instance is
        ' loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp)

        ' Load the workflow.
        wfApp.Load(instance)

        ' Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", userGuess)

        ' Clear the Guess textbox.
        Guess.Clear()
        Guess.Focus()
    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {
        if (WorkflowInstanceId == Guid.Empty)
        {
            MessageBox.Show("Please select a workflow.");
            return;
        }

        int guess;
        if (!Int32.TryParse(Guess.Text, out guess))
        {
            MessageBox.Show("Please enter an integer.");
            Guess.SelectAll();
            Guess.Focus();
            return;
        }

        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);

        // Use the persisted WorkflowIdentity to retrieve the correct workflow
        // definition from the dictionary.
        Activity wf =
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

        // Associate the WorkflowApplication with the correct definition
        var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

        // Configure the extensions and lifecycle handlers.
        // Do this before the instance is loaded. Once the instance is
        // loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp);

        // Load the workflow.
        wfApp.Load(instance);

        // Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", guess);

        // Clear the Guess textbox.
        Guess.Clear();
        Guess.Focus();
    }
    ```

## <a name="to-terminate-a-workflow"></a>Per terminare un flusso di lavoro

1. Aggiungere un gestore `Click` per `QuitGame`. Per aggiungere il gestore, passare alla **visualizzazione progettazione** per il form e fare doppio clic su `QuitGame` . Ogni volta che l'utente fa clic sul pulsante, il flusso di lavoro selezionato viene interrotto.

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. Aggiungere al gestore `QuitGame_Click` il codice riportato di seguito. Tramite il codice viene innanzitutto verificato che un flusso di lavoro venga selezionato nell'elenco di flussi di controllo. Successivamente viene caricata l'istanza persistente in un'istanza `WorkflowApplicationInstance`, viene usato `DefinitionIdentity` per determinare la definizione del flusso di lavoro corretta e, infine, viene inizializzata l'istanza `WorkflowApplication`. In seguito, le estensioni e i gestori del ciclo di vita del flusso di lavoro vengono configurati con una chiamata al metodo `ConfigureWorkflowApplication`. Una volta configurata, l'istanza `WorkflowApplication` viene caricata e viene chiamato `Terminate`.

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition.
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

    ' Configure the extensions and lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Terminate the workflow.
    wfApp.Terminate("User resigns.")
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

    // Configure the extensions and lifecycle handlers
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Terminate the workflow.
    wfApp.Terminate("User resigns.");
    ```

## <a name="to-build-and-run-the-application"></a>Per compilare ed eseguire l'applicazione

1. Fare doppio clic su **Program.cs** (o **Module1. vb**) in **Esplora soluzioni** per visualizzare il codice.

2. Aggiungere la seguente istruzione `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. Rimuovere o impostare come commento il codice di hosting del flusso di lavoro esistente da [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md)e sostituirlo con il codice seguente.

    ```vb
    Sub Main()
        Application.EnableVisualStyles()
        Application.Run(New WorkflowHostForm())
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        Application.EnableVisualStyles();
        Application.Run(new WorkflowHostForm());
    }
    ```

4. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e scegliere **proprietà**. Nella scheda **applicazione** specificare **applicazione Windows** per il tipo di **output**. Questo passaggio è facoltativo, ma se non viene effettuato, oltre al form viene visualizzata anche la finestra della console.

5. Premere CTRL+MAIUSC+B per compilare l'applicazione.

6. Verificare che **NumberGuessWorkflowHost** sia impostato come applicazione di avvio e premere CTRL + F5 per avviare l'applicazione.

7. Selezionare un intervallo per il gioco Guess e il tipo di flusso di lavoro da avviare, quindi fare clic su **nuovo gioco**. Immettere una supposizione nella casella **Guess** e fare clic su **go** per inviare l'ipotesi. Si noti che l'output dalle attività `WriteLine` viene visualizzato nel form.

8. Avviare diversi flussi di lavoro usando diversi tipi di flussi di lavoro e intervalli di numeri, immettere alcune ipotesi e passare tra i flussi di lavoro selezionando dall'elenco **ID istanza del flusso** di lavoro.

    Si noti che quando si passa a un nuovo flusso di lavoro, i tentativi precedenti e lo stato di avanzamento del flusso di lavoro non vengono visualizzati nella finestra di stato. Lo stato non è disponibile poiché non è stato acquisito e salvato da nessuna parte. Nel passaggio successivo dell'esercitazione, [procedura: creare un partecipante del rilevamento personalizzato](how-to-create-a-custom-tracking-participant.md), creare un partecipante del rilevamento personalizzato che salva queste informazioni.
