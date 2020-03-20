---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: e2df5d83375b2daa2e39ba1ee990c47a6a04f6fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151858"
---
# <a name="workflow"></a><span data-ttu-id="04fdf-101">\<> del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="04fdf-101">\<workflow></span></span>
<span data-ttu-id="04fdf-102">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04fdf-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="04fdf-103">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [Profili di rilevamento e tracciabilità](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) e [rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)del flusso di lavoro .</span><span class="sxs-lookup"><span data-stu-id="04fdf-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="04fdf-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04fdf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04fdf-105">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="04fdf-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="04fdf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="04fdf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="04fdf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="04fdf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="04fdf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>del flusso di lavoro**</span><span class="sxs-lookup"><span data-stu-id="04fdf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04fdf-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04fdf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04fdf-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="04fdf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="04fdf-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="04fdf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04fdf-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="04fdf-112">Attributes</span></span>  
  
|<span data-ttu-id="04fdf-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="04fdf-113">Attribute</span></span>|<span data-ttu-id="04fdf-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04fdf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04fdf-115">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="04fdf-115">activityDefinitionId</span></span>|<span data-ttu-id="04fdf-116">Stringa che specifica l'ID di definizione dell'attività del flusso di lavoro rilevato.</span><span class="sxs-lookup"><span data-stu-id="04fdf-116">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04fdf-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="04fdf-117">Child Elements</span></span>  
  
|<span data-ttu-id="04fdf-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="04fdf-118">Element</span></span>|<span data-ttu-id="04fdf-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04fdf-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04fdf-120">\<>activityScheduledQueries</span><span class="sxs-lookup"><span data-stu-id="04fdf-120">\<activityScheduledQueries></span></span>](activityscheduledqueries.md)|<span data-ttu-id="04fdf-121">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="04fdf-121">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="04fdf-122">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="04fdf-122">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="04fdf-123">\<>activityStateQueries</span><span class="sxs-lookup"><span data-stu-id="04fdf-123">\<activityStateQueries></span></span>](activitystatequeries.md)|<span data-ttu-id="04fdf-124">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="04fdf-124">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="04fdf-125">Ad esempio, è possibile tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="04fdf-125">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="04fdf-126">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="04fdf-126">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="04fdf-127">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="04fdf-127">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="04fdf-128">\<>bookmarkResumptionQueries</span><span class="sxs-lookup"><span data-stu-id="04fdf-128">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="04fdf-129">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="04fdf-129">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="04fdf-130">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="04fdf-130">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="04fdf-131">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="04fdf-131">\<cancelRequestedQueries></span></span>](cancelrequestedqueries.md)|<span data-ttu-id="04fdf-132">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="04fdf-132">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="04fdf-133">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="04fdf-133">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="04fdf-134">\<>customTrackingQueries</span><span class="sxs-lookup"><span data-stu-id="04fdf-134">\<customTrackingQueries></span></span>](customtrackingqueries.md)|<span data-ttu-id="04fdf-135">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="04fdf-135">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="04fdf-136">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="04fdf-136">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="04fdf-137">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="04fdf-137">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="04fdf-138">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="04fdf-138">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="04fdf-139">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="04fdf-139">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="04fdf-140">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="04fdf-140">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="04fdf-141">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="04fdf-141">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="04fdf-142">\<workflowIstanzaQuery></span><span class="sxs-lookup"><span data-stu-id="04fdf-142">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="04fdf-143">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="04fdf-143">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04fdf-144">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="04fdf-144">Parent Elements</span></span>  
  
|<span data-ttu-id="04fdf-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="04fdf-145">Element</span></span>|<span data-ttu-id="04fdf-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04fdf-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04fdf-147">\<>trackingProfile</span><span class="sxs-lookup"><span data-stu-id="04fdf-147">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="04fdf-148">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione dei record di rilevamento del flusso di lavoro in un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="04fdf-148">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="04fdf-149">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="04fdf-149">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="04fdf-150">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="04fdf-150">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04fdf-151">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="04fdf-151">Remarks</span></span>  
 <span data-ttu-id="04fdf-152">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di una determinata istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="04fdf-152">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="04fdf-153">L'istanza del flusso di lavoro rilevata viene identificata da questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="04fdf-153">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="04fdf-154">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="04fdf-154">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="04fdf-155">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="04fdf-155">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="04fdf-156">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="04fdf-156">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="04fdf-157">Esistono diversi tipi di query che consentono di sottoscrivere classi differenti di record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="04fdf-157">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="04fdf-158">Per un elenco completo delle query, vedere l'elenco degli elementi figlio di questo argomento e [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="04fdf-158">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="04fdf-159">Nell'esempio seguente viene illustrato un profilo di rilevamento in `Started` `Completed` un file di configurazione che consente a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro e .</span><span class="sxs-lookup"><span data-stu-id="04fdf-159">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04fdf-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04fdf-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="04fdf-161">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="04fdf-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="04fdf-162">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="04fdf-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
