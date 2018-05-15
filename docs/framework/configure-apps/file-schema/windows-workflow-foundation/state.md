---
title: '&lt;state&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 327a5e98a9ecf6ba23eaf47c3d6d73bfb7852ee7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltstategt"></a><span data-ttu-id="b87e7-102">&lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="b87e7-102">&lt;state&gt;</span></span>
<span data-ttu-id="b87e7-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b87e7-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="b87e7-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b87e7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b87e7-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b87e7-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b87e7-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="b87e7-106">\<tracking></span></span>  
<span data-ttu-id="b87e7-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b87e7-107">\<trackingProfile></span></span>  
<span data-ttu-id="b87e7-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="b87e7-108">\<workflow></span></span>  
<span data-ttu-id="b87e7-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="b87e7-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="b87e7-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="b87e7-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="b87e7-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="b87e7-111">\<states></span></span>  
<span data-ttu-id="b87e7-112">\<stato ></span><span class="sxs-lookup"><span data-stu-id="b87e7-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b87e7-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b87e7-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b87e7-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b87e7-114">Attributes and Elements</span></span>  
 <span data-ttu-id="b87e7-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b87e7-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b87e7-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="b87e7-116">Attributes</span></span>  
  
|<span data-ttu-id="b87e7-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="b87e7-117">Attribute</span></span>|<span data-ttu-id="b87e7-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b87e7-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b87e7-119">name</span><span class="sxs-lookup"><span data-stu-id="b87e7-119">name</span></span>|<span data-ttu-id="b87e7-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b87e7-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b87e7-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b87e7-121">Child Elements</span></span>  
 <span data-ttu-id="b87e7-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b87e7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b87e7-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b87e7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b87e7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b87e7-124">Element</span></span>|<span data-ttu-id="b87e7-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b87e7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b87e7-126">\<stati ></span><span class="sxs-lookup"><span data-stu-id="b87e7-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="b87e7-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b87e7-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b87e7-128">Note</span><span class="sxs-lookup"><span data-stu-id="b87e7-128">Remarks</span></span>  
 <span data-ttu-id="b87e7-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="b87e7-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="b87e7-130">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b87e7-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="b87e7-131">Stato</span><span class="sxs-lookup"><span data-stu-id="b87e7-131">State</span></span>|<span data-ttu-id="b87e7-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b87e7-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b87e7-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="b87e7-133">Aborted</span></span>|<span data-ttu-id="b87e7-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="b87e7-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="b87e7-135">Completata</span><span class="sxs-lookup"><span data-stu-id="b87e7-135">Completed</span></span>|<span data-ttu-id="b87e7-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="b87e7-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="b87e7-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="b87e7-137">Deleted</span></span>|<span data-ttu-id="b87e7-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="b87e7-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="b87e7-139">Idle</span><span class="sxs-lookup"><span data-stu-id="b87e7-139">Idle</span></span>|<span data-ttu-id="b87e7-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="b87e7-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="b87e7-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="b87e7-141">Persisted</span></span>|<span data-ttu-id="b87e7-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="b87e7-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="b87e7-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="b87e7-143">Resumed</span></span>|<span data-ttu-id="b87e7-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="b87e7-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="b87e7-145">Started</span><span class="sxs-lookup"><span data-stu-id="b87e7-145">Started</span></span>|<span data-ttu-id="b87e7-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="b87e7-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="b87e7-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="b87e7-147">UnhandledException</span></span>|<span data-ttu-id="b87e7-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="b87e7-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="b87e7-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="b87e7-149">Unloaded</span></span>|<span data-ttu-id="b87e7-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="b87e7-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="b87e7-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="b87e7-151">Canceled</span></span>|<span data-ttu-id="b87e7-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="b87e7-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="b87e7-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="b87e7-153">Suspended</span></span>|<span data-ttu-id="b87e7-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="b87e7-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="b87e7-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="b87e7-155">Terminated</span></span>|<span data-ttu-id="b87e7-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="b87e7-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="b87e7-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="b87e7-157">Unsuspended</span></span>|<span data-ttu-id="b87e7-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="b87e7-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b87e7-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="b87e7-159">Example</span></span>  
 <span data-ttu-id="b87e7-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="b87e7-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b87e7-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b87e7-161">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>      
 [<span data-ttu-id="b87e7-162">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b87e7-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b87e7-163">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b87e7-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
