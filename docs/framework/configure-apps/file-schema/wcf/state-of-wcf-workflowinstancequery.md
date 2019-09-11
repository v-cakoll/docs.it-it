---
title: <state>di WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854958"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="d3cbb-102">\<> di stato di WCF \<, workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="d3cbb-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="d3cbb-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="d3cbb-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d3cbb-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d3cbb-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d3cbb-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="d3cbb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="d3cbb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="d3cbb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="d3cbb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="d3cbb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="d3cbb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="d3cbb-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Stati >** ](states-of-wcf-workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)</span></span>\
<span data-ttu-id="d3cbb-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di stato**</span><span class="sxs-lookup"><span data-stu-id="d3cbb-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3cbb-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3cbb-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3cbb-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d3cbb-116">Attributes and elements</span></span>

<span data-ttu-id="d3cbb-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d3cbb-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="d3cbb-118">Attributes</span></span>

|<span data-ttu-id="d3cbb-119">Attributo</span><span class="sxs-lookup"><span data-stu-id="d3cbb-119">Attribute</span></span>|<span data-ttu-id="d3cbb-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3cbb-120">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d3cbb-121">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-121">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3cbb-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d3cbb-122">Child elements</span></span>

<span data-ttu-id="d3cbb-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d3cbb-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d3cbb-124">Parent elements</span></span>

|<span data-ttu-id="d3cbb-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3cbb-125">Element</span></span>|<span data-ttu-id="d3cbb-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3cbb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3cbb-127">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="d3cbb-127">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="d3cbb-128">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-128">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3cbb-129">Note</span><span class="sxs-lookup"><span data-stu-id="d3cbb-129">Remarks</span></span>  

<span data-ttu-id="d3cbb-130">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="d3cbb-131">Nella tabella seguente sono descritti i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="d3cbb-131">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="d3cbb-132">Stato</span><span class="sxs-lookup"><span data-stu-id="d3cbb-132">State</span></span>|<span data-ttu-id="d3cbb-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3cbb-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d3cbb-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="d3cbb-134">Aborted</span></span>|<span data-ttu-id="d3cbb-135">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="d3cbb-136">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="d3cbb-136">Completed</span></span>|<span data-ttu-id="d3cbb-137">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="d3cbb-138">Eliminato</span><span class="sxs-lookup"><span data-stu-id="d3cbb-138">Deleted</span></span>|<span data-ttu-id="d3cbb-139">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="d3cbb-140">Idle</span><span class="sxs-lookup"><span data-stu-id="d3cbb-140">Idle</span></span>|<span data-ttu-id="d3cbb-141">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="d3cbb-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="d3cbb-142">Persisted</span></span>|<span data-ttu-id="d3cbb-143">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="d3cbb-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="d3cbb-144">Resumed</span></span>|<span data-ttu-id="d3cbb-145">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="d3cbb-146">Started</span><span class="sxs-lookup"><span data-stu-id="d3cbb-146">Started</span></span>|<span data-ttu-id="d3cbb-147">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="d3cbb-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="d3cbb-148">UnhandledException</span></span>|<span data-ttu-id="d3cbb-149">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="d3cbb-150">Scaricato</span><span class="sxs-lookup"><span data-stu-id="d3cbb-150">Unloaded</span></span>|<span data-ttu-id="d3cbb-151">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="d3cbb-152">Annullato</span><span class="sxs-lookup"><span data-stu-id="d3cbb-152">Canceled</span></span>|<span data-ttu-id="d3cbb-153">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="d3cbb-154">Suspended</span><span class="sxs-lookup"><span data-stu-id="d3cbb-154">Suspended</span></span>|<span data-ttu-id="d3cbb-155">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="d3cbb-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="d3cbb-156">Terminated</span></span>|<span data-ttu-id="d3cbb-157">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="d3cbb-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="d3cbb-158">Unsuspended</span></span>|<span data-ttu-id="d3cbb-159">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3cbb-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3cbb-160">Example</span></span>

<span data-ttu-id="d3cbb-161">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="d3cbb-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3cbb-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d3cbb-163">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d3cbb-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d3cbb-164">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d3cbb-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
