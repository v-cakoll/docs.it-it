---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: e54f98c980f60d02377e38d53d9d0eb48581eec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613306"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="456bc-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="456bc-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="456bc-102">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="456bc-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="456bc-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="456bc-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="456bc-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="456bc-104">\<system.serviceModel></span></span>  
<span data-ttu-id="456bc-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="456bc-105">\<tracking></span></span>  
<span data-ttu-id="456bc-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="456bc-106">\<trackingProfile></span></span>  
<span data-ttu-id="456bc-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="456bc-107">\<workflow></span></span>  
<span data-ttu-id="456bc-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="456bc-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="456bc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="456bc-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="456bc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="456bc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="456bc-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="456bc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="456bc-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="456bc-112">Attributes</span></span>  
 <span data-ttu-id="456bc-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="456bc-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="456bc-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="456bc-114">Child Elements</span></span>  
  
|<span data-ttu-id="456bc-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="456bc-115">Element</span></span>|<span data-ttu-id="456bc-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="456bc-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="456bc-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="456bc-117">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="456bc-118">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="456bc-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="456bc-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="456bc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="456bc-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="456bc-120">Element</span></span>|<span data-ttu-id="456bc-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="456bc-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="456bc-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="456bc-122">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="456bc-123">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="456bc-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="456bc-124">Note</span><span class="sxs-lookup"><span data-stu-id="456bc-124">Remarks</span></span>  
 <span data-ttu-id="456bc-125">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="456bc-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="456bc-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="456bc-126">Example</span></span>  
 <span data-ttu-id="456bc-127">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="456bc-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="456bc-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="456bc-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="456bc-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="456bc-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="456bc-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="456bc-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
