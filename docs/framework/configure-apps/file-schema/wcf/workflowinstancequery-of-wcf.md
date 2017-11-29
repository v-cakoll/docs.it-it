---
title: '&lt;workflowInstanceQuery&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 413e341c31b5312d2d772a901965c3917d05e44f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="3506e-102">&lt;workflowInstanceQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="3506e-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>
<span data-ttu-id="3506e-103">Rappresenta una query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="3506e-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="3506e-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3506e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="3506e-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3506e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3506e-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="3506e-106">\<tracking></span></span>  
<span data-ttu-id="3506e-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3506e-107">\<trackingProfile></span></span>  
<span data-ttu-id="3506e-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="3506e-108">\<workflow></span></span>  
<span data-ttu-id="3506e-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="3506e-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="3506e-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="3506e-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3506e-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3506e-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3506e-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3506e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3506e-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3506e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3506e-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="3506e-114">Attributes</span></span>  
 <span data-ttu-id="3506e-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3506e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3506e-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3506e-116">Child Elements</span></span>  
  
|<span data-ttu-id="3506e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3506e-117">Element</span></span>|<span data-ttu-id="3506e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3506e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3506e-119">\<stati ></span><span class="sxs-lookup"><span data-stu-id="3506e-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="3506e-120">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="3506e-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3506e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3506e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3506e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3506e-122">Element</span></span>|<span data-ttu-id="3506e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3506e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3506e-124">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="3506e-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="3506e-125">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="3506e-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3506e-126">Note</span><span class="sxs-lookup"><span data-stu-id="3506e-126">Remarks</span></span>  
 <span data-ttu-id="3506e-127">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="3506e-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="3506e-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="3506e-128">Example</span></span>  
 <span data-ttu-id="3506e-129">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="3506e-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3506e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3506e-130">See Also</span></span>  
 <span data-ttu-id="3506e-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3506e-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3506e-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3506e-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3506e-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3506e-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3506e-134">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3506e-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
