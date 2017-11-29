---
title: '&lt;workflowInstanceQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6ca8104ba2470593e07e03a7fe0bc80c9cd2f6a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="c3616-102">&lt;workflowInstanceQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="c3616-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="c3616-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="c3616-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="c3616-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c3616-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="c3616-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c3616-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c3616-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="c3616-106">\<tracking></span></span>  
<span data-ttu-id="c3616-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c3616-107">\<trackingProfile></span></span>  
<span data-ttu-id="c3616-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="c3616-108">\<workflow></span></span>  
<span data-ttu-id="c3616-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="c3616-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3616-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3616-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3616-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c3616-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c3616-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c3616-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3616-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c3616-113">Attributes</span></span>  
 <span data-ttu-id="c3616-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c3616-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c3616-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c3616-115">Child Elements</span></span>  
  
|<span data-ttu-id="c3616-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3616-116">Element</span></span>|<span data-ttu-id="c3616-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3616-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3616-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="c3616-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="c3616-119">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3616-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3616-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c3616-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c3616-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3616-121">Element</span></span>|<span data-ttu-id="c3616-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3616-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3616-123">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="c3616-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c3616-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal [activityDefinitionId](http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) proprietà.</span><span class="sxs-lookup"><span data-stu-id="c3616-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3616-125">Note</span><span class="sxs-lookup"><span data-stu-id="c3616-125">Remarks</span></span>  
 <span data-ttu-id="c3616-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3616-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="c3616-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3616-127">Example</span></span>  
 <span data-ttu-id="c3616-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="c3616-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3616-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3616-129">See Also</span></span>  
 <span data-ttu-id="c3616-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c3616-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="c3616-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c3616-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="c3616-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c3616-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c3616-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c3616-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
