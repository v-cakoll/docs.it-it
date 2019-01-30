---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: fa96cb374204ffbdb4c0fcd353c70b6e27ef7481
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263810"
---
# <a name="tracking"></a><span data-ttu-id="2e857-101">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2e857-101">\<tracking></span></span>
<span data-ttu-id="2e857-102">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e857-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="2e857-103">Per altre informazioni sul rilevamento del flusso di lavoro e la relativa configurazione, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [configurazione del rilevamento per un flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="2e857-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="2e857-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2e857-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2e857-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2e857-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e857-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e857-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e857-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2e857-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2e857-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2e857-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e857-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="2e857-109">Attributes</span></span>  
 <span data-ttu-id="2e857-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2e857-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2e857-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2e857-111">Child Elements</span></span>  
  
|<span data-ttu-id="2e857-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e857-112">Element</span></span>|<span data-ttu-id="2e857-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e857-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e857-114">\<participants></span><span class="sxs-lookup"><span data-stu-id="2e857-114">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="2e857-115">Una raccolta di elementi di configurazione che definiscono partecipanti che sottoscrivono record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2e857-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="2e857-116">I partecipanti del rilevamento contengono la logica per elaborare il payload dai record di rilevamento, ad esempio possono scegliere di scrivere in un file.</span><span class="sxs-lookup"><span data-stu-id="2e857-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="2e857-117">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2e857-117">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="2e857-118">Profilo di rilevamento che consente di filtrare i record di rilevamento generati da un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e857-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e857-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2e857-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2e857-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e857-120">Element</span></span>|<span data-ttu-id="2e857-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e857-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e857-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2e857-122">system.ServiceModel</span></span>|<span data-ttu-id="2e857-123">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e857-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e857-124">Note</span><span class="sxs-lookup"><span data-stu-id="2e857-124">Remarks</span></span>  
 <span data-ttu-id="2e857-125">Il rilevamento consente di esaminare l'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e857-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="2e857-126">L'infrastruttura di rilevamento del flusso di lavoro instrumenta un flusso di lavoro per generare record che riflettono gli eventi principali che si verificano durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e857-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="2e857-127">Vengono ad esempio generati record di rilevamento quando viene avviata o completata un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e857-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="2e857-128">Il rilevamento consente inoltre di estrarre dati aziendali rilevanti associati alle variabili del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e857-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="2e857-129">Se, ad esempio, il flusso di lavoro rappresenta un sistema di elaborazione degli ordini, è possibile estrarre l'ID dell'ordine insieme al record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2e857-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="2e857-130">In generale, l'abilitazione del rilevamento WF semplifica la diagnostica o l'analisi aziendale dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e857-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e857-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e857-131">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="2e857-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2e857-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
