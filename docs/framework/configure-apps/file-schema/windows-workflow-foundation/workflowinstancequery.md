---
title: '&lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: bef9ddcee2e373f4588d6aed06b7c51e4c6ed4b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662049"
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="31b06-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="31b06-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="31b06-103">Rappresenta una query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="31b06-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="31b06-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="31b06-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="31b06-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="31b06-105">\<system.serviceModel></span></span>  
<span data-ttu-id="31b06-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="31b06-106">\<tracking></span></span>  
<span data-ttu-id="31b06-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="31b06-107">\<trackingProfile></span></span>  
<span data-ttu-id="31b06-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="31b06-108">\<workflow></span></span>  
<span data-ttu-id="31b06-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="31b06-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="31b06-110">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="31b06-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31b06-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31b06-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31b06-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="31b06-112">Attributes and Elements</span></span>  
 <span data-ttu-id="31b06-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="31b06-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31b06-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="31b06-114">Attributes</span></span>  
 <span data-ttu-id="31b06-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="31b06-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="31b06-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="31b06-116">Child Elements</span></span>  
  
|<span data-ttu-id="31b06-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="31b06-117">Element</span></span>|<span data-ttu-id="31b06-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31b06-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31b06-119">\<states></span><span class="sxs-lookup"><span data-stu-id="31b06-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="31b06-120">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="31b06-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31b06-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="31b06-121">Parent Elements</span></span>  
  
|<span data-ttu-id="31b06-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="31b06-122">Element</span></span>|<span data-ttu-id="31b06-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31b06-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31b06-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="31b06-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="31b06-125">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="31b06-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31b06-126">Note</span><span class="sxs-lookup"><span data-stu-id="31b06-126">Remarks</span></span>  
 <span data-ttu-id="31b06-127">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="31b06-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="31b06-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="31b06-128">Example</span></span>  
 <span data-ttu-id="31b06-129">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="31b06-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31b06-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31b06-130">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="31b06-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="31b06-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="31b06-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="31b06-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
