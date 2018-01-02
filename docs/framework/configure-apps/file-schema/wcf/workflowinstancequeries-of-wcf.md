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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecccb2f3b062afd631ef9ba36bc8ac8521db7646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="1497a-102">&lt;workflowInstanceQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="1497a-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="1497a-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="1497a-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="1497a-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1497a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="1497a-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1497a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1497a-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="1497a-106">\<tracking></span></span>  
<span data-ttu-id="1497a-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1497a-107">\<trackingProfile></span></span>  
<span data-ttu-id="1497a-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="1497a-108">\<workflow></span></span>  
<span data-ttu-id="1497a-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="1497a-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1497a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1497a-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1497a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1497a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1497a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1497a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1497a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1497a-113">Attributes</span></span>  
 <span data-ttu-id="1497a-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1497a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1497a-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1497a-115">Child Elements</span></span>  
  
|<span data-ttu-id="1497a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="1497a-116">Element</span></span>|<span data-ttu-id="1497a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1497a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1497a-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="1497a-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="1497a-119">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1497a-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1497a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1497a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1497a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1497a-121">Element</span></span>|<span data-ttu-id="1497a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1497a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1497a-123">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="1497a-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1497a-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal [activityDefinitionId](http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) proprietà.</span><span class="sxs-lookup"><span data-stu-id="1497a-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1497a-125">Note</span><span class="sxs-lookup"><span data-stu-id="1497a-125">Remarks</span></span>  
 <span data-ttu-id="1497a-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="1497a-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="1497a-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="1497a-127">Example</span></span>  
 <span data-ttu-id="1497a-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="1497a-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1497a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1497a-129">See Also</span></span>  
 <span data-ttu-id="1497a-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1497a-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="1497a-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1497a-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="1497a-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1497a-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1497a-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="1497a-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
