---
title: '&lt;workflowInstanceQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 182a4082de6f1c67b7a0bc26662e2491623b2bba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="9f694-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="9f694-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="9f694-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="9f694-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="9f694-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9f694-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9f694-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9f694-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9f694-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="9f694-106">\<tracking></span></span>  
<span data-ttu-id="9f694-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9f694-107">\<trackingProfile></span></span>  
<span data-ttu-id="9f694-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="9f694-108">\<workflow></span></span>  
<span data-ttu-id="9f694-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="9f694-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f694-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f694-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f694-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9f694-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9f694-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9f694-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f694-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="9f694-113">Attributes</span></span>  
 <span data-ttu-id="9f694-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9f694-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9f694-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9f694-115">Child Elements</span></span>  
  
|<span data-ttu-id="9f694-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f694-116">Element</span></span>|<span data-ttu-id="9f694-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f694-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f694-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="9f694-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="9f694-119">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f694-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f694-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9f694-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9f694-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f694-121">Element</span></span>|<span data-ttu-id="9f694-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f694-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f694-123">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="9f694-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9f694-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="9f694-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f694-125">Note</span><span class="sxs-lookup"><span data-stu-id="9f694-125">Remarks</span></span>  
 <span data-ttu-id="9f694-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f694-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="9f694-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f694-127">Example</span></span>  
 <span data-ttu-id="9f694-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="9f694-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f694-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f694-129">See Also</span></span>  
 <span data-ttu-id="9f694-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9f694-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="9f694-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9f694-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="9f694-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9f694-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9f694-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9f694-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
