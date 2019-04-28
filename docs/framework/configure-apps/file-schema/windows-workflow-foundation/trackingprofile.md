---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 747660df58604dd9384abefccb51ea665f97e2e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614973"
---
# <a name="trackingprofile"></a><span data-ttu-id="24654-101">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="24654-101">\<trackingProfile></span></span>
<span data-ttu-id="24654-102">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione di record di rilevamento in un partecipante del rilevamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24654-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="24654-103">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="24654-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="24654-104">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="24654-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="24654-105">Per altre informazioni sul rilevamento del flusso di lavoro e la relativa configurazione, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="24654-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="24654-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="24654-106">\<system.serviceModel></span></span>  
<span data-ttu-id="24654-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="24654-107">\<tracking></span></span>  
<span data-ttu-id="24654-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="24654-108">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24654-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24654-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24654-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="24654-110">Attributes and Elements</span></span>  
 <span data-ttu-id="24654-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="24654-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24654-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="24654-112">Attributes</span></span>  
  
|<span data-ttu-id="24654-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="24654-113">Attribute</span></span>|<span data-ttu-id="24654-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24654-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24654-115">name</span><span class="sxs-lookup"><span data-stu-id="24654-115">name</span></span>|<span data-ttu-id="24654-116">Stringa che specifica il nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="24654-116">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24654-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="24654-117">Child Elements</span></span>  
  
|<span data-ttu-id="24654-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="24654-118">Element</span></span>|<span data-ttu-id="24654-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24654-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24654-120">\<participants></span><span class="sxs-lookup"><span data-stu-id="24654-120">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="24654-121">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="24654-121">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24654-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="24654-122">Parent Elements</span></span>  
  
|<span data-ttu-id="24654-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="24654-123">Element</span></span>|<span data-ttu-id="24654-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24654-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24654-125">\<tracking></span><span class="sxs-lookup"><span data-stu-id="24654-125">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="24654-126">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24654-126">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24654-127">Note</span><span class="sxs-lookup"><span data-stu-id="24654-127">Remarks</span></span>  
 <span data-ttu-id="24654-128">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="24654-128">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="24654-129">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24654-129">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="24654-130">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="24654-130">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="24654-131">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="24654-131">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="24654-132">Esistono diversi tipi di query che consentono di sottoscrivere classi differenti di <xref:System.Activities.Tracking.TrackingRecord> oggetti.</span><span class="sxs-lookup"><span data-stu-id="24654-132">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="24654-133">Per un elenco completo delle query, vedere [ \<partecipanti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) e [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="24654-133">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="24654-134">Nell'esempio seguente viene illustrato un profilo di rilevamento in un file di configurazione che consente a un partecipante di rilevamento sottoscrivere i `Started` e `Completed` gli eventi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="24654-134">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="24654-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24654-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="24654-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="24654-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="24654-137">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="24654-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
