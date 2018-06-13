---
title: '&lt;stati&gt; di WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef3d8d05dad684b07ee527dbd34ae6269ae57657
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749488"
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="781c1-102">&lt;stati&gt; di WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="781c1-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="781c1-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="781c1-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="781c1-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="781c1-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="781c1-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="781c1-105">\<system.serviceModel></span></span>  
<span data-ttu-id="781c1-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="781c1-106">\<tracking></span></span>  
<span data-ttu-id="781c1-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="781c1-107">\<trackingProfile></span></span>  
<span data-ttu-id="781c1-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="781c1-108">\<workflow></span></span>  
<span data-ttu-id="781c1-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="781c1-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="781c1-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="781c1-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="781c1-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="781c1-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="781c1-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="781c1-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="781c1-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="781c1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="781c1-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="781c1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="781c1-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="781c1-115">Attributes</span></span>  
 <span data-ttu-id="781c1-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="781c1-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="781c1-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="781c1-117">Child Elements</span></span>  
  
|<span data-ttu-id="781c1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="781c1-118">Element</span></span>|<span data-ttu-id="781c1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="781c1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="781c1-120">\<stati ></span><span class="sxs-lookup"><span data-stu-id="781c1-120">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="781c1-121">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="781c1-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="781c1-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="781c1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="781c1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="781c1-123">Element</span></span>|<span data-ttu-id="781c1-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="781c1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="781c1-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="781c1-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="781c1-126">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="781c1-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="781c1-127">Note</span><span class="sxs-lookup"><span data-stu-id="781c1-127">Remarks</span></span>  
 <span data-ttu-id="781c1-128">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="781c1-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="781c1-129">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="781c1-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="781c1-130">Stato</span><span class="sxs-lookup"><span data-stu-id="781c1-130">State</span></span>|<span data-ttu-id="781c1-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="781c1-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="781c1-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="781c1-132">Aborted</span></span>|<span data-ttu-id="781c1-133">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="781c1-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="781c1-134">Completata</span><span class="sxs-lookup"><span data-stu-id="781c1-134">Completed</span></span>|<span data-ttu-id="781c1-135">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="781c1-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="781c1-136">Eliminato</span><span class="sxs-lookup"><span data-stu-id="781c1-136">Deleted</span></span>|<span data-ttu-id="781c1-137">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="781c1-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="781c1-138">Idle</span><span class="sxs-lookup"><span data-stu-id="781c1-138">Idle</span></span>|<span data-ttu-id="781c1-139">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="781c1-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="781c1-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="781c1-140">Persisted</span></span>|<span data-ttu-id="781c1-141">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="781c1-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="781c1-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="781c1-142">Resumed</span></span>|<span data-ttu-id="781c1-143">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="781c1-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="781c1-144">Started</span><span class="sxs-lookup"><span data-stu-id="781c1-144">Started</span></span>|<span data-ttu-id="781c1-145">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="781c1-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="781c1-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="781c1-146">UnhandledException</span></span>|<span data-ttu-id="781c1-147">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="781c1-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="781c1-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="781c1-148">Unloaded</span></span>|<span data-ttu-id="781c1-149">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="781c1-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="781c1-150">Annullato</span><span class="sxs-lookup"><span data-stu-id="781c1-150">Canceled</span></span>|<span data-ttu-id="781c1-151">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="781c1-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="781c1-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="781c1-152">Suspended</span></span>|<span data-ttu-id="781c1-153">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="781c1-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="781c1-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="781c1-154">Terminated</span></span>|<span data-ttu-id="781c1-155">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="781c1-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="781c1-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="781c1-156">Unsuspended</span></span>|<span data-ttu-id="781c1-157">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="781c1-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="781c1-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="781c1-158">Example</span></span>  
 <span data-ttu-id="781c1-159">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="781c1-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="781c1-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="781c1-160">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="781c1-161">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="781c1-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="781c1-162">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="781c1-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
