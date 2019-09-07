---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 11e301de1ab3dbd4c97f236bfd07c5de4a632272
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398583"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="bf27e-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="bf27e-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="bf27e-102">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="bf27e-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="bf27e-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bf27e-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bf27e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf27e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf27e-105">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="bf27e-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="bf27e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="bf27e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="bf27e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="bf27e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="bf27e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="bf27e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="bf27e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceQueries**</span><span class="sxs-lookup"><span data-stu-id="bf27e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf27e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf27e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf27e-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bf27e-111">Attributes and Elements</span></span>  

<span data-ttu-id="bf27e-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bf27e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf27e-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="bf27e-113">Attributes</span></span>  

<span data-ttu-id="bf27e-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bf27e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf27e-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bf27e-115">Child Elements</span></span>  
  
|<span data-ttu-id="bf27e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf27e-116">Element</span></span>|<span data-ttu-id="bf27e-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="bf27e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf27e-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="bf27e-118">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="bf27e-119">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bf27e-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf27e-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bf27e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bf27e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf27e-121">Element</span></span>|<span data-ttu-id="bf27e-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf27e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf27e-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="bf27e-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="bf27e-124">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="bf27e-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf27e-125">Note</span><span class="sxs-lookup"><span data-stu-id="bf27e-125">Remarks</span></span>  

<span data-ttu-id="bf27e-126">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf27e-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="bf27e-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf27e-127">Example</span></span>  

<span data-ttu-id="bf27e-128">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="bf27e-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf27e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf27e-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bf27e-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="bf27e-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bf27e-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="bf27e-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
