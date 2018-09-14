---
title: '&lt;workflowInstanceQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: dfa75a7e4729244ba5887e6666c0fdfe840e9faf
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45508356"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="e6cb4-102">&lt;workflowInstanceQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="e6cb4-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="e6cb4-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="e6cb4-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="e6cb4-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e6cb4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="e6cb4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e6cb4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e6cb4-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="e6cb4-106">\<tracking></span></span>  
<span data-ttu-id="e6cb4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e6cb4-107">\<trackingProfile></span></span>  
<span data-ttu-id="e6cb4-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e6cb4-108">\<workflow></span></span>  
<span data-ttu-id="e6cb4-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="e6cb4-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6cb4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6cb4-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6cb4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e6cb4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e6cb4-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e6cb4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6cb4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e6cb4-113">Attributes</span></span>  
 <span data-ttu-id="e6cb4-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e6cb4-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6cb4-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e6cb4-115">Child Elements</span></span>  
  
|<span data-ttu-id="e6cb4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6cb4-116">Element</span></span>|<span data-ttu-id="e6cb4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6cb4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6cb4-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="e6cb4-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="e6cb4-119">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e6cb4-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6cb4-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e6cb4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e6cb4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6cb4-121">Element</span></span>|<span data-ttu-id="e6cb4-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6cb4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6cb4-123">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e6cb4-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e6cb4-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6cb4-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6cb4-125">Note</span><span class="sxs-lookup"><span data-stu-id="e6cb4-125">Remarks</span></span>  
 <span data-ttu-id="e6cb4-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6cb4-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="e6cb4-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6cb4-127">Example</span></span>  
 <span data-ttu-id="e6cb4-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="e6cb4-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6cb4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6cb4-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="e6cb4-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e6cb4-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e6cb4-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e6cb4-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
