---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151910"
---
# <a name="tracking"></a><span data-ttu-id="36347-101">\<> di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="36347-101">\<tracking></span></span>
<span data-ttu-id="36347-102">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36347-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="36347-103">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [Rilevamento e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) e Configurazione del [rilevamento per un flusso di lavoro](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="36347-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="36347-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36347-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36347-105">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="36347-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="36347-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>di tracciamento**</span><span class="sxs-lookup"><span data-stu-id="36347-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36347-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36347-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36347-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="36347-108">Attributes and Elements</span></span>  
 <span data-ttu-id="36347-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="36347-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36347-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="36347-110">Attributes</span></span>  
 <span data-ttu-id="36347-111">No.</span><span class="sxs-lookup"><span data-stu-id="36347-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36347-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="36347-112">Child Elements</span></span>  
  
|<span data-ttu-id="36347-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="36347-113">Element</span></span>|<span data-ttu-id="36347-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36347-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36347-115">\<partecipanti></span><span class="sxs-lookup"><span data-stu-id="36347-115">\<participants></span></span>](participants.md)|<span data-ttu-id="36347-116">Raccolta di elementi di configurazione che definiscono partecipanti che sottoscrivono record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="36347-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="36347-117">I partecipanti del rilevamento contengono la logica per elaborare il payload dai record di rilevamento, ad esempio possono scegliere di scrivere in un file.</span><span class="sxs-lookup"><span data-stu-id="36347-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="36347-118">\<>trackingProfile</span><span class="sxs-lookup"><span data-stu-id="36347-118">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="36347-119">Profilo di rilevamento che consente di filtrare i record di rilevamento generati da un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36347-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36347-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="36347-120">Parent Elements</span></span>  
  
|<span data-ttu-id="36347-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="36347-121">Element</span></span>|<span data-ttu-id="36347-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36347-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36347-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="36347-123">system.ServiceModel</span></span>|<span data-ttu-id="36347-124">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36347-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36347-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="36347-125">Remarks</span></span>  
 <span data-ttu-id="36347-126">Il rilevamento consente di esaminare l'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36347-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="36347-127">L'infrastruttura di rilevamento del flusso di lavoro instrumenta un flusso di lavoro per generare record che riflettono gli eventi principali che si verificano durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36347-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="36347-128">Vengono ad esempio generati record di rilevamento quando viene avviata o completata un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36347-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="36347-129">Il rilevamento consente inoltre di estrarre dati aziendali rilevanti associati alle variabili del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36347-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="36347-130">Se, ad esempio, il flusso di lavoro rappresenta un sistema di elaborazione degli ordini, è possibile estrarre l'ID dell'ordine insieme al record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="36347-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="36347-131">In generale, l'abilitazione del rilevamento WF semplifica la diagnostica o l'analisi aziendale dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36347-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36347-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36347-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="36347-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36347-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
