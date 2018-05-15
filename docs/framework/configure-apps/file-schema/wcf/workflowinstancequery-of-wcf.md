---
title: '&lt;workflowInstanceQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: c3b68dda42fd7a9356366a0887feb359d0232b32
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="97966-102">&lt;workflowInstanceQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="97966-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>
<span data-ttu-id="97966-103">Rappresenta una query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="97966-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="97966-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="97966-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="97966-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="97966-105">\<system.serviceModel></span></span>  
<span data-ttu-id="97966-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="97966-106">\<tracking></span></span>  
<span data-ttu-id="97966-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="97966-107">\<trackingProfile></span></span>  
<span data-ttu-id="97966-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="97966-108">\<workflow></span></span>  
<span data-ttu-id="97966-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="97966-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="97966-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="97966-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97966-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97966-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97966-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="97966-112">Attributes and Elements</span></span>  
 <span data-ttu-id="97966-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="97966-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97966-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="97966-114">Attributes</span></span>  
 <span data-ttu-id="97966-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="97966-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97966-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="97966-116">Child Elements</span></span>  
  
|<span data-ttu-id="97966-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="97966-117">Element</span></span>|<span data-ttu-id="97966-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97966-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97966-119">\<stati ></span><span class="sxs-lookup"><span data-stu-id="97966-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="97966-120">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="97966-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97966-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="97966-121">Parent Elements</span></span>  
  
|<span data-ttu-id="97966-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="97966-122">Element</span></span>|<span data-ttu-id="97966-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97966-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97966-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="97966-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="97966-125">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="97966-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97966-126">Note</span><span class="sxs-lookup"><span data-stu-id="97966-126">Remarks</span></span>  
 <span data-ttu-id="97966-127">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="97966-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="97966-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="97966-128">Example</span></span>  
 <span data-ttu-id="97966-129">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="97966-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="97966-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97966-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="97966-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="97966-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="97966-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="97966-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
