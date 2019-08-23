---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: fd0b57d7d08cf77ba7792e079b7abd2ff8f2839e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947400"
---
# <a name="states"></a><span data-ttu-id="b6279-101">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="b6279-101">\<states></span></span>
<span data-ttu-id="b6279-102">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b6279-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="b6279-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b6279-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b6279-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6279-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b6279-105">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="b6279-105">\<tracking></span></span>  
<span data-ttu-id="b6279-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b6279-106">\<trackingProfile></span></span>  
<span data-ttu-id="b6279-107">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b6279-107">\<workflow></span></span>  
<span data-ttu-id="b6279-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b6279-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="b6279-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="b6279-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="b6279-110">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="b6279-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6279-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6279-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6279-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6279-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b6279-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6279-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6279-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6279-114">Attributes</span></span>  
 <span data-ttu-id="b6279-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b6279-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6279-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6279-116">Child Elements</span></span>  
  
|<span data-ttu-id="b6279-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6279-117">Element</span></span>|<span data-ttu-id="b6279-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b6279-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6279-119">\<state></span><span class="sxs-lookup"><span data-stu-id="b6279-119">\<state></span></span>](states.md)|<span data-ttu-id="b6279-120">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="b6279-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6279-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6279-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b6279-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6279-122">Element</span></span>|<span data-ttu-id="b6279-123">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b6279-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6279-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="b6279-124">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="b6279-125">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="b6279-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6279-126">Note</span><span class="sxs-lookup"><span data-stu-id="b6279-126">Remarks</span></span>  
 <span data-ttu-id="b6279-127">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="b6279-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="b6279-128">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6279-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="b6279-129">Stato</span><span class="sxs-lookup"><span data-stu-id="b6279-129">State</span></span>|<span data-ttu-id="b6279-130">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b6279-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6279-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="b6279-131">Aborted</span></span>|<span data-ttu-id="b6279-132">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="b6279-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="b6279-133">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="b6279-133">Completed</span></span>|<span data-ttu-id="b6279-134">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="b6279-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="b6279-135">Eliminato</span><span class="sxs-lookup"><span data-stu-id="b6279-135">Deleted</span></span>|<span data-ttu-id="b6279-136">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="b6279-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="b6279-137">Idle</span><span class="sxs-lookup"><span data-stu-id="b6279-137">Idle</span></span>|<span data-ttu-id="b6279-138">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="b6279-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="b6279-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="b6279-139">Persisted</span></span>|<span data-ttu-id="b6279-140">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="b6279-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="b6279-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="b6279-141">Resumed</span></span>|<span data-ttu-id="b6279-142">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="b6279-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="b6279-143">Started</span><span class="sxs-lookup"><span data-stu-id="b6279-143">Started</span></span>|<span data-ttu-id="b6279-144">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="b6279-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="b6279-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="b6279-145">UnhandledException</span></span>|<span data-ttu-id="b6279-146">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="b6279-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="b6279-147">Scaricato</span><span class="sxs-lookup"><span data-stu-id="b6279-147">Unloaded</span></span>|<span data-ttu-id="b6279-148">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="b6279-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="b6279-149">Annullato</span><span class="sxs-lookup"><span data-stu-id="b6279-149">Canceled</span></span>|<span data-ttu-id="b6279-150">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="b6279-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="b6279-151">Suspended</span><span class="sxs-lookup"><span data-stu-id="b6279-151">Suspended</span></span>|<span data-ttu-id="b6279-152">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="b6279-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="b6279-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="b6279-153">Terminated</span></span>|<span data-ttu-id="b6279-154">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="b6279-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="b6279-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="b6279-155">Unsuspended</span></span>|<span data-ttu-id="b6279-156">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="b6279-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b6279-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6279-157">Example</span></span>  
 <span data-ttu-id="b6279-158">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="b6279-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6279-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6279-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b6279-160">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b6279-160">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b6279-161">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b6279-161">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
