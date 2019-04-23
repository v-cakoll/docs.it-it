---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073122"
---
# <a name="states"></a><span data-ttu-id="4fa17-101">\<states></span><span class="sxs-lookup"><span data-stu-id="4fa17-101">\<states></span></span>
<span data-ttu-id="4fa17-102">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="4fa17-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="4fa17-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4fa17-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4fa17-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4fa17-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4fa17-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4fa17-105">\<tracking></span></span>  
<span data-ttu-id="4fa17-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4fa17-106">\<trackingProfile></span></span>  
<span data-ttu-id="4fa17-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="4fa17-107">\<workflow></span></span>  
<span data-ttu-id="4fa17-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="4fa17-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="4fa17-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="4fa17-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="4fa17-110">\<states></span><span class="sxs-lookup"><span data-stu-id="4fa17-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fa17-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fa17-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fa17-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4fa17-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4fa17-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4fa17-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fa17-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="4fa17-114">Attributes</span></span>  
 <span data-ttu-id="4fa17-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4fa17-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fa17-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4fa17-116">Child Elements</span></span>  
  
|<span data-ttu-id="4fa17-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fa17-117">Element</span></span>|<span data-ttu-id="4fa17-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fa17-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fa17-119">\<state></span><span class="sxs-lookup"><span data-stu-id="4fa17-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="4fa17-120">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="4fa17-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fa17-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4fa17-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4fa17-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fa17-122">Element</span></span>|<span data-ttu-id="4fa17-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fa17-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fa17-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="4fa17-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="4fa17-125">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="4fa17-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fa17-126">Note</span><span class="sxs-lookup"><span data-stu-id="4fa17-126">Remarks</span></span>  
 <span data-ttu-id="4fa17-127">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="4fa17-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="4fa17-128">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4fa17-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="4fa17-129">Stato</span><span class="sxs-lookup"><span data-stu-id="4fa17-129">State</span></span>|<span data-ttu-id="4fa17-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fa17-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4fa17-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="4fa17-131">Aborted</span></span>|<span data-ttu-id="4fa17-132">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="4fa17-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="4fa17-133">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="4fa17-133">Completed</span></span>|<span data-ttu-id="4fa17-134">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="4fa17-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="4fa17-135">Eliminato</span><span class="sxs-lookup"><span data-stu-id="4fa17-135">Deleted</span></span>|<span data-ttu-id="4fa17-136">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="4fa17-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="4fa17-137">Idle</span><span class="sxs-lookup"><span data-stu-id="4fa17-137">Idle</span></span>|<span data-ttu-id="4fa17-138">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="4fa17-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="4fa17-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="4fa17-139">Persisted</span></span>|<span data-ttu-id="4fa17-140">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="4fa17-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="4fa17-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="4fa17-141">Resumed</span></span>|<span data-ttu-id="4fa17-142">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="4fa17-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="4fa17-143">Avviata</span><span class="sxs-lookup"><span data-stu-id="4fa17-143">Started</span></span>|<span data-ttu-id="4fa17-144">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="4fa17-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="4fa17-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="4fa17-145">UnhandledException</span></span>|<span data-ttu-id="4fa17-146">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="4fa17-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="4fa17-147">Scaricato</span><span class="sxs-lookup"><span data-stu-id="4fa17-147">Unloaded</span></span>|<span data-ttu-id="4fa17-148">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="4fa17-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="4fa17-149">Annullato</span><span class="sxs-lookup"><span data-stu-id="4fa17-149">Canceled</span></span>|<span data-ttu-id="4fa17-150">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="4fa17-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="4fa17-151">Sospeso</span><span class="sxs-lookup"><span data-stu-id="4fa17-151">Suspended</span></span>|<span data-ttu-id="4fa17-152">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="4fa17-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="4fa17-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="4fa17-153">Terminated</span></span>|<span data-ttu-id="4fa17-154">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="4fa17-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="4fa17-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="4fa17-155">Unsuspended</span></span>|<span data-ttu-id="4fa17-156">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="4fa17-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4fa17-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="4fa17-157">Example</span></span>  
 <span data-ttu-id="4fa17-158">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="4fa17-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fa17-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fa17-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4fa17-160">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4fa17-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4fa17-161">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4fa17-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
