---
title: <state> di WCF, <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 1615c83ffe0735d9e55e822f2651da41d02b1610
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757963"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="c736b-102">\<stato > di WCF, \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="c736b-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="c736b-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="c736b-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="c736b-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c736b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c736b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c736b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c736b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c736b-106">\<tracking></span></span>  
<span data-ttu-id="c736b-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="c736b-107">\<profiles></span></span>  
<span data-ttu-id="c736b-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c736b-108">\<trackingProfile></span></span>  
<span data-ttu-id="c736b-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="c736b-109">\<workflow></span></span>  
<span data-ttu-id="c736b-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="c736b-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="c736b-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c736b-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="c736b-112">\<states></span><span class="sxs-lookup"><span data-stu-id="c736b-112">\<states></span></span>  
<span data-ttu-id="c736b-113">\<state></span><span class="sxs-lookup"><span data-stu-id="c736b-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c736b-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c736b-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c736b-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c736b-115">Attributes and elements</span></span>

<span data-ttu-id="c736b-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c736b-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c736b-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="c736b-117">Attributes</span></span>

|<span data-ttu-id="c736b-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="c736b-118">Attribute</span></span>|<span data-ttu-id="c736b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c736b-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="c736b-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="c736b-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c736b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c736b-121">Child elements</span></span>

<span data-ttu-id="c736b-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c736b-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c736b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c736b-123">Parent elements</span></span>

|<span data-ttu-id="c736b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c736b-124">Element</span></span>|<span data-ttu-id="c736b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c736b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c736b-126">\<states></span><span class="sxs-lookup"><span data-stu-id="c736b-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="c736b-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="c736b-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c736b-128">Note</span><span class="sxs-lookup"><span data-stu-id="c736b-128">Remarks</span></span>  

<span data-ttu-id="c736b-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="c736b-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="c736b-130">I valori di stato possibili sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="c736b-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="c736b-131">Stato</span><span class="sxs-lookup"><span data-stu-id="c736b-131">State</span></span>|<span data-ttu-id="c736b-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c736b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c736b-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="c736b-133">Aborted</span></span>|<span data-ttu-id="c736b-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="c736b-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c736b-135">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="c736b-135">Completed</span></span>|<span data-ttu-id="c736b-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="c736b-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="c736b-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="c736b-137">Deleted</span></span>|<span data-ttu-id="c736b-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="c736b-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="c736b-139">Idle</span><span class="sxs-lookup"><span data-stu-id="c736b-139">Idle</span></span>|<span data-ttu-id="c736b-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="c736b-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="c736b-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="c736b-141">Persisted</span></span>|<span data-ttu-id="c736b-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="c736b-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="c736b-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="c736b-143">Resumed</span></span>|<span data-ttu-id="c736b-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="c736b-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="c736b-145">Avviata</span><span class="sxs-lookup"><span data-stu-id="c736b-145">Started</span></span>|<span data-ttu-id="c736b-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="c736b-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="c736b-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="c736b-147">UnhandledException</span></span>|<span data-ttu-id="c736b-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="c736b-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="c736b-149">Scaricato</span><span class="sxs-lookup"><span data-stu-id="c736b-149">Unloaded</span></span>|<span data-ttu-id="c736b-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="c736b-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="c736b-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="c736b-151">Canceled</span></span>|<span data-ttu-id="c736b-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="c736b-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="c736b-153">Sospeso</span><span class="sxs-lookup"><span data-stu-id="c736b-153">Suspended</span></span>|<span data-ttu-id="c736b-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="c736b-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="c736b-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="c736b-155">Terminated</span></span>|<span data-ttu-id="c736b-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="c736b-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="c736b-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="c736b-157">Unsuspended</span></span>|<span data-ttu-id="c736b-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="c736b-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c736b-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="c736b-159">Example</span></span>

<span data-ttu-id="c736b-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="c736b-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="c736b-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c736b-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c736b-162">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c736b-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c736b-163">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c736b-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
