---
title: '&lt;workflowInstanceQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 300637031c64f7c9e072f04835fc3590348ddc9e
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50047397"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="cd480-102">&lt;workflowInstanceQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="cd480-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>

<span data-ttu-id="cd480-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="cd480-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="cd480-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cd480-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cd480-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cd480-105">\<system.serviceModel></span></span>  
<span data-ttu-id="cd480-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="cd480-106">\<tracking></span></span>  
<span data-ttu-id="cd480-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="cd480-107">\<profiles></span></span>  
<span data-ttu-id="cd480-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cd480-108">\<trackingProfile></span></span>  
<span data-ttu-id="cd480-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="cd480-109">\<workflow></span></span>  
<span data-ttu-id="cd480-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="cd480-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd480-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd480-111">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd480-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cd480-112">Attributes and elements</span></span>

<span data-ttu-id="cd480-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cd480-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd480-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="cd480-114">Attributes</span></span>  

<span data-ttu-id="cd480-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cd480-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd480-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cd480-116">Child elements</span></span>  
  
|<span data-ttu-id="cd480-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd480-117">Element</span></span>|<span data-ttu-id="cd480-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd480-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd480-119">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="cd480-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="cd480-120">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cd480-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd480-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cd480-121">Parent elements</span></span>  
  
|<span data-ttu-id="cd480-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd480-122">Element</span></span>|<span data-ttu-id="cd480-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd480-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd480-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="cd480-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="cd480-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) proprietà.</span><span class="sxs-lookup"><span data-stu-id="cd480-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd480-126">Note</span><span class="sxs-lookup"><span data-stu-id="cd480-126">Remarks</span></span>

<span data-ttu-id="cd480-127">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd480-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="cd480-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd480-128">Example</span></span>  

<span data-ttu-id="cd480-129">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="cd480-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>  
    <states>  
      <state name="Started"/>  
    </states>  
  </workflowInstanceQuery>  
</workflowInstanceQueries>
```
  
## <a name="see-also"></a><span data-ttu-id="cd480-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd480-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="cd480-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cd480-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cd480-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="cd480-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
