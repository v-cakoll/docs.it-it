---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 88ad61dca6c0f756a14538e7b207532ff7173ec5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624741"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="77a94-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="77a94-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="77a94-102">Rappresenta una query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="77a94-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="77a94-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="77a94-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="77a94-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="77a94-104">\<system.serviceModel></span></span>  
<span data-ttu-id="77a94-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="77a94-105">\<tracking></span></span>  
<span data-ttu-id="77a94-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="77a94-106">\<trackingProfile></span></span>  
<span data-ttu-id="77a94-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="77a94-107">\<workflow></span></span>  
<span data-ttu-id="77a94-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="77a94-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="77a94-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="77a94-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a94-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77a94-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77a94-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77a94-111">Attributes and Elements</span></span>  
 <span data-ttu-id="77a94-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77a94-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77a94-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="77a94-113">Attributes</span></span>  
 <span data-ttu-id="77a94-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="77a94-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="77a94-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77a94-115">Child Elements</span></span>  
  
|<span data-ttu-id="77a94-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="77a94-116">Element</span></span>|<span data-ttu-id="77a94-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77a94-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77a94-118">\<states></span><span class="sxs-lookup"><span data-stu-id="77a94-118">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="77a94-119">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="77a94-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77a94-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77a94-120">Parent Elements</span></span>  
  
|<span data-ttu-id="77a94-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="77a94-121">Element</span></span>|<span data-ttu-id="77a94-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77a94-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77a94-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="77a94-123">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="77a94-124">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="77a94-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77a94-125">Note</span><span class="sxs-lookup"><span data-stu-id="77a94-125">Remarks</span></span>  
 <span data-ttu-id="77a94-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="77a94-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="77a94-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="77a94-127">Example</span></span>  
 <span data-ttu-id="77a94-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="77a94-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77a94-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77a94-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="77a94-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="77a94-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="77a94-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="77a94-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
