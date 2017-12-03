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
ms.openlocfilehash: 3f1ed21f359e9f0e2b07154bc37d3352dd52db12
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltstategt"></a><span data-ttu-id="dee81-102">&lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="dee81-102">&lt;state&gt;</span></span>
<span data-ttu-id="dee81-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dee81-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="dee81-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="dee81-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="dee81-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dee81-105">\<system.serviceModel></span></span>  
<span data-ttu-id="dee81-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dee81-106">\<tracking></span></span>  
<span data-ttu-id="dee81-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dee81-107">\<trackingProfile></span></span>  
<span data-ttu-id="dee81-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="dee81-108">\<workflow></span></span>  
<span data-ttu-id="dee81-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="dee81-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="dee81-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="dee81-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="dee81-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="dee81-111">\<states></span></span>  
<span data-ttu-id="dee81-112">\<stato ></span><span class="sxs-lookup"><span data-stu-id="dee81-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dee81-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dee81-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dee81-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dee81-114">Attributes and Elements</span></span>  
 <span data-ttu-id="dee81-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dee81-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dee81-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="dee81-116">Attributes</span></span>  
  
|<span data-ttu-id="dee81-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="dee81-117">Attribute</span></span>|<span data-ttu-id="dee81-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dee81-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dee81-119">name</span><span class="sxs-lookup"><span data-stu-id="dee81-119">name</span></span>|<span data-ttu-id="dee81-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dee81-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dee81-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dee81-121">Child Elements</span></span>  
 <span data-ttu-id="dee81-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dee81-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dee81-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dee81-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dee81-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="dee81-124">Element</span></span>|<span data-ttu-id="dee81-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dee81-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dee81-126">\<stati ></span><span class="sxs-lookup"><span data-stu-id="dee81-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="dee81-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dee81-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dee81-128">Note</span><span class="sxs-lookup"><span data-stu-id="dee81-128">Remarks</span></span>  
 <span data-ttu-id="dee81-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="dee81-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="dee81-130">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="dee81-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="dee81-131">Stato</span><span class="sxs-lookup"><span data-stu-id="dee81-131">State</span></span>|<span data-ttu-id="dee81-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dee81-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dee81-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="dee81-133">Aborted</span></span>|<span data-ttu-id="dee81-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="dee81-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="dee81-135">Completata</span><span class="sxs-lookup"><span data-stu-id="dee81-135">Completed</span></span>|<span data-ttu-id="dee81-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="dee81-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="dee81-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="dee81-137">Deleted</span></span>|<span data-ttu-id="dee81-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="dee81-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="dee81-139">Idle</span><span class="sxs-lookup"><span data-stu-id="dee81-139">Idle</span></span>|<span data-ttu-id="dee81-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="dee81-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="dee81-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="dee81-141">Persisted</span></span>|<span data-ttu-id="dee81-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="dee81-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="dee81-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="dee81-143">Resumed</span></span>|<span data-ttu-id="dee81-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="dee81-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="dee81-145">Started</span><span class="sxs-lookup"><span data-stu-id="dee81-145">Started</span></span>|<span data-ttu-id="dee81-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="dee81-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="dee81-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="dee81-147">UnhandledException</span></span>|<span data-ttu-id="dee81-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="dee81-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="dee81-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="dee81-149">Unloaded</span></span>|<span data-ttu-id="dee81-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="dee81-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="dee81-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="dee81-151">Canceled</span></span>|<span data-ttu-id="dee81-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="dee81-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="dee81-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="dee81-153">Suspended</span></span>|<span data-ttu-id="dee81-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="dee81-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="dee81-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="dee81-155">Terminated</span></span>|<span data-ttu-id="dee81-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="dee81-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="dee81-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="dee81-157">Unsuspended</span></span>|<span data-ttu-id="dee81-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="dee81-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dee81-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="dee81-159">Example</span></span>  
 <span data-ttu-id="dee81-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="dee81-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dee81-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dee81-161">See Also</span></span>  
 <span data-ttu-id="dee81-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dee81-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dee81-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dee81-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dee81-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dee81-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>      
 [<span data-ttu-id="dee81-165">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dee81-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dee81-166">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dee81-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
