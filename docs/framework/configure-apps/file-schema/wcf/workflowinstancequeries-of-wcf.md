---
title: '&lt;workflowInstanceQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: dfa75a7e4729244ba5887e6666c0fdfe840e9faf
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46527959"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="0d043-102">&lt;workflowInstanceQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="0d043-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="0d043-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="0d043-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="0d043-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0d043-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="0d043-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0d043-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0d043-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="0d043-106">\<tracking></span></span>  
<span data-ttu-id="0d043-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0d043-107">\<trackingProfile></span></span>  
<span data-ttu-id="0d043-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="0d043-108">\<workflow></span></span>  
<span data-ttu-id="0d043-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="0d043-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d043-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d043-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d043-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0d043-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0d043-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0d043-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d043-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0d043-113">Attributes</span></span>  
 <span data-ttu-id="0d043-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0d043-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d043-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0d043-115">Child Elements</span></span>  
  
|<span data-ttu-id="0d043-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d043-116">Element</span></span>|<span data-ttu-id="0d043-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d043-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d043-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="0d043-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="0d043-119">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d043-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d043-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0d043-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0d043-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d043-121">Element</span></span>|<span data-ttu-id="0d043-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d043-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d043-123">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="0d043-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="0d043-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) proprietà.</span><span class="sxs-lookup"><span data-stu-id="0d043-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d043-125">Note</span><span class="sxs-lookup"><span data-stu-id="0d043-125">Remarks</span></span>  
 <span data-ttu-id="0d043-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d043-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="0d043-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d043-127">Example</span></span>  
 <span data-ttu-id="0d043-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="0d043-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d043-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d043-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0d043-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d043-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0d043-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0d043-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
