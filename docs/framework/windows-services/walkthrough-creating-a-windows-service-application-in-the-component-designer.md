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
ms.openlocfilehash: 52c2f64bbb71e07dcab1fd7cd42662f9ed2c8445
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2019
ms.locfileid: "56665030"
---
# <a name="walkthrough-create-a-windows-service-app"></a><span data-ttu-id="47ee3-102">Procedura dettagliata: Creare un'app di servizio di Windows</span><span class="sxs-lookup"><span data-stu-id="47ee3-102">Walkthrough: Create a Windows service app</span></span>

<span data-ttu-id="47ee3-103">Questo articolo illustra come creare una semplice app di servizio di Windows in Visual Studio che scrive messaggi in un log eventi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-103">This article demonstrates how to create a simple Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="47ee3-104">Creare un servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-104">Create a service</span></span>

<span data-ttu-id="47ee3-105">Le prime operazioni da effettuare sono la creazione del progetto e l'impostazione dei valori necessari per garantire il corretto funzionamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-105">To begin, create the project and set values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="47ee3-106">Sulla barra dei menu di Visual Studio scegliere **File** > **Nuovo** > **Progetto** (o premere **CTRL**+**MAIUSC**+**N**) per aprire la finestra di dialogo **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-106">In Visual Studio, on the menu bar, choose **File** > **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** dialog.</span></span>

2. <span data-ttu-id="47ee3-107">Cercare e selezionare il modello di progetto **Servizio Windows**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-107">Navigate to and select the **Windows Service** project template.</span></span> <span data-ttu-id="47ee3-108">Espandere **Installato** > [**Visual C#** o **Visual Basic**] > **Desktop di Windows** o digitare **Servizio Windows** nella casella di ricerca in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="47ee3-108">Expand **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, or type **Windows Service** in the search box on the upper right.</span></span>

   ![Modello Servizio Windows nella finestra di dialogo Nuovo progetto di Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="47ee3-110">Se il modello **Servizio Windows** non è visualizzato, potrebbe essere necessario installare il carico di lavoro **Sviluppo per desktop .NET**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-110">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload.</span></span> <span data-ttu-id="47ee3-111">Nella finestra di dialogo **Nuovo progetto** fare clic sul collegamento **Apri il programma di installazione di Visual Studio** in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="47ee3-111">In the **New Project** dialog, click the link that says **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="47ee3-112">In **Programma di installazione di Visual Studio** selezionare il carico di lavoro **Sviluppo per desktop .NET** e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-112">In **Visual Studio Installer**, select the **.NET desktop development** workload and then choose **Modify**.</span></span>

3. <span data-ttu-id="47ee3-113">Assegnare al progetto il nome **MyNewService** e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-113">Name the project **MyNewService**, and then choose **OK**.</span></span>

   <span data-ttu-id="47ee3-114">Il modello di progetto include una classe di componente denominata `Service1` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47ee3-114">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="47ee3-115">Include gran parte del codice del servizio di base, ad esempio il codice per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-115">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="47ee3-116">Rinominare il servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-116">Rename the service</span></span>

<span data-ttu-id="47ee3-117">Rinominare il servizio da **Service1** a **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-117">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="47ee3-118">Nella visualizzazione **Progettazione** per Service1.cs (o Service1.vb) fare clic sul collegamento per **passare alla visualizzazione Codice**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-118">In the **Design** view for Service1.cs (or Service1.vb), click the link to **switch to code view**.</span></span> <span data-ttu-id="47ee3-119">Fare clic con il pulsante destro del mouse su **Service1** e scegliere **Rinomina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="47ee3-119">Right-click on **Service1** and select **Rename** from the context menu.</span></span> <span data-ttu-id="47ee3-120">Immettere **MyNewService** e quindi premere **INVIO** o fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-120">Enter **MyNewService** and then press **Enter** or click **Apply**.</span></span>

2. <span data-ttu-id="47ee3-121">Nella finestra **Proprietà** per **Service1.cs [Progettazione]** o **Service1.vb [Progettazione]** impostare il valore **ServiceName** su **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-121">In the **Properties** window for **Service1.cs [Design]** or **Service1.vb [Design]**, change the **ServiceName** value to **MyNewService**.</span></span>

3. <span data-ttu-id="47ee3-122">In **Esplora soluzioni** rinominare **Service1.cs** in **MyNewService.cs** o rinominare **Service1.vb** in **MyNewService.vb**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-122">In **Solution Explorer**, rename **Service1.cs** to **MyNewService.cs**, or rename **Service1.vb** to **MyNewService.vb**.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="47ee3-123">Aggiungere funzionalità al servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-123">Add features to the service</span></span>

<span data-ttu-id="47ee3-124">In questa sezione verrà aggiunto un log eventi personalizzato al servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-124">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="47ee3-125">I log eventi non sono in alcun modo associati ai servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-125">Event logs are not associated in any way with Windows services.</span></span> <span data-ttu-id="47ee3-126">Il componente <xref:System.Diagnostics.EventLog> viene usato qui come esempio del tipo di componente che è possibile aggiungere a un servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-126">The <xref:System.Diagnostics.EventLog> component is used here as an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="47ee3-127">Aggiungere la funzionalità del log eventi personalizzato</span><span class="sxs-lookup"><span data-stu-id="47ee3-127">Add custom event log functionality</span></span>

1. <span data-ttu-id="47ee3-128">In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-128">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="47ee3-129">Dalla sezione **Componenti** della **Casella degli strumenti**trascinare un componente <xref:System.Diagnostics.EventLog> nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-129">From the **Components** section of the **Toolbox**, drag an <xref:System.Diagnostics.EventLog> component to the designer.</span></span>

3. <span data-ttu-id="47ee3-130">In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-130">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Code**.</span></span>

4. <span data-ttu-id="47ee3-131">Modificare il costruttore per definire un log eventi personalizzato:</span><span class="sxs-lookup"><span data-stu-id="47ee3-131">Edit the constructor to define a custom event log:</span></span>

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

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="47ee3-132">Definire quello che accade quando il servizio viene avviato</span><span class="sxs-lookup"><span data-stu-id="47ee3-132">Define what occurs when the service starts</span></span>

<span data-ttu-id="47ee3-133">Nell'editor di codice individuare il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> di cui è stato eseguito automaticamente l'override al momento della creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="47ee3-133">In the code editor, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method that was automatically overridden when you created the project.</span></span> <span data-ttu-id="47ee3-134">Aggiungere una riga di codice che scrive una voce nel log eventi all'avvio del servizio:</span><span class="sxs-lookup"><span data-stu-id="47ee3-134">Add a line of code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

<span data-ttu-id="47ee3-135">Poiché le applicazioni di servizio sono progettate per un'esecuzione di lunga durata, generalmente eseguono operazioni di polling o di monitoraggio nel sistema.</span><span class="sxs-lookup"><span data-stu-id="47ee3-135">A service application is designed to be long-running, so it usually polls or monitors something in the system.</span></span> <span data-ttu-id="47ee3-136">Il monitoraggio viene impostato nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="47ee3-136">The monitoring is set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="47ee3-137">Il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> , tuttavia, non esegue effettivamente il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-137">However, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> doesn’t actually do the monitoring.</span></span> <span data-ttu-id="47ee3-138">Il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> deve rispondere al sistema operativo dopo l'avvio del servizio, poiché</span><span class="sxs-lookup"><span data-stu-id="47ee3-138">The <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method must return to the operating system after the service's operation has begun.</span></span> <span data-ttu-id="47ee3-139">Non deve entrare in un ciclo o bloccarsi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-139">It must not loop forever or block.</span></span> <span data-ttu-id="47ee3-140">Per impostare un semplice meccanismo di polling, è possibile usare il componente <xref:System.Timers.Timer?displayProperty=nameWithType> come segue: Nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> impostare i parametri per il componente e quindi impostare la proprietà <xref:System.Timers.Timer.Enabled%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="47ee3-140">To set up a simple polling mechanism, you can use the <xref:System.Timers.Timer?displayProperty=nameWithType> component as follows: In the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, set parameters on the component, and then set the <xref:System.Timers.Timer.Enabled%2A> property to `true`.</span></span> <span data-ttu-id="47ee3-141">Il timer genera degli eventi nel codice periodicamente e, a quel punto, il servizio può svolgere la propria funzione di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-141">The timer raises events in your code periodically, at which time your service could do its monitoring.</span></span> <span data-ttu-id="47ee3-142">A tale scopo, è possibile usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="47ee3-142">You can use the following code to do this:</span></span>

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

<span data-ttu-id="47ee3-143">Aggiungere una variabile membro alla classe.</span><span class="sxs-lookup"><span data-stu-id="47ee3-143">Add a member variable to the class.</span></span> <span data-ttu-id="47ee3-144">Contiene l'identificatore dell'evento successivo da scrivere nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-144">It contains the identifier of the next event to write into the event log.</span></span>

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

<span data-ttu-id="47ee3-145">Aggiungere un nuovo metodo per gestire l'evento timer:</span><span class="sxs-lookup"><span data-stu-id="47ee3-145">Add a new method to handle the timer event:</span></span>

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

<span data-ttu-id="47ee3-146">Potrebbe essere necessario eseguire le attività usando un thread di lavoro in background invece di eseguire tutto il lavoro sul thread principale.</span><span class="sxs-lookup"><span data-stu-id="47ee3-146">You might want to perform tasks by using background worker threads instead of running all your work on the main thread.</span></span> <span data-ttu-id="47ee3-147">Per ulteriori informazioni, vedere <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="47ee3-147">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="47ee3-148">Definire quello che accade quando il servizio viene arrestato</span><span class="sxs-lookup"><span data-stu-id="47ee3-148">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="47ee3-149">Aggiungere al metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> una riga di codice che aggiunge una voce nel log eventi all'arresto del servizio:</span><span class="sxs-lookup"><span data-stu-id="47ee3-149">Add a line of code to the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="47ee3-150">Definire altre azioni del servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-150">Define other actions for the service</span></span>

<span data-ttu-id="47ee3-151">È possibile eseguire l'override dei metodi <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> e <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> per definire ulteriori operazioni di elaborazione del componente.</span><span class="sxs-lookup"><span data-stu-id="47ee3-151">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span> <span data-ttu-id="47ee3-152">L'esempio di codice seguente mostra come eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :</span><span class="sxs-lookup"><span data-stu-id="47ee3-152">The following code shows how you can override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

<span data-ttu-id="47ee3-153">Quando un servizio Windows viene installato mediante la classe <xref:System.Configuration.Install.Installer> , è necessario eseguire alcune azioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="47ee3-153">Some custom actions have to occur when a Windows service is installed by the <xref:System.Configuration.Install.Installer> class.</span></span> <span data-ttu-id="47ee3-154">Visual Studio può creare questi programmi di installazione specificamente per un servizio Windows e aggiungerli al progetto.</span><span class="sxs-lookup"><span data-stu-id="47ee3-154">Visual Studio can create these installers specifically for a Windows service and add them to your project.</span></span>

## <a name="set-service-status"></a><span data-ttu-id="47ee3-155">Impostare lo stato del servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-155">Set service status</span></span>

<span data-ttu-id="47ee3-156">I servizi segnalano il relativo stato in Gestione controllo servizi, in modo che gli utenti possano stabilire se un servizio funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="47ee3-156">Services report their status to the Service Control Manager, so that users can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="47ee3-157">Per impostazione predefinita, i servizi che ereditano da <xref:System.ServiceProcess.ServiceBase> segnalano un set limitato di impostazioni di stato, tra cui Arrestato, In pausa e in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-157">By default, services that inherit from <xref:System.ServiceProcess.ServiceBase> report a limited set of status settings, including Stopped, Paused, and Running.</span></span> <span data-ttu-id="47ee3-158">Se l'avvio di un servizio richiede un po' di tempo, potrebbe essere utile segnalare lo stato Avvio in sospeso.</span><span class="sxs-lookup"><span data-stu-id="47ee3-158">If a service takes a little while to start up, it might be helpful to report a Start Pending status.</span></span> <span data-ttu-id="47ee3-159">È anche possibile implementare le impostazioni di stato Avvio in sospeso e Arresto in sospeso aggiungendo il codice che chiama la [funzione SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) di Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-159">You can also implement the Start Pending and Stop Pending status settings by adding code that calls into the Windows [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).</span></span>

<span data-ttu-id="47ee3-160">Per implementare lo stato in sospeso del servizio:</span><span class="sxs-lookup"><span data-stu-id="47ee3-160">To implement service pending status:</span></span>

1. <span data-ttu-id="47ee3-161">Aggiungere un'istruzione `using` o una dichiarazione `Imports` per lo spazio dei nomi <xref:System.Runtime.InteropServices?displayProperty=nameWithType> nel file MyNewService.cs o MyNewService.vb:</span><span class="sxs-lookup"><span data-stu-id="47ee3-161">Add a `using` statement or `Imports` declaration for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace in the MyNewService.cs or MyNewService.vb file:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="47ee3-162">Aggiungere il codice seguente in MyNewService.cs per dichiarare i valori `ServiceState` e per aggiungere una struttura per lo stato da usare in una chiamata di pInvoke:</span><span class="sxs-lookup"><span data-stu-id="47ee3-162">Add the following code to MyNewService.cs to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

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

3. <span data-ttu-id="47ee3-163">A questo punto, nella classe `MyNewService` dichiarare la [funzione SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) usando [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span><span class="sxs-lookup"><span data-stu-id="47ee3-163">Now, in the `MyNewService` class, declare the [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="47ee3-164">Per implementare lo stato Avvio in sospeso, aggiungere il codice seguente all'inizio del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :</span><span class="sxs-lookup"><span data-stu-id="47ee3-164">To implement the Start Pending status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

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

5. <span data-ttu-id="47ee3-165">Aggiungere il codice per impostare lo stato su In esecuzione alla fine del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="47ee3-165">Add code to set the status to Running at the end of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span>

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

6. <span data-ttu-id="47ee3-166">Ripetere questa procedura per il metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="47ee3-166">(Optional) Repeat this procedure for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="47ee3-167">La finestra di dialogo [Gestione controllo servizi](/windows/desktop/Services/service-control-manager) usa i membri `dwWaitHint` e `dwCheckpoint` della [struttura SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) per determinare il tempo di attesa per l'avvio o l'arresto di un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-167">The [Service Control Manager](/windows/desktop/Services/service-control-manager) uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/desktop/api/winsvc/ns-winsvc-_service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="47ee3-168">Se l'esecuzione dei metodi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> si prolunga, il servizio può richiedere più tempo chiamando di nuovo [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) con un valore `dwCheckPoint` incrementato.</span><span class="sxs-lookup"><span data-stu-id="47ee3-168">If your <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods run long, your service can request more time by calling [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) again with an incremented `dwCheckPoint` value.</span></span>

## <a name="add-installers-to-the-service"></a><span data-ttu-id="47ee3-169">Aggiungere programmi di installazione al servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-169">Add installers to the service</span></span>

<span data-ttu-id="47ee3-170">Prima di eseguire un servizio di Windows, è necessario installarlo, ovvero registrarlo con Gestione controllo servizi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-170">Before you can run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="47ee3-171">È possibile aggiungere al progetto i programmi di installazione che gestiscono i dettagli di registrazione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-171">You can add installers to your project that handle the registration details.</span></span>

1. <span data-ttu-id="47ee3-172">In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-172">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="47ee3-173">Fare clic sullo sfondo della finestra di progettazione per selezionare il servizio anziché il suo contenuto.</span><span class="sxs-lookup"><span data-stu-id="47ee3-173">Click the background of the designer to select the service itself, instead of any of its contents.</span></span>

3. <span data-ttu-id="47ee3-174">Aprire il menu di scelta rapida per la finestra di progettazione (se si sta usando un dispositivo di puntamento, fare clic con il pulsante destro del mouse all'interno della finestra), quindi scegliere **Aggiungi programma di installazione**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-174">Open the context menu for the designer window (if you’re using a pointing device, right-click inside the window), and then choose **Add Installer**.</span></span>

   <span data-ttu-id="47ee3-175">Per impostazione predefinita, al progetto viene aggiunta la classe di componente contenente due programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-175">By default, a component class that contains two installers is added to your project.</span></span> <span data-ttu-id="47ee3-176">Il componente è denominato **ProjectInstaller**e i programmi di installazione in esso contenuti sono rispettivamente quello del servizio e quello del processo associato al servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-176">The component is named **ProjectInstaller**, and the installers it contains are the installer for your service and the installer for the service's associated process.</span></span>

4. <span data-ttu-id="47ee3-177">Nella visualizzazione **Progettazione** per **ProjectInstaller**scegliere **serviceInstaller1** per un progetto Visual C# o su **ServiceInstaller1** per un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47ee3-177">In **Design** view for **ProjectInstaller**, choose **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project.</span></span>

5. <span data-ttu-id="47ee3-178">Nella finestra **Proprietà** verificare che la proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> sia impostata su **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-178">In the **Properties** window, make sure the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

6. <span data-ttu-id="47ee3-179">Specificare un testo per la proprietà **Descrizione** , ad esempio "Servizio di esempio".</span><span class="sxs-lookup"><span data-stu-id="47ee3-179">Set the **Description** property to some text, such as "A sample service".</span></span> <span data-ttu-id="47ee3-180">Questo testo viene visualizzato nella finestra Servizi e consente all'utente di identificare il servizio e comprenderne la funzione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-180">This text appears in the Services window and helps the user identify the service and understand what it’s used for.</span></span>

7. <span data-ttu-id="47ee3-181">Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> sul testo da visualizzare nella colonna **Nome** della finestra Servizi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-181">Set the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property to the text that you want to appear in the Services window in the **Name** column.</span></span> <span data-ttu-id="47ee3-182">Ad esempio, è possibile immettere "Nome visualizzato MyNewService".</span><span class="sxs-lookup"><span data-stu-id="47ee3-182">For example, you can enter "MyNewService Display Name".</span></span> <span data-ttu-id="47ee3-183">Questo nome può essere diverso dalla proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , che rappresenta il nome usato dal sistema (ad esempio, quando si usa il comando `net start` per avviare il servizio).</span><span class="sxs-lookup"><span data-stu-id="47ee3-183">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name used by the system (for example, when you use the `net start` command to start your service).</span></span>

8. <span data-ttu-id="47ee3-184">Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="47ee3-184">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span></span>

     <span data-ttu-id="47ee3-185">![Proprietà del programma di installazione per un servizio di Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span><span class="sxs-lookup"><span data-stu-id="47ee3-185">![Installer Properties for a Windows service](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span></span>

9. <span data-ttu-id="47ee3-186">Nella finestra di progettazione scegliere **serviceProcessInstaller1** per un progetto Visual C# o **ServiceProcessInstaller1** per un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47ee3-186">In the designer, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project.</span></span> <span data-ttu-id="47ee3-187">Impostare la proprietà <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> su <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span><span class="sxs-lookup"><span data-stu-id="47ee3-187">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span></span> <span data-ttu-id="47ee3-188">In questo modo il servizio verrà installato ed eseguito usando l'account di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="47ee3-188">This causes the service to be installed and to run using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="47ee3-189">L'account <xref:System.ServiceProcess.ServiceAccount.LocalSystem> dispone di ampie autorizzazioni, tra cui la possibilità di scrivere nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-189">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="47ee3-190">Usare questo account con attenzione, perché potrebbe aumentare il rischio di attacchi da parte di software dannoso.</span><span class="sxs-lookup"><span data-stu-id="47ee3-190">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="47ee3-191">Per altre attività, è opportuno usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a tutti i server remoti.</span><span class="sxs-lookup"><span data-stu-id="47ee3-191">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="47ee3-192">Questo esempio non riesce se si tenta di usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> perché sono necessarie le autorizzazioni per scrivere nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-192">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="47ee3-193">Per altre informazioni sui programmi di installazione, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="47ee3-193">For more information about installers, see [How to: Add Installers to Your service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="47ee3-194">(Facoltativo) Impostare i parametri di avvio</span><span class="sxs-lookup"><span data-stu-id="47ee3-194">(Optional) Set startup parameters</span></span>

<span data-ttu-id="47ee3-195">Un servizio di Windows, come qualsiasi altro file eseguibile, può accettare gli argomenti della riga di comando o i parametri di avvio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-195">A Windows service, like any other executable, can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="47ee3-196">Quando si aggiunge il codice ai parametri di avvio del processo, gli utenti possono avviare il servizio con i parametri di avvio personalizzati usando la finestra Servizi nel Pannello di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-196">When you add code to process startup parameters, users can start your service with their own custom startup parameters by using the Services window in the Windows Control Panel.</span></span> <span data-ttu-id="47ee3-197">Tuttavia, questi parametri di avvio non vengono mantenuti al successivo avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-197">However, these startup parameters are not persisted the next time the service starts.</span></span> <span data-ttu-id="47ee3-198">Per impostare i parametri di avvio in modo permanente, è possibile impostarli nel Registro di sistema, come illustrato in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="47ee3-198">To set startup parameters permanently, you can set them in the registry, as shown in this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="47ee3-199">Prima di decidere di aggiungere parametri di avvio, valutare se sia l'approccio migliore per passare informazioni al servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-199">Before you decide to add startup parameters, consider whether that is the best way to pass information to your service.</span></span> <span data-ttu-id="47ee3-200">Anche se i parametri di avvio sono facili da usare e da analizzare e gli utenti possono facilmente eseguirne l'override, potrebbero essere più difficili da individuare e usare senza documentazione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-200">Although startup parameters are easy to use and to parse, and users can easily override them, they might be harder for users to discover and use without documentation.</span></span> <span data-ttu-id="47ee3-201">In generale, se il servizio richiede diversi parametri di avvio, provare a usare il Registro di sistema o un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-201">Generally, if your service requires more than just a few startup parameters, you should consider using the registry or a configuration file instead.</span></span> <span data-ttu-id="47ee3-202">Ogni servizio di Windows ha una voce nel Registro di sistema in **HKLM\System\CurrentControlSet\services**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-202">Every Windows service has an entry in the registry under **HKLM\System\CurrentControlSet\services**.</span></span> <span data-ttu-id="47ee3-203">Nella chiave del servizio è possibile usare la sottochiave **Parametri** per archiviare le informazioni a cui il servizio può accedere.</span><span class="sxs-lookup"><span data-stu-id="47ee3-203">Under the service's key, you can use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="47ee3-204">È possibile usare i file di configurazione dell'applicazione per un servizio di Windows in modo analogo a come avviene per gli altri tipi di programmi.</span><span class="sxs-lookup"><span data-stu-id="47ee3-204">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="47ee3-205">Per il codice di esempio, vedere <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="47ee3-205">For example code, see <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span></span>

<span data-ttu-id="47ee3-206">Per aggiungere i parametri di avvio:</span><span class="sxs-lookup"><span data-stu-id="47ee3-206">To add startup parameters:</span></span>

1. <span data-ttu-id="47ee3-207">Nel metodo `Main` in Program.cs o in MyNewService.Designer.vb aggiungere un parametro di input da passare al costruttore del servizio:</span><span class="sxs-lookup"><span data-stu-id="47ee3-207">In the `Main` method in Program.cs or in MyNewService.Designer.vb, add an input parameter to pass to the service constructor:</span></span>

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

2. <span data-ttu-id="47ee3-208">Modificare il costruttore `MyNewService` come segue:</span><span class="sxs-lookup"><span data-stu-id="47ee3-208">Change the `MyNewService` constructor as follows:</span></span>

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

   <span data-ttu-id="47ee3-209">Questo codice imposta l'origine evento e il nome log in base ai parametri di avvio forniti oppure usa i valori predefiniti se non vengono forniti argomenti.</span><span class="sxs-lookup"><span data-stu-id="47ee3-209">This code sets the event source and log name according to the supplied startup parameters, or uses default values if no arguments are supplied.</span></span>

3. <span data-ttu-id="47ee3-210">Per specificare gli argomenti della riga di comando, aggiungere il codice seguente alla classe `ProjectInstaller` in ProjectInstaller.cs o ProjectInstaller.vb:</span><span class="sxs-lookup"><span data-stu-id="47ee3-210">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in ProjectInstaller.cs or ProjectInstaller.vb:</span></span>

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

   <span data-ttu-id="47ee3-211">Questo codice modifica la chiave del Registro di sistema **ImagePath**, che in genere contiene il percorso completo dell'eseguibile per il servizio di Windows, aggiungendo i valori dei parametri predefiniti.</span><span class="sxs-lookup"><span data-stu-id="47ee3-211">This code modifies the **ImagePath** registry key, which typically contains the full path to the executable for the Windows service, by adding the default parameter values.</span></span> <span data-ttu-id="47ee3-212">Le virgolette che racchiudono il percorso, e ogni singolo parametro, sono necessarie per il corretto avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-212">The quotation marks around the path (and around each individual parameter) are required for the service to start up correctly.</span></span> <span data-ttu-id="47ee3-213">Per modificare i parametri di avvio per questo servizio di Windows, gli utenti possono modificare i parametri specificati nella chiave del Registro di sistema **ImagePath**, anche se l'approccio migliore consiste nell'eseguire la modifica a livello di codice ed esporre le funzionalità agli utenti in modo intuitivo, ad esempio in un'utilità di configurazione o gestione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-213">To change the startup parameters for this Windows service, users can change the parameters given in the **ImagePath** registry key, although the better way is to change it programmatically and expose the functionality to users in a friendly way (for example, in a management or configuration utility).</span></span>

## <a name="build-the-service"></a><span data-ttu-id="47ee3-214">Compilare il servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-214">Build the service</span></span>

1. <span data-ttu-id="47ee3-215">In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-215">In **Solution Explorer**, open the context menu for your project, and then choose **Properties**.</span></span>

   <span data-ttu-id="47ee3-216">Verranno visualizzate le pagine delle proprietà per il progetto.</span><span class="sxs-lookup"><span data-stu-id="47ee3-216">The property pages for your project appear.</span></span>

2. <span data-ttu-id="47ee3-217">Nell'elenco **Oggetto di avvio** della scheda **Applicazione** scegliere **MyNewService.Program**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-217">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**.</span></span>

3. <span data-ttu-id="47ee3-218">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto, quindi scegliere **Compila** per compilare il progetto (o premere **CTRL**+**MAIUSC**+**B**).</span><span class="sxs-lookup"><span data-stu-id="47ee3-218">In **Solution Explorer**, open the context menu for your project, and then choose **Build** to build the project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="47ee3-219">Installare il servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-219">Install the service</span></span>

<span data-ttu-id="47ee3-220">Una volta compilato il servizio Windows, è possibile installarlo.</span><span class="sxs-lookup"><span data-stu-id="47ee3-220">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="47ee3-221">Per installare un servizio di Windows, è necessario avere le credenziali di amministratore nel computer in cui viene eseguita l'installazione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-221">To install a Windows service, you must have administrator credentials on the computer on which you're installing it.</span></span>

1. <span data-ttu-id="47ee3-222">Aprire il **Prompt dei comandi per gli sviluppatori per Visual Studio** con credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="47ee3-222">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span> <span data-ttu-id="47ee3-223">Se si usa un mouse, fare clic con il pulsante destro del mouse su **Developer Command Prompt for VS 2017** (Prompt dei comandi per gli sviluppatori per VS 2017) nel menu Start di Windows, quindi scegliere **Altro** > **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-223">If you’re using a mouse, right-click on **Developer Command Prompt for VS 2017** in the Windows Start menu, and then choose **More** > **Run as Administrator**.</span></span>

2. <span data-ttu-id="47ee3-224">Nella finestra **Prompt dei comandi per gli sviluppatori** passare alla cartella contenente l'output del progetto. Per impostazione predefinita, è la sottodirectory *\bin\Debug* del progetto.</span><span class="sxs-lookup"><span data-stu-id="47ee3-224">In the **Developer Command Prompt** window, navigate to the folder that contains your project's output (by default, it's the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="47ee3-225">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="47ee3-225">Enter the following command:</span></span>

    ```shell
    installutil.exe MyNewService.exe
    ```

    <span data-ttu-id="47ee3-226">Se il servizio viene installato correttamente, tramite il file **installutil.exe** viene segnalato l'esito positivo.</span><span class="sxs-lookup"><span data-stu-id="47ee3-226">If the service installs successfully, **installutil.exe** reports success.</span></span> <span data-ttu-id="47ee3-227">Se il sistema non riesce a trovare **InstallUtil.exe**, assicurarsi che sia presente nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="47ee3-227">If the system could not find **InstallUtil.exe**, make sure that it exists on your computer.</span></span> <span data-ttu-id="47ee3-228">Questo strumento viene installato con .NET Framework nella cartella *%windir%\Microsoft.NET\Framework[64]\\[versione framework]*.</span><span class="sxs-lookup"><span data-stu-id="47ee3-228">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\[framework version]*.</span></span> <span data-ttu-id="47ee3-229">Il percorso predefinito per la versione a 32 bit, ad esempio, è *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="47ee3-229">For example, the default path for the 32-bit version is *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="47ee3-230">Se il processo **installutil.exe** segnala un errore, controllare il log di installazione per determinarne il motivo.</span><span class="sxs-lookup"><span data-stu-id="47ee3-230">If the **installutil.exe** process reports failure, check the install log to find out why.</span></span> <span data-ttu-id="47ee3-231">Per impostazione predefinita, il log è nella stessa cartella del file eseguibile del servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-231">By default the log is in the same folder as the service executable.</span></span> <span data-ttu-id="47ee3-232">L'installazione potrebbe non riuscire se la classe <xref:System.ComponentModel.RunInstallerAttribute> non è presente nella classe `ProjectInstaller`, se l'attributo non è impostato su **true** o se la classe `ProjectInstaller` non è contrassegnata come **public**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-232">The installation can fail if  the <xref:System.ComponentModel.RunInstallerAttribute> Class is not present on the `ProjectInstaller` class, if the attribute is not set to **true**, or if the `ProjectInstaller` class is not marked **public**.</span></span>

<span data-ttu-id="47ee3-233">Per altre informazioni, vedere [Procedura: Installare e disinstallare servizi](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="47ee3-233">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="47ee3-234">Avviare ed eseguire il servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-234">Start and run the service</span></span>

1. <span data-ttu-id="47ee3-235">In Windows aprire l'app desktop **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-235">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="47ee3-236">Premere **Windows**+**R** per aprire la casella **Esegui** e quindi immettere **services.msc** e premere **INVIO** o fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-236">Press **Windows**+**R** to open the **Run** box, and then enter **services.msc** and press **Enter** or click **OK**.</span></span>

     <span data-ttu-id="47ee3-237">Il servizio verrà elencato in **Servizi**, in ordine alfabetico in base al nome visualizzato impostato.</span><span class="sxs-lookup"><span data-stu-id="47ee3-237">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![MyNewService nella finestra Servizi.](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="47ee3-239">In **Servizi** aprire il menu di scelta rapida per il servizio, quindi scegliere **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-239">In **Services**, open the shortcut menu for your service, and then choose **Start**.</span></span>

3. <span data-ttu-id="47ee3-240">Per arrestare il servizio, aprire il menu di scelta rapida per il servizio, quindi scegliere **Arresta**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-240">To stop the service, open the shortcut menu for the service, and then choose **Stop**.</span></span>

4. <span data-ttu-id="47ee3-241">Dalla riga di comando è possibile usare i comandi `net start ServiceName` e `net stop ServiceName` per avviare e arrestare il servizio (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="47ee3-241">(Optional) From the command line, you can use the commands `net start ServiceName` and `net stop ServiceName` to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="47ee3-242">Verificare l'output del log eventi del servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-242">Verify the event log output of your service</span></span>

1. <span data-ttu-id="47ee3-243">Per aprire il **Visualizzatore eventi**, iniziare a digitare **Visualizzatore eventi** nella casella di ricerca sulla barra della applicazioni di Windows e quindi selezionare **Visualizzatore eventi** nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="47ee3-243">Open **Event Viewer** by starting to type **Event Viewer** in the search box on the Windows task bar, and then selecting **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="47ee3-244">In Visual Studio è possibile accedere ai registri eventi aprendo **Esplora server** (tastiera: **CTRL**+**ALT**+**S**) e quindi espandendo il nodo **Registri eventi** per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="47ee3-244">In Visual Studio, you can access event logs by opening **Server Explorer** (Keyboard: **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="47ee3-245">Nel **Visualizzatore eventi** espandere **Registri applicazioni e servizi**.</span><span class="sxs-lookup"><span data-stu-id="47ee3-245">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="47ee3-246">Individuare l'elenco per **MyNewLog** (o **MyLogFile1**, se è stata seguita la procedura facoltativa per aggiungere gli argomenti della riga di comando) ed espanderlo.</span><span class="sxs-lookup"><span data-stu-id="47ee3-246">Locate the listing for **MyNewLog** (or **MyLogFile1**, if you followed the optional procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="47ee3-247">Verranno visualizzate le voci per le due azioni (avvio e arresto) eseguite dal servizio.</span><span class="sxs-lookup"><span data-stu-id="47ee3-247">You should see entries for the two actions (start and stop) that your service performed.</span></span>

     ![Usare il Visualizzatore eventi per visualizzare le voci del log eventi](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a><span data-ttu-id="47ee3-249">Disinstallare il servizio</span><span class="sxs-lookup"><span data-stu-id="47ee3-249">Uninstall the service</span></span>

1. <span data-ttu-id="47ee3-250">Aprire il **Prompt dei comandi per gli sviluppatori per Visual Studio** con credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="47ee3-250">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="47ee3-251">Nella finestra del prompt dei comandi passare alla cartella che contiene l'output del progetto.</span><span class="sxs-lookup"><span data-stu-id="47ee3-251">In the command prompt window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="47ee3-252">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="47ee3-252">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="47ee3-253">Se il servizio viene disinstallato correttamente, tramite il file **installutil.exe** viene segnalato che il servizio è stato rimosso correttamente.</span><span class="sxs-lookup"><span data-stu-id="47ee3-253">If the service uninstalls successfully, **installutil.exe** reports that your service was successfully removed.</span></span> <span data-ttu-id="47ee3-254">Per altre informazioni, vedere [Procedura: Installare e disinstallare servizi](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="47ee3-254">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="47ee3-255">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="47ee3-255">Next steps</span></span>

<span data-ttu-id="47ee3-256">Dopo aver creato il servizio, potrebbe essere necessario creare un programma di installazione autonomo che altri utenti possono usare per installare il servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-256">Now that you've created the service, you might want to create a standalone setup program that others can use to install your Windows service.</span></span> <span data-ttu-id="47ee3-257">ClickOnce non supporta i servizi di Windows, ma è possibile usare [WiX Toolset](http://wixtoolset.org/) per creare un programma di installazione per un servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="47ee3-257">ClickOnce doesn't support Windows services, but you can use the [WiX Toolset](http://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="47ee3-258">Per altre idee, vedere [Creare un pacchetto di installazione](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="47ee3-258">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

<span data-ttu-id="47ee3-259">Per inviare comandi al servizio installato, è anche possibile usare il componente <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="47ee3-259">You might explore the use of a <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

<span data-ttu-id="47ee3-260">È possibile usare il programma di installazione per creare un log eventi durante l'installazione dell'applicazione, anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-260">You can use an installer to create an event log when the application is installed instead of creating the event log when the application runs.</span></span> <span data-ttu-id="47ee3-261">Il log eventi verrà inoltre eliminato dal programma di installazione durante la disinstallazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47ee3-261">Additionally, the event log will be deleted by the installer when the application is uninstalled.</span></span> <span data-ttu-id="47ee3-262">Per altre informazioni, vedere la pagina di riferimento <xref:System.Diagnostics.EventLogInstaller> .</span><span class="sxs-lookup"><span data-stu-id="47ee3-262">For more information, see the <xref:System.Diagnostics.EventLogInstaller> reference page.</span></span>

## <a name="see-also"></a><span data-ttu-id="47ee3-263">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47ee3-263">See also</span></span>

- [<span data-ttu-id="47ee3-264">Applicazioni di servizi di Windows</span><span class="sxs-lookup"><span data-stu-id="47ee3-264">Windows service applications</span></span>](../../../docs/framework/windows-services/index.md)
- [<span data-ttu-id="47ee3-265">Introduzione alle applicazioni di servizio di Windows</span><span class="sxs-lookup"><span data-stu-id="47ee3-265">Introduction to Windows service applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="47ee3-266">Procedura: Eseguire il debug di applicazioni di servizio di Windows</span><span class="sxs-lookup"><span data-stu-id="47ee3-266">How to: Debug Windows service applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="47ee3-267">Servizi (Windows)</span><span class="sxs-lookup"><span data-stu-id="47ee3-267">Services (Windows)</span></span>](/windows/desktop/Services/services)
