---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 0a32e6ee22cdf984e64c1b8fa16836c4c56d0380
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932744"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="90818-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="90818-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="90818-102">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="90818-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="90818-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="90818-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="90818-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90818-104">\<system.serviceModel></span></span>  
<span data-ttu-id="90818-105">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="90818-105">\<tracking></span></span>  
<span data-ttu-id="90818-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="90818-106">\<trackingProfile></span></span>  
<span data-ttu-id="90818-107">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="90818-107">\<workflow></span></span>  
<span data-ttu-id="90818-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="90818-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90818-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90818-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90818-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90818-110">Attributes and Elements</span></span>  
 <span data-ttu-id="90818-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90818-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90818-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="90818-112">Attributes</span></span>  
 <span data-ttu-id="90818-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90818-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90818-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90818-114">Child Elements</span></span>  
  
|<span data-ttu-id="90818-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="90818-115">Element</span></span>|<span data-ttu-id="90818-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90818-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90818-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="90818-117">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="90818-118">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="90818-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90818-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90818-119">Parent Elements</span></span>  
  
|<span data-ttu-id="90818-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="90818-120">Element</span></span>|<span data-ttu-id="90818-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="90818-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90818-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="90818-122">\<workflow></span></span>](workflow.md)|<span data-ttu-id="90818-123">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="90818-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90818-124">Note</span><span class="sxs-lookup"><span data-stu-id="90818-124">Remarks</span></span>  
 <span data-ttu-id="90818-125">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="90818-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="90818-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="90818-126">Example</span></span>  
 <span data-ttu-id="90818-127">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="90818-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90818-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90818-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="90818-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="90818-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="90818-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="90818-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
