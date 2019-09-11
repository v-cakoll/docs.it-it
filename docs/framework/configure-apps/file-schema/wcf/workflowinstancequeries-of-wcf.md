---
title: <workflowInstanceQueries>di WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854778"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="14e01-102">\<> workflowInstanceQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="14e01-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="14e01-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="14e01-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="14e01-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="14e01-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="14e01-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14e01-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14e01-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="14e01-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="14e01-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="14e01-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="14e01-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="14e01-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="14e01-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="14e01-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="14e01-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="14e01-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="14e01-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceQueries**</span><span class="sxs-lookup"><span data-stu-id="14e01-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e01-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14e01-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14e01-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14e01-113">Attributes and elements</span></span>

<span data-ttu-id="14e01-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14e01-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14e01-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="14e01-115">Attributes</span></span>  

<span data-ttu-id="14e01-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="14e01-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14e01-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14e01-117">Child elements</span></span>  
  
|<span data-ttu-id="14e01-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="14e01-118">Element</span></span>|<span data-ttu-id="14e01-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14e01-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14e01-120">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="14e01-120">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="14e01-121">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="14e01-121">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14e01-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14e01-122">Parent elements</span></span>  
  
|<span data-ttu-id="14e01-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="14e01-123">Element</span></span>|<span data-ttu-id="14e01-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14e01-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14e01-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="14e01-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="14e01-126">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà [ActivityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="14e01-126">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e01-127">Note</span><span class="sxs-lookup"><span data-stu-id="14e01-127">Remarks</span></span>

<span data-ttu-id="14e01-128">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="14e01-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="14e01-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="14e01-129">Example</span></span>  

<span data-ttu-id="14e01-130">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="14e01-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="14e01-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14e01-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="14e01-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="14e01-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="14e01-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="14e01-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
