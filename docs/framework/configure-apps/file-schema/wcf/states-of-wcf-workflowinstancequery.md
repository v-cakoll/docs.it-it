---
title: <states>di WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855031"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="c05d0-102">\<Stati > di WCF, \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="c05d0-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="c05d0-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="c05d0-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="c05d0-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c05d0-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c05d0-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c05d0-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="c05d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="c05d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="c05d0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="c05d0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="c05d0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="c05d0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c05d0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="c05d0-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Stati >**</span><span class="sxs-lookup"><span data-stu-id="c05d0-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c05d0-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c05d0-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c05d0-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c05d0-115">Attributes and elements</span></span>

<span data-ttu-id="c05d0-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c05d0-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c05d0-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="c05d0-117">Attributes</span></span>  

<span data-ttu-id="c05d0-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c05d0-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c05d0-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c05d0-119">Child elements</span></span>
  
|<span data-ttu-id="c05d0-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c05d0-120">Element</span></span>|<span data-ttu-id="c05d0-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c05d0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c05d0-122">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="c05d0-122">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="c05d0-123">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="c05d0-123">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c05d0-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c05d0-124">Parent elements</span></span>  
  
|<span data-ttu-id="c05d0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="c05d0-125">Element</span></span>|<span data-ttu-id="c05d0-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c05d0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c05d0-127">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c05d0-127">\<workflowInstanceQuery></span></span>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="c05d0-128">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="c05d0-128">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c05d0-129">Note</span><span class="sxs-lookup"><span data-stu-id="c05d0-129">Remarks</span></span>

<span data-ttu-id="c05d0-130">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="c05d0-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="c05d0-131">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c05d0-131">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="c05d0-132">Stato</span><span class="sxs-lookup"><span data-stu-id="c05d0-132">State</span></span>|<span data-ttu-id="c05d0-133">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c05d0-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c05d0-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="c05d0-134">Aborted</span></span>|<span data-ttu-id="c05d0-135">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="c05d0-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c05d0-136">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="c05d0-136">Completed</span></span>|<span data-ttu-id="c05d0-137">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="c05d0-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="c05d0-138">Eliminato</span><span class="sxs-lookup"><span data-stu-id="c05d0-138">Deleted</span></span>|<span data-ttu-id="c05d0-139">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="c05d0-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="c05d0-140">Idle</span><span class="sxs-lookup"><span data-stu-id="c05d0-140">Idle</span></span>|<span data-ttu-id="c05d0-141">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="c05d0-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="c05d0-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="c05d0-142">Persisted</span></span>|<span data-ttu-id="c05d0-143">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="c05d0-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="c05d0-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="c05d0-144">Resumed</span></span>|<span data-ttu-id="c05d0-145">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="c05d0-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="c05d0-146">Started</span><span class="sxs-lookup"><span data-stu-id="c05d0-146">Started</span></span>|<span data-ttu-id="c05d0-147">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="c05d0-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="c05d0-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="c05d0-148">UnhandledException</span></span>|<span data-ttu-id="c05d0-149">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="c05d0-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="c05d0-150">Scaricato</span><span class="sxs-lookup"><span data-stu-id="c05d0-150">Unloaded</span></span>|<span data-ttu-id="c05d0-151">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="c05d0-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="c05d0-152">Annullato</span><span class="sxs-lookup"><span data-stu-id="c05d0-152">Canceled</span></span>|<span data-ttu-id="c05d0-153">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="c05d0-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="c05d0-154">Suspended</span><span class="sxs-lookup"><span data-stu-id="c05d0-154">Suspended</span></span>|<span data-ttu-id="c05d0-155">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="c05d0-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="c05d0-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="c05d0-156">Terminated</span></span>|<span data-ttu-id="c05d0-157">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="c05d0-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="c05d0-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="c05d0-158">Unsuspended</span></span>|<span data-ttu-id="c05d0-159">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="c05d0-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c05d0-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="c05d0-160">Example</span></span>

<span data-ttu-id="c05d0-161">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="c05d0-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="c05d0-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c05d0-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c05d0-163">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c05d0-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c05d0-164">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c05d0-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
