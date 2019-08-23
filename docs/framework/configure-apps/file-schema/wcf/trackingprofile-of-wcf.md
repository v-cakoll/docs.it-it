---
title: <trackingProfile>di WCF
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: 79326322eeed1f6b73729da675eb02fe6de670df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932343"
---
# <a name="trackingprofile-of-wcf"></a><span data-ttu-id="dbe39-102">\<trackingProfile > di WCF</span><span class="sxs-lookup"><span data-stu-id="dbe39-102">\<trackingProfile> of WCF</span></span>
<span data-ttu-id="dbe39-103">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione ai record di rilevamento del flusso di lavoro in un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dbe39-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="dbe39-104">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dbe39-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="dbe39-105">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="dbe39-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="dbe39-106">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [profili](../../../windows-workflow-foundation/tracking-profiles.md)di rilevamento [e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="dbe39-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="dbe39-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dbe39-107">\<system.serviceModel></span></span>  
<span data-ttu-id="dbe39-108">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dbe39-108">\<tracking></span></span>  
<span data-ttu-id="dbe39-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dbe39-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe39-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbe39-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String" />
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String">
              <arguments>
                <argument name="String" />
              </arguments>
              <states>
                <state name="String" />
              </states>
              <variables>
                <variable name="String" />
              </variables>
            </activityStateQuery>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestedQueries>
            <cancelRequestedQuery activityName="String"
                                  childActivityName="String" />
          </cancelRequestedQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String" />
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery faultSourceActivityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <stateMachineStateQueries>
            <stateMachineStateQuery activityName="String" />
          </stateMachineStateQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbe39-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dbe39-111">Attributes and Elements</span></span>  

<span data-ttu-id="dbe39-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dbe39-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbe39-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="dbe39-113">Attributes</span></span>  
  
|<span data-ttu-id="dbe39-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="dbe39-114">Attribute</span></span>|<span data-ttu-id="dbe39-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dbe39-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbe39-116">name</span><span class="sxs-lookup"><span data-stu-id="dbe39-116">name</span></span>|<span data-ttu-id="dbe39-117">Stringa che specifica il nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dbe39-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbe39-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dbe39-118">Child Elements</span></span>  
  
|<span data-ttu-id="dbe39-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbe39-119">Element</span></span>|<span data-ttu-id="dbe39-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dbe39-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbe39-121">\<participants></span><span class="sxs-lookup"><span data-stu-id="dbe39-121">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="dbe39-122">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dbe39-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dbe39-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dbe39-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dbe39-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbe39-124">Element</span></span>|<span data-ttu-id="dbe39-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbe39-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbe39-126">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dbe39-126">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="dbe39-127">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dbe39-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbe39-128">Note</span><span class="sxs-lookup"><span data-stu-id="dbe39-128">Remarks</span></span>  
 <span data-ttu-id="dbe39-129">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dbe39-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="dbe39-130">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dbe39-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="dbe39-131">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="dbe39-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="dbe39-132">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="dbe39-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="dbe39-133">Sono disponibili alcuni tipi di query che consentono di sottoscrivere classi diverse di <xref:System.Activities.Tracking.TrackingRecord> oggetti.</span><span class="sxs-lookup"><span data-stu-id="dbe39-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="dbe39-134">Per un elenco completo di query, vedere [ \<partecipanti >](../windows-workflow-foundation/participants.md) e [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dbe39-134">For a complete list of queries, see [\<participants>](../windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="dbe39-135">Nell'esempio seguente viene illustrato un profilo di rilevamento in un file di configurazione che consente a un partecipante del `Started` rilevamento `Completed` di sottoscrivere gli eventi del flusso di lavoro e.</span><span class="sxs-lookup"><span data-stu-id="dbe39-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started" />
                <state name="Completed" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="dbe39-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbe39-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="dbe39-137">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dbe39-137">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dbe39-138">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dbe39-138">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
