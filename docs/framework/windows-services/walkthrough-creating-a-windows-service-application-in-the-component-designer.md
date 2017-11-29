---
title: 'Procedura dettagliata: creazione di un''applicazione di servizio Windows in Progettazione componenti'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Service applications, walkthroughs
- Windows Service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
caps.latest.revision: "57"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: fb868aa38381294333538afcd99c030162d2f235
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2017
---
# <a name="walkthrough-creating-a-windows-service-application-in-the-component-designer"></a><span data-ttu-id="4ea24-102">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="4ea24-102">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>
<span data-ttu-id="4ea24-103">Questo articolo illustra come creare una semplice applicazione del servizio Windows in Visual Studio che scrive messaggi in un log eventi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-103">This article demonstrates how to create a simple Windows Service application in Visual Studio that writes messages to an event log.</span></span> <span data-ttu-id="4ea24-104">I passaggi di base da eseguire per la creazione e l'uso del servizio includono:</span><span class="sxs-lookup"><span data-stu-id="4ea24-104">Here are the basic steps that you perform to create and use your service:</span></span>  
  
1.  <span data-ttu-id="4ea24-105">[Creazione di un servizio](#BK_CreateProject) usando il modello di progetto del **servizio Windows** e configurarlo.</span><span class="sxs-lookup"><span data-stu-id="4ea24-105">[Creating a Service](#BK_CreateProject) by using the **Windows Service** project template, and configure it.</span></span> <span data-ttu-id="4ea24-106">Tale modello crea automaticamente una classe che eredita da <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> e scrive la maggior parte del codice di base del servizio, ad esempio il codice per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-106">This template creates a class for you that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> and writes much of the basic service code, such as the code to start the service.</span></span>  
  
2.  <span data-ttu-id="4ea24-107">[Aggiunta di funzionalità al servizio](#BK_WriteCode) per le routine <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> ed eseguire l'override degli altri metodi da ridefinire.</span><span class="sxs-lookup"><span data-stu-id="4ea24-107">[Adding Features to the Service](#BK_WriteCode) for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures, and override any other methods that you want to redefine.</span></span>  
  
3.  <span data-ttu-id="4ea24-108">[Impostazione dello stato del servizio](#BK_SetStatus).</span><span class="sxs-lookup"><span data-stu-id="4ea24-108">[Setting Service Status](#BK_SetStatus).</span></span> <span data-ttu-id="4ea24-109">Per impostazione predefinita, i servizi creati con <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> implementano solo un subset di flag di stato disponibili.</span><span class="sxs-lookup"><span data-stu-id="4ea24-109">By default, services created with <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> implement only a subset of the available status flags.</span></span> <span data-ttu-id="4ea24-110">Se le operazioni di avvio, sospensione e arresto del servizio richiedono molto tempo, è possibile implementare i valori di stato come Avvio in sospeso o Arresto in sospeso per indicare che è in corso un'operazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-110">If your service takes a long time to start up, pause, or stop, you can implement status values such as Start Pending or Stop Pending to indicate that it's working on an operation.</span></span>  
  
4.  <span data-ttu-id="4ea24-111">[Aggiunta di programmi di installazione al servizio](#BK_AddInstallers) per l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-111">[Adding Installers to the Service](#BK_AddInstallers) for your service application.</span></span>  
  
5.  <span data-ttu-id="4ea24-112">(Facoltativo) [Impostare i parametri di avvio](#BK_StartupParameters), specificare gli argomenti di avvio predefiniti e consentire agli utenti di eseguire l'override delle impostazioni predefinite quando avviano il servizio manualmente.</span><span class="sxs-lookup"><span data-stu-id="4ea24-112">(Optional) [Set Startup Parameters](#BK_StartupParameters), specify default startup arguments, and enable users to override default settings when they start your service manually.</span></span>  
  
6.  <span data-ttu-id="4ea24-113">[Compilazione del servizio](#BK_Build).</span><span class="sxs-lookup"><span data-stu-id="4ea24-113">[Building the Service](#BK_Build).</span></span>  
  
7.  <span data-ttu-id="4ea24-114">[Installazione del servizio](#BK_Install) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="4ea24-114">[Installing the Service](#BK_Install) on the local machine.</span></span>  
  
8.  <span data-ttu-id="4ea24-115">Accedere a Gestione controllo servizi di Windows e [Avvio ed esecuzione del servizio](#BK_StartService).</span><span class="sxs-lookup"><span data-stu-id="4ea24-115">Access the Windows Service Control Manager and [Starting and Running the Service](#BK_StartService).</span></span>  
  
9. <span data-ttu-id="4ea24-116">[Disinstallazione di un servizio Windows](#BK_Uninstall).</span><span class="sxs-lookup"><span data-stu-id="4ea24-116">[Uninstalling a Windows Service](#BK_Uninstall).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4ea24-117">Il modello di progetto Servizi Windows che è richiesto in questa procedura dettagliata non è disponibile nell'edizione Express di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-117">The Windows Services project template that is required for this walkthrough is not available in the Express edition of Visual Studio.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]  
  
<a name="BK_CreateProject"></a>   
## <a name="creating-a-service"></a><span data-ttu-id="4ea24-118">Creazione di un servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-118">Creating a Service</span></span>  
 <span data-ttu-id="4ea24-119">Le prime operazioni da effettuare sono la creazione del progetto e l'impostazione dei valori necessari per garantire il corretto funzionamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-119">To begin, you create the project and set values that are required for the service to function correctly.</span></span>  
  
#### <a name="to-create-and-configure-your-service"></a><span data-ttu-id="4ea24-120">Per creare e configurare il servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-120">To create and configure your service</span></span>  
  
1.  <span data-ttu-id="4ea24-121">Nella barra dei menu di Visual Studio scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-121">In Visual Studio, on the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="4ea24-122">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="4ea24-122">The **New Project** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="4ea24-123">Nell'elenco dei modelli di progetto di Visual Basic o Visual C# scegliere **Servizio Windows**e assegnare al progetto il nome **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-123">In the list of Visual Basic or Visual C# project templates, choose **Windows Service**, and name the project **MyNewService**.</span></span> <span data-ttu-id="4ea24-124">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-124">Choose **OK**.</span></span>  
  
     <span data-ttu-id="4ea24-125">Il modello di progetto aggiunge automaticamente una classe di componente denominata `Service1` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ea24-125">The project template automatically adds a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span>  
  
3.  <span data-ttu-id="4ea24-126">Nel menu **Modifica** scegliere **Trova e sostituisci**, **Cerca nei file** (scelta rapida da tastiera: CTRL+MAIUSC+F).</span><span class="sxs-lookup"><span data-stu-id="4ea24-126">On the **Edit** menu, choose **Find and Replace**, **Find in Files** (Keyboard: Ctrl+Shift+F).</span></span> <span data-ttu-id="4ea24-127">Modificare tutte le occorrenze di `Service1` in `MyNewService`.</span><span class="sxs-lookup"><span data-stu-id="4ea24-127">Change all occurrences of `Service1` to `MyNewService`.</span></span> <span data-ttu-id="4ea24-128">Sono presenti istanze in Service1.cs, Program.cs e Service1.Designer.cs (o nei relativi equivalenti in VB).</span><span class="sxs-lookup"><span data-stu-id="4ea24-128">You’ll find instances in Service1.cs, Program.cs, and Service1.Designer.cs (or their .vb equivalents).</span></span>  
  
4.  <span data-ttu-id="4ea24-129">Nella finestra **Proprietà** per **Service1.cs [Design]** o **Service1.vb [Design]**impostare la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> e **(Name)** per `Service1` su **MyNewService**, se non è già impostata.</span><span class="sxs-lookup"><span data-stu-id="4ea24-129">In the **Properties** window for **Service1.cs [Design]** or **Service1.vb [Design]**, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> and the **(Name)** property for `Service1` to **MyNewService**, if it's not already set.</span></span>  
  
5.  <span data-ttu-id="4ea24-130">In Esplora soluzioni rinominare **Service1.cs** in **MyNewService.cs**o **Service1.vb** in **MyNewService.vb**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-130">In Solution Explorer, rename **Service1.cs** to **MyNewService.cs**, or **Service1.vb** to **MyNewService.vb**.</span></span>  
  
<a name="BK_WriteCode"></a>   
## <a name="adding-features-to-the-service"></a><span data-ttu-id="4ea24-131">Aggiunta di funzionalità al servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-131">Adding Features to the Service</span></span>  
 <span data-ttu-id="4ea24-132">In questa sezione verrà aggiunto un log eventi personalizzato al servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea24-132">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="4ea24-133">I log eventi non sono in alcun modo associati ai servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea24-133">Event logs are not associated in any way with Windows services.</span></span> <span data-ttu-id="4ea24-134">In questa situazione il componente <xref:System.Diagnostics.EventLog> viene usato come un esempio del tipo di componente che è possibile aggiungere a un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea24-134">Here the <xref:System.Diagnostics.EventLog> component is used as an example of the type of component you could add to a Windows service.</span></span>  
  
#### <a name="to-add-custom-event-log-functionality-to-your-service"></a><span data-ttu-id="4ea24-135">Per aggiungere la funzionalità del log eventi personalizzato al servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-135">To add custom event log functionality to your service</span></span>  
  
1.  <span data-ttu-id="4ea24-136">In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-136">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>  
  
2.  <span data-ttu-id="4ea24-137">Dalla sezione **Componenti** della **Casella degli strumenti**trascinare un componente <xref:System.Diagnostics.EventLog> nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-137">From the **Components** section of the **Toolbox**, drag an <xref:System.Diagnostics.EventLog> component to the designer.</span></span>  
  
3.  <span data-ttu-id="4ea24-138">In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-138">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Code**.</span></span>  
  
4.  <span data-ttu-id="4ea24-139">Aggiungere una dichiarazione per l'oggetto **eventLog** oggetto nella classe `MyNewService` subito dopo la riga che dichiara la variabile `components` :</span><span class="sxs-lookup"><span data-stu-id="4ea24-139">Add a declaration for the **eventLog** object in the `MyNewService` class, right after the line that declares the `components` variable:</span></span>  
  
     [!code-csharp[VbRadconService#16](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#16)]
     [!code-vb[VbRadconService#16](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#16)]  
  
5.  <span data-ttu-id="4ea24-140">Aggiungere o modificare il costruttore in modo da definire un log eventi personalizzato:</span><span class="sxs-lookup"><span data-stu-id="4ea24-140">Add or edit the constructor to define a custom event log:</span></span>  
  
     [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
     [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]  
  
#### <a name="to-define-what-occurs-when-the-service-starts"></a><span data-ttu-id="4ea24-141">Per definire quello che accade quando il servizio viene avviato</span><span class="sxs-lookup"><span data-stu-id="4ea24-141">To define what occurs when the service starts</span></span>  
  
-   <span data-ttu-id="4ea24-142">Nell'editor di codice individuare il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> di cui è stato eseguito automaticamente l'override al momento della creazione del progetto e sostituire il codice esistente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4ea24-142">In the Code Editor, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method that was automatically overridden when you created the project, and replace the code with the following.</span></span> <span data-ttu-id="4ea24-143">In questo modo viene aggiunta una voce nel log eventi all'avvio dell'esecuzione del servizio:</span><span class="sxs-lookup"><span data-stu-id="4ea24-143">This adds an entry to the event log when the service starts running:</span></span>  
  
     [!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
     [!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]  
  
     <span data-ttu-id="4ea24-144">Poiché le applicazioni di servizio sono progettate per un'esecuzione di lunga durata, generalmente eseguono operazioni di polling o di monitoraggio nel sistema.</span><span class="sxs-lookup"><span data-stu-id="4ea24-144">A service application is designed to be long-running, so it usually polls or monitors something in the system.</span></span> <span data-ttu-id="4ea24-145">Il monitoraggio viene impostato nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="4ea24-145">The monitoring is set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="4ea24-146">Il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> , tuttavia, non esegue effettivamente il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-146">However, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> doesn’t actually do the monitoring.</span></span> <span data-ttu-id="4ea24-147">Il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> deve rispondere al sistema operativo dopo l'avvio del servizio, poiché</span><span class="sxs-lookup"><span data-stu-id="4ea24-147">The <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method must return to the operating system after the service's operation has begun.</span></span> <span data-ttu-id="4ea24-148">Non deve entrare in un ciclo o bloccarsi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-148">It must not loop forever or block.</span></span> <span data-ttu-id="4ea24-149">Per impostare un semplice meccanismo di polling, è possibile usare il componente <xref:System.Timers.Timer?displayProperty=nameWithType>. Nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> impostare i parametri del componente e la proprietà <xref:System.Timers.Timer.Enabled%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="4ea24-149">To set up a simple polling mechanism, you can use the <xref:System.Timers.Timer?displayProperty=nameWithType> component as follows: In the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, set parameters on the component, and then set the <xref:System.Timers.Timer.Enabled%2A> property to `true`.</span></span> <span data-ttu-id="4ea24-150">Il timer genera degli eventi nel codice periodicamente e, a quel punto, il servizio può svolgere la propria funzione di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-150">The timer raises events in your code periodically, at which time your service could do its monitoring.</span></span> <span data-ttu-id="4ea24-151">A tale scopo, è possibile usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4ea24-151">You can use the following code to do this:</span></span>  
  
    ```csharp  
    // Set up a timer to trigger every minute.  
    System.Timers.Timer timer = new System.Timers.Timer();  
    timer.Interval = 60000; // 60 seconds  
    timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);  
    timer.Start();  
    ```  
  
    ```vb  
    ' Set up a timer to trigger every minute.  
    Dim timer As System.Timers.Timer = New System.Timers.Timer()  
    timer.Interval = 60000 ' 60 seconds  
    AddHandler timer.Elapsed, AddressOf Me.OnTimer  
    timer.Start()  
    ```  
     <span data-ttu-id="4ea24-152">Aggiungere una variabile membro alla classe.</span><span class="sxs-lookup"><span data-stu-id="4ea24-152">Add a member variable to the class.</span></span> <span data-ttu-id="4ea24-153">Contiene l'identificatore dell'evento successivo per scrivere nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-153">It will contain the identifier of the next event to write into the event log.</span></span>

    ```csharp
    private int eventId = 1;
    ```

    ```vb
    Private eventId As Integer = 1
    ```

     <span data-ttu-id="4ea24-154">Aggiungere il codice per gestire l'evento timer:</span><span class="sxs-lookup"><span data-stu-id="4ea24-154">Add code to handle the timer event:</span></span>  
  
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
  
     <span data-ttu-id="4ea24-155">Potrebbe essere necessario eseguire le attività usando un thread di lavoro in background invece di eseguire tutto il lavoro sul thread principale.</span><span class="sxs-lookup"><span data-stu-id="4ea24-155">You might want to perform tasks by using background worker threads instead of running all your work on the main thread.</span></span> <span data-ttu-id="4ea24-156">Per un esempio, vedere la pagina di riferimento <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ea24-156">For an example of this, see the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> reference page.</span></span>  
  
#### <a name="to-define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="4ea24-157">Per definire quello che accade quando il servizio viene interrotto</span><span class="sxs-lookup"><span data-stu-id="4ea24-157">To define what occurs when the service is stopped</span></span>  
  
-   <span data-ttu-id="4ea24-158">Sostituire il codice del metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4ea24-158">Replace the code for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method with the following.</span></span> <span data-ttu-id="4ea24-159">In questo modo viene aggiunta una voce nel log eventi all'arresto del servizio:</span><span class="sxs-lookup"><span data-stu-id="4ea24-159">This adds an entry to the event log when the service is stopped:</span></span>  
  
     [!code-csharp[VbRadconService#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
     [!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]  
  
 <span data-ttu-id="4ea24-160">Nella sezione successiva è possibile eseguire l'override dei metodi <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>e <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> per definire ulteriori operazioni di elaborazione del componente.</span><span class="sxs-lookup"><span data-stu-id="4ea24-160">In the next section, you can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span>  
  
#### <a name="to-define-other-actions-for-the-service"></a><span data-ttu-id="4ea24-161">Per definire altre azioni del servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-161">To define other actions for the service</span></span>  
  
-   <span data-ttu-id="4ea24-162">Individuare il metodo da gestire ed eseguirne l'override per definire le azioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="4ea24-162">Locate the method that you want to handle, and override it to define what you want to occur.</span></span>  
  
     <span data-ttu-id="4ea24-163">L'esempio di codice seguente mostra come eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :</span><span class="sxs-lookup"><span data-stu-id="4ea24-163">The following code shows how you can override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method:</span></span>  
  
     [!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
     [!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]  
  
 <span data-ttu-id="4ea24-164">Quando un servizio Windows viene installato mediante la classe <xref:System.Configuration.Install.Installer> , è necessario eseguire alcune azioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="4ea24-164">Some custom actions have to occur when a Windows service is installed by the <xref:System.Configuration.Install.Installer> class.</span></span> <span data-ttu-id="4ea24-165">Visual Studio può creare questi programmi di installazione specificamente per un servizio Windows e aggiungerli al progetto.</span><span class="sxs-lookup"><span data-stu-id="4ea24-165">Visual Studio can create these installers specifically for a Windows service and add them to your project.</span></span>  
  
<a name="BK_SetStatus"></a>   
## <a name="setting-service-status"></a><span data-ttu-id="4ea24-166">Impostazione dello stato del servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-166">Setting Service Status</span></span>  
 <span data-ttu-id="4ea24-167">I servizi segnalano il relativo stato in Gestione controllo servizi, in modo che gli utenti possano stabilire se un servizio funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="4ea24-167">Services report their status to the Service Control Manager, so that users can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="4ea24-168">Per impostazione predefinita, i servizi che ereditano da <xref:System.ServiceProcess.ServiceBase> segnalano un set limitato di impostazioni di stato, tra cui Arrestato, In pausa e in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-168">By default, services that inherit from <xref:System.ServiceProcess.ServiceBase> report a limited set of status settings, including Stopped, Paused, and Running.</span></span> <span data-ttu-id="4ea24-169">Se l'avvio di un servizio richiede un po' di tempo, potrebbe essere utile segnalare lo stato Avvio in sospeso.</span><span class="sxs-lookup"><span data-stu-id="4ea24-169">If a service takes a little while to start up, it might be helpful to report a Start Pending status.</span></span> <span data-ttu-id="4ea24-170">È anche possibile implementare le impostazioni di stato Avvio in sospeso e Arresto in sospeso aggiungendo il codice che chiama la [funzione SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx)di Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea24-170">You can also implement the Start Pending and Stop Pending status settings by adding code that calls into the Windows [SetServiceStatus function](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx).</span></span>  
  
#### <a name="to-implement-service-pending-status"></a><span data-ttu-id="4ea24-171">Per implementare lo stato in sospeso del servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-171">To implement service pending status</span></span>  
  
1.  <span data-ttu-id="4ea24-172">Aggiungere un'istruzione `using` o una dichiarazione `Imports` allo spazio dei nomi <xref:System.Runtime.InteropServices?displayProperty=nameWithType> nel file MyNewService.cs o MyNewService.vb:</span><span class="sxs-lookup"><span data-stu-id="4ea24-172">Add a `using` statement or `Imports` declaration to the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace in the MyNewService.cs or MyNewService.vb file:</span></span>  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    ```  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    ```  
  
2.  <span data-ttu-id="4ea24-173">Aggiungere il codice seguente in MyNewService.cs per dichiarare i valori `ServiceState` e per aggiungere una struttura per lo stato da usare in una chiamata di pInvoke:</span><span class="sxs-lookup"><span data-stu-id="4ea24-173">Add the following code to MyNewService.cs to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>  
  
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
  
3.  <span data-ttu-id="4ea24-174">A questo punto, nella classe `MyNewService` dichiarare la [funzione SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) mediante pInvoke:</span><span class="sxs-lookup"><span data-stu-id="4ea24-174">Now, in the `MyNewService` class, declare the [SetServiceStatus function](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) by using platform invoke:</span></span>  
  
    ```csharp  
    [DllImport("advapi32.dll", SetLastError=true)]  
            private static extern bool SetServiceStatus(IntPtr handle, ref ServiceStatus serviceStatus);  
    ```  
  
    ```vb  
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean  
    ```  
  
4.  <span data-ttu-id="4ea24-175">Per implementare lo stato Avvio in sospeso, aggiungere il codice seguente all'inizio del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :</span><span class="sxs-lookup"><span data-stu-id="4ea24-175">To implement the Start Pending status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>  
  
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
  
5.  <span data-ttu-id="4ea24-176">Aggiungere il codice per impostare lo stato su In esecuzione alla fine del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="4ea24-176">Add code to set the status to Running at the end of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span>  
  
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
  
6.  <span data-ttu-id="4ea24-177">Ripetere questa procedura per il metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="4ea24-177">(Optional) Repeat this procedure for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4ea24-178">Verrà visualizzata la finestra di dialogo [Gestione controllo servizi](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) usa i membri `dwWaitHint` e `dwCheckpoint` della [struttura SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) per determinare il tempo di attesa per l'avvio o l'arresto di un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea24-178">The [Service Control Manager](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) to determine how much time to wait for a Windows Service to start or shut down.</span></span> <span data-ttu-id="4ea24-179">Se l'esecuzione dei metodi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> si prolunga, il servizio può richiedere più tempo chiamando di nuovo [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) con un valore `dwCheckPoint` incrementato.</span><span class="sxs-lookup"><span data-stu-id="4ea24-179">If your <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods run long, your service can request more time by calling [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) again with an incremented `dwCheckPoint` value.</span></span>  
  
<a name="BK_AddInstallers"></a>   
## <a name="adding-installers-to-the-service"></a><span data-ttu-id="4ea24-180">Aggiunta di programmi di installazione al servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-180">Adding Installers to the Service</span></span>  
 <span data-ttu-id="4ea24-181">Prima di eseguire un servizio Windows, è necessario installarlo, ovvero registrarlo con Gestione controllo servizi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-181">Before you can run a Windows Service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="4ea24-182">È possibile aggiungere al progetto i programmi di installazione che gestiscono i dettagli di registrazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-182">You can add installers to your project that handle the registration details.</span></span>  
  
#### <a name="to-create-the-installers-for-your-service"></a><span data-ttu-id="4ea24-183">Per creare i programmi di installazione per il servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-183">To create the installers for your service</span></span>  
  
1.  <span data-ttu-id="4ea24-184">In **Esplora soluzioni**aprire il menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-184">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>  
  
2.  <span data-ttu-id="4ea24-185">Fare clic sullo sfondo della finestra di progettazione per selezionare il servizio anziché il suo contenuto.</span><span class="sxs-lookup"><span data-stu-id="4ea24-185">Click the background of the designer to select the service itself, instead of any of its contents.</span></span>  
  
3.  <span data-ttu-id="4ea24-186">Aprire il menu di scelta rapida per la finestra di progettazione (se si sta usando un dispositivo di puntamento, fare clic con il pulsante destro del mouse all'interno della finestra), quindi scegliere **Aggiungi programma di installazione**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-186">Open the context menu for the designer window (if you’re using a pointing device, right-click inside the window), and then choose **Add Installer**.</span></span>  
  
     <span data-ttu-id="4ea24-187">Per impostazione predefinita, al progetto viene aggiunta la classe di componente contenente due programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-187">By default, a component class that contains two installers is added to your project.</span></span> <span data-ttu-id="4ea24-188">Il componente è denominato **ProjectInstaller**e i programmi di installazione in esso contenuti sono rispettivamente quello del servizio e quello del processo associato al servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-188">The component is named **ProjectInstaller**, and the installers it contains are the installer for your service and the installer for the service's associated process.</span></span>  
  
4.  <span data-ttu-id="4ea24-189">Nella visualizzazione **Progettazione** per **ProjectInstaller**scegliere **serviceInstaller1** per un progetto Visual C# o su **ServiceInstaller1** per un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4ea24-189">In **Design** view for **ProjectInstaller**, choose **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project.</span></span>  
  
5.  <span data-ttu-id="4ea24-190">Nella finestra **Proprietà** verificare che la proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> sia impostata su **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-190">In the **Properties** window, make sure the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>  
  
6.  <span data-ttu-id="4ea24-191">Specificare un testo per la proprietà **Descrizione** , ad esempio "Servizio di esempio".</span><span class="sxs-lookup"><span data-stu-id="4ea24-191">Set the **Description** property to some text, such as "A sample service".</span></span> <span data-ttu-id="4ea24-192">Questo testo viene visualizzato nella finestra Servizi e consente all'utente di identificare il servizio e comprenderne la funzione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-192">This text appears in the Services window and helps the user identify the service and understand what it’s used for.</span></span>  
  
7.  <span data-ttu-id="4ea24-193">Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> sul testo da visualizzare nella colonna **Nome** della finestra Servizi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-193">Set the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property to the text that you want to appear in the Services window in the **Name** column.</span></span> <span data-ttu-id="4ea24-194">Ad esempio, è possibile immettere "Nome visualizzato MyNewService".</span><span class="sxs-lookup"><span data-stu-id="4ea24-194">For example, you can enter "MyNewService Display Name".</span></span> <span data-ttu-id="4ea24-195">Questo nome può essere diverso dalla proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , che rappresenta il nome usato dal sistema (ad esempio, quando si usa il comando `net start` per avviare il servizio).</span><span class="sxs-lookup"><span data-stu-id="4ea24-195">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name used by the system (for example, when you use the `net start` command to start your service).</span></span>  
  
8.  <span data-ttu-id="4ea24-196">Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="4ea24-196">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span></span>  
  
     <span data-ttu-id="4ea24-197">![Proprietà di installazione per un servizio Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span><span class="sxs-lookup"><span data-stu-id="4ea24-197">![Installer Properties for a Windows Service](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span></span>  
  
9. <span data-ttu-id="4ea24-198">Nella finestra di progettazione scegliere **serviceProcessInstaller1** per un progetto Visual C# o **ServiceProcessInstaller1** per un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4ea24-198">In the designer, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project.</span></span> <span data-ttu-id="4ea24-199">Impostare la proprietà <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> su <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span><span class="sxs-lookup"><span data-stu-id="4ea24-199">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span></span> <span data-ttu-id="4ea24-200">In questo modo il servizio verrà installato ed eseguito su un account del servizio locale.</span><span class="sxs-lookup"><span data-stu-id="4ea24-200">This will cause the service to be installed and to run on a local service account.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4ea24-201">L'account <xref:System.ServiceProcess.ServiceAccount.LocalSystem> dispone di ampie autorizzazioni, tra cui la possibilità di scrivere nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-201">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="4ea24-202">Usare questo account con attenzione, perché potrebbe aumentare il rischio di attacchi da parte di software dannoso.</span><span class="sxs-lookup"><span data-stu-id="4ea24-202">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="4ea24-203">Per altre attività, è opportuno usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a tutti i server remoti.</span><span class="sxs-lookup"><span data-stu-id="4ea24-203">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="4ea24-204">Questo esempio non riesce se si tenta di usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> perché sono necessarie le autorizzazioni per scrivere nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-204">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>  
  
     <span data-ttu-id="4ea24-205">Per altre informazioni sui programmi di installazione, vedere [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="4ea24-205">For more information about installers, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
<a name="BK_StartupParameters"></a>   
## <a name="set-startup-parameters"></a><span data-ttu-id="4ea24-206">Impostare i parametri di avvio</span><span class="sxs-lookup"><span data-stu-id="4ea24-206">Set Startup Parameters</span></span>  
 <span data-ttu-id="4ea24-207">Un servizio Windows, come qualsiasi altro file eseguibile, può accettare gli argomenti della riga di comando o i parametri di avvio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-207">A Windows Service, like any other executable, can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="4ea24-208">Quando si aggiunge il codice ai parametri di avvio del processo, gli utenti possono avviare il servizio con i parametri di avvio personalizzati usando la finestra Servizi nel Pannello di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea24-208">When you add code to process startup parameters, users can start your service with their own custom startup parameters by using the Services window in the Windows Control Panel.</span></span> <span data-ttu-id="4ea24-209">Tuttavia, questi parametri di avvio non vengono mantenuti al successivo avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-209">However, these startup parameters are not persisted the next time the service starts.</span></span> <span data-ttu-id="4ea24-210">Per impostare i parametri di avvio in modo permanente, è possibile impostarli nel Registro di sistema, come illustrato in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4ea24-210">To set startup parameters permanently, you can set them in the registry, as shown in this procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ea24-211">Prima di decidere di aggiungere parametri di avvio, valutare se sia l'approccio migliore per passare informazioni al servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-211">Before you decide to add startup parameters, consider whether that is the best way to pass information to your service.</span></span> <span data-ttu-id="4ea24-212">Anche se i parametri di avvio sono facili da usare e da analizzare e gli utenti possono facilmente eseguirne l'override, potrebbero essere più difficili da individuare e usare senza documentazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-212">Although startup parameters are easy to use and to parse, and users can easily override them, they might be harder for users to discover and use without documentation.</span></span> <span data-ttu-id="4ea24-213">In generale, se il servizio richiede diversi parametri di avvio, provare a usare il Registro di sistema o un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-213">Generally, if your service requires more than just a few startup parameters, you should consider using the registry or a configuration file instead.</span></span> <span data-ttu-id="4ea24-214">Ogni servizio Windows ha una voce nel Registro di sistema in HKLM\System\CurrentControlSet\services.</span><span class="sxs-lookup"><span data-stu-id="4ea24-214">Every Windows Service has an entry in the registry under HKLM\System\CurrentControlSet\services.</span></span> <span data-ttu-id="4ea24-215">Nella chiave del servizio è possibile usare la sottochiave **Parametri** per archiviare le informazioni a cui il servizio può accedere.</span><span class="sxs-lookup"><span data-stu-id="4ea24-215">Under the service's key, you can use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="4ea24-216">È possibile usare i file di configurazione dell'applicazione per un servizio Windows in modo analogo a come avviene per gli altri tipi di programmi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-216">You can use application configuration files for a Windows Service the same way you do for other types of programs.</span></span> <span data-ttu-id="4ea24-217">Per il codice di esempio, vedere <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ea24-217">For example code, see <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span></span>  
  
#### <a name="adding-startup-parameters"></a><span data-ttu-id="4ea24-218">Aggiunta di parametri di avvio</span><span class="sxs-lookup"><span data-stu-id="4ea24-218">Adding startup parameters</span></span>  
  
1.  <span data-ttu-id="4ea24-219">Nel metodo `Main` in Program.cs o in MyNewService.Designer.vb aggiungere un argomento per la riga di comando:</span><span class="sxs-lookup"><span data-stu-id="4ea24-219">In the `Main` method in Program.cs or in MyNewService.Designer.vb, add an argument for the command line:</span></span>  
  
```csharp  
static void Main(string[] args)
{
    ServiceBase[] ServicesToRun = new ServiceBase[] { new MyNewService(args) };
    ServiceBase.Run(ServicesToRun);
}
```  
  
```vb
Shared Sub Main(ByVal cmdArgs() As String)
    Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
    System.ServiceProcess.ServiceBase.Run(ServicesToRun)
End Sub
```  
  
2.  <span data-ttu-id="4ea24-220">Modificare il costruttore `MyNewService` come segue:</span><span class="sxs-lookup"><span data-stu-id="4ea24-220">Change the `MyNewService` constructor as follows:</span></span>  
  
```csharp  
public MyNewService(string[] args)
{
    InitializeComponent();
    string eventSourceName = "MySource";
    string logName = "MyNewLog";
    if (args.Count() > 0) 
    {
        eventSourceName = args[0];
    }
    if (args.Count() > 1)
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
  
<span data-ttu-id="4ea24-221">Questo codice imposta l'origine evento e il nome log in base ai parametri di avvio forniti oppure usa i valori predefiniti se non vengono forniti argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ea24-221">This code sets the event source and log name according to the supplied startup parameters, or uses default values if no arguments are supplied.</span></span>  
  
3. <span data-ttu-id="4ea24-222">Per specificare gli argomenti della riga di comando, aggiungere il codice seguente alla classe `ProjectInstaller` in ProjectInstaller.cs o ProjectInstaller.vb:</span><span class="sxs-lookup"><span data-stu-id="4ea24-222">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in ProjectInstaller.cs or ProjectInstaller.vb:</span></span>  
  
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
  
<span data-ttu-id="4ea24-223">Questo codice modifica la chiave del Registro di sistema **ImagePath** , che in genere contiene il percorso completo dell'eseguibile per il servizio Windows, aggiungendo i valori dei parametri predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4ea24-223">This code modifies the **ImagePath** registry key, which typically contains the full path to the executable for the Windows Service, by adding the default parameter values.</span></span> <span data-ttu-id="4ea24-224">Le virgolette che racchiudono il percorso, e ogni singolo parametro, sono necessarie per il corretto avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-224">The quotation marks around the path (and around each individual parameter) are required for the service to start up correctly.</span></span> <span data-ttu-id="4ea24-225">Per modificare i parametri di avvio per questo servizio Windows, gli utenti possono modificare i parametri specificati nella chiave del Registro di sistema **ImagePath** , anche se l'approccio migliore consiste nell'eseguire la modifica a livello di codice ed esporre le funzionalità agli utenti in modo intuitivo, ad esempio in un'utilità di configurazione o gestione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-225">To change the startup parameters for this Windows Service, users can change the parameters given in the **ImagePath** registry key, although the better way is to change it programmatically and expose the functionality to users in a friendly way (for example, in a management or configuration utility).</span></span>  
  
<a name="BK_Build"></a>   
## <a name="building-the-service"></a><span data-ttu-id="4ea24-226">Compilazione del servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-226">Building the Service</span></span>  
  
#### <a name="to-build-your-service-project"></a><span data-ttu-id="4ea24-227">Per compilare il progetto di servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-227">To build your service project</span></span>  
  
1.  <span data-ttu-id="4ea24-228">In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-228">In **Solution Explorer**, open the context menu for your project, and then choose **Properties**.</span></span> <span data-ttu-id="4ea24-229">Verranno visualizzate le pagine delle proprietà per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4ea24-229">The property pages for your project  appear.</span></span>  
  
2.  <span data-ttu-id="4ea24-230">Nell'elenco **Oggetto di avvio** della scheda Applicazione scegliere **MyNewService.Program**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-230">On the Application tab, in the **Startup object** list, choose **MyNewService.Program**.</span></span>  
  
3.  <span data-ttu-id="4ea24-231">In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Compila** per compilare il progetto (scelta rapida da tastiera: CTRL+MAIUSC+B).</span><span class="sxs-lookup"><span data-stu-id="4ea24-231">In **Solution Explorer**, open the context menu for your project, and then choose **Build** to build the project (Keyboard: Ctrl+Shift+B).</span></span>  
  
<a name="BK_Install"></a>   
## <a name="installing-the-service"></a><span data-ttu-id="4ea24-232">Installazione del servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-232">Installing the Service</span></span>  
 <span data-ttu-id="4ea24-233">Una volta compilato il servizio Windows, è possibile installarlo.</span><span class="sxs-lookup"><span data-stu-id="4ea24-233">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="4ea24-234">Per installare un servizio Windows, è necessario avere le credenziali amministrative nel computer in cui viene eseguita l'installazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-234">To install a Windows service, you must have administrative credentials on the computer on which you're installing it.</span></span>  
  
#### <a name="to-install-a-windows-service"></a><span data-ttu-id="4ea24-235">Per installare un servizio Windows</span><span class="sxs-lookup"><span data-stu-id="4ea24-235">To install a Windows Service</span></span>  
  
1.  <span data-ttu-id="4ea24-236">In Windows 7 e Windows Server aprire il **Prompt dei comandi per gli sviluppatori** negli **Strumenti di Visual Studio** nel menu **Start** .</span><span class="sxs-lookup"><span data-stu-id="4ea24-236">In Windows 7 and Windows Server, open the **Developer Command Prompt** under **Visual Studio Tools** in the **Start** menu.</span></span> <span data-ttu-id="4ea24-237">In Windows 8 o Windows 8.1 scegliere il riquadro **Strumenti di Visual Studio** nella schermata **Start** , quindi eseguire il Prompt dei comandi per gli sviluppatori con credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="4ea24-237">In Windows 8 or Windows 8.1, choose the **Visual Studio Tools** tile on the **Start** screen, and then run Developer Command Prompt with administrative credentials.</span></span> <span data-ttu-id="4ea24-238">Se si usa un mouse, fare clic con il pulsante destro del mouse su **Prompt dei comandi per gli sviluppatori**, quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-238">(If you’re using a mouse, right-click on **Developer Command Prompt**, and then choose **Run as Administrator**.)</span></span>  
  
2.  <span data-ttu-id="4ea24-239">Nella finestra del prompt dei comandi passare alla cartella che contiene l'output del progetto.</span><span class="sxs-lookup"><span data-stu-id="4ea24-239">In the Command Prompt window, navigate to the folder that contains your project's output.</span></span> <span data-ttu-id="4ea24-240">Ad esempio, nella cartella Documenti passare a Visual Studio 2013\Progetti\MyNewService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="4ea24-240">For example, under your My Documents folder, navigate to Visual Studio 2013\Projects\MyNewService\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="4ea24-241">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4ea24-241">Enter the following command:</span></span>  
  
    ```  
    installutil.exe MyNewService.exe  
    ```  
  
     <span data-ttu-id="4ea24-242">Se il servizio viene installato correttamente, tramite il file installutil.exe verrà segnalato l'esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4ea24-242">If the service installs successfully, installutil.exe will report success.</span></span> <span data-ttu-id="4ea24-243">Se il sistema non riesce a trovare InstallUtil.exe, assicurarsi che sia presente nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="4ea24-243">If the system could not find InstallUtil.exe, make sure that it exists on your computer.</span></span> <span data-ttu-id="4ea24-244">Questo strumento viene installato con .NET Framework nella cartella `%WINDIR%\Microsoft.NET\Framework[64]\`*versione_framework*.</span><span class="sxs-lookup"><span data-stu-id="4ea24-244">This tool is installed with the .NET Framework to the folder `%WINDIR%\Microsoft.NET\Framework[64]\`*framework_version*.</span></span> <span data-ttu-id="4ea24-245">Ad esempio, per la versione a 32 bit di .NET Framework 4, 4.5, 4.5.1 o 4.5.2. il percorso predefinito è `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="4ea24-245">For example, the default path for the 32-bit version of the .NET Framework 4, 4.5, 4.5.1, and 4.5.2 is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span>  
  
     <span data-ttu-id="4ea24-246">Se il processo installutil.exe segnala un errore, controllare il log di installazione per determinarne il motivo.</span><span class="sxs-lookup"><span data-stu-id="4ea24-246">If the installutil.exe process reports failure, check the install log to find out why.</span></span> <span data-ttu-id="4ea24-247">Per impostazione predefinita, il log è nella stessa cartella del file eseguibile del servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-247">By default the log is in the same folder as the service executable.</span></span> <span data-ttu-id="4ea24-248">L'installazione può non riuscire se il <xref:System.ComponentModel.RunInstallerAttribute> classe non è presente nel `ProjectInstaller` classe, altrimenti l'attributo non è impostata su `true`, oppure `ProjectInstaller` non `public`.</span><span class="sxs-lookup"><span data-stu-id="4ea24-248">The installation can fail if  the <xref:System.ComponentModel.RunInstallerAttribute> Class is not present on the `ProjectInstaller` class, or else the attribute is not set to `true`, or else the `ProjectInstaller` class is not `public`.</span></span>  
  
     <span data-ttu-id="4ea24-249">Per altre informazioni, vedere [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ea24-249">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
<a name="BK_StartService"></a>   
## <a name="starting-and-running-the-service"></a><span data-ttu-id="4ea24-250">Avvio ed esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-250">Starting and Running the Service</span></span>  
  
#### <a name="to-start-and-stop-your-service"></a><span data-ttu-id="4ea24-251">Per avviare e interrompere il servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-251">To start and stop your service</span></span>  
  
1.  <span data-ttu-id="4ea24-252">In Windows aprire la schermata **Start** o il menu **Start** , quindi digitare `services.msc`.</span><span class="sxs-lookup"><span data-stu-id="4ea24-252">In Windows, open the **Start** screen or **Start** menu, and type `services.msc`.</span></span>  
  
     <span data-ttu-id="4ea24-253">Nella finestra **Servizi** ora dovrebbe essere visualizzato **MyNewService** .</span><span class="sxs-lookup"><span data-stu-id="4ea24-253">You should now see **MyNewService** listed in the **Services** window.</span></span>  
  
     <span data-ttu-id="4ea24-254">![MyNewService nella finestra servizi. ] (../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "WindowsServices_ServicesWindow")</span><span class="sxs-lookup"><span data-stu-id="4ea24-254">![MyNewService in the Services window.](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "WindowsServices_ServicesWindow")</span></span>  
  
2.  <span data-ttu-id="4ea24-255">Nella finestra **Servizi** aprire il menu di scelta rapida per il servizio, quindi scegliere **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-255">In the **Services** window, open the shortcut menu for your service, and then choose **Start**.</span></span>  
  
3.  <span data-ttu-id="4ea24-256">Aprire il menu di scelta rapida per il servizio, quindi scegliere **Arresta**.</span><span class="sxs-lookup"><span data-stu-id="4ea24-256">Open the shortcut menu for the service, and then choose **Stop**.</span></span>  
  
4.  <span data-ttu-id="4ea24-257">Dalla riga di comando è possibile usare i comandi `net start``ServiceName` e `net stop``ServiceName` per avviare e arrestare il servizio (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="4ea24-257">(Optional) From the command line, you can use the commands `net start``ServiceName` and `net stop``ServiceName` to start and stop your service.</span></span>  
  
#### <a name="to-verify-the-event-log-output-of-your-service"></a><span data-ttu-id="4ea24-258">Per verificare l'output del log eventi del servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-258">To verify the event log output of your service</span></span>  
  
1.  <span data-ttu-id="4ea24-259">In Visual Studio aprire **Esplora server** (scelta rapida da tastiera: CTRL+ALT+S) e accedere al nodo **Log eventi** per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="4ea24-259">In Visual Studio, open **Server Explorer** (Keyboard: Ctrl+Alt+S), and access the **Event Logs** node for the local computer.</span></span>  
  
2.  <span data-ttu-id="4ea24-260">Individuare l'elenco per **MyNewLog** (o **MyLogFile1**, se è stata usata la procedura facoltativa per aggiungere gli argomenti della riga di comando) ed espanderlo.</span><span class="sxs-lookup"><span data-stu-id="4ea24-260">Locate the listing for **MyNewLog** (or **MyLogFile1**, if you used the optional procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="4ea24-261">Verranno visualizzate le voci per le due azioni (avvio e arresto) eseguite dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea24-261">You should see entries for the two actions (start and stop) your service has performed.</span></span>  
  
     <span data-ttu-id="4ea24-262">![Utilizzare il Visualizzatore eventi per visualizzare le voci del registro eventi. ] (../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "WindowsServices_EventViewer")</span><span class="sxs-lookup"><span data-stu-id="4ea24-262">![Use the Event Viewer to see the event log entries.](../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "WindowsServices_EventViewer")</span></span>  
  
<a name="BK_Uninstall"></a>   
## <a name="uninstalling-a-windows-service"></a><span data-ttu-id="4ea24-263">Disinstallazione di un servizio Windows</span><span class="sxs-lookup"><span data-stu-id="4ea24-263">Uninstalling a Windows Service</span></span>  
  
#### <a name="to-uninstall-your-service"></a><span data-ttu-id="4ea24-264">Per disinstallare il servizio</span><span class="sxs-lookup"><span data-stu-id="4ea24-264">To uninstall your service</span></span>  
  
1.  <span data-ttu-id="4ea24-265">Aprire un prompt dei comandi per gli sviluppatori con credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="4ea24-265">Open a developer command prompt with administrative credentials.</span></span>  
  
2.  <span data-ttu-id="4ea24-266">Nella finestra del prompt dei comandi passare alla cartella che contiene l'output del progetto.</span><span class="sxs-lookup"><span data-stu-id="4ea24-266">In the Command Prompt window, navigate to the folder that contains your project's output.</span></span> <span data-ttu-id="4ea24-267">Ad esempio, nella cartella Documenti passare a Visual Studio 2013\Progetti\MyNewService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="4ea24-267">For example, under your My Documents folder, navigate to Visual Studio 2013\Projects\MyNewService\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="4ea24-268">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4ea24-268">Enter the following command:</span></span>  
  
    ```  
    installutil.exe /u MyNewService.exe  
    ```  
  
     <span data-ttu-id="4ea24-269">Se il servizio viene disinstallato correttamente, tramite il file installutil.exe verrà segnalato che il servizio è stato rimosso correttamente.</span><span class="sxs-lookup"><span data-stu-id="4ea24-269">If the service uninstalls successfully, installutil.exe will report that your service was successfully removed.</span></span> <span data-ttu-id="4ea24-270">Per altre informazioni, vedere [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ea24-270">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4ea24-271">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4ea24-271">Next Steps</span></span>  
 <span data-ttu-id="4ea24-272">È possibile creare un programma di installazione autonomo che altri utenti possono usare per installare il servizio Windows, ma sono richiesti alcuni passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="4ea24-272">You can create a standalone setup program that others can use to install your Windows service, but it requires additional steps.</span></span> <span data-ttu-id="4ea24-273">ClickOnce non supporta i servizi Windows, pertanto non è possibile usare Pubblicazione guidata.</span><span class="sxs-lookup"><span data-stu-id="4ea24-273">ClickOnce doesn't support Windows services, so you can't use the Publish Wizard.</span></span> <span data-ttu-id="4ea24-274">È possibile usare una versione completa di InstallShield, che è però non fornita da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ea24-274">You can use a full edition of InstallShield, which Microsoft doesn't provide.</span></span> <span data-ttu-id="4ea24-275">Per altre informazioni su InstallShield, vedere [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition).</span><span class="sxs-lookup"><span data-stu-id="4ea24-275">For more information about InstallShield, see [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition).</span></span> <span data-ttu-id="4ea24-276">È inoltre possibile usare il [set di strumenti XML di Windows Installer](http://go.microsoft.com/fwlink/?LinkId=249067) per creare un programma di installazione per un servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea24-276">You can also use the [Windows Installer XML Toolset](http://go.microsoft.com/fwlink/?LinkId=249067) to create an installer for a Windows service.</span></span>  
  
 <span data-ttu-id="4ea24-277">Per inviare comandi al servizio installato, è anche possibile usare il componente <xref:System.ServiceProcess.ServiceController> .</span><span class="sxs-lookup"><span data-stu-id="4ea24-277">You might explore the use of a <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you have installed.</span></span>  
  
 <span data-ttu-id="4ea24-278">È possibile usare il programma di installazione per creare un log eventi durante l'installazione dell'applicazione, anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-278">You can use an installer to create an event log when the application is installed instead of creating the event log when the application runs.</span></span> <span data-ttu-id="4ea24-279">Il log eventi verrà inoltre eliminato dal programma di installazione durante la disinstallazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ea24-279">Additionally, the event log will be deleted by the installer when the application is uninstalled.</span></span> <span data-ttu-id="4ea24-280">Per altre informazioni, vedere la pagina di riferimento <xref:System.Diagnostics.EventLogInstaller> .</span><span class="sxs-lookup"><span data-stu-id="4ea24-280">For more information, see the <xref:System.Diagnostics.EventLogInstaller> reference page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea24-281">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ea24-281">See Also</span></span>  
 [<span data-ttu-id="4ea24-282">Applicazioni di servizi Windows</span><span class="sxs-lookup"><span data-stu-id="4ea24-282">Windows Service Applications</span></span>](../../../docs/framework/windows-services/index.md)  
 [<span data-ttu-id="4ea24-283">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="4ea24-283">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="4ea24-284">Procedura: eseguire il Debug di applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="4ea24-284">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="4ea24-285">Servizi (Windows)</span><span class="sxs-lookup"><span data-stu-id="4ea24-285">Services (Windows)</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
