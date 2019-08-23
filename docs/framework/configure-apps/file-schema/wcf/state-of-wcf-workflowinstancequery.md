---
title: <state>di WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 99387a8f60e96beb2ec7706d9abf4bb6ae84b868
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938213"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="224e4-102">\<> di stato di WCF \<, workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="224e4-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="224e4-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="224e4-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="224e4-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="224e4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="224e4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="224e4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="224e4-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="224e4-106">\<tracking></span></span>  
<span data-ttu-id="224e4-107">\<profili ></span><span class="sxs-lookup"><span data-stu-id="224e4-107">\<profiles></span></span>  
<span data-ttu-id="224e4-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="224e4-108">\<trackingProfile></span></span>  
<span data-ttu-id="224e4-109">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="224e4-109">\<workflow></span></span>  
<span data-ttu-id="224e4-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="224e4-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="224e4-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="224e4-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="224e4-112">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="224e4-112">\<states></span></span>  
<span data-ttu-id="224e4-113">\<> di stato</span><span class="sxs-lookup"><span data-stu-id="224e4-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="224e4-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="224e4-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="224e4-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="224e4-115">Attributes and elements</span></span>

<span data-ttu-id="224e4-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="224e4-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="224e4-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="224e4-117">Attributes</span></span>

|<span data-ttu-id="224e4-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="224e4-118">Attribute</span></span>|<span data-ttu-id="224e4-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="224e4-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="224e4-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="224e4-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="224e4-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="224e4-121">Child elements</span></span>

<span data-ttu-id="224e4-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="224e4-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="224e4-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="224e4-123">Parent elements</span></span>

|<span data-ttu-id="224e4-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="224e4-124">Element</span></span>|<span data-ttu-id="224e4-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="224e4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="224e4-126">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="224e4-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="224e4-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="224e4-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="224e4-128">Note</span><span class="sxs-lookup"><span data-stu-id="224e4-128">Remarks</span></span>  

<span data-ttu-id="224e4-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="224e4-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="224e4-130">Nella tabella seguente sono descritti i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="224e4-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="224e4-131">Stato</span><span class="sxs-lookup"><span data-stu-id="224e4-131">State</span></span>|<span data-ttu-id="224e4-132">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="224e4-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="224e4-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="224e4-133">Aborted</span></span>|<span data-ttu-id="224e4-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="224e4-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="224e4-135">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="224e4-135">Completed</span></span>|<span data-ttu-id="224e4-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="224e4-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="224e4-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="224e4-137">Deleted</span></span>|<span data-ttu-id="224e4-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="224e4-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="224e4-139">Idle</span><span class="sxs-lookup"><span data-stu-id="224e4-139">Idle</span></span>|<span data-ttu-id="224e4-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="224e4-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="224e4-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="224e4-141">Persisted</span></span>|<span data-ttu-id="224e4-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="224e4-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="224e4-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="224e4-143">Resumed</span></span>|<span data-ttu-id="224e4-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="224e4-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="224e4-145">Started</span><span class="sxs-lookup"><span data-stu-id="224e4-145">Started</span></span>|<span data-ttu-id="224e4-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="224e4-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="224e4-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="224e4-147">UnhandledException</span></span>|<span data-ttu-id="224e4-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="224e4-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="224e4-149">Scaricato</span><span class="sxs-lookup"><span data-stu-id="224e4-149">Unloaded</span></span>|<span data-ttu-id="224e4-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="224e4-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="224e4-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="224e4-151">Canceled</span></span>|<span data-ttu-id="224e4-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="224e4-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="224e4-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="224e4-153">Suspended</span></span>|<span data-ttu-id="224e4-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="224e4-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="224e4-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="224e4-155">Terminated</span></span>|<span data-ttu-id="224e4-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="224e4-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="224e4-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="224e4-157">Unsuspended</span></span>|<span data-ttu-id="224e4-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="224e4-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="224e4-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="224e4-159">Example</span></span>

<span data-ttu-id="224e4-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="224e4-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="224e4-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="224e4-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="224e4-162">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="224e4-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="224e4-163">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="224e4-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
