---
title: "Esercitazione: creare un'app di servizio Windows"
ms.date: 03/27/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: e5ff40d8413acf64e7a8a129a7b268f58780d591
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053475"
---
# <a name="tutorial-create-a-windows-service-app"></a>Esercitazione: creare un'app di servizio Windows

Questo articolo illustra come creare in Visual Studio un'app di servizio di Windows che scrive messaggi in un log eventi.

## <a name="create-a-service"></a>Creare un servizio

Le prime operazioni da effettuare sono la creazione del progetto e l'impostazione dei valori necessari per garantire il corretto funzionamento del servizio.

1. Dal menu **File** di Visual Studio scegliere **Nuovo** > **Progetto** (o premere **CTRL**+**MAIUSC**+**N**) per aprire la finestra **Nuovo progetto**.

2. Cercare e selezionare il modello di progetto **Servizio di Windows (.NET Framework)**. Per trovarlo, espandere **Installati** e **Visual C# ** o **Visual Basic** e quindi selezionare **Windows Desktop**. In alternativa, immettere *Servizio di Windows* nella casella di ricerca in alto a destra e premere **Invio**.

   ![Modello Servizio Windows nella finestra di dialogo Nuovo progetto di Visual Studio](./media/new-project-dialog.png)

   > [!NOTE]
   > Se il modello di **servizio Windows** non è visibile, potrebbe essere necessario installare il carico di lavoro sviluppo di applicazioni **desktop .NET** :
   >
   > Nella finestra di dialogo **Nuovo progetto** selezionare **Apri il programma di installazione di Visual Studio** in basso a sinistra. Selezionare il carico di lavoro **Sviluppo per desktop .NET** e quindi selezionare **Modifica**.

3. Per **Nome** immettere *MyNewService* e quindi selezionare **OK**.

   Verrà visualizzata la scheda **Progettazione** (**Service1.cs [Progettazione]** oppure **Service1.vb [Progettazione]**).

   Il modello di progetto include una classe di componente denominata `Service1` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>. Include gran parte del codice del servizio di base, ad esempio il codice per avviare il servizio.

## <a name="rename-the-service"></a>Rinominare il servizio

Rinominare il servizio da **Service1** a **MyNewService**.

1. In **Esplora soluzioni** selezionare **Service1.cs** o **Service1.vb** e quindi scegliere **Rinomina** dal menu di scelta rapida. Rinominare il file in **MyNewService.cs** o in **MyNewService.vb** e quindi premere **Invio**

    Una finestra popup chiederà se si vogliono rinominare tutti i riferimenti all'elemento di codice *Service1*.

2. Nella finestra popup selezionare **Sì**.

    ![Domanda sulla ridenominazione](./media/windows-service-rename.png "Domanda sulla ridenominazione del servizio di Windows")

3. Nella scheda **Progettazione** selezionare **Proprietà** dal menu di scelta rapida. Nella finestra **Proprietà** cambiare il valore di **ServiceName** in *MyNewService*.

    ![Proprietà del servizio](./media/windows-service-properties.png "Proprietà del servizio di Windows")

4. Selezionare **Salva tutto** dal menu **File**.

## <a name="add-features-to-the-service"></a>Aggiungere funzionalità al servizio

In questa sezione verrà aggiunto un log eventi personalizzato al servizio Windows. Il componente <xref:System.Diagnostics.EventLog> è un esempio del tipo di componente che è possibile aggiungere a un servizio di Windows.

### <a name="add-custom-event-log-functionality"></a>Aggiungere la funzionalità del log eventi personalizzato

1. Dal menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb** in **Esplora soluzioni** scegliere **Visualizza finestra di progettazione**.

2. Nella **Casella degli strumenti** espandere **Componenti** e quindi trascinare il componente **EventLog** nella scheda **Service1.cs [Progettazione]** o **Service1.vb [Progettazione]**.

3. Dal menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb** in **Esplora soluzioni** scegliere **Visualizza codice**.

4. Definire un log eventi personalizzato. Per C#, modificare il costruttore `MyNewService()` esistente. Per Visual Basic, aggiungere il costruttore `New()`:

   [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. Aggiungere un'istruzione `using` a **MyNewService.cs** (se non esiste già) o un'istruzione `Imports` a **MyNewService.vb** per lo spazio dei nomi <xref:System.Diagnostics?displayProperty=nameWithType>:

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. Selezionare **Salva tutto** dal menu **File**.

### <a name="define-what-occurs-when-the-service-starts"></a>Definire quello che accade quando il servizio viene avviato

Nell'editor di codice per **MyNewService.cs** o **MyNewService.vb** individuare il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Visual Studio ha creato automaticamente una definizione di metodo vuota quando è stato creato il progetto. Aggiungere codice che scriva una voce nel log eventi all'avvio del servizio:

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a>Polling

Poiché le applicazioni di servizio sono progettate per un'esecuzione di lunga durata, generalmente eseguono operazioni di polling o di monitoraggio del sistema, che vengono configurate nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Il metodo `OnStart` deve rispondere al sistema operativo dopo l'avvio del servizio, perché il sistema non rimanga bloccato.

Per impostare un semplice meccanismo di polling, usare il componente <xref:System.Timers.Timer?displayProperty=nameWithType>. Il timer genera un evento <xref:System.Timers.Timer.Elapsed> a intervalli regolari. In corrispondenza di questo evento il servizio può eseguire il monitoraggio. Per usare il componente <xref:System.Timers.Timer> eseguire le operazioni seguenti:

- Impostare le proprietà del componente <xref:System.Timers.Timer> nel metodo `MyNewService.OnStart`.
- Avviare il timer tramite una chiamata al metodo <xref:System.Timers.Timer.Start%2A>.

##### <a name="set-up-the-polling-mechanism"></a>Configurare il meccanismo di polling.

1. Aggiungere il codice seguente nell'evento `MyNewService.OnStart` per configurare il meccanismo di polling:

   ```csharp
   // Set up a timer that triggers every minute.
   Timer timer = new Timer();
   timer.Interval = 60000; // 60 seconds
   timer.Elapsed += new ElapsedEventHandler(this.OnTimer);
   timer.Start();
   ```

   ```vb
   ' Set up a timer that triggers every minute.
   Dim timer As Timer = New Timer()
   timer.Interval = 60000 ' 60 seconds
   AddHandler timer.Elapsed, AddressOf Me.OnTimer
   timer.Start()
   ```

2. Aggiungere un'istruzione `using` a **MyNewService.cs** o un'istruzione `Imports` a **MyNewService.vb** per lo spazio dei nomi <xref:System.Timers?displayProperty=nameWithType>:

   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```

3. Nella classe `MyNewService` aggiungere il metodo `OnTimer` per gestire l'evento <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType>:

   ```csharp
   public void OnTimer(object sender, ElapsedEventArgs args)
   {
       // TODO: Insert monitoring activities here.
       eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);
   }
   ```

   ```vb
   Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)
      ' TODO: Insert monitoring activities here.
      eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)
      eventId = eventId + 1
   End Sub
   ```

4. Nella classe `MyNewService` aggiungere una variabile membro. Questa contiene l'identificatore dell'evento successivo da scrivere nel log eventi:

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

Invece di eseguire tutto il lavoro nel thread principale, è possibile eseguire le attività tramite thread di lavoro in background. Per altre informazioni, vedere <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.

### <a name="define-what-occurs-when-the-service-is-stopped"></a>Definire quello che accade quando il servizio viene arrestato

Inserire nel metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> una riga di codice che aggiunga una voce nel log eventi all'arresto del servizio:

[!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a>Definire altre azioni del servizio

È possibile eseguire l'override dei metodi <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> e <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> per definire ulteriori operazioni di elaborazione del componente.

Il codice seguente illustra come eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> nella classe `MyNewService`:

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

## <a name="set-service-status"></a>Impostare lo stato del servizio

I servizi segnalano il proprio stato a [Gestione controllo servizi](/windows/desktop/Services/service-control-manager), in modo che gli utenti possano stabilire se un servizio funziona correttamente. Per impostazione predefinita, un servizio che eredita da <xref:System.ServiceProcess.ServiceBase> segnala un set limitato di impostazioni di stato, ovvero SERVICE_STOPPED, SERVICE_PAUSED e SERVICE_RUNNING. Se l'avvio di un servizio richiede tempo, è utile segnalare lo stato SERVICE_START_PENDING.

È possibile implementare le impostazioni di stato SERVICE_START_PENDING e SERVICE_STOP_PENDING aggiungendo codice che chiami la funzione [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) di Windows.

### <a name="implement-service-pending-status"></a>Implementare lo stato corrispondente al servizio in sospeso

1. Aggiungere un'istruzione `using` a **MyNewService.cs** o un'istruzione `Imports` a **MyNewService.vb** per lo spazio dei nomi <xref:System.Runtime.InteropServices?displayProperty=nameWithType>:

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. Aggiungere il codice seguente in **MyNewService.cs** o in **MyNewService.vb** per dichiarare i valori di `ServiceState` e per aggiungere una struttura per lo stato da usare in una chiamata platform invoke:

    ```csharp
    public enum ServiceState
    {
        SERVICE_STOPPED = 0x00000001,
        SERVICE_START_PENDING = 0x00000002,
        SERVICE_STOP_PENDING = 0x00000003,
        SERVICE_RUNNING = 0x00000004,
        SERVICE_CONTINUE_PENDING = 0x00000005,
        SERVICE_PAUSE_PENDING = 0x00000006,
        SERVICE_PAUSED = 0x00000007,
    }

    [StructLayout(LayoutKind.Sequential)]
    public struct ServiceStatus
    {
        public int dwServiceType;
        public ServiceState dwCurrentState;
        public int dwControlsAccepted;
        public int dwWin32ExitCode;
        public int dwServiceSpecificExitCode;
        public int dwCheckPoint;
        public int dwWaitHint;
    };
    ```

    ```vb
    Public Enum ServiceState
        SERVICE_STOPPED = 1
        SERVICE_START_PENDING = 2
        SERVICE_STOP_PENDING = 3
        SERVICE_RUNNING = 4
        SERVICE_CONTINUE_PENDING = 5
        SERVICE_PAUSE_PENDING = 6
        SERVICE_PAUSED = 7
    End Enum

    <StructLayout(LayoutKind.Sequential)>
    Public Structure ServiceStatus
        Public dwServiceType As Long
        Public dwCurrentState As ServiceState
        Public dwControlsAccepted As Long
        Public dwWin32ExitCode As Long
        Public dwServiceSpecificExitCode As Long
        Public dwCheckPoint As Long
        Public dwWaitHint As Long
    End Structure
    ```

    > [!NOTE]
    > La finestra di dialogo Gestione controllo servizi usa i membri `dwWaitHint` e `dwCheckpoint` della [struttura SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) per determinare il tempo di attesa per l'avvio o l'arresto di un servizio Windows. Se l'esecuzione dei metodi `OnStart` e `OnStop` è prolungata, il servizio può richiedere più tempo chiamando di nuovo `SetServiceStatus` con un valore di `dwCheckPoint` incrementato.

3. Nella classe `MyNewService` dichiarare la funzione [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) usando [platform invoke](../interop/consuming-unmanaged-dll-functions.md):

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. Per implementare lo stato SERVICE_START_PENDING, aggiungere il codice seguente all'inizio del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>:

    ```csharp
    // Update the service state to Start Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Start Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

5. Aggiungere codice alla fine del metodo `OnStart` per impostare lo stato su SERVICE_RUNNING:

    ```csharp
    // Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

6. (Facoltativo) Se <xref:System.ServiceProcess.ServiceBase.OnStop%2A> è un metodo a esecuzione prolungata, ripetere questa procedura nel metodo `OnStop`. Implementare lo stato SERVICE_STOP_PENDING e restituire lo stato SERVICE_STOPPED prima che il metodo `OnStop` esca.

   Ad esempio:

    ```csharp
    // Update the service state to Stop Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);

    // Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Stop Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)

    ' Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

## <a name="add-installers-to-the-service"></a>Aggiungere programmi di installazione al servizio

Prima di eseguire un servizio di Windows, è necessario installarlo, ovvero registrarlo con Gestione controllo servizi. Per gestire i dettagli della registrazione, aggiungere programmi di installazione al progetto.

1. Dal menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb** in **Esplora soluzioni** scegliere **Visualizza finestra di progettazione**.

2. Nella visualizzazione **Progettazione** selezionare l'area di sfondo e quindi scegliere **Aggiungi programma di installazione** dal menu di scelta rapida.

     Per impostazione predefinita, Visual Studio aggiunge al progetto una classe di componenti denominata `ProjectInstaller`, contenente due programmi di installazione. Questi programmi di installazione sono destinati al servizio e al processo associato al servizio stesso.

3. Nella visualizzazione **Progettazione** per **ProjectInstaller** selezionare **serviceInstaller1** per un progetto Visual C# o **ServiceInstaller1** per un progetto Visual Basic e quindi scegliere **Proprietà** dal menu di scelta rapida.

4. Nella finestra **Proprietà** verificare che la proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> sia impostata su **MyNewService**.

5. Aggiungere testo alla proprietà <xref:System.ServiceProcess.ServiceInstaller.Description%2A>, ad esempio *A sample service* (Servizio di esempio).

     Questo testo, che viene visualizzato nella colonna **Descrizione** della finestra **Servizi**, descrive il servizio all'utente.

    ![Descrizione del servizio nella finestra Servizi. ](./media/windows-service-description.png "Descrizione del servizio")

6. Aggiungere testo alla proprietà <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A>, ad esempio, *MyNewService Display Name* (Nome visualizzato di MyNewService).

     Questo testo viene visualizzato nella colonna **Nome visualizzato** della finestra **Servizi**. Questo nome può essere diverso dalla proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>, che corrisponde al nome usato dal sistema, ad esempio il nome usato con il comando `net start` per avviare il servizio.

7. Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su <xref:System.ServiceProcess.ServiceStartMode.Automatic> dall'elenco a discesa.

8. Al termine, la finestra **Proprietà** dovrebbe avere l'aspetto della figura seguente:

     ![Proprietà del programma di installazione per un servizio di Windows](./media/windows-service-installer-properties.png "Proprietà del programma di installazione di un servizio di Windows")

9. Nella visualizzazione **Progettazione** per **ProjectInstaller** scegliere **serviceProcessInstaller1** per un progetto Visual C# o **ServiceProcessInstaller1** per un progetto Visual Basic e quindi scegliere **Proprietà** dal menu di scelta rapida. Impostare la proprietà <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> su <xref:System.ServiceProcess.ServiceAccount.LocalSystem> dall'elenco a discesa.

     Questa impostazione consente di installare ed eseguire il servizio tramite l'account di sistema locale.

    > [!IMPORTANT]
    > L'account <xref:System.ServiceProcess.ServiceAccount.LocalSystem> dispone di ampie autorizzazioni, tra cui la possibilità di scrivere nel log eventi. Usare questo account con attenzione, perché potrebbe aumentare il rischio di attacchi da parte di software dannoso. Per altre attività, è opportuno usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a tutti i server remoti. Questo esempio non riesce se si tenta di usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> perché sono necessarie le autorizzazioni per scrivere nel log eventi.

Per altre informazioni sui programmi di installazione, vedere [procedura: aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).

## <a name="optional-set-startup-parameters"></a>(Facoltativo) Impostare i parametri di avvio

> [!NOTE]
> Prima di decidere di aggiungere parametri di avvio, valutare se sia l'approccio migliore per passare informazioni al servizio. Anche se i parametri di avvio sono facili da usare e da analizzare e gli utenti possono facilmente eseguirne l'override, possono essere più difficili da individuare e da usare senza documentazione. In genere, se il servizio richiede diversi parametri di avvio, è consigliabile usare il Registro di sistema o un file di configurazione.

Un servizio di Windows può accettare argomenti della riga di comando o parametri di avvio. Quando si aggiunge il codice ai parametri di avvio del processo, gli utenti possono avviare il servizio con parametri di avvio personalizzati nella finestra delle proprietà del servizio. Questi parametri di avvio, tuttavia, non vengono mantenuti al successivo avvio del servizio. Per impostare parametri di avvio in modo permanente, impostarli nel Registro di sistema.

Ogni servizio di Windows ha una voce del Registro di sistema nella sottochiave **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services**. Nella sottochiave di ogni servizio usare la sottochiave **Parameters** per archiviare le informazioni a cui il servizio può accedere. È possibile usare i file di configurazione dell'applicazione per un servizio di Windows in modo analogo a come avviene per gli altri tipi di programmi. Per codice di esempio, vedere <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.

### <a name="to-add-startup-parameters"></a>Per aggiungere parametri di avvio

1. Selezionare **Program.cs** o **MyNewService.Designer.vb** e quindi scegliere **Visualizza codice** dal menu di scelta rapida. Nel metodo `Main` modificare il codice aggiungendo un parametro di input e passare quest'ultimo al costruttore del servizio:

   [!code-csharp[VbRadconService](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/Program-add-parameter.cs?highlight=1,6)]
   [!code-vb[VbRadconService](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.Designer-add-parameter.vb?highlight=1-2)]

2. In **MyNewService.cs** o **MyNewService.vb** modificare il costruttore `MyNewService` in modo che elabori il parametro di input come segue:

   ```csharp
   using System.Diagnostics;

   public MyNewService(string[] args)
   {
       InitializeComponent();

       string eventSourceName = "MySource";
       string logName = "MyNewLog";

       if (args.Length > 0)
       {
          eventSourceName = args[0];
       }

       if (args.Length > 1)
       {
           logName = args[1];
       }

       eventLog1 = new EventLog();

       if (!EventLog.SourceExists(eventSourceName))
       {
           EventLog.CreateEventSource(eventSourceName, logName);
       }

       eventLog1.Source = eventSourceName;
       eventLog1.Log = logName;
   }
   ```

   ```vb
   Imports System.Diagnostics

   Public Sub New(ByVal cmdArgs() As String)
       InitializeComponent()
       Dim eventSourceName As String = "MySource"
       Dim logName As String = "MyNewLog"
       If (cmdArgs.Count() > 0) Then
           eventSourceName = cmdArgs(0)
       End If
       If (cmdArgs.Count() > 1) Then
           logName = cmdArgs(1)
       End If
       eventLog1 = New EventLog()
       If (Not EventLog.SourceExists(eventSourceName)) Then
           EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   Questo codice imposta l'origine e il nome del log dell'evento in base ai parametri di avvio specificati dall'utente. Se non vengono specificati argomenti, usa i valori predefiniti.

3. Per specificare gli argomenti della riga di comando, aggiungere il codice seguente alla `ProjectInstaller` classe in **ProjectInstaller.cs**o **ProjectInstaller. vb**:

   ```csharp
   protected override void OnBeforeInstall(IDictionary savedState)
   {
       string parameter = "MySource1\" \"MyLogFile1";
       Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
       base.OnBeforeInstall(savedState);
   }
   ```

   ```vb
   Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
       Dim parameter As String = "MySource1"" ""MyLogFile1"
       Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
       MyBase.OnBeforeInstall(savedState)
   End Sub
   ```

   In genere, questo valore contiene il percorso completo del file eseguibile per il servizio di Windows. Perché il servizio venga avviato correttamente, è necessario usare le virgolette per il percorso e per ogni singolo parametro. È possibile cambiare i parametri nella voce del Registro di sistema **ImagePath** per cambiare i parametri di avvio del servizio di Windows. Una soluzione migliore, tuttavia, consiste nel cambiare il valore a livello di codice e nell'esporre la funzionalità in un modo semplice da usare, ad esempio tramite un'utilità di gestione o di configurazione.

## <a name="build-the-service"></a>Compilare il servizio

1. In **Esplora soluzioni** scegliere **Proprietà** dal menu di scelta rapida del progetto **MyNewService**.

   Verranno visualizzate le pagine delle proprietà per il progetto.

2. Nell'elenco **Oggetto di avvio** della scheda **Applicazione** scegliere **MyNewService.Program** o **Sub Main** per i progetti Visual Basic.

3. Per compilare il progetto, in **Esplora soluzioni** scegliere **Compila** dal menu di scelta rapida del progetto o premere **CTRL**+**MAIUSC**+**B**.

## <a name="install-the-service"></a>Installare il servizio

Una volta compilato il servizio Windows, è possibile installarlo. Per installare un servizio di Windows, è necessario avere credenziali di amministratore per il computer in cui il servizio è installato.

1. Aprire il [Prompt dei comandi per gli sviluppatori per Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) con credenziali amministrative. Dal menu **Start** di Windows selezionare **Prompt dei comandi per gli sviluppatori per VS 2017** nella cartella di Visual Studio e quindi selezionare **Altro** > **Esegui come amministratore** dal menu di scelta rapida.

2. Nella finestra **Prompt dei comandi per gli sviluppatori per Visual Studio** passare alla cartella contenente l'output del progetto, per impostazione predefinita la sottodirectory *\bin\Debug* del progetto.

3. Immettere il comando seguente:

    ```shell
    installutil MyNewService.exe
    ```

    Se il servizio viene installato correttamente, il comando segnala l'esito positivo.

    Se il sistema non riesce a trovare *installutil.exe*, assicurarsi che sia presente nel computer in uso. Questo strumento viene installato con il .NET Framework alla cartella *%windir%\Microsoft.NET\Framework [64\\&lt;&gt;] versione del Framework*. Il percorso predefinito per la versione a 64 bit, ad esempio, è *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.

    Se il processo **installutil.exe** ha esito negativo, controllare il log di installazione per determinarne il motivo. Per impostazione predefinita, il log è nella stessa cartella del file eseguibile del servizio. L'installazione può non riuscire se:
    - La classe <xref:System.ComponentModel.RunInstallerAttribute> non è presente nella classe `ProjectInstaller`.
    - L'attributo non è impostato su `true`.
    - La classe `ProjectInstaller` non è definita come `public`.

Per altre informazioni, vedere [How to: install and Uninstall Services](how-to-install-and-uninstall-services.md).

## <a name="start-and-run-the-service"></a>Avviare ed eseguire il servizio

1. In Windows aprire l'app desktop **Servizi**. Premere **Windows**+**R** per aprire la casella **Esegui** , immettere *Services. msc*, quindi premere **invio** o fare clic su **OK**.

     Il servizio verrà elencato in **Servizi**, in ordine alfabetico in base al nome visualizzato impostato.

     ![MyNewService nella finestra Servizi.](./media/windowsservices-serviceswindow.PNG)

2. Per avviare il servizio, scegliere **Avvia** dal menu di scelta rapida del servizio.

3. Per arrestare il servizio, scegliere **Arresta** dal menu di scelta rapida del servizio.

4. (Facoltativo) Dalla riga di comando usare i comandi **net start &lt;nome servizio&gt;** e **net stop &lt;nome servizio&gt;** per avviare e arrestare il servizio.

### <a name="verify-the-event-log-output-of-your-service"></a>Verificare l'output del log eventi del servizio

1. In Windows aprire l'app desktop **Visualizzatore eventi**. Immettere *Visualizzatore eventi* nella barra di ricerca di Windows e quindi selezionare **Visualizzatore eventi** dai risultati della ricerca.

   > [!TIP]
   > In Visual Studio è possibile accedere ai log eventi aprendo **Esplora server** dal menu **Visualizza**, o premendo **CTRL**+**ALT**+**S**, ed espandendo il nodo **Log eventi** per il computer locale.

2. Nel **Visualizzatore eventi** espandere **Registri applicazioni e servizi**.

3. Individuare l'elenco per **MyNewLog** (o **MyLogFile1**, se è stata seguita la procedura per aggiungere argomenti della riga di comando) ed espanderlo. Verranno visualizzate le voci per le due azioni (avvio e arresto) eseguite dal servizio.

     ![Usare il Visualizzatore eventi per visualizzare le voci del log eventi](./media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a>Pulire le risorse

Se l'app del servizio di Windows non è più necessaria, è possibile rimuoverla.

1. Aprire il **Prompt dei comandi per gli sviluppatori per Visual Studio** con credenziali amministrative.

2. Nella finestra **Prompt dei comandi per gli sviluppatori per Visual Studio** passare alla cartella contenente l'output del progetto.

3. Immettere il comando seguente:

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   Se il servizio viene disinstallato correttamente, il comando segnala che il servizio è stato rimosso correttamente. Per altre informazioni, vedere [How to: install and Uninstall Services](how-to-install-and-uninstall-services.md).

## <a name="next-steps"></a>Passaggi successivi

Dopo aver creato il servizio, è possibile:

- Creare un programma di installazione autonomo che gli altri utenti possono usare per installare il servizio di Windows. Usare il [set di strumenti WiX](https://wixtoolset.org/) per creare un programma di installazione per un servizio di Windows. Per altre idee, vedere [Creare un pacchetto di installazione](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).

- Esaminare il componente <xref:System.ServiceProcess.ServiceController>, che consente di inviare comandi al servizio installato.

- Anziché creare il log eventi durante l'esecuzione dell'applicazione, crearlo durante l'installazione dell'applicazione stessa tramite il programma di installazione. Il log eventi viene eliminato dal programma di installazione quando si disinstalla l'applicazione. Per altre informazioni, vedere <xref:System.Diagnostics.EventLogInstaller>.

## <a name="see-also"></a>Vedere anche

- [Applicazioni di servizi di Windows](index.md)
- [Introduzione alle applicazioni di servizio di Windows](introduction-to-windows-service-applications.md)
- [Procedura: Eseguire il debug di applicazioni di servizio di Windows](how-to-debug-windows-service-applications.md)
- [Servizi (Windows)](/windows/desktop/Services/services)
