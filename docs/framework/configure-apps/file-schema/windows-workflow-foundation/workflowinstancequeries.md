---
title: '&lt;workflowInstanceQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 8ee8c74e88f1605ae3858db787c38976de9cc976
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693704"
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="06e92-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="06e92-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="06e92-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="06e92-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="06e92-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="06e92-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="06e92-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="06e92-105">\<system.serviceModel></span></span>  
<span data-ttu-id="06e92-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="06e92-106">\<tracking></span></span>  
<span data-ttu-id="06e92-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="06e92-107">\<trackingProfile></span></span>  
<span data-ttu-id="06e92-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="06e92-108">\<workflow></span></span>  
<span data-ttu-id="06e92-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="06e92-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e92-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06e92-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06e92-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="06e92-111">Attributes and Elements</span></span>  
 <span data-ttu-id="06e92-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="06e92-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06e92-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="06e92-113">Attributes</span></span>  
 <span data-ttu-id="06e92-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="06e92-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="06e92-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="06e92-115">Child Elements</span></span>  
  
|<span data-ttu-id="06e92-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="06e92-116">Element</span></span>|<span data-ttu-id="06e92-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06e92-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06e92-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="06e92-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="06e92-119">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="06e92-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06e92-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="06e92-120">Parent Elements</span></span>  
  
|<span data-ttu-id="06e92-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="06e92-121">Element</span></span>|<span data-ttu-id="06e92-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06e92-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06e92-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="06e92-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="06e92-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="06e92-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06e92-125">Note</span><span class="sxs-lookup"><span data-stu-id="06e92-125">Remarks</span></span>  
 <span data-ttu-id="06e92-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="06e92-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="06e92-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="06e92-127">Example</span></span>  
 <span data-ttu-id="06e92-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="06e92-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06e92-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06e92-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="06e92-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="06e92-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="06e92-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="06e92-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
