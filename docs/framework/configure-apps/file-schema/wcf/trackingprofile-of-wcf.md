---
title: <trackingProfile>di WCF
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: c5df03d63653e658a23a36e8943c06f156d2ae00
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854947"
---
# <a name="trackingprofile-of-wcf"></a><span data-ttu-id="f31a5-102">\<trackingProfile > di WCF</span><span class="sxs-lookup"><span data-stu-id="f31a5-102">\<trackingProfile> of WCF</span></span>
<span data-ttu-id="f31a5-103">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione ai record di rilevamento del flusso di lavoro in un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f31a5-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="f31a5-104">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f31a5-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="f31a5-105">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="f31a5-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
<span data-ttu-id="f31a5-106">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [profili](../../../windows-workflow-foundation/tracking-profiles.md)di rilevamento [e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="f31a5-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f31a5-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f31a5-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f31a5-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f31a5-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f31a5-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f31a5-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="f31a5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="f31a5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="f31a5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di trackingProfile**</span><span class="sxs-lookup"><span data-stu-id="f31a5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f31a5-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f31a5-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f31a5-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f31a5-113">Attributes and Elements</span></span>  

<span data-ttu-id="f31a5-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f31a5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f31a5-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="f31a5-115">Attributes</span></span>  
  
|<span data-ttu-id="f31a5-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="f31a5-116">Attribute</span></span>|<span data-ttu-id="f31a5-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f31a5-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f31a5-118">name</span><span class="sxs-lookup"><span data-stu-id="f31a5-118">name</span></span>|<span data-ttu-id="f31a5-119">Stringa che specifica il nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f31a5-119">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f31a5-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f31a5-120">Child Elements</span></span>  
  
|<span data-ttu-id="f31a5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f31a5-121">Element</span></span>|<span data-ttu-id="f31a5-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f31a5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f31a5-123">\<participants></span><span class="sxs-lookup"><span data-stu-id="f31a5-123">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="f31a5-124">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f31a5-124">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f31a5-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f31a5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f31a5-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f31a5-126">Element</span></span>|<span data-ttu-id="f31a5-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f31a5-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f31a5-128">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="f31a5-128">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="f31a5-129">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f31a5-129">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f31a5-130">Note</span><span class="sxs-lookup"><span data-stu-id="f31a5-130">Remarks</span></span>  
 <span data-ttu-id="f31a5-131">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f31a5-131">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="f31a5-132">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f31a5-132">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="f31a5-133">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f31a5-133">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="f31a5-134">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="f31a5-134">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="f31a5-135">Sono disponibili alcuni tipi di query che consentono di sottoscrivere classi diverse di <xref:System.Activities.Tracking.TrackingRecord> oggetti.</span><span class="sxs-lookup"><span data-stu-id="f31a5-135">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="f31a5-136">Per un elenco completo di query, vedere [ \<partecipanti >](../windows-workflow-foundation/participants.md) e [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f31a5-136">For a complete list of queries, see [\<participants>](../windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="f31a5-137">Nell'esempio seguente viene illustrato un profilo di rilevamento in un file di configurazione che consente a un partecipante del `Started` rilevamento `Completed` di sottoscrivere gli eventi del flusso di lavoro e.</span><span class="sxs-lookup"><span data-stu-id="f31a5-137">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f31a5-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f31a5-138">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="f31a5-139">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f31a5-139">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f31a5-140">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f31a5-140">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
