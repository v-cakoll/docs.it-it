---
title: Rilevamento personalizzato
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 32abf1dc4c9607b4a86f836fa2c759af1dbf1b69
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989405"
---
# <a name="custom-tracking"></a><span data-ttu-id="2812c-102">Rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="2812c-102">Custom Tracking</span></span>
<span data-ttu-id="2812c-103">Nell'esempio viene illustrato come creare un partecipante di rilevamento personalizzato e scrivere il contenuto dei dati di rilevamento nella console.</span><span class="sxs-lookup"><span data-stu-id="2812c-103">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="2812c-104">Nell'esempio viene inoltre illustrato come generare oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> popolati con dati definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2812c-104">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="2812c-105">Il partecipante di rilevamento basato su console filtra gli oggetti <xref:System.Activities.Tracking.TrackingRecord> generati dal flusso di lavoro usando un oggetto profilo di rilevamento creato nel codice.</span><span class="sxs-lookup"><span data-stu-id="2812c-105">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>

## <a name="sample-details"></a><span data-ttu-id="2812c-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="2812c-106">Sample Details</span></span>
 <span data-ttu-id="2812c-107">Windows Workflow Foundation (WF) fornisce un'infrastruttura di rilevamento per tenere traccia dell'esecuzione di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-107">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="2812c-108">Il runtime di rilevamento implementa un'istanza del flusso di lavoro per generare eventi correlati al ciclo di vita del flusso di lavoro, eventi da attività del flusso di lavoro ed eventi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2812c-108">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="2812c-109">Nella tabella seguente sono indicati in dettaglio i componenti primari dell'infrastruttura di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2812c-109">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="2812c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2812c-110">Component</span></span>|<span data-ttu-id="2812c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2812c-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2812c-112">Esecuzione del rilevamento</span><span class="sxs-lookup"><span data-stu-id="2812c-112">Tracking runtime</span></span>|<span data-ttu-id="2812c-113">Fornisce l'infrastruttura per la creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2812c-113">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="2812c-114">Partecipanti del rilevamento</span><span class="sxs-lookup"><span data-stu-id="2812c-114">Tracking participants</span></span>|<span data-ttu-id="2812c-115">Usa i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2812c-115">Consumes the tracking records.</span></span> [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] <span data-ttu-id="2812c-116">viene fornito con un partecipante del rilevamento che scrive record di rilevamento come eventi ETW (Traccia eventi per Windows).</span><span class="sxs-lookup"><span data-stu-id="2812c-116">ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="2812c-117">Profilo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2812c-117">Tracking profile</span></span>|<span data-ttu-id="2812c-118">Meccanismo di filtro che consente a un partecipante del rilevamento di sottoscrivere un subset dei record di rilevamento creati da un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-118">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

 <span data-ttu-id="2812c-119">Nella tabella seguente vengono indicati in dettaglio i record di rilevamento creati dall'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-119">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="2812c-120">Record di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2812c-120">Tracking Record</span></span>|<span data-ttu-id="2812c-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2812c-121">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="2812c-122">Record di rilevamento dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-122">Workflow instance tracking records.</span></span>|<span data-ttu-id="2812c-123">Descrivono il ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-123">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="2812c-124">Ad esempio un record di istanza viene creato quando viene avviato o completato il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-124">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="2812c-125">Record di rilevamento dello stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2812c-125">Activity state Tracking Records.</span></span>|<span data-ttu-id="2812c-126">Illustrano in dettaglio l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2812c-126">Details activity execution.</span></span> <span data-ttu-id="2812c-127">Questi record indicano lo stato di un'attività del flusso di lavoro, ad esempio quando un'attività viene pianificata, quando viene completata o quando viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="2812c-127">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="2812c-128">Record di ripresa del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="2812c-128">Bookmark resumption record.</span></span>|<span data-ttu-id="2812c-129">Generato quando viene ripreso un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-129">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="2812c-130">Record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2812c-130">Custom Tracking Records.</span></span>|<span data-ttu-id="2812c-131">Un autore del flusso di lavoro può creare record di rilevamento personalizzati e generarli all'interno dell'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2812c-131">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|

 <span data-ttu-id="2812c-132">Il partecipante di rilevamento sottoscrive un subset degli oggetti <xref:System.Activities.Tracking.TrackingRecord> generati usando profili di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2812c-132">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="2812c-133">Un profilo di rilevamento contiene query di rilevamento che consentono la sottoscrizione di un particolare tipo di record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2812c-133">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="2812c-134">I profili di rilevamento possono essere specificati nel codice o nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="2812c-134">Tracking profiles can be specified in code or in configuration.</span></span>

### <a name="custom-tracking-participant"></a><span data-ttu-id="2812c-135">Partecipante di rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="2812c-135">Custom Tracking Participant</span></span>
 <span data-ttu-id="2812c-136">L'API del partecipante di rilevamento consente l'estensione del runtime di rilevamento con un partecipante di rilevamento fornito dall'utente, che può includere la logica personalizzata per gestire gli oggetti <xref:System.Activities.Tracking.TrackingRecord> generati dall'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-136">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>

 <span data-ttu-id="2812c-137">Per scrivere un partecipante di rilevamento l'utente deve implementare <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="2812c-137">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="2812c-138">In particolare, il metodo <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> deve essere implementato dal partecipante personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2812c-138">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="2812c-139">Questo metodo viene chiamato quando un oggetto <xref:System.Activities.Tracking.TrackingRecord> viene generato dall'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-139">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 <span data-ttu-id="2812c-140">Il partecipante di rilevamento completo viene implementato nel file ConsoleTrackingParticipant.cs.</span><span class="sxs-lookup"><span data-stu-id="2812c-140">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.</span></span> <span data-ttu-id="2812c-141">L'esempio di codice seguente è <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> il metodo per il partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2812c-141">The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 <span data-ttu-id="2812c-142">Nell'esempio di codice seguente viene aggiunto il partecipante della console all'oggetto invoker del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2812c-142">The following code example adds the console participant to the workflow invoker.</span></span>

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="2812c-143">Creazione di record di rilevamento personalizzati</span><span class="sxs-lookup"><span data-stu-id="2812c-143">Emitting Custom Tracking Records</span></span>
 <span data-ttu-id="2812c-144">In questo esempio viene inoltre illustrata la possibilità di generare oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> da un'attività flusso di lavoro personalizzata:</span><span class="sxs-lookup"><span data-stu-id="2812c-144">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>

- <span data-ttu-id="2812c-145">Gli oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> vengono creati e popolati con dati definiti dall'utente che si desidera vengano generati con il record.</span><span class="sxs-lookup"><span data-stu-id="2812c-145">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>

- <span data-ttu-id="2812c-146">Viene emesso chiamando il metodo Track dell'oggetto <xref:System.Activities.ActivityContext>. <xref:System.Activities.Tracking.CustomTrackingRecord></span><span class="sxs-lookup"><span data-stu-id="2812c-146">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>

 <span data-ttu-id="2812c-147">Nell'esempio seguente viene illustrato come generare oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> all'interno di un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2812c-147">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="2812c-148">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="2812c-148">To use this sample</span></span>

1. <span data-ttu-id="2812c-149">Con Visual Studio 2010 aprire il file della soluzione CustomTrackingSample. sln.</span><span class="sxs-lookup"><span data-stu-id="2812c-149">Using Visual Studio 2010, open the CustomTrackingSample.sln solution file.</span></span>

2. <span data-ttu-id="2812c-150">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="2812c-150">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="2812c-151">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="2812c-151">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2812c-152">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2812c-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2812c-153">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2812c-153">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="2812c-154">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi.</span><span class="sxs-lookup"><span data-stu-id="2812c-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2812c-155">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2812c-155">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="2812c-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2812c-156">See also</span></span>

- [<span data-ttu-id="2812c-157">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="2812c-157">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
