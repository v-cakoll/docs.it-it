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
# <a name="tutorial-create-a-windows-service-app"></a><span data-ttu-id="1da61-102">Esercitazione: creare un'app di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="1da61-102">Tutorial: Create a Windows service app</span></span>

<span data-ttu-id="1da61-103">Questo articolo illustra come creare in Visual Studio un'app di servizio di Windows che scrive messaggi in un log eventi.</span><span class="sxs-lookup"><span data-stu-id="1da61-103">This article demonstrates how to create a Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="1da61-104">Creare un servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-104">Create a service</span></span>

<span data-ttu-id="1da61-105">Le prime operazioni da effettuare sono la creazione del progetto e l'impostazione dei valori necessari per garantire il corretto funzionamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-105">To begin, create the project and set the values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="1da61-106">Dal menu **File** di Visual Studio scegliere **Nuovo** > **Progetto** (o premere **CTRL**+**MAIUSC**+**N**) per aprire la finestra **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="1da61-106">From the Visual Studio **File** menu, select **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** window.</span></span>

2. <span data-ttu-id="1da61-107">Cercare e selezionare il modello di progetto **Servizio di Windows (.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="1da61-107">Navigate to and select the **Windows Service (.NET Framework)** project template.</span></span> <span data-ttu-id="1da61-108">Per trovarlo, espandere **Installati** e \*\*Visual C# \*\* o **Visual Basic** e quindi selezionare **Windows Desktop**.</span><span class="sxs-lookup"><span data-stu-id="1da61-108">To find it, expand **Installed** and **Visual C#** or **Visual Basic**, then select **Windows Desktop**.</span></span> <span data-ttu-id="1da61-109">In alternativa, immettere *Servizio di Windows* nella casella di ricerca in alto a destra e premere **Invio**.</span><span class="sxs-lookup"><span data-stu-id="1da61-109">Or, enter *Windows Service* in the search box on the upper right and press **Enter**.</span></span>

   ![Modello Servizio Windows nella finestra di dialogo Nuovo progetto di Visual Studio](./media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="1da61-111">Se il modello di **servizio Windows** non è visibile, potrebbe essere necessario installare il carico di lavoro sviluppo di applicazioni **desktop .NET** :</span><span class="sxs-lookup"><span data-stu-id="1da61-111">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload:</span></span>
   >
   > <span data-ttu-id="1da61-112">Nella finestra di dialogo **Nuovo progetto** selezionare **Apri il programma di installazione di Visual Studio** in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1da61-112">In the **New Project** dialog, select **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="1da61-113">Selezionare il carico di lavoro **Sviluppo per desktop .NET** e quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1da61-113">Select the **.NET desktop development** workload, and then select **Modify**.</span></span>

3. <span data-ttu-id="1da61-114">Per **Nome** immettere *MyNewService* e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1da61-114">For **Name**, enter *MyNewService*, and then select **OK**.</span></span>

   <span data-ttu-id="1da61-115">Verrà visualizzata la scheda **Progettazione** (**Service1.cs [Progettazione]** oppure **Service1.vb [Progettazione]**).</span><span class="sxs-lookup"><span data-stu-id="1da61-115">The **Design** tab appears (**Service1.cs [Design]** or **Service1.vb [Design]**).</span></span>

   <span data-ttu-id="1da61-116">Il modello di progetto include una classe di componente denominata `Service1` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1da61-116">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1da61-117">Include gran parte del codice del servizio di base, ad esempio il codice per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-117">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="1da61-118">Rinominare il servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-118">Rename the service</span></span>

<span data-ttu-id="1da61-119">Rinominare il servizio da **Service1** a **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="1da61-119">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="1da61-120">In **Esplora soluzioni** selezionare **Service1.cs** o **Service1.vb** e quindi scegliere **Rinomina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1da61-120">In **Solution Explorer**, select **Service1.cs**, or **Service1.vb**, and choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="1da61-121">Rinominare il file in **MyNewService.cs** o in **MyNewService.vb** e quindi premere **Invio**</span><span class="sxs-lookup"><span data-stu-id="1da61-121">Rename the file to **MyNewService.cs**, or **MyNewService.vb**, and then press **Enter**</span></span>

    <span data-ttu-id="1da61-122">Una finestra popup chiederà se si vogliono rinominare tutti i riferimenti all'elemento di codice *Service1*.</span><span class="sxs-lookup"><span data-stu-id="1da61-122">A pop-up window appears asking whether you would like to rename all references to the code element *Service1*.</span></span>

2. <span data-ttu-id="1da61-123">Nella finestra popup selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1da61-123">In the pop-up window, select **Yes**.</span></span>

    <span data-ttu-id="1da61-124">![Domanda sulla ridenominazione](./media/windows-service-rename.png "Domanda sulla ridenominazione del servizio di Windows")</span><span class="sxs-lookup"><span data-stu-id="1da61-124">![Rename prompt](./media/windows-service-rename.png "Windows service rename prompt")</span></span>

3. <span data-ttu-id="1da61-125">Nella scheda **Progettazione** selezionare **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1da61-125">In the **Design** tab, select **Properties** from the shortcut menu.</span></span> <span data-ttu-id="1da61-126">Nella finestra **Proprietà** cambiare il valore di **ServiceName** in *MyNewService*.</span><span class="sxs-lookup"><span data-stu-id="1da61-126">From the **Properties** window, change the **ServiceName** value to *MyNewService*.</span></span>

    <span data-ttu-id="1da61-127">![Proprietà del servizio](./media/windows-service-properties.png "Proprietà del servizio di Windows")</span><span class="sxs-lookup"><span data-stu-id="1da61-127">![Service properties](./media/windows-service-properties.png "Windows service properties")</span></span>

4. <span data-ttu-id="1da61-128">Selezionare **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="1da61-128">Select **Save All** from the **File** menu.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="1da61-129">Aggiungere funzionalità al servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-129">Add features to the service</span></span>

<span data-ttu-id="1da61-130">In questa sezione verrà aggiunto un log eventi personalizzato al servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-130">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="1da61-131">Il componente <xref:System.Diagnostics.EventLog> è un esempio del tipo di componente che è possibile aggiungere a un servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-131">The <xref:System.Diagnostics.EventLog> component is an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="1da61-132">Aggiungere la funzionalità del log eventi personalizzato</span><span class="sxs-lookup"><span data-stu-id="1da61-132">Add custom event log functionality</span></span>

1. <span data-ttu-id="1da61-133">Dal menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb** in **Esplora soluzioni** scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="1da61-133">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="1da61-134">Nella **Casella degli strumenti** espandere **Componenti** e quindi trascinare il componente **EventLog** nella scheda **Service1.cs [Progettazione]** o **Service1.vb [Progettazione]**.</span><span class="sxs-lookup"><span data-stu-id="1da61-134">In **Toolbox**, expand **Components**, and then drag the **EventLog** component to the **Service1.cs [Design]**, or **Service1.vb [Design]** tab.</span></span>

3. <span data-ttu-id="1da61-135">Dal menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb** in **Esplora soluzioni** scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="1da61-135">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Code**.</span></span>

4. <span data-ttu-id="1da61-136">Definire un log eventi personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1da61-136">Define a custom event log.</span></span> <span data-ttu-id="1da61-137">Per C#, modificare il costruttore `MyNewService()` esistente. Per Visual Basic, aggiungere il costruttore `New()`:</span><span class="sxs-lookup"><span data-stu-id="1da61-137">For C#, edit the existing `MyNewService()` constructor; for Visual Basic, add the `New()` constructor:</span></span>

   [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. <span data-ttu-id="1da61-138">Aggiungere un'istruzione `using` a **MyNewService.cs** (se non esiste già) o un'istruzione `Imports` a **MyNewService.vb** per lo spazio dei nomi <xref:System.Diagnostics?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1da61-138">Add a `using` statement to **MyNewService.cs** (if it doesn't already exist), or an `Imports` statement **MyNewService.vb**, for the <xref:System.Diagnostics?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. <span data-ttu-id="1da61-139">Selezionare **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="1da61-139">Select **Save All** from the **File** menu.</span></span>

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="1da61-140">Definire quello che accade quando il servizio viene avviato</span><span class="sxs-lookup"><span data-stu-id="1da61-140">Define what occurs when the service starts</span></span>

<span data-ttu-id="1da61-141">Nell'editor di codice per **MyNewService.cs** o **MyNewService.vb** individuare il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Visual Studio ha creato automaticamente una definizione di metodo vuota quando è stato creato il progetto.</span><span class="sxs-lookup"><span data-stu-id="1da61-141">In the code editor for **MyNewService.cs** or **MyNewService.vb**, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method; Visual Studio automatically created an empty method definition when you created the project.</span></span> <span data-ttu-id="1da61-142">Aggiungere codice che scriva una voce nel log eventi all'avvio del servizio:</span><span class="sxs-lookup"><span data-stu-id="1da61-142">Add code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a><span data-ttu-id="1da61-143">Polling</span><span class="sxs-lookup"><span data-stu-id="1da61-143">Polling</span></span>

<span data-ttu-id="1da61-144">Poiché le applicazioni di servizio sono progettate per un'esecuzione di lunga durata, generalmente eseguono operazioni di polling o di monitoraggio del sistema, che vengono configurate nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="1da61-144">Because a service application is designed to be long-running, it usually polls or monitors the system, which you set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="1da61-145">Il metodo `OnStart` deve rispondere al sistema operativo dopo l'avvio del servizio, perché il sistema non rimanga bloccato.</span><span class="sxs-lookup"><span data-stu-id="1da61-145">The `OnStart` method must return to the operating system after the service's operation has begun so that the system isn't blocked.</span></span>

<span data-ttu-id="1da61-146">Per impostare un semplice meccanismo di polling, usare il componente <xref:System.Timers.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1da61-146">To set up a simple polling mechanism, use the <xref:System.Timers.Timer?displayProperty=nameWithType> component.</span></span> <span data-ttu-id="1da61-147">Il timer genera un evento <xref:System.Timers.Timer.Elapsed> a intervalli regolari. In corrispondenza di questo evento il servizio può eseguire il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="1da61-147">The timer raises an <xref:System.Timers.Timer.Elapsed> event at regular intervals, at which time your service can do its monitoring.</span></span> <span data-ttu-id="1da61-148">Per usare il componente <xref:System.Timers.Timer> eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1da61-148">You use the <xref:System.Timers.Timer> component as follows:</span></span>

- <span data-ttu-id="1da61-149">Impostare le proprietà del componente <xref:System.Timers.Timer> nel metodo `MyNewService.OnStart`.</span><span class="sxs-lookup"><span data-stu-id="1da61-149">Set the properties of the <xref:System.Timers.Timer> component in the `MyNewService.OnStart` method.</span></span>
- <span data-ttu-id="1da61-150">Avviare il timer tramite una chiamata al metodo <xref:System.Timers.Timer.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="1da61-150">Start the timer by calling the <xref:System.Timers.Timer.Start%2A> method.</span></span>

##### <a name="set-up-the-polling-mechanism"></a><span data-ttu-id="1da61-151">Configurare il meccanismo di polling.</span><span class="sxs-lookup"><span data-stu-id="1da61-151">Set up the polling mechanism.</span></span>

1. <span data-ttu-id="1da61-152">Aggiungere il codice seguente nell'evento `MyNewService.OnStart` per configurare il meccanismo di polling:</span><span class="sxs-lookup"><span data-stu-id="1da61-152">Add the following code in the `MyNewService.OnStart` event to set up the polling mechanism:</span></span>

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

2. <span data-ttu-id="1da61-153">Aggiungere un'istruzione `using` a **MyNewService.cs** o un'istruzione `Imports` a **MyNewService.vb** per lo spazio dei nomi <xref:System.Timers?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1da61-153">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Timers?displayProperty=nameWithType> namespace:</span></span>

   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```

3. <span data-ttu-id="1da61-154">Nella classe `MyNewService` aggiungere il metodo `OnTimer` per gestire l'evento <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1da61-154">In the `MyNewService` class, add the `OnTimer` method to handle the <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> event:</span></span>

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

4. <span data-ttu-id="1da61-155">Nella classe `MyNewService` aggiungere una variabile membro.</span><span class="sxs-lookup"><span data-stu-id="1da61-155">In the `MyNewService` class, add a member variable.</span></span> <span data-ttu-id="1da61-156">Questa contiene l'identificatore dell'evento successivo da scrivere nel log eventi:</span><span class="sxs-lookup"><span data-stu-id="1da61-156">It contains the identifier of the next event to write into the event log:</span></span>

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

<span data-ttu-id="1da61-157">Invece di eseguire tutto il lavoro nel thread principale, è possibile eseguire le attività tramite thread di lavoro in background.</span><span class="sxs-lookup"><span data-stu-id="1da61-157">Instead of running all your work on the main thread, you can run tasks by using background worker threads.</span></span> <span data-ttu-id="1da61-158">Per altre informazioni, vedere <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1da61-158">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="1da61-159">Definire quello che accade quando il servizio viene arrestato</span><span class="sxs-lookup"><span data-stu-id="1da61-159">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="1da61-160">Inserire nel metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> una riga di codice che aggiunga una voce nel log eventi all'arresto del servizio:</span><span class="sxs-lookup"><span data-stu-id="1da61-160">Insert a line of code in the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

[!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="1da61-161">Definire altre azioni del servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-161">Define other actions for the service</span></span>

<span data-ttu-id="1da61-162">È possibile eseguire l'override dei metodi <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> e <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> per definire ulteriori operazioni di elaborazione del componente.</span><span class="sxs-lookup"><span data-stu-id="1da61-162">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span>

<span data-ttu-id="1da61-163">Il codice seguente illustra come eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> nella classe `MyNewService`:</span><span class="sxs-lookup"><span data-stu-id="1da61-163">The following code shows how you to override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method in the `MyNewService` class:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

## <a name="set-service-status"></a><span data-ttu-id="1da61-164">Impostare lo stato del servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-164">Set service status</span></span>

<span data-ttu-id="1da61-165">I servizi segnalano il proprio stato a [Gestione controllo servizi](/windows/desktop/Services/service-control-manager), in modo che gli utenti possano stabilire se un servizio funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="1da61-165">Services report their status to the [Service Control Manager](/windows/desktop/Services/service-control-manager) so that a user can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="1da61-166">Per impostazione predefinita, un servizio che eredita da <xref:System.ServiceProcess.ServiceBase> segnala un set limitato di impostazioni di stato, ovvero SERVICE_STOPPED, SERVICE_PAUSED e SERVICE_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="1da61-166">By default, a service that inherits from <xref:System.ServiceProcess.ServiceBase> reports a limited set of status settings, which include SERVICE_STOPPED, SERVICE_PAUSED, and SERVICE_RUNNING.</span></span> <span data-ttu-id="1da61-167">Se l'avvio di un servizio richiede tempo, è utile segnalare lo stato SERVICE_START_PENDING.</span><span class="sxs-lookup"><span data-stu-id="1da61-167">If a service takes a while to start up, it's useful to report a SERVICE_START_PENDING status.</span></span>

<span data-ttu-id="1da61-168">È possibile implementare le impostazioni di stato SERVICE_START_PENDING e SERVICE_STOP_PENDING aggiungendo codice che chiami la funzione [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) di Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-168">You can implement the SERVICE_START_PENDING and SERVICE_STOP_PENDING status settings by adding code that calls the Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function.</span></span>

### <a name="implement-service-pending-status"></a><span data-ttu-id="1da61-169">Implementare lo stato corrispondente al servizio in sospeso</span><span class="sxs-lookup"><span data-stu-id="1da61-169">Implement service pending status</span></span>

1. <span data-ttu-id="1da61-170">Aggiungere un'istruzione `using` a **MyNewService.cs** o un'istruzione `Imports` a **MyNewService.vb** per lo spazio dei nomi <xref:System.Runtime.InteropServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1da61-170">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="1da61-171">Aggiungere il codice seguente in **MyNewService.cs** o in **MyNewService.vb** per dichiarare i valori di `ServiceState` e per aggiungere una struttura per lo stato da usare in una chiamata platform invoke:</span><span class="sxs-lookup"><span data-stu-id="1da61-171">Add the following code to **MyNewService.cs**, or **MyNewService.vb**, to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

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
    > <span data-ttu-id="1da61-172">La finestra di dialogo Gestione controllo servizi usa i membri `dwWaitHint` e `dwCheckpoint` della [struttura SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) per determinare il tempo di attesa per l'avvio o l'arresto di un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-172">The Service Control Manager uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/win32/api/winsvc/ns-winsvc-service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="1da61-173">Se l'esecuzione dei metodi `OnStart` e `OnStop` è prolungata, il servizio può richiedere più tempo chiamando di nuovo `SetServiceStatus` con un valore di `dwCheckPoint` incrementato.</span><span class="sxs-lookup"><span data-stu-id="1da61-173">If your `OnStart` and `OnStop` methods run long, your service can request more time by calling `SetServiceStatus` again with an incremented `dwCheckPoint` value.</span></span>

3. <span data-ttu-id="1da61-174">Nella classe `MyNewService` dichiarare la funzione [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) usando [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span><span class="sxs-lookup"><span data-stu-id="1da61-174">In the `MyNewService` class, declare the [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="1da61-175">Per implementare lo stato SERVICE_START_PENDING, aggiungere il codice seguente all'inizio del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>:</span><span class="sxs-lookup"><span data-stu-id="1da61-175">To implement the SERVICE_START_PENDING status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

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

5. <span data-ttu-id="1da61-176">Aggiungere codice alla fine del metodo `OnStart` per impostare lo stato su SERVICE_RUNNING:</span><span class="sxs-lookup"><span data-stu-id="1da61-176">Add code to the end of the `OnStart` method to set the status to SERVICE_RUNNING:</span></span>

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

6. <span data-ttu-id="1da61-177">(Facoltativo) Se <xref:System.ServiceProcess.ServiceBase.OnStop%2A> è un metodo a esecuzione prolungata, ripetere questa procedura nel metodo `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="1da61-177">(Optional) If <xref:System.ServiceProcess.ServiceBase.OnStop%2A> is a long-running method, repeat this procedure in the `OnStop` method.</span></span> <span data-ttu-id="1da61-178">Implementare lo stato SERVICE_STOP_PENDING e restituire lo stato SERVICE_STOPPED prima che il metodo `OnStop` esca.</span><span class="sxs-lookup"><span data-stu-id="1da61-178">Implement the SERVICE_STOP_PENDING status and return the SERVICE_STOPPED status before the `OnStop` method exits.</span></span>

   <span data-ttu-id="1da61-179">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1da61-179">For example:</span></span>

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

## <a name="add-installers-to-the-service"></a><span data-ttu-id="1da61-180">Aggiungere programmi di installazione al servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-180">Add installers to the service</span></span>

<span data-ttu-id="1da61-181">Prima di eseguire un servizio di Windows, è necessario installarlo, ovvero registrarlo con Gestione controllo servizi.</span><span class="sxs-lookup"><span data-stu-id="1da61-181">Before you run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="1da61-182">Per gestire i dettagli della registrazione, aggiungere programmi di installazione al progetto.</span><span class="sxs-lookup"><span data-stu-id="1da61-182">Add installers to your project to handle the registration details.</span></span>

1. <span data-ttu-id="1da61-183">Dal menu di scelta rapida per **MyNewService.cs** o **MyNewService.vb** in **Esplora soluzioni** scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="1da61-183">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="1da61-184">Nella visualizzazione **Progettazione** selezionare l'area di sfondo e quindi scegliere **Aggiungi programma di installazione** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1da61-184">In the **Design** view, select the background area, then choose **Add Installer** from the shortcut menu.</span></span>

     <span data-ttu-id="1da61-185">Per impostazione predefinita, Visual Studio aggiunge al progetto una classe di componenti denominata `ProjectInstaller`, contenente due programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="1da61-185">By default, Visual Studio adds a component class named `ProjectInstaller`, which contains two installers, to your project.</span></span> <span data-ttu-id="1da61-186">Questi programmi di installazione sono destinati al servizio e al processo associato al servizio stesso.</span><span class="sxs-lookup"><span data-stu-id="1da61-186">These installers are for your service and for the service's associated process.</span></span>

3. <span data-ttu-id="1da61-187">Nella visualizzazione **Progettazione** per **ProjectInstaller** selezionare **serviceInstaller1** per un progetto Visual C# o **ServiceInstaller1** per un progetto Visual Basic e quindi scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1da61-187">In the **Design** view for **ProjectInstaller**, select **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="1da61-188">Nella finestra **Proprietà** verificare che la proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> sia impostata su **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="1da61-188">In the **Properties** window, verify the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

5. <span data-ttu-id="1da61-189">Aggiungere testo alla proprietà <xref:System.ServiceProcess.ServiceInstaller.Description%2A>, ad esempio *A sample service* (Servizio di esempio).</span><span class="sxs-lookup"><span data-stu-id="1da61-189">Add text to the <xref:System.ServiceProcess.ServiceInstaller.Description%2A> property, such as *A sample service*.</span></span>

     <span data-ttu-id="1da61-190">Questo testo, che viene visualizzato nella colonna **Descrizione** della finestra **Servizi**, descrive il servizio all'utente.</span><span class="sxs-lookup"><span data-stu-id="1da61-190">This text appears in the **Description** column of the **Services** window and describes the service to the user.</span></span>

    <span data-ttu-id="1da61-191">![Descrizione del servizio nella finestra Servizi. ](./media/windows-service-description.png "Descrizione del servizio")</span><span class="sxs-lookup"><span data-stu-id="1da61-191">![Service description in the Services window.](./media/windows-service-description.png "Service description")</span></span>

6. <span data-ttu-id="1da61-192">Aggiungere testo alla proprietà <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A>,</span><span class="sxs-lookup"><span data-stu-id="1da61-192">Add text to the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property.</span></span> <span data-ttu-id="1da61-193">ad esempio, *MyNewService Display Name* (Nome visualizzato di MyNewService).</span><span class="sxs-lookup"><span data-stu-id="1da61-193">For example, *MyNewService Display Name*.</span></span>

     <span data-ttu-id="1da61-194">Questo testo viene visualizzato nella colonna **Nome visualizzato** della finestra **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="1da61-194">This text appears in the **Display Name** column of the **Services** window.</span></span> <span data-ttu-id="1da61-195">Questo nome può essere diverso dalla proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>, che corrisponde al nome usato dal sistema, ad esempio il nome usato con il comando `net start` per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-195">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name the system uses (for example, the name you use for the `net start` command to start your service).</span></span>

7. <span data-ttu-id="1da61-196">Impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su <xref:System.ServiceProcess.ServiceStartMode.Automatic> dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1da61-196">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic> from the drop-down list.</span></span>

8. <span data-ttu-id="1da61-197">Al termine, la finestra **Proprietà** dovrebbe avere l'aspetto della figura seguente:</span><span class="sxs-lookup"><span data-stu-id="1da61-197">When you're finished, the **Properties** windows should look like the following figure:</span></span>

     <span data-ttu-id="1da61-198">![Proprietà del programma di installazione per un servizio di Windows](./media/windows-service-installer-properties.png "Proprietà del programma di installazione di un servizio di Windows")</span><span class="sxs-lookup"><span data-stu-id="1da61-198">![Installer Properties for a Windows service](./media/windows-service-installer-properties.png "Windows service installer properties")</span></span>

9. <span data-ttu-id="1da61-199">Nella visualizzazione **Progettazione** per **ProjectInstaller** scegliere **serviceProcessInstaller1** per un progetto Visual C# o **ServiceProcessInstaller1** per un progetto Visual Basic e quindi scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1da61-199">In the **Design** view for **ProjectInstaller**, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="1da61-200">Impostare la proprietà <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> su <xref:System.ServiceProcess.ServiceAccount.LocalSystem> dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1da61-200">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem> from the drop-down list.</span></span>

     <span data-ttu-id="1da61-201">Questa impostazione consente di installare ed eseguire il servizio tramite l'account di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="1da61-201">This setting installs the service and runs it by using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1da61-202">L'account <xref:System.ServiceProcess.ServiceAccount.LocalSystem> dispone di ampie autorizzazioni, tra cui la possibilità di scrivere nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="1da61-202">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="1da61-203">Usare questo account con attenzione, perché potrebbe aumentare il rischio di attacchi da parte di software dannoso.</span><span class="sxs-lookup"><span data-stu-id="1da61-203">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="1da61-204">Per altre attività, è opportuno usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a tutti i server remoti.</span><span class="sxs-lookup"><span data-stu-id="1da61-204">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="1da61-205">Questo esempio non riesce se si tenta di usare l'account <xref:System.ServiceProcess.ServiceAccount.LocalService> perché sono necessarie le autorizzazioni per scrivere nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="1da61-205">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="1da61-206">Per altre informazioni sui programmi di installazione, vedere [procedura: aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="1da61-206">For more information about installers, see [How to: Add installers to your service application](how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="1da61-207">(Facoltativo) Impostare i parametri di avvio</span><span class="sxs-lookup"><span data-stu-id="1da61-207">(Optional) Set startup parameters</span></span>

> [!NOTE]
> <span data-ttu-id="1da61-208">Prima di decidere di aggiungere parametri di avvio, valutare se sia l'approccio migliore per passare informazioni al servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-208">Before you decide to add startup parameters, consider whether it's the best way to pass information to your service.</span></span> <span data-ttu-id="1da61-209">Anche se i parametri di avvio sono facili da usare e da analizzare e gli utenti possono facilmente eseguirne l'override, possono essere più difficili da individuare e da usare senza documentazione.</span><span class="sxs-lookup"><span data-stu-id="1da61-209">Although they're easy to use and parse, and a user can easily override them, they might be harder for a user to discover and use without documentation.</span></span> <span data-ttu-id="1da61-210">In genere, se il servizio richiede diversi parametri di avvio, è consigliabile usare il Registro di sistema o un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1da61-210">Generally, if your service requires more than just a few startup parameters, you should use the registry or a configuration file instead.</span></span>

<span data-ttu-id="1da61-211">Un servizio di Windows può accettare argomenti della riga di comando o parametri di avvio.</span><span class="sxs-lookup"><span data-stu-id="1da61-211">A Windows service can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="1da61-212">Quando si aggiunge il codice ai parametri di avvio del processo, gli utenti possono avviare il servizio con parametri di avvio personalizzati nella finestra delle proprietà del servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-212">When you add code to process startup parameters, a user can start your service with their own custom startup parameters in the service properties window.</span></span> <span data-ttu-id="1da61-213">Questi parametri di avvio, tuttavia, non vengono mantenuti al successivo avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-213">However, these startup parameters aren't persisted the next time the service starts.</span></span> <span data-ttu-id="1da61-214">Per impostare parametri di avvio in modo permanente, impostarli nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="1da61-214">To set startup parameters permanently, set them in the registry.</span></span>

<span data-ttu-id="1da61-215">Ogni servizio di Windows ha una voce del Registro di sistema nella sottochiave **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services**.</span><span class="sxs-lookup"><span data-stu-id="1da61-215">Each Windows service has a registry entry under the **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** subkey.</span></span> <span data-ttu-id="1da61-216">Nella sottochiave di ogni servizio usare la sottochiave **Parameters** per archiviare le informazioni a cui il servizio può accedere.</span><span class="sxs-lookup"><span data-stu-id="1da61-216">Under each service's subkey, use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="1da61-217">È possibile usare i file di configurazione dell'applicazione per un servizio di Windows in modo analogo a come avviene per gli altri tipi di programmi.</span><span class="sxs-lookup"><span data-stu-id="1da61-217">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="1da61-218">Per codice di esempio, vedere <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1da61-218">For sample code, see <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span></span>

### <a name="to-add-startup-parameters"></a><span data-ttu-id="1da61-219">Per aggiungere parametri di avvio</span><span class="sxs-lookup"><span data-stu-id="1da61-219">To add startup parameters</span></span>

1. <span data-ttu-id="1da61-220">Selezionare **Program.cs** o **MyNewService.Designer.vb** e quindi scegliere **Visualizza codice** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1da61-220">Select **Program.cs**, or **MyNewService.Designer.vb**, then choose **View Code** from the shortcut menu.</span></span> <span data-ttu-id="1da61-221">Nel metodo `Main` modificare il codice aggiungendo un parametro di input e passare quest'ultimo al costruttore del servizio:</span><span class="sxs-lookup"><span data-stu-id="1da61-221">In the `Main` method, change the code to add an input parameter and pass it to the service constructor:</span></span>

   [!code-csharp[VbRadconService](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/Program-add-parameter.cs?highlight=1,6)]
   [!code-vb[VbRadconService](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.Designer-add-parameter.vb?highlight=1-2)]

2. <span data-ttu-id="1da61-222">In **MyNewService.cs** o **MyNewService.vb** modificare il costruttore `MyNewService` in modo che elabori il parametro di input come segue:</span><span class="sxs-lookup"><span data-stu-id="1da61-222">In **MyNewService.cs**, or **MyNewService.vb**, change the `MyNewService` constructor to process the input parameter as follows:</span></span>

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

   <span data-ttu-id="1da61-223">Questo codice imposta l'origine e il nome del log dell'evento in base ai parametri di avvio specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1da61-223">This code sets the event source and log name according to the startup parameters that the user supplies.</span></span> <span data-ttu-id="1da61-224">Se non vengono specificati argomenti, usa i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="1da61-224">If no arguments are supplied, it uses default values.</span></span>

3. <span data-ttu-id="1da61-225">Per specificare gli argomenti della riga di comando, aggiungere il codice seguente alla `ProjectInstaller` classe in **ProjectInstaller.cs**o **ProjectInstaller. vb**:</span><span class="sxs-lookup"><span data-stu-id="1da61-225">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in **ProjectInstaller.cs**, or **ProjectInstaller.vb**:</span></span>

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

   <span data-ttu-id="1da61-226">In genere, questo valore contiene il percorso completo del file eseguibile per il servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-226">Typically, this value contains the full path to the executable for the Windows service.</span></span> <span data-ttu-id="1da61-227">Perché il servizio venga avviato correttamente, è necessario usare le virgolette per il percorso e per ogni singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="1da61-227">For the service to start up correctly, the user must supply quotation marks for the path and each individual parameter.</span></span> <span data-ttu-id="1da61-228">È possibile cambiare i parametri nella voce del Registro di sistema **ImagePath** per cambiare i parametri di avvio del servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-228">A user can change the parameters in the **ImagePath** registry entry to change the startup parameters for the Windows service.</span></span> <span data-ttu-id="1da61-229">Una soluzione migliore, tuttavia, consiste nel cambiare il valore a livello di codice e nell'esporre la funzionalità in un modo semplice da usare, ad esempio tramite un'utilità di gestione o di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1da61-229">However, a better way is to change the value programmatically and expose the functionality in a user-friendly way, such as by using a management or configuration utility.</span></span>

## <a name="build-the-service"></a><span data-ttu-id="1da61-230">Compilare il servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-230">Build the service</span></span>

1. <span data-ttu-id="1da61-231">In **Esplora soluzioni** scegliere **Proprietà** dal menu di scelta rapida del progetto **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="1da61-231">In **Solution Explorer**, choose **Properties** from the shortcut menu for the **MyNewService** project.</span></span>

   <span data-ttu-id="1da61-232">Verranno visualizzate le pagine delle proprietà per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1da61-232">The property pages for your project appear.</span></span>

2. <span data-ttu-id="1da61-233">Nell'elenco **Oggetto di avvio** della scheda **Applicazione** scegliere **MyNewService.Program** o **Sub Main** per i progetti Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1da61-233">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**, or **Sub Main** for Visual Basic projects.</span></span>

3. <span data-ttu-id="1da61-234">Per compilare il progetto, in **Esplora soluzioni** scegliere **Compila** dal menu di scelta rapida del progetto o premere **CTRL**+**MAIUSC**+**B**.</span><span class="sxs-lookup"><span data-stu-id="1da61-234">To build the project, in **Solution Explorer**, choose **Build** from the shortcut menu for your project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="1da61-235">Installare il servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-235">Install the service</span></span>

<span data-ttu-id="1da61-236">Una volta compilato il servizio Windows, è possibile installarlo.</span><span class="sxs-lookup"><span data-stu-id="1da61-236">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="1da61-237">Per installare un servizio di Windows, è necessario avere credenziali di amministratore per il computer in cui il servizio è installato.</span><span class="sxs-lookup"><span data-stu-id="1da61-237">To install a Windows service, you must have administrator credentials on the computer where it's installed.</span></span>

1. <span data-ttu-id="1da61-238">Aprire il [Prompt dei comandi per gli sviluppatori per Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) con credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="1da61-238">Open [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) with administrative credentials.</span></span> <span data-ttu-id="1da61-239">Dal menu **Start** di Windows selezionare **Prompt dei comandi per gli sviluppatori per VS 2017** nella cartella di Visual Studio e quindi selezionare **Altro** > **Esegui come amministratore** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1da61-239">From the Windows **Start** menu, select **Developer Command Prompt for VS 2017** in the Visual Studio folder, then select **More** > **Run as Administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="1da61-240">Nella finestra **Prompt dei comandi per gli sviluppatori per Visual Studio** passare alla cartella contenente l'output del progetto, per impostazione predefinita la sottodirectory *\bin\Debug* del progetto.</span><span class="sxs-lookup"><span data-stu-id="1da61-240">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output (by default, the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="1da61-241">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1da61-241">Enter the following command:</span></span>

    ```shell
    installutil MyNewService.exe
    ```

    <span data-ttu-id="1da61-242">Se il servizio viene installato correttamente, il comando segnala l'esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1da61-242">If the service installs successfully, the command reports success.</span></span>

    <span data-ttu-id="1da61-243">Se il sistema non riesce a trovare *installutil.exe*, assicurarsi che sia presente nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="1da61-243">If the system can't find *installutil.exe*, make sure that it exists on your computer.</span></span> <span data-ttu-id="1da61-244">Questo strumento viene installato con il .NET Framework alla cartella *%windir%\Microsoft.NET\Framework [64\\&lt;&gt;] versione del Framework*.</span><span class="sxs-lookup"><span data-stu-id="1da61-244">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\&lt;framework version&gt;*.</span></span> <span data-ttu-id="1da61-245">Il percorso predefinito per la versione a 64 bit, ad esempio, è *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="1da61-245">For example, the default path for the 64-bit version is *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="1da61-246">Se il processo **installutil.exe** ha esito negativo, controllare il log di installazione per determinarne il motivo.</span><span class="sxs-lookup"><span data-stu-id="1da61-246">If the **installutil.exe** process fails, check the install log to find out why.</span></span> <span data-ttu-id="1da61-247">Per impostazione predefinita, il log è nella stessa cartella del file eseguibile del servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-247">By default, the log is in the same folder as the service executable.</span></span> <span data-ttu-id="1da61-248">L'installazione può non riuscire se:</span><span class="sxs-lookup"><span data-stu-id="1da61-248">The installation can fail if:</span></span>
    - <span data-ttu-id="1da61-249">La classe <xref:System.ComponentModel.RunInstallerAttribute> non è presente nella classe `ProjectInstaller`.</span><span class="sxs-lookup"><span data-stu-id="1da61-249">The <xref:System.ComponentModel.RunInstallerAttribute> class isn't present on the `ProjectInstaller` class.</span></span>
    - <span data-ttu-id="1da61-250">L'attributo non è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="1da61-250">The attribute isn't set to `true`.</span></span>
    - <span data-ttu-id="1da61-251">La classe `ProjectInstaller` non è definita come `public`.</span><span class="sxs-lookup"><span data-stu-id="1da61-251">The `ProjectInstaller` class isn't defined as `public`.</span></span>

<span data-ttu-id="1da61-252">Per altre informazioni, vedere [How to: install and Uninstall Services](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="1da61-252">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="1da61-253">Avviare ed eseguire il servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-253">Start and run the service</span></span>

1. <span data-ttu-id="1da61-254">In Windows aprire l'app desktop **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="1da61-254">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="1da61-255">Premere **Windows**+**R** per aprire la casella **Esegui** , immettere *Services. msc*, quindi premere **invio** o fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1da61-255">Press **Windows**+**R** to open the **Run** box, enter *services.msc*, and then press **Enter** or select **OK**.</span></span>

     <span data-ttu-id="1da61-256">Il servizio verrà elencato in **Servizi**, in ordine alfabetico in base al nome visualizzato impostato.</span><span class="sxs-lookup"><span data-stu-id="1da61-256">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![MyNewService nella finestra Servizi.](./media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="1da61-258">Per avviare il servizio, scegliere **Avvia** dal menu di scelta rapida del servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-258">To start the service, choose **Start** from the service's shortcut menu.</span></span>

3. <span data-ttu-id="1da61-259">Per arrestare il servizio, scegliere **Arresta** dal menu di scelta rapida del servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-259">To stop the service, choose **Stop** from the service's shortcut menu.</span></span>

4. <span data-ttu-id="1da61-260">(Facoltativo) Dalla riga di comando usare i comandi **net start &lt;nome servizio&gt;** e **net stop &lt;nome servizio&gt;** per avviare e arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-260">(Optional) From the command line, use the commands **net start &lt;service name&gt;** and **net stop &lt;service name&gt;** to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="1da61-261">Verificare l'output del log eventi del servizio</span><span class="sxs-lookup"><span data-stu-id="1da61-261">Verify the event log output of your service</span></span>

1. <span data-ttu-id="1da61-262">In Windows aprire l'app desktop **Visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="1da61-262">In Windows, open the **Event Viewer** desktop app.</span></span> <span data-ttu-id="1da61-263">Immettere *Visualizzatore eventi* nella barra di ricerca di Windows e quindi selezionare **Visualizzatore eventi** dai risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1da61-263">Enter *Event Viewer* in the Windows search bar, and then select **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="1da61-264">In Visual Studio è possibile accedere ai log eventi aprendo **Esplora server** dal menu **Visualizza**, o premendo **CTRL**+**ALT**+**S**, ed espandendo il nodo **Log eventi** per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="1da61-264">In Visual Studio, you can access event logs by opening **Server Explorer** from the **View** menu (or press **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="1da61-265">Nel **Visualizzatore eventi** espandere **Registri applicazioni e servizi**.</span><span class="sxs-lookup"><span data-stu-id="1da61-265">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="1da61-266">Individuare l'elenco per **MyNewLog** (o **MyLogFile1**, se è stata seguita la procedura per aggiungere argomenti della riga di comando) ed espanderlo.</span><span class="sxs-lookup"><span data-stu-id="1da61-266">Locate the listing for **MyNewLog** (or **MyLogFile1** if you followed the procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="1da61-267">Verranno visualizzate le voci per le due azioni (avvio e arresto) eseguite dal servizio.</span><span class="sxs-lookup"><span data-stu-id="1da61-267">You should see the entries for the two actions (start and stop) that your service performed.</span></span>

     ![Usare il Visualizzatore eventi per visualizzare le voci del log eventi](./media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a><span data-ttu-id="1da61-269">Pulire le risorse</span><span class="sxs-lookup"><span data-stu-id="1da61-269">Clean up resources</span></span>

<span data-ttu-id="1da61-270">Se l'app del servizio di Windows non è più necessaria, è possibile rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="1da61-270">If you no longer need the Windows service app, you can remove it.</span></span>

1. <span data-ttu-id="1da61-271">Aprire il **Prompt dei comandi per gli sviluppatori per Visual Studio** con credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="1da61-271">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="1da61-272">Nella finestra **Prompt dei comandi per gli sviluppatori per Visual Studio** passare alla cartella contenente l'output del progetto.</span><span class="sxs-lookup"><span data-stu-id="1da61-272">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="1da61-273">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1da61-273">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="1da61-274">Se il servizio viene disinstallato correttamente, il comando segnala che il servizio è stato rimosso correttamente.</span><span class="sxs-lookup"><span data-stu-id="1da61-274">If the service uninstalls successfully, the command reports that your service was successfully removed.</span></span> <span data-ttu-id="1da61-275">Per altre informazioni, vedere [How to: install and Uninstall Services](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="1da61-275">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1da61-276">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1da61-276">Next steps</span></span>

<span data-ttu-id="1da61-277">Dopo aver creato il servizio, è possibile:</span><span class="sxs-lookup"><span data-stu-id="1da61-277">Now that you've created the service, you can:</span></span>

- <span data-ttu-id="1da61-278">Creare un programma di installazione autonomo che gli altri utenti possono usare per installare il servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-278">Create a standalone setup program for others to use to install your Windows service.</span></span> <span data-ttu-id="1da61-279">Usare il [set di strumenti WiX](https://wixtoolset.org/) per creare un programma di installazione per un servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="1da61-279">Use the [WiX Toolset](https://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="1da61-280">Per altre idee, vedere [Creare un pacchetto di installazione](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="1da61-280">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

- <span data-ttu-id="1da61-281">Esaminare il componente <xref:System.ServiceProcess.ServiceController>, che consente di inviare comandi al servizio installato.</span><span class="sxs-lookup"><span data-stu-id="1da61-281">Explore the <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

- <span data-ttu-id="1da61-282">Anziché creare il log eventi durante l'esecuzione dell'applicazione, crearlo durante l'installazione dell'applicazione stessa tramite il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="1da61-282">Instead of creating the event log when the application runs, use an installer to create an event log when you install the application.</span></span> <span data-ttu-id="1da61-283">Il log eventi viene eliminato dal programma di installazione quando si disinstalla l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1da61-283">The event log is deleted by the installer when you uninstall the application.</span></span> <span data-ttu-id="1da61-284">Per altre informazioni, vedere <xref:System.Diagnostics.EventLogInstaller>.</span><span class="sxs-lookup"><span data-stu-id="1da61-284">For more information, see <xref:System.Diagnostics.EventLogInstaller>.</span></span>

## <a name="see-also"></a><span data-ttu-id="1da61-285">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1da61-285">See also</span></span>

- [<span data-ttu-id="1da61-286">Applicazioni di servizi di Windows</span><span class="sxs-lookup"><span data-stu-id="1da61-286">Windows service applications</span></span>](index.md)
- [<span data-ttu-id="1da61-287">Introduzione alle applicazioni di servizio di Windows</span><span class="sxs-lookup"><span data-stu-id="1da61-287">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="1da61-288">Procedura: Eseguire il debug di applicazioni di servizio di Windows</span><span class="sxs-lookup"><span data-stu-id="1da61-288">How to: Debug Windows service applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="1da61-289">Servizi (Windows)</span><span class="sxs-lookup"><span data-stu-id="1da61-289">Services (Windows)</span></span>](/windows/desktop/Services/services)
