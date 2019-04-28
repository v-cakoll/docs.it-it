---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797800"
---
# <a name="states"></a><span data-ttu-id="355f2-101">\<states></span><span class="sxs-lookup"><span data-stu-id="355f2-101">\<states></span></span>
<span data-ttu-id="355f2-102">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="355f2-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="355f2-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="355f2-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="355f2-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="355f2-104">\<system.serviceModel></span></span>  
<span data-ttu-id="355f2-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="355f2-105">\<tracking></span></span>  
<span data-ttu-id="355f2-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="355f2-106">\<trackingProfile></span></span>  
<span data-ttu-id="355f2-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="355f2-107">\<workflow></span></span>  
<span data-ttu-id="355f2-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="355f2-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="355f2-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="355f2-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="355f2-110">\<states></span><span class="sxs-lookup"><span data-stu-id="355f2-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="355f2-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="355f2-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="355f2-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="355f2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="355f2-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="355f2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="355f2-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="355f2-114">Attributes</span></span>  
 <span data-ttu-id="355f2-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="355f2-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="355f2-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="355f2-116">Child Elements</span></span>  
  
|<span data-ttu-id="355f2-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="355f2-117">Element</span></span>|<span data-ttu-id="355f2-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="355f2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="355f2-119">\<state></span><span class="sxs-lookup"><span data-stu-id="355f2-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="355f2-120">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="355f2-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="355f2-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="355f2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="355f2-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="355f2-122">Element</span></span>|<span data-ttu-id="355f2-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="355f2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="355f2-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="355f2-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="355f2-125">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="355f2-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="355f2-126">Note</span><span class="sxs-lookup"><span data-stu-id="355f2-126">Remarks</span></span>  
 <span data-ttu-id="355f2-127">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="355f2-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="355f2-128">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="355f2-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="355f2-129">Stato</span><span class="sxs-lookup"><span data-stu-id="355f2-129">State</span></span>|<span data-ttu-id="355f2-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="355f2-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="355f2-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="355f2-131">Aborted</span></span>|<span data-ttu-id="355f2-132">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="355f2-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="355f2-133">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="355f2-133">Completed</span></span>|<span data-ttu-id="355f2-134">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="355f2-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="355f2-135">Eliminato</span><span class="sxs-lookup"><span data-stu-id="355f2-135">Deleted</span></span>|<span data-ttu-id="355f2-136">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="355f2-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="355f2-137">Idle</span><span class="sxs-lookup"><span data-stu-id="355f2-137">Idle</span></span>|<span data-ttu-id="355f2-138">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="355f2-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="355f2-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="355f2-139">Persisted</span></span>|<span data-ttu-id="355f2-140">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="355f2-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="355f2-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="355f2-141">Resumed</span></span>|<span data-ttu-id="355f2-142">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="355f2-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="355f2-143">Avviata</span><span class="sxs-lookup"><span data-stu-id="355f2-143">Started</span></span>|<span data-ttu-id="355f2-144">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="355f2-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="355f2-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="355f2-145">UnhandledException</span></span>|<span data-ttu-id="355f2-146">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="355f2-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="355f2-147">Scaricato</span><span class="sxs-lookup"><span data-stu-id="355f2-147">Unloaded</span></span>|<span data-ttu-id="355f2-148">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="355f2-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="355f2-149">Annullato</span><span class="sxs-lookup"><span data-stu-id="355f2-149">Canceled</span></span>|<span data-ttu-id="355f2-150">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="355f2-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="355f2-151">Sospeso</span><span class="sxs-lookup"><span data-stu-id="355f2-151">Suspended</span></span>|<span data-ttu-id="355f2-152">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="355f2-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="355f2-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="355f2-153">Terminated</span></span>|<span data-ttu-id="355f2-154">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="355f2-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="355f2-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="355f2-155">Unsuspended</span></span>|<span data-ttu-id="355f2-156">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="355f2-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="355f2-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="355f2-157">Example</span></span>  
 <span data-ttu-id="355f2-158">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="355f2-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="355f2-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="355f2-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="355f2-160">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="355f2-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="355f2-161">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="355f2-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
