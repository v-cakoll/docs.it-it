---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 8985da7e1223ac117cf1b68227140634f9c85d3a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151889"
---
# \<trackingProfile>
<span data-ttu-id="411c9-101">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione dei record di rilevamento del flusso di lavoro in un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="411c9-101">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="411c9-102">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="411c9-102">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="411c9-103">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="411c9-103">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="411c9-104">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [profili](../../../windows-workflow-foundation/tracking-profiles.md)di rilevamento [e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="411c9-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**  
  
## <a name="syntax"></a><span data-ttu-id="411c9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="411c9-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="411c9-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="411c9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="411c9-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="411c9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="411c9-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="411c9-108">Attributes</span></span>  
  
|<span data-ttu-id="411c9-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="411c9-109">Attribute</span></span>|<span data-ttu-id="411c9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="411c9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="411c9-111">name</span><span class="sxs-lookup"><span data-stu-id="411c9-111">name</span></span>|<span data-ttu-id="411c9-112">Stringa che specifica il nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="411c9-112">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="411c9-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="411c9-113">Child Elements</span></span>  
  
|<span data-ttu-id="411c9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="411c9-114">Element</span></span>|<span data-ttu-id="411c9-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="411c9-115">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="411c9-116">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="411c9-116">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="411c9-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="411c9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="411c9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="411c9-118">Element</span></span>|<span data-ttu-id="411c9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="411c9-119">Description</span></span>|  
|-------------|-----------------|  
|[\<tracking>](tracking.md)|<span data-ttu-id="411c9-120">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="411c9-120">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="411c9-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="411c9-121">Remarks</span></span>  
 <span data-ttu-id="411c9-122">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="411c9-122">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="411c9-123">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="411c9-123">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="411c9-124">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="411c9-124">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="411c9-125">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="411c9-125">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="411c9-126">Sono disponibili alcuni tipi di query che consentono di sottoscrivere classi diverse di <xref:System.Activities.Tracking.TrackingRecord> oggetti.</span><span class="sxs-lookup"><span data-stu-id="411c9-126">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="411c9-127">Per un elenco completo di query, vedere [\<participants>](participants.md) e [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="411c9-127">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="411c9-128">Nell'esempio seguente viene illustrato un profilo di rilevamento in un file di configurazione che consente a un partecipante del rilevamento di sottoscrivere gli `Started` `Completed` eventi del flusso di lavoro e.</span><span class="sxs-lookup"><span data-stu-id="411c9-128">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="411c9-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="411c9-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="411c9-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="411c9-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="411c9-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="411c9-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
