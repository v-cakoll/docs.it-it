---
title: Profili di rilevamento
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 9217f25ba4499e7ff75020642be387aa79ba27bf
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837623"
---
# <a name="tracking-profiles"></a><span data-ttu-id="ff9aa-102">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ff9aa-102">Tracking Profiles</span></span>

<span data-ttu-id="ff9aa-103">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro creati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-103">Tracking profiles contain tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span>

## <a name="tracking-profiles"></a><span data-ttu-id="ff9aa-104">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ff9aa-104">Tracking Profiles</span></span>

<span data-ttu-id="ff9aa-105">I profili di rilevamento vengono usati per specificare le informazioni di rilevamento generate per un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-105">Tracking profiles are used to specify which tracking information is emitted for a workflow instance.</span></span> <span data-ttu-id="ff9aa-106">Se non è specificato alcun profilo, vengono generati tutti gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-106">If no profile is specified, then all tracking events are emitted.</span></span> <span data-ttu-id="ff9aa-107">Se viene specificato un profilo, verranno generati gli eventi di rilevamento specificati nel profilo.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-107">If a profile is specified, then the tracking events specified in the profile will be emitted.</span></span> <span data-ttu-id="ff9aa-108">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generale che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ff9aa-108">Depending on your monitoring requirements, you may write a profile that is very general, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="ff9aa-109">oppure creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-109">Conversely, you may create a very detailed profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>

<span data-ttu-id="ff9aa-110">I profili di rilevamento si manifestano come elementi XML all'interno di un file di configurazione .NET Framework standard o specificati nel codice.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-110">Tracking profiles manifest themselves as XML elements within a standard .NET Framework configuration file or specified in code.</span></span> <span data-ttu-id="ff9aa-111">Nell'esempio seguente è illustrato un profilo di rilevamento di [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] in un file di configurazione che consente a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro `Started` e `Completed`.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-111">The following example is of a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>

```xml
<system.serviceModel>
    ...
    <tracking>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started"/>
                <state name="Completed"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
    ...
</system.serviceModel>
```

<span data-ttu-id="ff9aa-112">Nell'esempio seguente viene illustrato il profilo di rilevamento equivalente creato usando il codice.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-112">The following example shows the equivalent tracking profile created using code.</span></span>

```csharp
TrackingProfile profile = new TrackingProfile()
{
    Name = "CustomTrackingProfile",
    Queries =
    {
        new WorkflowInstanceQuery()
        {
            // Limit workflow instance tracking records for started and
            // completed workflow states.
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },
        }
    }
};
```

<span data-ttu-id="ff9aa-113">I record di rilevamento vengono filtrati tramite la modalità di visibilità all'interno di un profilo di rilevamento usando l'attributo <xref:System.Activities.Tracking.ImplementationVisibility>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-113">Tracking records are filtered through the visibility mode within a tracking profile by using the <xref:System.Activities.Tracking.ImplementationVisibility> attribute.</span></span> <span data-ttu-id="ff9aa-114">Un'attività composita è un'attività di primo livello che contiene le altre attività che formano l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-114">A composite activity is a top-level activity that contains other activities that form its implementation.</span></span> <span data-ttu-id="ff9aa-115">La modalità di visibilità specifica i record di rilevamento creati dalle attività composite all'interno di un'attività di flusso di lavoro per specificare se le attività che formano l'implementazione vengono rilevate.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-115">The visibility mode specifies the tracking records emitted from composite activities within a workflow activity, to specify if activities that form the implementation are being tracked.</span></span> <span data-ttu-id="ff9aa-116">La modalità di visibilità si applica a livello del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-116">The visibility mode applies at the tracking profile level.</span></span> <span data-ttu-id="ff9aa-117">L'applicazione di filtri ai record di rilevamento per singole attività all'interno di un flusso di lavoro viene controllata dalle query incluse nel profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-117">The filtering of tracking records for individual activities within a workflow is controlled by the queries within the tracking profile.</span></span> <span data-ttu-id="ff9aa-118">Per ulteriori informazioni, vedere la sezione relativa ai **tipi di query del profilo di rilevamento** in questo documento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-118">For more information, see the **Tracking Profile Query Types** section in this document.</span></span>

<span data-ttu-id="ff9aa-119">Le due modalità di visibilità specificate dall'attributo `implementationVisibility` nel profilo di rilevamento sono: `RootScope` e `All`.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-119">The two visibility modes specified by the `implementationVisibility` attribute in the tracking profile are `RootScope` and `All`.</span></span> <span data-ttu-id="ff9aa-120">Usando la modalità `RootScope` vengono eliminati i record di rilevamento per le attività che formano l'implementazione di un'attività nel caso in cui un'attività composita non costituisca la radice di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-120">Using the `RootScope` mode suppresses the tracking records for activities that form the implementation of an activity in the case where a composite activity is not the root of a workflow.</span></span> <span data-ttu-id="ff9aa-121">Di conseguenza, quando un'attività implementata tramite altre attività viene aggiunta a un flusso di lavoro e l'attributo `implementationVisibility` viene impostato su RootScope, viene rilevata solo l'attività di primo livello all'interno di tale attività composita.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-121">This implies that, when an activity that is implemented using other activities is added to a workflow, and the `implementationVisibility` set to RootScope, only the top-level activity within that composite activity is tracked.</span></span> <span data-ttu-id="ff9aa-122">Se un'attività costituisce la radice del flusso di lavoro, l'implementazione dell'attività è il flusso di lavoro stesso e i record di rilevamento vengono creati per le attività che formano l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-122">If an activity is the root of the workflow, then the implementation of the activity is the workflow itself and tracking records are emitted for activities that form the implementation.</span></span> <span data-ttu-id="ff9aa-123">Tramite la modalità All, tutti i record di rilevamento possono essere creati per l'attività radice e tutte le relative attività composite.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-123">Using the All mode permits all tracking records to be emitted for the root activity and all its composite activities.</span></span>

<span data-ttu-id="ff9aa-124">Si supponga, ad esempio, che *l'attività sia* un'attività composita la cui implementazione contiene due attività, *Activity1* e *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-124">For example, suppose *MyActivity* is a composite activity whose implementation contains two activities, *Activity1* and *Activity2*.</span></span> <span data-ttu-id="ff9aa-125">Quando questa attività viene aggiunta a un flusso di lavoro e il rilevamento viene abilitato con un profilo di rilevamento con `implementationVisibility` impostato su `RootScope`, i record di rilevamento vengono generati solo per l' *attività*.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-125">When this activity is added to a workflow and tracking is enabled with a tracking profile with `implementationVisibility` set to `RootScope`, tracking records are emitted only for *MyActivity*.</span></span> <span data-ttu-id="ff9aa-126">Tuttavia, non viene generato alcun record per le attività *Activity1* e *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-126">However, no records are emitted for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="ff9aa-127">Tuttavia, se l'attributo `implementationVisibility` per il profilo di rilevamento è impostato su `All`, i record di rilevamento vengono generati non solo per l' *attività Activity*, ma anche per le attività *Activity1* e *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-127">However, if the `implementationVisibility` attribute for the tracking profile is  set to `All`, then tracking records are emitted not only for *MyActivity*, but also for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="ff9aa-128">Il flag `implementationVisibility` si applica ai seguenti tipi di record di rilevamento:</span><span class="sxs-lookup"><span data-stu-id="ff9aa-128">The `implementationVisibility` flag applies to following tracking record types:</span></span>

- <span data-ttu-id="ff9aa-129">ActivityStateRecord</span><span class="sxs-lookup"><span data-stu-id="ff9aa-129">ActivityStateRecord</span></span>

- <span data-ttu-id="ff9aa-130">FaultPropagationRecord</span><span class="sxs-lookup"><span data-stu-id="ff9aa-130">FaultPropagationRecord</span></span>

- <span data-ttu-id="ff9aa-131">CancelRequestedRecord</span><span class="sxs-lookup"><span data-stu-id="ff9aa-131">CancelRequestedRecord</span></span>

- <span data-ttu-id="ff9aa-132">ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="ff9aa-132">ActivityScheduledRecord</span></span>

> [!NOTE]
> <span data-ttu-id="ff9aa-133">I record CustomTrackingRecords creati dall'implementazione di attività non vengono filtrati dall'impostazione implementationVisibility.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-133">CustomTrackingRecords emitted from activity implementation are not filtered out by the implementationVisibility setting.</span></span>

<span data-ttu-id="ff9aa-134">La funzionalità `implementationVisibility` viene specificata come <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> nel profilo di rilevamento nel codice come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ff9aa-134">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> on the tracking profile in code as follows:</span></span>

```csharp
TrackingProfile sampleTrackingProfile = new TrackingProfile()
{
    Name = "Sample Tracking Profile",
    ImplementationVisibility = ImplementationVisibility.RootScope
};
```

<span data-ttu-id="ff9aa-135">La funzionalità `implementationVisibility` è specificata come <xref:System.Activities.Tracking.ImplementationVisibility.All> nel profilo di rilevamento in un file di configurazione come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ff9aa-135">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.All> on the tracking profile in a configuration file as follows:</span></span>

```xml
<tracking>
      <profiles>
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">
          <workflow activityDefinitionId="*">
...
         </workflow>
        </trackingProfile>
      </profiles>
</tracking>
```

<span data-ttu-id="ff9aa-136">L'impostazione `ImplementationVisibility` nel profilo di rilevamento è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-136">The `ImplementationVisibility` setting on the tracking profile is optional.</span></span> <span data-ttu-id="ff9aa-137">Per impostazione predefinita, il relativo valore è impostato su `RootScope`.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-137">By default, its value is set to `RootScope`.</span></span> <span data-ttu-id="ff9aa-138">Per i valori di questo attributo viene applicata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-138">The values for this attribute are also case-sensitive.</span></span>

### <a name="tracking-profile-query-types"></a><span data-ttu-id="ff9aa-139">Tipi di query del profilo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ff9aa-139">Tracking Profile Query Types</span></span>

<span data-ttu-id="ff9aa-140">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-140">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="ff9aa-141">Sono disponibili numerosi tipi di query che consentono di sottoscrivere classi differenti di oggetti <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-141">There are several query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="ff9aa-142">I profili di rilevamento possono essere specificati nella configurazione o tramite codice.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-142">Tracking profiles can be specified in configuration or through code.</span></span> <span data-ttu-id="ff9aa-143">Di seguito sono riportati i tipi di query più comuni:</span><span class="sxs-lookup"><span data-stu-id="ff9aa-143">Here are the most common query types:</span></span>

- <span data-ttu-id="ff9aa-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery>: usare questo tipo per rilevare le modifiche del ciclo di vita dell'istanza del flusso di lavoro, ad esempio gli eventi `Started` e `Completed` dimostrati precedentemente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - Use this to track workflow instance life cycle changes like the previously-demonstrated `Started` and `Completed`.</span></span> <span data-ttu-id="ff9aa-145">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff9aa-145">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>

  - <xref:System.Activities.Tracking.WorkflowInstanceRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>

  <span data-ttu-id="ff9aa-146">Gli stati disponibili per la sottoscrizione sono specificati nella classe <xref:System.Activities.Tracking.WorkflowInstanceStates>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-146">The states that can be subscribed to are specified in the <xref:System.Activities.Tracking.WorkflowInstanceStates> class.</span></span>

  <span data-ttu-id="ff9aa-147">La configurazione o il codice usato per sottoscrivere i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando l'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-147">The configuration or code used to subscribe to workflow instance-level tracking records for the `Started` instance state using the <xref:System.Activities.Tracking.WorkflowInstanceQuery> is shown in the following example.</span></span>

  ```xml
  <workflowInstanceQueries>
      <workflowInstanceQuery>
        <states>
          <state name="Started"/>
        </states>
      </workflowInstanceQuery>
  </workflowInstanceQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new WorkflowInstanceQuery()
          {
              States = { WorkflowInstanceStates.Started}
          }
      }
  };
  ```

- <span data-ttu-id="ff9aa-148"><xref:System.Activities.Tracking.ActivityStateQuery>: usare questo tipo per rilevare le modifiche del ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-148"><xref:System.Activities.Tracking.ActivityStateQuery> - Use this to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ff9aa-149">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-149">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ff9aa-150">Questa query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-150">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityStateRecord> objects.</span></span> <span data-ttu-id="ff9aa-151">Gli stati disponibili per la sottoscrizione sono specificati nell'oggetto <xref:System.Activities.Tracking.ActivityStates>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-151">The available states to subscribe to are specified in <xref:System.Activities.Tracking.ActivityStates>.</span></span>

  <span data-ttu-id="ff9aa-152">La configurazione e il codice usati per sottoscrivere i record di rilevamento dello stato dell'attività che usano l'oggetto <xref:System.Activities.Tracking.ActivityStateQuery> per l'attività `SendEmailActivity` sono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-152">The configuration and code used to subscribe activity state tracking records that use the <xref:System.Activities.Tracking.ActivityStateQuery> for the `SendEmailActivity` activity is shown in the following example.</span></span>

  ```xml
  <activityStateQueries>
    <activityStateQuery activityName="SendEmailActivity">
      <states>
        <state name="Closed"/>
      </states>
    </activityStateQuery>
  </activityStateQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityStateQuery()
          {
              ActivityName = "SendEmailActivity",
              States = { ActivityStates.Closed }
          }
      }
  };
  ```

  > [!NOTE]
  > <span data-ttu-id="ff9aa-153">Se più elementi activityStateQuery hanno lo stesso nome, solo gli stati nell'ultimo elemento vengono usati nel profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-153">If multiple activityStateQuery elements have the same name, only the states in the last element are used in the tracking profile.</span></span>

- <span data-ttu-id="ff9aa-154"><xref:System.Activities.Tracking.ActivityScheduledQuery>: questa query consente di rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - This query allows you to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ff9aa-155">La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.ActivityScheduledRecord>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-155">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityScheduledRecord> objects.</span></span>

  <span data-ttu-id="ff9aa-156">La configurazione e il codice usati per sottoscrivere i record relativi all'attività figlio `SendEmailActivity` in fase di pianificazione tramite l'oggetto <xref:System.Activities.Tracking.ActivityScheduledQuery> sono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-156">The configuration and code used to subscribe to records related to the `SendEmailActivity` child activity being scheduled using the <xref:System.Activities.Tracking.ActivityScheduledQuery> is shown in the following example.</span></span>

  ```xml
  <activityScheduledQueries>
    <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </activityScheduledQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityScheduledQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="ff9aa-157"><xref:System.Activities.Tracking.FaultPropagationQuery>: usare questo tipo per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - Use this to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="ff9aa-158">La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-158">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.FaultPropagationRecord> objects.</span></span>

  <span data-ttu-id="ff9aa-159">La configurazione e il codice usati per sottoscrivere i record relativi alla propagazione degli errori tramite l'oggetto <xref:System.Activities.Tracking.FaultPropagationQuery> sono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-159">The configuration and code used to subscribe to records related to fault propagation using <xref:System.Activities.Tracking.FaultPropagationQuery> is shown in the following example.</span></span>

  ```xml
  <faultPropagationQueries>
    <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />
  </faultPropagationQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new FaultPropagationQuery()
          {
              FaultSourceActivityName = "SendEmailActivity",
              FaultHandlerActivityName = "NotificationsFaultHandler"
          }
      }
  };
  ```

- <span data-ttu-id="ff9aa-160"><xref:System.Activities.Tracking.CancelRequestedQuery>: usare questo tipo per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - Use this to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ff9aa-161">La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.CancelRequestedRecord>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-161">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CancelRequestedRecord> objects.</span></span>

  <span data-ttu-id="ff9aa-162">Nell'esempio seguente viene illustrato il codice e la configurazione usati per sottoscrivere i record relativi all'annullamento dell'attività usando <xref:System.Activities.Tracking.CancelRequestedQuery>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-162">The configuration and code used to subscribe to records related to activity cancellation using <xref:System.Activities.Tracking.CancelRequestedQuery> is shown in the following example.</span></span>

  ```xml
  <cancelRequestedQueries>
    <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </cancelRequestedQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CancelRequestedQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="ff9aa-163"><xref:System.Activities.Tracking.CustomTrackingQuery>: usare questo tipo per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - Use this to track events that you define in your code activities.</span></span> <span data-ttu-id="ff9aa-164">La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.CustomTrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-164">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CustomTrackingRecord> objects.</span></span>

  <span data-ttu-id="ff9aa-165">La configurazione e il codice usati per sottoscrivere i record relativi ai record di rilevamento personalizzati tramite l'oggetto <xref:System.Activities.Tracking.CustomTrackingQuery> sono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-165">The configuration and code used to subscribe to records related to custom tracking records using <xref:System.Activities.Tracking.CustomTrackingQuery> is shown in the following example.</span></span>

  ```xml
  <customTrackingQueries>
    <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />
  </customTrackingQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CustomTrackingQuery()
          {
              Name = "EmailAddress",
              ActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="ff9aa-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery>: usare questo tipo per rilevare la ripresa di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - Use this to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ff9aa-167">Questa query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.BookmarkResumptionRecord>.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-167">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.BookmarkResumptionRecord> objects.</span></span>

  <span data-ttu-id="ff9aa-168">La configurazione e il codice usati per sottoscrivere i record relativi alla ripresa del segnalibro tramite l'oggetto <xref:System.Activities.Tracking.BookmarkResumptionQuery> sono illustrati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-168">The configuration and code used to subscribe to records related to bookmark resumption using <xref:System.Activities.Tracking.BookmarkResumptionQuery> is shown in the following example.</span></span>

  ```xml
  <bookmarkResumptionQueries>
    <bookmarkResumptionQuery name="SentEmailBookmark" />
  </bookmarkResumptionQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new BookmarkResumptionQuery()
          {
              Name = "sentEmailBookmark"
          }
      }
  };
  ```

### <a name="annotations"></a><span data-ttu-id="ff9aa-169">Annotations</span><span class="sxs-lookup"><span data-stu-id="ff9aa-169">Annotations</span></span>

<span data-ttu-id="ff9aa-170">Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-170">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="ff9aa-171">È possibile, ad esempio, che si desideri contrassegnare più record di rilevamento in diversi flussi di lavoro con "mail server" = = "mail Server1".</span><span class="sxs-lookup"><span data-stu-id="ff9aa-171">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="ff9aa-172">Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-172">This makes it easy to find all records with this tag when querying tracking records later.</span></span>

<span data-ttu-id="ff9aa-173">A tal fine, viene aggiunta un'annotazione a una query di rilevamento come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-173">To accomplish this, an annotation is added to a tracking query as shown in the following example.</span></span>

```xml
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed"/>
  </states>
  <annotations>
    <annotation name="MailServer" value="Mail Server1"/>
  </annotations>
</activityStateQuery>
```

### <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="ff9aa-174">Modalità di creazione di un profilo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ff9aa-174">How to Create a Tracking Profile</span></span>

<span data-ttu-id="ff9aa-175">Gli elementi della query di rilevamento vengono usati per creare un profilo di rilevamento tramite un file di configurazione XML o il codice di [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff9aa-175">Tracking query elements are used to create a tracking profile using either an XML configuration file or [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]code.</span></span> <span data-ttu-id="ff9aa-176">Di seguito è riportato un esempio di un profilo di rilevamento creato usando un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-176">Here is an example of a tracking profile created using a configuration file.</span></span>

```xml
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile ">
        <workflow activityDefinitionId="*">
          <!--Specify the tracking profile query elements to subscribe for tracking records-->
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```

> [!WARNING]
> <span data-ttu-id="ff9aa-177">Per un servizio WF in cui viene usato l'host del servizio del flusso di lavoro, il profilo di rilevamento viene generalmente creato usando un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-177">For a WF using the Workflow service host, the tracking profile is typically created using a configuration file.</span></span> <span data-ttu-id="ff9aa-178">È anche possibile creare un profilo di rilevamento con il codice, usando il profilo di rilevamento e l'API della query di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-178">It is also possible to create a tracking profile with code using the tracking profile and tracking query API.</span></span>

<span data-ttu-id="ff9aa-179">Un profilo configurato come file di configurazione XML viene applicato a un partecipante del rilevamento tramite un'estensione di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-179">A profile configured as an XML configuration file is applied to a tracking participant using a behavior extension.</span></span> <span data-ttu-id="ff9aa-180">Viene aggiunto a un WorkflowServiceHost, come descritto nella sezione successiva [configurazione del rilevamento per un flusso di lavoro](configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ff9aa-180">This is added to a WorkflowServiceHost as described in the later section [Configuring Tracking for a Workflow](configuring-tracking-for-a-workflow.md).</span></span>

<span data-ttu-id="ff9aa-181">Il livello di dettaglio dei record di rilevamento creati dall'host è determinato dalle impostazioni di configurazione all'interno del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-181">The verbosity of the tracking records emitted by the host is determined by configuration settings within the tracking profile.</span></span> <span data-ttu-id="ff9aa-182">Un partecipante del rilevamento sottoscrive i record di rilevamento aggiungendo query a un profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-182">A tracking participant subscribes to tracking records by adding queries to a tracking profile.</span></span> <span data-ttu-id="ff9aa-183">Per sottoscrivere tutti i record di rilevamento, il profilo di rilevamento deve specificare tutte le query di rilevamento utilizzando "\*" nei campi nome di ogni query.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-183">To subscribe to all tracking records, the tracking profile needs to specify all tracking queries using "\*" in the name fields in each of the queries.</span></span>

<span data-ttu-id="ff9aa-184">Di seguito sono riportati alcuni degli esempi comuni di profili di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-184">Here are some of the common examples of tracking profiles.</span></span>

- <span data-ttu-id="ff9aa-185">Profilo di rilevamento per ottenere i record dell'istanza del flusso di lavoro e gli errori.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-185">A tracking profile to obtain workflow instance records and faults.</span></span>

  ```xml
  <trackingProfile name="Instance and Fault Records">
    <workflow activityDefinitionId="*">
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="*" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
      <activityStateQueries>
        <activityStateQuery activityName="*">
          <states>
            <state name="Faulted"/>
          </states>
        </activityStateQuery>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
  ```

- <span data-ttu-id="ff9aa-186">Profilo di rilevamento per ottenere tutti i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ff9aa-186">A tracking profile to obtain all custom tracking records.</span></span>

  ```xml
  <trackingProfile name="Instance_And_Custom_Records">
    <workflow activityDefinitionId="*">
      <customTrackingQueries>
        <customTrackingQuery name="*" activityName="*" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
  ```

## <a name="see-also"></a><span data-ttu-id="ff9aa-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff9aa-187">See also</span></span>

- [<span data-ttu-id="ff9aa-188">Rilevamento SQL</span><span class="sxs-lookup"><span data-stu-id="ff9aa-188">SQL Tracking</span></span>](./samples/sql-tracking.md)
- <span data-ttu-id="ff9aa-189">[Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ff9aa-189">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="ff9aa-190">[Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ff9aa-190">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
