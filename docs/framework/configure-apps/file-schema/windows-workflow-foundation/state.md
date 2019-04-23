---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 6f1a9474f3f12005df364a6fb84dc63aa1b68e04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108172"
---
# <a name="state"></a><span data-ttu-id="e9bfd-101">\<state></span><span class="sxs-lookup"><span data-stu-id="e9bfd-101">\<state></span></span>
<span data-ttu-id="e9bfd-102">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="e9bfd-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e9bfd-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e9bfd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e9bfd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e9bfd-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e9bfd-105">\<tracking></span></span>  
<span data-ttu-id="e9bfd-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e9bfd-106">\<trackingProfile></span></span>  
<span data-ttu-id="e9bfd-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e9bfd-107">\<workflow></span></span>  
<span data-ttu-id="e9bfd-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="e9bfd-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="e9bfd-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="e9bfd-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="e9bfd-110">\<states></span><span class="sxs-lookup"><span data-stu-id="e9bfd-110">\<states></span></span>  
<span data-ttu-id="e9bfd-111">\<state></span><span class="sxs-lookup"><span data-stu-id="e9bfd-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9bfd-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9bfd-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9bfd-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9bfd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e9bfd-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9bfd-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9bfd-115">Attributes</span></span>  
  
|<span data-ttu-id="e9bfd-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="e9bfd-116">Attribute</span></span>|<span data-ttu-id="e9bfd-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9bfd-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9bfd-118">name</span><span class="sxs-lookup"><span data-stu-id="e9bfd-118">name</span></span>|<span data-ttu-id="e9bfd-119">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9bfd-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9bfd-120">Child Elements</span></span>  
 <span data-ttu-id="e9bfd-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9bfd-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9bfd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e9bfd-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9bfd-123">Element</span></span>|<span data-ttu-id="e9bfd-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9bfd-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9bfd-125">\<states></span><span class="sxs-lookup"><span data-stu-id="e9bfd-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="e9bfd-126">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9bfd-127">Note</span><span class="sxs-lookup"><span data-stu-id="e9bfd-127">Remarks</span></span>  
 <span data-ttu-id="e9bfd-128">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="e9bfd-129">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="e9bfd-130">Stato</span><span class="sxs-lookup"><span data-stu-id="e9bfd-130">State</span></span>|<span data-ttu-id="e9bfd-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9bfd-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e9bfd-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="e9bfd-132">Aborted</span></span>|<span data-ttu-id="e9bfd-133">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e9bfd-134">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="e9bfd-134">Completed</span></span>|<span data-ttu-id="e9bfd-135">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="e9bfd-136">Eliminato</span><span class="sxs-lookup"><span data-stu-id="e9bfd-136">Deleted</span></span>|<span data-ttu-id="e9bfd-137">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="e9bfd-138">Idle</span><span class="sxs-lookup"><span data-stu-id="e9bfd-138">Idle</span></span>|<span data-ttu-id="e9bfd-139">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="e9bfd-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="e9bfd-140">Persisted</span></span>|<span data-ttu-id="e9bfd-141">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="e9bfd-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="e9bfd-142">Resumed</span></span>|<span data-ttu-id="e9bfd-143">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="e9bfd-144">Avviata</span><span class="sxs-lookup"><span data-stu-id="e9bfd-144">Started</span></span>|<span data-ttu-id="e9bfd-145">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="e9bfd-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="e9bfd-146">UnhandledException</span></span>|<span data-ttu-id="e9bfd-147">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="e9bfd-148">Scaricato</span><span class="sxs-lookup"><span data-stu-id="e9bfd-148">Unloaded</span></span>|<span data-ttu-id="e9bfd-149">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="e9bfd-150">Annullato</span><span class="sxs-lookup"><span data-stu-id="e9bfd-150">Canceled</span></span>|<span data-ttu-id="e9bfd-151">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="e9bfd-152">Sospeso</span><span class="sxs-lookup"><span data-stu-id="e9bfd-152">Suspended</span></span>|<span data-ttu-id="e9bfd-153">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="e9bfd-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="e9bfd-154">Terminated</span></span>|<span data-ttu-id="e9bfd-155">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="e9bfd-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="e9bfd-156">Unsuspended</span></span>|<span data-ttu-id="e9bfd-157">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e9bfd-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9bfd-158">Example</span></span>  
 <span data-ttu-id="e9bfd-159">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="e9bfd-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9bfd-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9bfd-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e9bfd-161">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e9bfd-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e9bfd-162">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e9bfd-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
