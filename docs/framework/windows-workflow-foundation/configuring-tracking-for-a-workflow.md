---
title: Configurazione del rilevamento per un flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 905adcc9-30a0-4918-acd6-563f86db988a
ms.openlocfilehash: 97b25873e9f20d5d390b7a59531b3a5af32296df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802674"
---
# <a name="configuring-tracking-for-a-workflow"></a><span data-ttu-id="1a47f-102">Configurazione del rilevamento per un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1a47f-102">Configuring Tracking for a Workflow</span></span>

<span data-ttu-id="1a47f-103">Un flusso di lavoro può essere eseguito in tre modi:</span><span class="sxs-lookup"><span data-stu-id="1a47f-103">A workflow can execute in three ways:</span></span>

- <span data-ttu-id="1a47f-104">Ospitato nell'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="1a47f-104">Hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>

- <span data-ttu-id="1a47f-105">Eseguito come un oggetto <xref:System.Activities.WorkflowApplication></span><span class="sxs-lookup"><span data-stu-id="1a47f-105">Executed as a <xref:System.Activities.WorkflowApplication></span></span>

- <span data-ttu-id="1a47f-106">Eseguito direttamente usando l'oggetto <xref:System.Activities.WorkflowInvoker></span><span class="sxs-lookup"><span data-stu-id="1a47f-106">Executed directly using <xref:System.Activities.WorkflowInvoker></span></span>

<span data-ttu-id="1a47f-107">A seconda dell'opzione di hosting del flusso di lavoro, un partecipante del rilevamento può essere aggiunto tramite codice o un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1a47f-107">Depending on the workflow hosting option, a tracking participant can be added either through code or through a configuration file.</span></span> <span data-ttu-id="1a47f-108">In questo argomento viene descritta la configurazione del rilevamento tramite l'aggiunta di un partecipante del rilevamento agli oggetti <xref:System.Activities.WorkflowApplication> e <xref:System.ServiceModel.Activities.WorkflowServiceHost> e viene illustrato come abilitare il rilevamento quando si usa l'oggetto <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-108">This topic describes how tracking is configured by adding a tracking participant to a <xref:System.Activities.WorkflowApplication> and to a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, and how to enable tracking when using <xref:System.Activities.WorkflowInvoker>.</span></span>

## <a name="configuring-workflow-application-tracking"></a><span data-ttu-id="1a47f-109">Configurazione del rilevamento dell'applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1a47f-109">Configuring Workflow Application Tracking</span></span>

<span data-ttu-id="1a47f-110">Un flusso di lavoro può essere eseguito usando la classe <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-110">A workflow can run using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="1a47f-111">In questo argomento viene illustrata la configurazione del rilevamento per un'applicazione flusso di lavoro di [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tramite l'aggiunta di un partecipante del rilevamento all'host del flusso di lavoro <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-111">This topic demonstrates how tracking is configured for a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] workflow application by adding a tracking participant to the <xref:System.Activities.WorkflowApplication> workflow host.</span></span> <span data-ttu-id="1a47f-112">In questo caso, il flusso di lavoro viene eseguito come un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1a47f-112">In this case, the workflow runs as a workflow application.</span></span> <span data-ttu-id="1a47f-113">Quest'ultima viene configurata tramite codice (anziché tramite un file di configurazione), ovvero un file con estensione exe indipendente che usa la classe <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-113">You configure a workflow application through code (rather than by using a configuration file), which is a self-hosted .exe file using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="1a47f-114">Il partecipante del rilevamento viene aggiunto come estensione all'istanza <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-114">The tracking participant is added as an extension to the <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="1a47f-115">Tale operazione viene eseguita aggiungendo l'oggetto <xref:System.Activities.Tracking.TrackingParticipant> alla raccolta di estensioni per l'istanza WorkflowApplication.</span><span class="sxs-lookup"><span data-stu-id="1a47f-115">This is done by adding the <xref:System.Activities.Tracking.TrackingParticipant> to the extensions collection for the WorkflowApplication instance.</span></span>

<span data-ttu-id="1a47f-116">Per un'applicazione flusso di lavoro, è possibile aggiungere l'estensione di comportamento <xref:System.Activities.Tracking.EtwTrackingParticipant> come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1a47f-116">For a workflow application, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension as shown in the following code.</span></span>

```csharp
LogActivity activity = new LogActivity();

WorkflowApplication instance = new WorkflowApplication(activity);
EtwTrackingParticipant trackingParticipant =
    new EtwTrackingParticipant
{

        TrackingProfile = new TrackingProfile
           {
               Name = "SampleTrackingProfile",
               ActivityDefinitionId = "ProcessOrder",
               Queries = new WorkflowInstanceQuery
               {
                  States = { "*" }
              }
          }
       };
instance.Extensions.Add(trackingParticipant);
```

### <a name="configuring-workflow-service-tracking"></a><span data-ttu-id="1a47f-117">Configurazione del rilevamento del servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1a47f-117">Configuring Workflow Service Tracking</span></span>

<span data-ttu-id="1a47f-118">Un flusso di lavoro può essere esposto come servizio WCF quando è ospitato nell'host del servizio <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-118">A workflow can be exposed as a WCF service when hosted in the <xref:System.ServiceModel.Activities.WorkflowServiceHost> service host.</span></span> <span data-ttu-id="1a47f-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> è un'implementazione specifica di .NET ServiceHost per un servizio basato sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1a47f-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> is a specialized .NET ServiceHost implementation for a workflow-based service.</span></span> <span data-ttu-id="1a47f-120">Contenuto della sezione viene illustrato come configurare il rilevamento per un servizio flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in esecuzione nell'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-120">This section explains how to configure tracking for a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow service running in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="1a47f-121">Viene configurato tramite un file Web.config (per un servizio ospitato sul Web) o un file App.config (per un servizio ospitato in un'applicazione autonoma, ad esempio un'applicazione console) specificando un comportamento del servizio oppure, tramite codice, aggiungendo un comportamento specifico del rilevamento alla raccolta <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> per l'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="1a47f-121">It is configured through a Web.config file (for a Web-hosted service) or an App.config file (for a service hosted in a stand-alone application, such as a console application) by specifying a service behavior or through code by adding a tracking-specific behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection for the service host.</span></span>

<span data-ttu-id="1a47f-122">Per un servizio del flusso di lavoro ospitato in <xref:System.ServiceModel.WorkflowServiceHost>, è possibile aggiungere l'<xref:System.Activities.Tracking.EtwTrackingParticipant> utilizzando l'elemento <`behavior`> in un file di configurazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1a47f-122">For a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>

```xml
<behaviors>
   <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
   </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="1a47f-123">In alternativa, per un servizio del flusso di lavoro ospitato nell'oggetto <xref:System.ServiceModel.WorkflowServiceHost>, è possibile aggiungere l'estensione di comportamento <xref:System.Activities.Tracking.EtwTrackingParticipant> tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="1a47f-123">Alternatively, for a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension through code.</span></span> <span data-ttu-id="1a47f-124">Per aggiungere un partecipante del rilevamento personalizzato, creare una nuova estensione di comportamento e aggiungerla all'oggetto <xref:System.ServiceModel.ServiceHost> come mostrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1a47f-124">To add a custom tracking participant, create a new behavior extension and add it to the <xref:System.ServiceModel.ServiceHost> as shown in the following example code.</span></span>

> [!NOTE]
> <span data-ttu-id="1a47f-125">Se si desidera visualizzare il codice di esempio che illustra come creare un elemento di comportamento personalizzato che aggiunge un partecipante del rilevamento personalizzato, fare riferimento agli esempi di [rilevamento](./samples/tracking.md) .</span><span class="sxs-lookup"><span data-stu-id="1a47f-125">If you want to view sample code that shows how to create a custom behavior element that adds a custom tracking participant, refer to the [Tracking](./samples/tracking.md) samples.</span></span>

```csharp
ServiceHost svcHost = new ServiceHost(typeof(WorkflowService), new
                                 Uri("http://localhost:8001/Sample"));
EtwTrackingBehavior trackingBehavior =
    new EtwTrackingBehavior
    {
        ProfileName = "Sample Tracking Profile"
    };
svcHost.Description.Behaviors.Add(trackingBehavior);
svcHost.Open();
```

<span data-ttu-id="1a47f-126">Il partecipante del rilevamento viene aggiunto all'host del servizio del flusso di lavoro come estensione al comportamento.</span><span class="sxs-lookup"><span data-stu-id="1a47f-126">The tracking participant is added to the workflow service host as an extension to the behavior.</span></span>

<span data-ttu-id="1a47f-127">Nel codice di esempio seguente viene mostrato come leggere un profilo di rilevamento dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1a47f-127">This sample code below shows how to read a tracking profile from configuration file.</span></span>

```csharp
TrackingProfile GetProfile(string profileName, string displayName)
        {
            TrackingProfile trackingProfile = null;
            TrackingSection trackingSection = (TrackingSection)WebConfigurationManager.GetSection("system.serviceModel/tracking");
            if (trackingSection == null)
            {
                return null;
            }

            profileName ??= "";

            //Find the profile with the specified profile name in the list of profile found in config
            var match = from p in new List<TrackingProfile>(trackingSection.TrackingProfiles)
                        where (p.Name == profileName) && ((p.ActivityDefinitionId == displayName) || (p.ActivityDefinitionId == "*"))
                        select p;

            if (match.Count() == 0)
            {
                //return an empty profile
                trackingProfile = new TrackingProfile()
                {
                    ActivityDefinitionId = displayName
                };

            }
            else
            {
                trackingProfile = match.First();
            }

            return trackingProfile;
```

<span data-ttu-id="1a47f-128">In questo codice di esempio viene illustrato come aggiungere un profilo di rilevamento a un host del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1a47f-128">This sample code shows how to add a tracking profile to a workflow host.</span></span>

```csharp
WorkflowServiceHost workflowServiceHost = serviceHostBase as WorkflowServiceHost;
if (null != workflowServiceHost)
{
    string workflowDisplayName = workflowServiceHost.Activity.DisplayName;
    TrackingProfile trackingProfile = GetProfile(this.profileName, workflowDisplayName);
    workflowServiceHost.WorkflowExtensions.Add(()  => new EtwTrackingParticipant {
        TrackingProfile = trackingProfile
    });
 }
```

> [!NOTE]
> <span data-ttu-id="1a47f-129">Per ulteriori informazioni sui profili di rilevamento, vedere [profili di rilevamento](tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1a47f-129">For more information on tracking profiles, refer to [Tracking Profiles](tracking-profiles.md).</span></span>

### <a name="configuring-tracking-using-workflowinvoker"></a><span data-ttu-id="1a47f-130">Configurazione del rilevamento tramite WorkflowInvoker</span><span class="sxs-lookup"><span data-stu-id="1a47f-130">Configuring tracking using WorkflowInvoker</span></span>

<span data-ttu-id="1a47f-131">Per configurare il rilevamento per un flusso di lavoro eseguito usando l'oggetto <xref:System.Activities.WorkflowInvoker>, aggiungere il provider del rilevamento come estensione a un'istanza <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="1a47f-131">To configure tracking for a workflow executed using <xref:System.Activities.WorkflowInvoker>, add the tracking provider as an extension to a <xref:System.Activities.WorkflowInvoker> instance.</span></span> <span data-ttu-id="1a47f-132">L'esempio di codice seguente è riportato nell'esempio di [rilevamento personalizzato](./samples/custom-tracking.md) .</span><span class="sxs-lookup"><span data-stu-id="1a47f-132">The following code example is from the [Custom Tracking](./samples/custom-tracking.md) sample.</span></span>

```csharp
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
invoker.Invoke();
```

### <a name="viewing-tracking-records-in-event-viewer"></a><span data-ttu-id="1a47f-133">Visualizzazione dei record di rilevamento in Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="1a47f-133">Viewing tracking records in Event Viewer</span></span>

<span data-ttu-id="1a47f-134">Esistono due log del Visualizzatore eventi di particolare interesse per il rilevamento dell'esecuzione di WF: il log analitico e il log debug.</span><span class="sxs-lookup"><span data-stu-id="1a47f-134">There are two Event Viewer logs of particular interest to view when tracking WF execution - the Analytic log and the Debug log.</span></span> <span data-ttu-id="1a47f-135">Entrambi i componenti si trovano nel&#124;nodo&#124;server applicazioni-applicazioni di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1a47f-135">Both reside under the Microsoft&#124;Windows&#124;Application Server-Applications node.</span></span> <span data-ttu-id="1a47f-136">I log presenti in questa sezione contengono gli eventi relativi una singola applicazione piuttosto che gli eventi che interessano l'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="1a47f-136">Logs within this section contain events from a single application rather than events that have an impact on the entire system.</span></span>

<span data-ttu-id="1a47f-137">Gli eventi di traccia di debug vengono scritti nel log di debug.</span><span class="sxs-lookup"><span data-stu-id="1a47f-137">Debug trace events are written to the Debug Log.</span></span> <span data-ttu-id="1a47f-138">Per raccogliere gli eventi di traccia di debug di WF nel Visualizzatore eventi, abilitare il log di debug.</span><span class="sxs-lookup"><span data-stu-id="1a47f-138">To collect WF debug trace events in the Event Viewer, enable the Debug Log.</span></span>

1. <span data-ttu-id="1a47f-139">Per aprire Visualizzatore eventi, fare clic sul pulsante **Start**, quindi scegliere **Esegui.**</span><span class="sxs-lookup"><span data-stu-id="1a47f-139">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="1a47f-140">Nella finestra di dialogo Esegui digitare `eventvwr`.</span><span class="sxs-lookup"><span data-stu-id="1a47f-140">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="1a47f-141">Nella finestra di dialogo Visualizzatore eventi espandere il nodo **registri applicazioni e servizi** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-141">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="1a47f-142">Espandere i nodi **Microsoft**, **Windows**e **server applicazioni-applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-142">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="1a47f-143">Fare clic con il pulsante destro del mouse sul nodo **debug** nel nodo **server applicazioni-applicazioni** e selezionare **Attiva log**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-143">Right-click the **Debug** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="1a47f-144">Eseguire l'applicazione abilitata per il rilevamento per generare gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1a47f-144">Execute your tracing-enabled application to generate tracing events.</span></span>

6. <span data-ttu-id="1a47f-145">Fare clic con il pulsante destro del mouse sul nodo **debug** e selezionare **Aggiorna.**</span><span class="sxs-lookup"><span data-stu-id="1a47f-145">Right-click the **Debug** node and select **Refresh.**</span></span> <span data-ttu-id="1a47f-146">Gli eventi di traccia verranno visualizzati nel riquadro centrale.</span><span class="sxs-lookup"><span data-stu-id="1a47f-146">Tracing events should be visible in the center pane.</span></span>

<span data-ttu-id="1a47f-147">In WF 4 è presente un partecipante del rilevamento mediante il quale vengono scritti i record di rilevamento in una sessione ETW (Event Tracing for Windows).</span><span class="sxs-lookup"><span data-stu-id="1a47f-147">WF 4 provides a tracking participant that writes tracking records to an ETW (Event Tracing for Windows) session.</span></span> <span data-ttu-id="1a47f-148">Il partecipante del rilevamento ETW viene configurato con un profilo di rilevamento per sottoscrivere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1a47f-148">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span> <span data-ttu-id="1a47f-149">Quando il rilevamento è abilitato, vengono generati record di rilevamento di errori su ETW.</span><span class="sxs-lookup"><span data-stu-id="1a47f-149">When tracking is enabled, errors tracking records are emitted to ETW.</span></span> <span data-ttu-id="1a47f-150">Gli eventi di rilevamento ETW (in un intervallo da 100 a 113) corrispondenti agli eventi di rilevamento generati dal partecipante del rilevamento ETW vengono scritti nel log analitico.</span><span class="sxs-lookup"><span data-stu-id="1a47f-150">ETW tracking events (between the range of 100-113) corresponding to the tracking events emitted by the ETW tracking participant are written to the Analytic Log.</span></span>

<span data-ttu-id="1a47f-151">Per visualizzare i record di rilevamento, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="1a47f-151">To view tracking records, follow these steps.</span></span>

1. <span data-ttu-id="1a47f-152">Per aprire Visualizzatore eventi, fare clic sul pulsante **Start**, quindi scegliere **Esegui.**</span><span class="sxs-lookup"><span data-stu-id="1a47f-152">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="1a47f-153">Nella finestra di dialogo Esegui digitare `eventvwr`.</span><span class="sxs-lookup"><span data-stu-id="1a47f-153">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="1a47f-154">Nella finestra di dialogo Visualizzatore eventi espandere il nodo **registri applicazioni e servizi** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-154">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="1a47f-155">Espandere i nodi **Microsoft**, **Windows**e **server applicazioni-applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-155">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="1a47f-156">Fare clic con il pulsante destro del mouse sul nodo **analitico** nel nodo **server applicazioni-applicazioni** e selezionare **Abilita log**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-156">Right-click the **Analytic** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="1a47f-157">Eseguire l'applicazione abilitata per il rilevamento per generare record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1a47f-157">Execute your tracking-enabled application to generate tracking records.</span></span>

6. <span data-ttu-id="1a47f-158">Fare clic con il pulsante destro del mouse sul nodo **analitico** e selezionare **Aggiorna.**</span><span class="sxs-lookup"><span data-stu-id="1a47f-158">Right-click the **Analytic** node and select **Refresh.**</span></span> <span data-ttu-id="1a47f-159">I record di rilevamento dovrebbero essere visibili nel riquadro centrale.</span><span class="sxs-lookup"><span data-stu-id="1a47f-159">Tracking records should be visible in the center pane.</span></span>

<span data-ttu-id="1a47f-160">Nella figura seguente vengono mostrati gli eventi di rilevamento nel Visualizzatore eventi:</span><span class="sxs-lookup"><span data-stu-id="1a47f-160">The following image shows tracking events in the event viewer:</span></span>

![Screenshot della Visualizzatore eventi che mostra i record di rilevamento.](./media/configuring-tracking-for-a-workflow/tracking-event-viewer.png)

### <a name="registering-an-application-specific-provider-id"></a><span data-ttu-id="1a47f-162">Registrazione di un ID provider specifico dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="1a47f-162">Registering an application-specific provider ID</span></span>

<span data-ttu-id="1a47f-163">Se gli eventi devono essere scritti in un registro applicazioni specifico, attenersi alla seguente procedura per registrare il nuovo manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="1a47f-163">If events need to be written to a specific application log, follow these steps to register the new provider manifest.</span></span>

1. <span data-ttu-id="1a47f-164">Dichiarare l'ID provider nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a47f-164">Declare the provider ID in the application configuration file.</span></span>

    ```xml
    <system.serviceModel>
        <diagnostics etwProviderId="2720e974-9fe9-477a-bb60-81fe3bf91eec"/>
    </system.serviceModel>
    ```

2. <span data-ttu-id="1a47f-165">Copiare il file manifesto da%windir%\Microsoft.NET\Framework\\\<versione più recente di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]> \Microsoft.Windows.ApplicationServer.Applications.man in un percorso temporaneo e rinominarlo in Microsoft. Windows. ApplicationServer. Applications_Provider1. Man</span><span class="sxs-lookup"><span data-stu-id="1a47f-165">Copy the manifest file from %windir%\Microsoft.NET\Framework\\\<latest version of [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]>\Microsoft.Windows.ApplicationServer.Applications.man to a temporary location, and rename it to Microsoft.Windows.ApplicationServer.Applications_Provider1.man</span></span>

3. <span data-ttu-id="1a47f-166">Modificare il GUID del file manifesto con il nuovo GUID.</span><span class="sxs-lookup"><span data-stu-id="1a47f-166">Change the GUID in the manifest file to the new GUID.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"
    ```

4. <span data-ttu-id="1a47f-167">Modificare il nome del provider se non si desidera disinstallare il provider predefinito.</span><span class="sxs-lookup"><span data-stu-id="1a47f-167">Change the provider name if you do not want to uninstall the default provider.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"
    ```

5. <span data-ttu-id="1a47f-168">Se è stato modificato il nome del provider nel passaggio precedente, modificare i nomi dei canali nel file manifesto in base al nuovo nome del provider.</span><span class="sxs-lookup"><span data-stu-id="1a47f-168">If you changed the provider name in the previous step, change the channel names in the manifest file to the new provider name.</span></span>

    ```xml
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Admin" chid="ADMIN_CHANNEL" symbol="ADMIN_CHANNEL" type="Admin" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ADMIN_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Operational" chid="OPERATIONAL_CHANNEL" symbol="OPERATIONAL_CHANNEL" type="Operational" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.OPERATIONAL_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Debug" chid="DEBUG_CHANNEL" symbol="DEBUG_CHANNEL" type="Debug" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.DEBUG_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Perf" chid="PERF_CHANNEL" symbol="PERF_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.PERF_CHANNEL.message)" />
    ```

6. <span data-ttu-id="1a47f-169">Generare la DLL di risorse attenendosi ai passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="1a47f-169">Generate the resource DLL by following these steps.</span></span>

    1. <span data-ttu-id="1a47f-170">Installare Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="1a47f-170">Install the Windows SDK.</span></span> <span data-ttu-id="1a47f-171">Il Windows SDK include il compilatore di messaggi ([MC. exe](/windows/win32/wes/message-compiler--mc-exe-)) e il compilatore di risorse ([RC. exe](/windows/win32/menurc/using-rc-the-rc-command-line-)).</span><span class="sxs-lookup"><span data-stu-id="1a47f-171">The Windows SDK includes the message compiler ([mc.exe](/windows/win32/wes/message-compiler--mc-exe-)) and resource compiler ([rc.exe](/windows/win32/menurc/using-rc-the-rc-command-line-)).</span></span>

    2. <span data-ttu-id="1a47f-172">In un prompt dei comandi di Windows SDK, eseguire mc.exe nel nuovo file manifesto.</span><span class="sxs-lookup"><span data-stu-id="1a47f-172">In a Windows SDK command prompt, run mc.exe on the new manifest file.</span></span>

        ```console
        mc.exe Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

    3. <span data-ttu-id="1a47f-173">Eseguire rc.exe nel file di risorse generato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1a47f-173">Run rc.exe on the resource file generated in the previous step.</span></span>

        ```console
        rc.exe  Microsoft.Windows.ApplicationServer.Applications_Provider1.rc
        ```

    4. <span data-ttu-id="1a47f-174">Creare un file cs vuoto denominato NewProviderReg.cs.</span><span class="sxs-lookup"><span data-stu-id="1a47f-174">Create an empty cs file called NewProviderReg.cs.</span></span>

    5. <span data-ttu-id="1a47f-175">Creare una DLL di risorse usando il compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="1a47f-175">Create a resource DLL using the C# compiler.</span></span>

        ```console
        csc /target:library /win32res:Microsoft.Windows.ApplicationServer.Applications_Provider1.res NewProviderReg.cs /out:Microsoft.Windows.ApplicationServer.Applications_Provider1.dll
        ```

    6. <span data-ttu-id="1a47f-176">Modificare il nome della risorsa e della dll del messaggio nel file manifesto da `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` al nuovo nome della dll.</span><span class="sxs-lookup"><span data-stu-id="1a47f-176">Change the resource and message dll name in the manifest file from `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` to the new dll name.</span></span>

        ```xml
        <provider name="Microsoft-Windows-Application Server-Applications_Provider1" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" symbol="Microsoft_Windows_ApplicationServer_ApplicationEvents" resourceFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" messageFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll">
        ```

    7. <span data-ttu-id="1a47f-177">Usare [wevtutil](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10)) per registrare il manifesto.</span><span class="sxs-lookup"><span data-stu-id="1a47f-177">Use [wevtutil](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10)) to register the manifest.</span></span>

        ```console
        wevtutil im Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

## <a name="see-also"></a><span data-ttu-id="1a47f-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a47f-178">See also</span></span>

- <span data-ttu-id="1a47f-179">[Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1a47f-179">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="1a47f-180">[Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1a47f-180">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
