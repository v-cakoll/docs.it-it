---
title: Creare un'applicazione di servizio di Windows in Visual Studio
ms.date: 09/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
manager: douge
ms.openlocfilehash: 27acdac5d34b96dd04fec1bb763edec9077ff928
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46493607"
---
# <a name="walkthrough-create-a-windows-service-app"></a>Procedura dettagliata: Creare un'app di servizio di Windows

Questo articolo illustra come creare una semplice app di servizio di Windows in Visual Studio che scrive messaggi in un log eventi.

## <a name="create-a-service"></a>Creare un servizio

Le prime operazioni da effettuare sono la creazione del progetto e l'impostazione dei valori necessari per garantire il corretto funzionamento del servizio.

1. Sulla barra dei menu di Visual Studio scegliere **File** > **Nuovo** > **Progetto** (o premere **CTRL**+**MAIUSC**+**N**) per aprire la finestra di dialogo **Nuovo progetto**.

2. Cercare e selezionare il modello di progetto **Servizio Windows**. Espandere **Installato** > [**Visual C#** o **Visual Basic**] > **Desktop di Windows** o digitare **Servizio Windows** nella casella di ricerca in alto a destra.

   ![Modello Servizio Windows nella finestra di dialogo Nuovo progetto di Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > Se il modello **Servizio Windows** non è visualizzato, potrebbe essere necessario installare il carico di lavoro **Sviluppo per desktop .NET**. Nella finestra di dialogo **Nuovo progetto** fare clic sul collegamento **Apri il programma di installazione di Visual Studio** in basso a sinistra. In **Programma di installazione di Visual Studio** selezionare il carico di lavoro **Sviluppo per desktop .NET** e quindi scegliere **Modifica**.

3. Assegnare al progetto il nome **MyNewService** e quindi scegliere **OK**.

   Il modello di progetto include una classe di componente denominata `Service1` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>. Include gran parte del codice del servizio di base, ad esempio il codice per avviare il servizio.

## <a name="rename-the-service"></a>Rinominare il servizio

Rinominare il servizio da **Service1** a **MyNewService**.

1. Nella visualizzazione **Progettazione** per Service1.cs (o Service1.vb) fare clic sul collegamento per **passare alla visualizzazione Codice**. Fare clic con il pulsante destro del mouse su **Service1** e scegliere **Rinomina** dal menu di scelta rapida. Immettere **MyNewService** e quindi premere **INVIO** o fare clic su **Applica**.

2. Nella finestra **Proprietà** per **Service1.cs [Progettazione]** o **Service1.vb [Progettazione]** impostare il valore **ServiceName** su **MyNewService**.

3. In **Esplora soluzioni** rinominare **Service1.cs** in **MyNewService.cs** o rinominare **Service1.vb** in **MyNewService.vb**.

## <a name="add-features-to-the-service"></a>Aggiungere funzionalità al servizio

In questa sezione verrà aggiunto un log eventi personalizzato al servizio Windows. I log eventi non sono in alcun modo associati ai servizi Windows. Il componente <xref:System.Diagnostics.EventLog> viene usato qui come esempio del tipo di componente che è possibile aggiungere a un servizio di Windows.

### <a name="add-custom-event-log-functionality"></a>Aggiungere la funzionalità del log eventi personalizzato

1. In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza finestra di progettazione**.

2. Dalla sezione **Componenti** della **Casella degli strumenti**trascinare un componente <xref:System.Diagnostics.EventLog> nella finestra di progettazione.

3. In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza codice**.

4. Modificare il costruttore per definire un log eventi personalizzato:

   ```csharp
   public MyNewService()
   {
        InitializeComponent();

        eventLog1 = new System.Diagnostics.EventLog();
        if (!System.Diagnostics.EventLog.SourceExists("MySource"))
        {
            System.Diagnostics.EventLog.CreateEventSource(
                "MySource", "MyNewLog");
        }
        eventLog1.Source = "MySource";
        eventLog1.Log = "MyNewLog";
    }
   ```

   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

### <a name="define-what-occurs-when-the-service-starts"></a>Definire quello che accade quando il servizio viene avviato

Nell'editor di codice individuare il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> di cui è stato eseguito automaticamente l'override al momento della creazione del progetto. Aggiungere una riga di codice che scrive una voce nel log eventi all'avvio del servizio:

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

Poiché le applicazioni di servizio sono progettate per un'esecuzione di lunga durata, generalmente eseguono operazioni di polling o di monitoraggio nel sistema. Il monitoraggio viene impostato nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> . Il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> , tuttavia, non esegue effettivamente il monitoraggio. Il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> deve rispondere al sistema operativo dopo l'avvio del servizio, poiché non può scorrere in ciclo all'infinito o bloccarsi. Per impostare un semplice meccanismo di polling, è possibile usare il componente <xref:System.Timers.Timer?displayProperty=nameWithType>. Nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> impostare i parametri del componente e la proprietà <xref:System.Timers.Timer.Enabled%2A> su `true`. Il timer genera degli eventi nel codice periodicamente e, a quel punto, il servizio può svolgere la propria funzione di monitoraggio. A tale scopo, è possibile usare il codice seguente:

```csharp
// Set up a timer that triggers every minute.
System.Timers.Timer timer = new System.Timers.Timer();
timer.Interval = 60000; // 60 seconds
timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);
timer.Start();
```

```vb
' Set up a timer that triggers every minute.
Dim timer As System.Timers.Timer = New System.Timers.Timer()
timer.Interval = 60000 ' 60 seconds
AddHandler timer.Elapsed, AddressOf Me.OnTimer
timer.Start()
```

Aggiungere una variabile membro alla classe. Contiene l'identificatore dell'evento successivo da scrivere nel log eventi.

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

Aggiungere un nuovo metodo per gestire l'evento timer:

```csharp
public void OnTimer(object sender, System.Timers.ElapsedEventArgs args)
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

Potrebbe essere necessario eseguire le attività usando un thread di lavoro in background invece di eseguire tutto il lavoro sul thread principale. Per ulteriori informazioni, vedere <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.

### <a name="define-what-occurs-when-the-service-is-stopped"></a>Definire quello che accade quando il servizio viene arrestato

Aggiungere al metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> una riga di codice che aggiunge una voce nel log eventi all'arresto del servizio:

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a>Definire altre azioni del servizio

È possibile eseguire l'override dei metodi <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> e <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> per definire ulteriori operazioni di elaborazione del componente. L'esempio di codice seguente mostra come eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

Quando un servizio Windows viene installato mediante la classe <xref:System.Configuration.Install.Installer> , è necessario eseguire alcune azioni personalizzate. Visual Studio può creare questi programmi di installazione specificamente per un servizio Windows e aggiungerli al progetto.

## <a name="set-service-status"></a>Impostare lo stato del servizio

I servizi segnalano il relativo stato in Gestione controllo servizi, in modo che gli utenti possano stabilire se un servizio funziona correttamente. Per impostazione predefinita, i servizi che ereditano da <xref:System.ServiceProcess.ServiceBase> segnalano un set limitato di impostazioni di stato, tra cui Arrestato, In pausa e in esecuzione. Se l'avvio di un servizio richiede un po' di tempo, potrebbe essere utile segnalare lo stato Avvio in sospeso. È anche possibile implementare le impostazioni di stato Avvio in sospeso e Arresto in sospeso aggiungendo il codice che chiama la [funzione SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) di Windows.

Per implementare lo stato in sospeso del servizio:

1. Aggiungere un'istruzione `using` o una dichiarazione `Imports` per lo spazio dei nomi <xref:System.Runtime.InteropServices?displayProperty=nameWithType> nel file MyNewService.cs o MyNewService.vb:

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. Aggiungere il codice seguente in MyNewService.cs per dichiarare i valori `ServiceState` e per aggiungere una struttura per lo stato da usare in una chiamata di pInvoke:

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

3. A questo punto, nella classe `MyNewService` dichiarare la [funzione SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) usando [platform invoke](../interop/consuming-unmanaged-dll-functions.md):

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. Per implementare lo stato Avvio in sospeso, aggiungere il codice seguente all'inizio del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :

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

5. Aggiungere il codice per impostare lo stato su In esecuzione alla fine del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .

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

6. Ripetere questa procedura per il metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> (facoltativo).

> [!NOTE]
> La finestra di dialogo [Gestione controllo servizi](/windows/desktop/Services/service-control-manager) usa i membri `dwWaitHint` e `dwCheckpoint` della [struttura SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) per determinare il tempo di attesa per l'avvio o l'arresto di un servizio Windows. Se l'esecuzione dei metodi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> si prolunga, il servizio può richiedere più tempo chiamando di nuovo [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) con un valore `dwCheckPoint` incrementato.

## <a name="add-installers-to-the-service"></a>Aggiungere programmi di installazione al servizio

Prima di eseguire un servizio di Windows, è necessario installarlo, ovvero registrarlo con Gestione controllo servizi. È possibile aggiungere al progetto i programmi di installazione che gestiscono i dettagli di registrazione.

1. In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza finestra di progettazione**.

2. Fare clic sullo sfondo della finestra di progettazione per selezionare il servizio anziché il suo contenuto.

3. Aprire il menu di scelta rapida per la finestra di progettazione (se si sta usando un dispositivo di puntamento, fare clic con il pulsante destro del mouse all'interno della finestra), quindi scegliere **Aggiungi programma di installazione**.

   Per impostazione predefinita, al progetto viene aggiunta la classe di componente contenente due programmi di installazione. Il componente è denominato **ProjectInstaller**e i programmi di installazione in esso contenuti sono rispettivamente quello del servizio e quello del processo associato al servizio.

4. Nella visualizzazione **Progettazione** per **ProjectInstaller**scegliere **serviceInstaller1** per un progetto Visual C# o su **ServiceInstaller1** per un progetto Visual Basic.

5. Nella finestra **Proprietà** verificare che la proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> sia impostata su **MyNewService**.

6. Specificare un testo per la proprietà **Descrizione** , ad esempio "Servizio di esempio". Questo testo viene visualizzato nella finestra Servizi e consente all'utente di identificare il servizio e comprenderne la funzione.

7. Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> sul testo da visualizzare nella colonna **Nome** della finestra Servizi. Ad esempio, è possibile immettere "Nome visualizzato MyNewService". Questo nome può essere diverso dalla proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , che rappresenta il nome usato dal sistema (ad esempio, quando si usa il comando `net start` per avviare il servizio).

8. Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su <xref:System.ServiceProcess.ServiceStartMode.Automatic>.

     ![Proprietà del programma di installazione per un servizio di Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")

9. Nella finestra di progettazione scegliere **serviceProcessInstaller1** per un progetto Visual C# o **ServiceProcessInstaller1** per un progetto Visual Basic. Impostare la proprietà <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> su <xref:System.ServiceProcess.ServiceAccount.LocalSystem>. In questo modo il servizio verrà installato ed eseguito usando l'account di sistema locale.

    > [!IMPORTANT]
    > L'account <xref:System.ServiceProcess.ServiceAccount.LocalSystem> dispone di ampie autorizzazioni, tra cui la possibilità di scrivere nel log eventi. Usare questo account con attenzione, perché potrebbe aumentare il rischio di attacchi da parte di software dannoso. Per altre attività, è opportuno usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a tutti i server remoti. Questo esempio non riesce se si tenta di usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> perché sono necessarie le autorizzazioni per scrivere nel log eventi.

Per altre informazioni sui programmi di installazione, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).

## <a name="optional-set-startup-parameters"></a>(Facoltativo) Impostare i parametri di avvio

Un servizio di Windows, come qualsiasi altro file eseguibile, può accettare gli argomenti della riga di comando o i parametri di avvio. Quando si aggiunge il codice ai parametri di avvio del processo, gli utenti possono avviare il servizio con i parametri di avvio personalizzati usando la finestra Servizi nel Pannello di controllo di Windows. Tuttavia, questi parametri di avvio non vengono mantenuti al successivo avvio del servizio. Per impostare i parametri di avvio in modo permanente, è possibile impostarli nel Registro di sistema, come illustrato in questa procedura.

> [!NOTE]
> Prima di decidere di aggiungere parametri di avvio, valutare se sia l'approccio migliore per passare informazioni al servizio. Anche se i parametri di avvio sono facili da usare e da analizzare e gli utenti possono facilmente eseguirne l'override, potrebbero essere più difficili da individuare e usare senza documentazione. In generale, se il servizio richiede diversi parametri di avvio, provare a usare il Registro di sistema o un file di configurazione. Ogni servizio di Windows ha una voce nel Registro di sistema in **HKLM\System\CurrentControlSet\services**. Nella chiave del servizio è possibile usare la sottochiave **Parametri** per archiviare le informazioni a cui il servizio può accedere. È possibile usare i file di configurazione dell'applicazione per un servizio di Windows in modo analogo a come avviene per gli altri tipi di programmi. Per il codice di esempio, vedere <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.

Per aggiungere i parametri di avvio:

1. Nel metodo `Main` in Program.cs o in MyNewService.Designer.vb aggiungere un parametro di input da passare al costruttore del servizio:

   ```csharp
   static void Main(string[] args)
   {
       ServiceBase[] ServicesToRun;
       ServicesToRun = new ServiceBase[]
       {
           new MyNewService(args)
       };
       ServiceBase.Run(ServicesToRun);
   }
   ```

   ```vb
   Shared Sub Main(ByVal cmdArgs() As String)
       Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
       System.ServiceProcess.ServiceBase.Run(ServicesToRun)
   End Sub
   ```

2. Modificare il costruttore `MyNewService` come segue:

   ```csharp
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

        eventLog1 = new System.Diagnostics.EventLog();

        if (!System.Diagnostics.EventLog.SourceExists(eventSourceName))
        {
            System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName);
        }

        eventLog1.Source = eventSourceName;
        eventLog1.Log = logName;
   }
   ```

   ```vb
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
       eventLog1 = New System.Diagnostics.EventLog()
       If (Not System.Diagnostics.EventLog.SourceExists(eventSourceName)) Then
           System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   Questo codice imposta l'origine evento e il nome log in base ai parametri di avvio forniti oppure usa i valori predefiniti se non vengono forniti argomenti.

3. Per specificare gli argomenti della riga di comando, aggiungere il codice seguente alla classe `ProjectInstaller` in ProjectInstaller.cs o ProjectInstaller.vb:

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

   Questo codice modifica la chiave del Registro di sistema **ImagePath**, che in genere contiene il percorso completo dell'eseguibile per il servizio di Windows, aggiungendo i valori dei parametri predefiniti. Le virgolette che racchiudono il percorso, e ogni singolo parametro, sono necessarie per il corretto avvio del servizio. Per modificare i parametri di avvio per questo servizio di Windows, gli utenti possono modificare i parametri specificati nella chiave del Registro di sistema **ImagePath**, anche se l'approccio migliore consiste nell'eseguire la modifica a livello di codice ed esporre le funzionalità agli utenti in modo intuitivo, ad esempio in un'utilità di configurazione o gestione.

## <a name="build-the-service"></a>Compilare il servizio

1. In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.

   Verranno visualizzate le pagine delle proprietà per il progetto.

2. Nell'elenco **Oggetto di avvio** della scheda **Applicazione** scegliere **MyNewService.Program**.

3. In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto, quindi scegliere **Compila** per compilare il progetto (o premere **CTRL**+**MAIUSC**+**B**).

## <a name="install-the-service"></a>Installare il servizio

Una volta compilato il servizio Windows, è possibile installarlo. Per installare un servizio di Windows, è necessario avere le credenziali di amministratore nel computer in cui viene eseguita l'installazione.

1. Aprire il **Prompt dei comandi per gli sviluppatori per Visual Studio** con credenziali amministrative. Se si usa un mouse, fare clic con il pulsante destro del mouse su **Developer Command Prompt for VS 2017** (Prompt dei comandi per gli sviluppatori per VS 2017) nel menu Start di Windows, quindi scegliere **Altro** > **Esegui come amministratore**.

2. Nella finestra **Prompt dei comandi per gli sviluppatori** passare alla cartella contenente l'output del progetto. Per impostazione predefinita, è la sottodirectory *\bin\Debug* del progetto.

3. Immettere il comando seguente:

    ```shell
    installutil.exe MyNewService.exe
    ```

    Se il servizio viene installato correttamente, tramite il file **installutil.exe** viene segnalato l'esito positivo. Se il sistema non riesce a trovare **InstallUtil.exe**, assicurarsi che sia presente nel computer in uso. Questo strumento viene installato con .NET Framework nella cartella *%windir%\Microsoft.NET\Framework[64]\\[versione framework]*. Il percorso predefinito per la versione a 32 bit, ad esempio, è *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.

    Se il processo **installutil.exe** segnala un errore, controllare il log di installazione per determinarne il motivo. Per impostazione predefinita, il log è nella stessa cartella del file eseguibile del servizio. L'installazione potrebbe non riuscire se la classe <xref:System.ComponentModel.RunInstallerAttribute> non è presente nella classe `ProjectInstaller`, se l'attributo non è impostato su **true** o se la classe `ProjectInstaller` non è contrassegnata come **public**.

Per altre informazioni, vedere [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="start-and-run-the-service"></a>Avviare ed eseguire il servizio

1. In Windows aprire l'app desktop **Servizi**. Premere **Windows**+**R** per aprire la casella **Esegui** e quindi immettere **services.msc** e premere **INVIO** o fare clic su **OK**.

     Il servizio verrà elencato in **Servizi**, in ordine alfabetico in base al nome visualizzato impostato.

     ![MyNewService nella finestra Servizi.](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. In **Servizi** aprire il menu di scelta rapida per il servizio, quindi scegliere **Avvia**.

3. Per arrestare il servizio, aprire il menu di scelta rapida per il servizio, quindi scegliere **Arresta**.

4. Dalla riga di comando è possibile usare i comandi `net start ServiceName` e `net stop ServiceName` per avviare e arrestare il servizio (facoltativo).

### <a name="verify-the-event-log-output-of-your-service"></a>Verificare l'output del log eventi del servizio

1. Per aprire il **Visualizzatore eventi**, iniziare a digitare **Visualizzatore eventi** nella casella di ricerca sulla barra della applicazioni di Windows e quindi selezionare **Visualizzatore eventi** nei risultati della ricerca.

   > [!TIP]
   > In Visual Studio è possibile accedere al log eventi aprendo **Esplora server** (tastiera: **CTRL**+**ALT**+**S**) ed espandendo il nodo **Log eventi** per il computer locale.

2. Nel **Visualizzatore eventi** espandere **Registri applicazioni e servizi**.

3. Individuare l'elenco per **MyNewLog** (o **MyLogFile1**, se è stata seguita la procedura facoltativa per aggiungere gli argomenti della riga di comando) ed espanderlo. Verranno visualizzate le voci per le due azioni (avvio e arresto) eseguite dal servizio.

     ![Usare il Visualizzatore eventi per visualizzare le voci del log eventi](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a>Disinstallare il servizio

1. Aprire il **Prompt dei comandi per gli sviluppatori per Visual Studio** con credenziali amministrative.

2. Nella finestra del prompt dei comandi passare alla cartella che contiene l'output del progetto.

3. Immettere il comando seguente:

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   Se il servizio viene disinstallato correttamente, tramite il file **installutil.exe** viene segnalato che il servizio è stato rimosso correttamente. Per altre informazioni, vedere [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="next-steps"></a>Passaggi successivi

Dopo aver creato il servizio, potrebbe essere necessario creare un programma di installazione autonomo che altri utenti possono usare per installare il servizio di Windows. ClickOnce non supporta i servizi di Windows, ma è possibile usare [WiX Toolset](http://wixtoolset.org/) per creare un programma di installazione per un servizio di Windows. Per altre idee, vedere [Creare un pacchetto di installazione](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).

Per inviare comandi al servizio installato, è anche possibile usare il componente <xref:System.ServiceProcess.ServiceController>.

È possibile usare il programma di installazione per creare un log eventi durante l'installazione dell'applicazione, anziché in fase di esecuzione. Il log eventi verrà inoltre eliminato dal programma di installazione durante la disinstallazione dell'applicazione. Per altre informazioni, vedere la pagina di riferimento <xref:System.Diagnostics.EventLogInstaller> .

## <a name="see-also"></a>Vedere anche

- [Applicazioni di servizi di Windows](../../../docs/framework/windows-services/index.md)
- [Introduzione alle applicazioni di servizio di Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Procedura: Eseguire il debug di applicazioni di servizio di Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [Servizi (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
