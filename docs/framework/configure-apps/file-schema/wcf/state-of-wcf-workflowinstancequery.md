---
title: '&lt;stato&gt; di WCF, &lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d6edb83370f36b73955ab9d619c8b956f36a007e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="dfdfa-102">&lt;stato&gt; di WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="dfdfa-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="dfdfa-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="dfdfa-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="dfdfa-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="dfdfa-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-105">\<system.serviceModel></span></span>  
<span data-ttu-id="dfdfa-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-106">\<tracking></span></span>  
<span data-ttu-id="dfdfa-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-107">\<trackingProfile></span></span>  
<span data-ttu-id="dfdfa-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-108">\<workflow></span></span>  
<span data-ttu-id="dfdfa-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="dfdfa-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="dfdfa-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-111">\<states></span></span>  
<span data-ttu-id="dfdfa-112">\<stato ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfdfa-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfdfa-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfdfa-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dfdfa-114">Attributes and Elements</span></span>  
 <span data-ttu-id="dfdfa-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfdfa-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="dfdfa-116">Attributes</span></span>  
  
|<span data-ttu-id="dfdfa-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="dfdfa-117">Attribute</span></span>|<span data-ttu-id="dfdfa-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfdfa-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfdfa-119">name</span><span class="sxs-lookup"><span data-stu-id="dfdfa-119">name</span></span>|<span data-ttu-id="dfdfa-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfdfa-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dfdfa-121">Child Elements</span></span>  
 <span data-ttu-id="dfdfa-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfdfa-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dfdfa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dfdfa-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfdfa-124">Element</span></span>|<span data-ttu-id="dfdfa-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfdfa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfdfa-126">\<stati ></span><span class="sxs-lookup"><span data-stu-id="dfdfa-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="dfdfa-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfdfa-128">Note</span><span class="sxs-lookup"><span data-stu-id="dfdfa-128">Remarks</span></span>  
 <span data-ttu-id="dfdfa-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="dfdfa-130">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="dfdfa-131">Stato</span><span class="sxs-lookup"><span data-stu-id="dfdfa-131">State</span></span>|<span data-ttu-id="dfdfa-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfdfa-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dfdfa-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="dfdfa-133">Aborted</span></span>|<span data-ttu-id="dfdfa-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="dfdfa-135">Completata</span><span class="sxs-lookup"><span data-stu-id="dfdfa-135">Completed</span></span>|<span data-ttu-id="dfdfa-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="dfdfa-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="dfdfa-137">Deleted</span></span>|<span data-ttu-id="dfdfa-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="dfdfa-139">Idle</span><span class="sxs-lookup"><span data-stu-id="dfdfa-139">Idle</span></span>|<span data-ttu-id="dfdfa-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="dfdfa-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="dfdfa-141">Persisted</span></span>|<span data-ttu-id="dfdfa-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="dfdfa-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="dfdfa-143">Resumed</span></span>|<span data-ttu-id="dfdfa-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="dfdfa-145">Started</span><span class="sxs-lookup"><span data-stu-id="dfdfa-145">Started</span></span>|<span data-ttu-id="dfdfa-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="dfdfa-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="dfdfa-147">UnhandledException</span></span>|<span data-ttu-id="dfdfa-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="dfdfa-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="dfdfa-149">Unloaded</span></span>|<span data-ttu-id="dfdfa-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="dfdfa-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="dfdfa-151">Canceled</span></span>|<span data-ttu-id="dfdfa-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="dfdfa-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="dfdfa-153">Suspended</span></span>|<span data-ttu-id="dfdfa-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="dfdfa-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="dfdfa-155">Terminated</span></span>|<span data-ttu-id="dfdfa-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="dfdfa-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="dfdfa-157">Unsuspended</span></span>|<span data-ttu-id="dfdfa-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dfdfa-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfdfa-159">Example</span></span>  
 <span data-ttu-id="dfdfa-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfdfa-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfdfa-161">See Also</span></span>  
 <span data-ttu-id="dfdfa-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dfdfa-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dfdfa-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dfdfa-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dfdfa-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dfdfa-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="dfdfa-165">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dfdfa-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dfdfa-166">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dfdfa-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
