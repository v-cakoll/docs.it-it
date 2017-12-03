---
title: '&lt;Stati&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5e9050a01cf58c3c103fdbe4e8b22e173efaf5c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt"></a><span data-ttu-id="2e772-102">&lt;Stati&gt;</span><span class="sxs-lookup"><span data-stu-id="2e772-102">&lt;states&gt;</span></span>
<span data-ttu-id="2e772-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2e772-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="2e772-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2e772-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2e772-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2e772-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2e772-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="2e772-106">\<tracking></span></span>  
<span data-ttu-id="2e772-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2e772-107">\<trackingProfile></span></span>  
<span data-ttu-id="2e772-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="2e772-108">\<workflow></span></span>  
<span data-ttu-id="2e772-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="2e772-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="2e772-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="2e772-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="2e772-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="2e772-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e772-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e772-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e772-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2e772-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2e772-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2e772-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e772-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="2e772-115">Attributes</span></span>  
 <span data-ttu-id="2e772-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2e772-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2e772-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2e772-117">Child Elements</span></span>  
  
|<span data-ttu-id="2e772-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e772-118">Element</span></span>|<span data-ttu-id="2e772-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e772-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e772-120">\<stato ></span><span class="sxs-lookup"><span data-stu-id="2e772-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2e772-121">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="2e772-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e772-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2e772-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2e772-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e772-123">Element</span></span>|<span data-ttu-id="2e772-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e772-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e772-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="2e772-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="2e772-126">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="2e772-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e772-127">Note</span><span class="sxs-lookup"><span data-stu-id="2e772-127">Remarks</span></span>  
 <span data-ttu-id="2e772-128">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="2e772-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="2e772-129">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2e772-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="2e772-130">Stato</span><span class="sxs-lookup"><span data-stu-id="2e772-130">State</span></span>|<span data-ttu-id="2e772-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e772-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e772-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="2e772-132">Aborted</span></span>|<span data-ttu-id="2e772-133">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="2e772-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2e772-134">Completata</span><span class="sxs-lookup"><span data-stu-id="2e772-134">Completed</span></span>|<span data-ttu-id="2e772-135">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="2e772-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="2e772-136">Eliminato</span><span class="sxs-lookup"><span data-stu-id="2e772-136">Deleted</span></span>|<span data-ttu-id="2e772-137">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="2e772-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="2e772-138">Idle</span><span class="sxs-lookup"><span data-stu-id="2e772-138">Idle</span></span>|<span data-ttu-id="2e772-139">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="2e772-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="2e772-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="2e772-140">Persisted</span></span>|<span data-ttu-id="2e772-141">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="2e772-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="2e772-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="2e772-142">Resumed</span></span>|<span data-ttu-id="2e772-143">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="2e772-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="2e772-144">Started</span><span class="sxs-lookup"><span data-stu-id="2e772-144">Started</span></span>|<span data-ttu-id="2e772-145">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="2e772-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="2e772-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="2e772-146">UnhandledException</span></span>|<span data-ttu-id="2e772-147">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="2e772-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="2e772-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="2e772-148">Unloaded</span></span>|<span data-ttu-id="2e772-149">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="2e772-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="2e772-150">Annullato</span><span class="sxs-lookup"><span data-stu-id="2e772-150">Canceled</span></span>|<span data-ttu-id="2e772-151">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="2e772-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="2e772-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="2e772-152">Suspended</span></span>|<span data-ttu-id="2e772-153">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="2e772-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="2e772-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="2e772-154">Terminated</span></span>|<span data-ttu-id="2e772-155">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="2e772-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="2e772-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="2e772-156">Unsuspended</span></span>|<span data-ttu-id="2e772-157">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="2e772-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2e772-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e772-158">Example</span></span>  
 <span data-ttu-id="2e772-159">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="2e772-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e772-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e772-160">See Also</span></span>  
 <span data-ttu-id="2e772-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2e772-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="2e772-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2e772-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="2e772-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2e772-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="2e772-164">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2e772-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2e772-165">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2e772-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
