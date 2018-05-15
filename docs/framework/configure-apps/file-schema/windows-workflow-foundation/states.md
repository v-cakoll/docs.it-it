---
title: '&lt;Stati&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: fe02106d8d7f70cb328214c7e464d80a41b75528
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltstatesgt"></a><span data-ttu-id="3d9ab-102">&lt;Stati&gt;</span><span class="sxs-lookup"><span data-stu-id="3d9ab-102">&lt;states&gt;</span></span>
<span data-ttu-id="3d9ab-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="3d9ab-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3d9ab-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3d9ab-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3d9ab-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3d9ab-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="3d9ab-106">\<tracking></span></span>  
<span data-ttu-id="3d9ab-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3d9ab-107">\<trackingProfile></span></span>  
<span data-ttu-id="3d9ab-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="3d9ab-108">\<workflow></span></span>  
<span data-ttu-id="3d9ab-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="3d9ab-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="3d9ab-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="3d9ab-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="3d9ab-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="3d9ab-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9ab-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d9ab-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d9ab-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3d9ab-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3d9ab-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d9ab-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="3d9ab-115">Attributes</span></span>  
 <span data-ttu-id="3d9ab-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d9ab-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3d9ab-117">Child Elements</span></span>  
  
|<span data-ttu-id="3d9ab-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d9ab-118">Element</span></span>|<span data-ttu-id="3d9ab-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d9ab-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d9ab-120">\<stato ></span><span class="sxs-lookup"><span data-stu-id="3d9ab-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="3d9ab-121">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d9ab-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3d9ab-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3d9ab-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d9ab-123">Element</span></span>|<span data-ttu-id="3d9ab-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d9ab-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d9ab-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="3d9ab-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="3d9ab-126">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d9ab-127">Note</span><span class="sxs-lookup"><span data-stu-id="3d9ab-127">Remarks</span></span>  
 <span data-ttu-id="3d9ab-128">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="3d9ab-129">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="3d9ab-130">Stato</span><span class="sxs-lookup"><span data-stu-id="3d9ab-130">State</span></span>|<span data-ttu-id="3d9ab-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d9ab-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d9ab-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="3d9ab-132">Aborted</span></span>|<span data-ttu-id="3d9ab-133">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="3d9ab-134">Completata</span><span class="sxs-lookup"><span data-stu-id="3d9ab-134">Completed</span></span>|<span data-ttu-id="3d9ab-135">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="3d9ab-136">Eliminato</span><span class="sxs-lookup"><span data-stu-id="3d9ab-136">Deleted</span></span>|<span data-ttu-id="3d9ab-137">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="3d9ab-138">Idle</span><span class="sxs-lookup"><span data-stu-id="3d9ab-138">Idle</span></span>|<span data-ttu-id="3d9ab-139">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="3d9ab-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="3d9ab-140">Persisted</span></span>|<span data-ttu-id="3d9ab-141">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="3d9ab-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="3d9ab-142">Resumed</span></span>|<span data-ttu-id="3d9ab-143">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="3d9ab-144">Started</span><span class="sxs-lookup"><span data-stu-id="3d9ab-144">Started</span></span>|<span data-ttu-id="3d9ab-145">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="3d9ab-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="3d9ab-146">UnhandledException</span></span>|<span data-ttu-id="3d9ab-147">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="3d9ab-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="3d9ab-148">Unloaded</span></span>|<span data-ttu-id="3d9ab-149">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="3d9ab-150">Annullato</span><span class="sxs-lookup"><span data-stu-id="3d9ab-150">Canceled</span></span>|<span data-ttu-id="3d9ab-151">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="3d9ab-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="3d9ab-152">Suspended</span></span>|<span data-ttu-id="3d9ab-153">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="3d9ab-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="3d9ab-154">Terminated</span></span>|<span data-ttu-id="3d9ab-155">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="3d9ab-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="3d9ab-156">Unsuspended</span></span>|<span data-ttu-id="3d9ab-157">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3d9ab-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d9ab-158">Example</span></span>  
 <span data-ttu-id="3d9ab-159">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="3d9ab-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d9ab-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d9ab-160">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="3d9ab-161">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3d9ab-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3d9ab-162">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3d9ab-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
