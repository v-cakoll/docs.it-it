---
title: '&lt;state&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7164bf15efc82f36a674f72652e6a1a5df09df1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltstategt"></a><span data-ttu-id="bc297-102">&lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="bc297-102">&lt;state&gt;</span></span>
<span data-ttu-id="bc297-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="bc297-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="bc297-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bc297-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bc297-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bc297-105">\<system.serviceModel></span></span>  
<span data-ttu-id="bc297-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="bc297-106">\<tracking></span></span>  
<span data-ttu-id="bc297-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="bc297-107">\<trackingProfile></span></span>  
<span data-ttu-id="bc297-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="bc297-108">\<workflow></span></span>  
<span data-ttu-id="bc297-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="bc297-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="bc297-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="bc297-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="bc297-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="bc297-111">\<states></span></span>  
<span data-ttu-id="bc297-112">\<stato ></span><span class="sxs-lookup"><span data-stu-id="bc297-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc297-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc297-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc297-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bc297-114">Attributes and Elements</span></span>  
 <span data-ttu-id="bc297-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bc297-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc297-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="bc297-116">Attributes</span></span>  
  
|<span data-ttu-id="bc297-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="bc297-117">Attribute</span></span>|<span data-ttu-id="bc297-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc297-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bc297-119">name</span><span class="sxs-lookup"><span data-stu-id="bc297-119">name</span></span>|<span data-ttu-id="bc297-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="bc297-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc297-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bc297-121">Child Elements</span></span>  
 <span data-ttu-id="bc297-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bc297-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc297-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bc297-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bc297-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc297-124">Element</span></span>|<span data-ttu-id="bc297-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc297-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc297-126">\<stati ></span><span class="sxs-lookup"><span data-stu-id="bc297-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="bc297-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="bc297-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc297-128">Note</span><span class="sxs-lookup"><span data-stu-id="bc297-128">Remarks</span></span>  
 <span data-ttu-id="bc297-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="bc297-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="bc297-130">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bc297-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="bc297-131">Stato</span><span class="sxs-lookup"><span data-stu-id="bc297-131">State</span></span>|<span data-ttu-id="bc297-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc297-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc297-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="bc297-133">Aborted</span></span>|<span data-ttu-id="bc297-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="bc297-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="bc297-135">Completata</span><span class="sxs-lookup"><span data-stu-id="bc297-135">Completed</span></span>|<span data-ttu-id="bc297-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="bc297-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="bc297-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="bc297-137">Deleted</span></span>|<span data-ttu-id="bc297-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="bc297-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="bc297-139">Idle</span><span class="sxs-lookup"><span data-stu-id="bc297-139">Idle</span></span>|<span data-ttu-id="bc297-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="bc297-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="bc297-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="bc297-141">Persisted</span></span>|<span data-ttu-id="bc297-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="bc297-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="bc297-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="bc297-143">Resumed</span></span>|<span data-ttu-id="bc297-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="bc297-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="bc297-145">Started</span><span class="sxs-lookup"><span data-stu-id="bc297-145">Started</span></span>|<span data-ttu-id="bc297-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="bc297-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="bc297-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="bc297-147">UnhandledException</span></span>|<span data-ttu-id="bc297-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="bc297-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="bc297-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="bc297-149">Unloaded</span></span>|<span data-ttu-id="bc297-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="bc297-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="bc297-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="bc297-151">Canceled</span></span>|<span data-ttu-id="bc297-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="bc297-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="bc297-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="bc297-153">Suspended</span></span>|<span data-ttu-id="bc297-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="bc297-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="bc297-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="bc297-155">Terminated</span></span>|<span data-ttu-id="bc297-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="bc297-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="bc297-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="bc297-157">Unsuspended</span></span>|<span data-ttu-id="bc297-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="bc297-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bc297-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc297-159">Example</span></span>  
 <span data-ttu-id="bc297-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="bc297-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc297-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc297-161">See Also</span></span>  
 <span data-ttu-id="bc297-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bc297-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="bc297-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bc297-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="bc297-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bc297-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>      
 [<span data-ttu-id="bc297-165">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="bc297-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="bc297-166">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="bc297-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
