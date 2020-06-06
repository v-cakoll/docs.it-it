---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: e2df5d83375b2daa2e39ba1ee990c47a6a04f6fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151858"
---
# \<workflow>
<span data-ttu-id="ac273-101">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac273-101">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ac273-102">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [profili](../../../windows-workflow-foundation/tracking-profiles.md)di rilevamento [e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="ac273-102">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflow>**  
  
## <a name="syntax"></a><span data-ttu-id="ac273-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac273-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String"
             profileName="String"
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac273-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ac273-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ac273-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ac273-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac273-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="ac273-106">Attributes</span></span>  
  
|<span data-ttu-id="ac273-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="ac273-107">Attribute</span></span>|<span data-ttu-id="ac273-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac273-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac273-109">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="ac273-109">activityDefinitionId</span></span>|<span data-ttu-id="ac273-110">Stringa che specifica l'ID di definizione dell'attività del flusso di lavoro rilevato.</span><span class="sxs-lookup"><span data-stu-id="ac273-110">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac273-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ac273-111">Child Elements</span></span>  
  
|<span data-ttu-id="ac273-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac273-112">Element</span></span>|<span data-ttu-id="ac273-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac273-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries.md)|<span data-ttu-id="ac273-114">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="ac273-114">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ac273-115">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ac273-115">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[\<activityStateQueries>](activitystatequeries.md)|<span data-ttu-id="ac273-116">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac273-116">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ac273-117">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac273-117">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ac273-118">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="ac273-118">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ac273-119">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="ac273-119">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="ac273-120">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac273-120">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ac273-121">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="ac273-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[\<cancelRequestedQueries>](cancelrequestedqueries.md)|<span data-ttu-id="ac273-122">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="ac273-122">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ac273-123">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="ac273-123">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[\<customTrackingQueries>](customtrackingqueries.md)|<span data-ttu-id="ac273-124">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="ac273-124">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ac273-125">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ac273-125">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="ac273-126">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="ac273-126">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ac273-127">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="ac273-127">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="ac273-128">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="ac273-128">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="ac273-129">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="ac273-129">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[\<workflowInstanceQueries>](workflowinstancequeries.md)|<span data-ttu-id="ac273-130">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="ac273-130">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac273-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ac273-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ac273-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac273-132">Element</span></span>|<span data-ttu-id="ac273-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac273-133">Description</span></span>|  
|-------------|-----------------|  
|[\<trackingProfile>](trackingprofile.md)|<span data-ttu-id="ac273-134">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione dei record di rilevamento del flusso di lavoro in un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ac273-134">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="ac273-135">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ac273-135">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="ac273-136">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac273-136">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac273-137">Commenti</span><span class="sxs-lookup"><span data-stu-id="ac273-137">Remarks</span></span>  
 <span data-ttu-id="ac273-138">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di una determinata istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ac273-138">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="ac273-139">L'istanza del flusso di lavoro rilevata viene identificata da questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ac273-139">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="ac273-140">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac273-140">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="ac273-141">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ac273-141">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="ac273-142">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="ac273-142">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="ac273-143">Esistono diversi tipi di query che consentono di sottoscrivere classi differenti di record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ac273-143">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="ac273-144">Per un elenco completo di query, vedere l'elenco di elementi figlio di questo argomento e [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ac273-144">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="ac273-145">Nell'esempio seguente viene illustrato un profilo di rilevamento in un file di configurazione che consente a un partecipante del rilevamento di sottoscrivere gli `Started` `Completed` eventi del flusso di lavoro e.</span><span class="sxs-lookup"><span data-stu-id="ac273-145">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
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
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac273-146">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ac273-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="ac273-147">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ac273-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ac273-148">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ac273-148">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
