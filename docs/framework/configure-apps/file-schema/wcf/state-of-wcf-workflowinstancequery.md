---
title: '&lt;stato&gt; di WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 168a6980e955f602ee60bff26461f06cb16c836a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145926"
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="11853-102">&lt;stato&gt; di WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="11853-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="11853-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="11853-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="11853-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="11853-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="11853-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="11853-105">\<system.serviceModel></span></span>  
<span data-ttu-id="11853-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="11853-106">\<tracking></span></span>  
<span data-ttu-id="11853-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="11853-107">\<profiles></span></span>  
<span data-ttu-id="11853-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="11853-108">\<trackingProfile></span></span>  
<span data-ttu-id="11853-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="11853-109">\<workflow></span></span>  
<span data-ttu-id="11853-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="11853-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="11853-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="11853-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="11853-112">\<stati ></span><span class="sxs-lookup"><span data-stu-id="11853-112">\<states></span></span>  
<span data-ttu-id="11853-113">\<stato ></span><span class="sxs-lookup"><span data-stu-id="11853-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11853-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11853-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11853-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="11853-115">Attributes and elements</span></span>

<span data-ttu-id="11853-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="11853-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="11853-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="11853-117">Attributes</span></span>

|<span data-ttu-id="11853-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="11853-118">Attribute</span></span>|<span data-ttu-id="11853-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11853-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="11853-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="11853-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11853-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="11853-121">Child elements</span></span>

<span data-ttu-id="11853-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="11853-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="11853-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="11853-123">Parent elements</span></span>

|<span data-ttu-id="11853-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="11853-124">Element</span></span>|<span data-ttu-id="11853-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11853-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11853-126">\<stati ></span><span class="sxs-lookup"><span data-stu-id="11853-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="11853-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="11853-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11853-128">Note</span><span class="sxs-lookup"><span data-stu-id="11853-128">Remarks</span></span>  

<span data-ttu-id="11853-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="11853-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="11853-130">I valori di stato possibili sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="11853-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="11853-131">Stato</span><span class="sxs-lookup"><span data-stu-id="11853-131">State</span></span>|<span data-ttu-id="11853-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11853-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="11853-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="11853-133">Aborted</span></span>|<span data-ttu-id="11853-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="11853-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="11853-135">Completata</span><span class="sxs-lookup"><span data-stu-id="11853-135">Completed</span></span>|<span data-ttu-id="11853-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="11853-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="11853-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="11853-137">Deleted</span></span>|<span data-ttu-id="11853-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="11853-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="11853-139">Idle</span><span class="sxs-lookup"><span data-stu-id="11853-139">Idle</span></span>|<span data-ttu-id="11853-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="11853-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="11853-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="11853-141">Persisted</span></span>|<span data-ttu-id="11853-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="11853-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="11853-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="11853-143">Resumed</span></span>|<span data-ttu-id="11853-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="11853-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="11853-145">Started</span><span class="sxs-lookup"><span data-stu-id="11853-145">Started</span></span>|<span data-ttu-id="11853-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="11853-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="11853-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="11853-147">UnhandledException</span></span>|<span data-ttu-id="11853-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="11853-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="11853-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="11853-149">Unloaded</span></span>|<span data-ttu-id="11853-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="11853-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="11853-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="11853-151">Canceled</span></span>|<span data-ttu-id="11853-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="11853-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="11853-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="11853-153">Suspended</span></span>|<span data-ttu-id="11853-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="11853-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="11853-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="11853-155">Terminated</span></span>|<span data-ttu-id="11853-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="11853-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="11853-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="11853-157">Unsuspended</span></span>|<span data-ttu-id="11853-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="11853-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="11853-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="11853-159">Example</span></span>

<span data-ttu-id="11853-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="11853-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="11853-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11853-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="11853-162">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="11853-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="11853-163">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="11853-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
