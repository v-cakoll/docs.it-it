---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 9ffe9f9f69f68b6f47cbc3a75200b2867aae2384
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947443"
---
# <a name="state"></a><span data-ttu-id="49c91-101">\<> di stato</span><span class="sxs-lookup"><span data-stu-id="49c91-101">\<state></span></span>
<span data-ttu-id="49c91-102">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="49c91-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="49c91-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="49c91-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="49c91-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="49c91-104">\<system.serviceModel></span></span>  
<span data-ttu-id="49c91-105">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="49c91-105">\<tracking></span></span>  
<span data-ttu-id="49c91-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="49c91-106">\<trackingProfile></span></span>  
<span data-ttu-id="49c91-107">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="49c91-107">\<workflow></span></span>  
<span data-ttu-id="49c91-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="49c91-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="49c91-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="49c91-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="49c91-110">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="49c91-110">\<states></span></span>  
<span data-ttu-id="49c91-111">\<> di stato</span><span class="sxs-lookup"><span data-stu-id="49c91-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49c91-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49c91-112">Syntax</span></span>  
  
```xml  
<tracking>
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
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49c91-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="49c91-113">Attributes and Elements</span></span>  
 <span data-ttu-id="49c91-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="49c91-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49c91-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="49c91-115">Attributes</span></span>  
  
|<span data-ttu-id="49c91-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="49c91-116">Attribute</span></span>|<span data-ttu-id="49c91-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49c91-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49c91-118">name</span><span class="sxs-lookup"><span data-stu-id="49c91-118">name</span></span>|<span data-ttu-id="49c91-119">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="49c91-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49c91-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="49c91-120">Child Elements</span></span>  
 <span data-ttu-id="49c91-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="49c91-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49c91-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="49c91-122">Parent Elements</span></span>  
  
|<span data-ttu-id="49c91-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="49c91-123">Element</span></span>|<span data-ttu-id="49c91-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="49c91-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49c91-125">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="49c91-125">\<states></span></span>](states.md)|<span data-ttu-id="49c91-126">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="49c91-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49c91-127">Note</span><span class="sxs-lookup"><span data-stu-id="49c91-127">Remarks</span></span>  
 <span data-ttu-id="49c91-128">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="49c91-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="49c91-129">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="49c91-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="49c91-130">Stato</span><span class="sxs-lookup"><span data-stu-id="49c91-130">State</span></span>|<span data-ttu-id="49c91-131">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="49c91-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="49c91-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="49c91-132">Aborted</span></span>|<span data-ttu-id="49c91-133">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="49c91-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="49c91-134">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="49c91-134">Completed</span></span>|<span data-ttu-id="49c91-135">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="49c91-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="49c91-136">Eliminato</span><span class="sxs-lookup"><span data-stu-id="49c91-136">Deleted</span></span>|<span data-ttu-id="49c91-137">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="49c91-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="49c91-138">Idle</span><span class="sxs-lookup"><span data-stu-id="49c91-138">Idle</span></span>|<span data-ttu-id="49c91-139">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="49c91-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="49c91-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="49c91-140">Persisted</span></span>|<span data-ttu-id="49c91-141">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="49c91-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="49c91-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="49c91-142">Resumed</span></span>|<span data-ttu-id="49c91-143">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="49c91-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="49c91-144">Started</span><span class="sxs-lookup"><span data-stu-id="49c91-144">Started</span></span>|<span data-ttu-id="49c91-145">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="49c91-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="49c91-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="49c91-146">UnhandledException</span></span>|<span data-ttu-id="49c91-147">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="49c91-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="49c91-148">Scaricato</span><span class="sxs-lookup"><span data-stu-id="49c91-148">Unloaded</span></span>|<span data-ttu-id="49c91-149">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="49c91-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="49c91-150">Annullato</span><span class="sxs-lookup"><span data-stu-id="49c91-150">Canceled</span></span>|<span data-ttu-id="49c91-151">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="49c91-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="49c91-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="49c91-152">Suspended</span></span>|<span data-ttu-id="49c91-153">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="49c91-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="49c91-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="49c91-154">Terminated</span></span>|<span data-ttu-id="49c91-155">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="49c91-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="49c91-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="49c91-156">Unsuspended</span></span>|<span data-ttu-id="49c91-157">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="49c91-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49c91-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="49c91-158">Example</span></span>  
 <span data-ttu-id="49c91-159">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="49c91-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="49c91-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49c91-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="49c91-161">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="49c91-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="49c91-162">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="49c91-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
