---
title: '&lt;trackingProfile&gt; di WCF'
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: a35b91867464b48b5e5ea858bca18296cb2d903a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629539"
---
# <a name="lttrackingprofilegt-of-wcf"></a><span data-ttu-id="b0c97-102">&lt;trackingProfile&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="b0c97-102">&lt;trackingProfile&gt; of WCF</span></span>
<span data-ttu-id="b0c97-103">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione di record di rilevamento in un partecipante del rilevamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0c97-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="b0c97-104">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b0c97-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="b0c97-105">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b0c97-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="b0c97-106">Per altre informazioni sul rilevamento del flusso di lavoro e la relativa configurazione, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b0c97-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="b0c97-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b0c97-107">\<system.serviceModel></span></span>  
<span data-ttu-id="b0c97-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b0c97-108">\<tracking></span></span>  
<span data-ttu-id="b0c97-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b0c97-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c97-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0c97-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0c97-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b0c97-111">Attributes and Elements</span></span>  

<span data-ttu-id="b0c97-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b0c97-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0c97-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b0c97-113">Attributes</span></span>  
  
|<span data-ttu-id="b0c97-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="b0c97-114">Attribute</span></span>|<span data-ttu-id="b0c97-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0c97-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0c97-116">name</span><span class="sxs-lookup"><span data-stu-id="b0c97-116">name</span></span>|<span data-ttu-id="b0c97-117">Stringa che specifica il nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b0c97-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0c97-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b0c97-118">Child Elements</span></span>  
  
|<span data-ttu-id="b0c97-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0c97-119">Element</span></span>|<span data-ttu-id="b0c97-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0c97-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0c97-121">\<participants></span><span class="sxs-lookup"><span data-stu-id="b0c97-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="b0c97-122">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0c97-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0c97-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b0c97-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b0c97-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0c97-124">Element</span></span>|<span data-ttu-id="b0c97-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0c97-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0c97-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b0c97-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="b0c97-127">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0c97-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0c97-128">Note</span><span class="sxs-lookup"><span data-stu-id="b0c97-128">Remarks</span></span>  
 <span data-ttu-id="b0c97-129">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b0c97-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="b0c97-130">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0c97-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="b0c97-131">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="b0c97-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="b0c97-132">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="b0c97-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="b0c97-133">Esistono diversi tipi di query che consentono di sottoscrivere classi differenti di <xref:System.Activities.Tracking.TrackingRecord> oggetti.</span><span class="sxs-lookup"><span data-stu-id="b0c97-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="b0c97-134">Per un elenco completo delle query, vedere [ \<partecipanti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) e [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b0c97-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="b0c97-135">Nell'esempio seguente viene illustrato un profilo di rilevamento in un file di configurazione che consente a un partecipante di rilevamento sottoscrivere i `Started` e `Completed` gli eventi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0c97-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0c97-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0c97-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="b0c97-137">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b0c97-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b0c97-138">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b0c97-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
