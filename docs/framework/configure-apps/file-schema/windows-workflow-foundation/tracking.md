---
title: '&lt;rilevamento&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8147f9d9366d323b551ce2bb8874f6e80fb50b5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="lttrackinggt"></a><span data-ttu-id="781c4-102">&lt;rilevamento&gt;</span><span class="sxs-lookup"><span data-stu-id="781c4-102">&lt;tracking&gt;</span></span>
<span data-ttu-id="781c4-103">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="781c4-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="781c4-104">Per altre informazioni, vedere rilevamento del flusso di lavoro e la relativa configurazione, vedere [flusso di lavoro rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [configurazione del rilevamento per un flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="781c4-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="781c4-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="781c4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="781c4-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="781c4-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="781c4-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="781c4-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="781c4-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="781c4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="781c4-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="781c4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="781c4-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="781c4-110">Attributes</span></span>  
 <span data-ttu-id="781c4-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="781c4-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="781c4-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="781c4-112">Child Elements</span></span>  
  
|<span data-ttu-id="781c4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="781c4-113">Element</span></span>|<span data-ttu-id="781c4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="781c4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="781c4-115">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="781c4-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="781c4-116">Una raccolta di elementi di configurazione che definiscono partecipanti che sottoscrivono record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="781c4-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="781c4-117">I partecipanti del rilevamento contengono la logica per elaborare il payload dai record di rilevamento, ad esempio possono scegliere di scrivere in un file.</span><span class="sxs-lookup"><span data-stu-id="781c4-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="781c4-118">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="781c4-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="781c4-119">Profilo di rilevamento che consente di filtrare i record di rilevamento generati da un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="781c4-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="781c4-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="781c4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="781c4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="781c4-121">Element</span></span>|<span data-ttu-id="781c4-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="781c4-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="781c4-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="781c4-123">system.ServiceModel</span></span>|<span data-ttu-id="781c4-124">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="781c4-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="781c4-125">Note</span><span class="sxs-lookup"><span data-stu-id="781c4-125">Remarks</span></span>  
 <span data-ttu-id="781c4-126">Il rilevamento consente di esaminare l'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="781c4-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="781c4-127">L'infrastruttura di rilevamento del flusso di lavoro instrumenta un flusso di lavoro per generare record che riflettono gli eventi principali che si verificano durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="781c4-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="781c4-128">Vengono ad esempio generati record di rilevamento quando viene avviata o completata un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="781c4-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="781c4-129">Il rilevamento consente inoltre di estrarre dati aziendali rilevanti associati alle variabili del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="781c4-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="781c4-130">Se, ad esempio, il flusso di lavoro rappresenta un sistema di elaborazione degli ordini, è possibile estrarre l'ID dell'ordine insieme al record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="781c4-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="781c4-131">In generale, l'abilitazione del rilevamento WF semplifica la diagnostica o l'analisi aziendale dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="781c4-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781c4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="781c4-132">See Also</span></span>  
 <span data-ttu-id="781c4-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="781c4-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="781c4-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="781c4-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
