---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398612"
---
# <a name="states"></a><span data-ttu-id="4303d-101">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="4303d-101">\<states></span></span>
<span data-ttu-id="4303d-102">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="4303d-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="4303d-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4303d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4303d-105">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="4303d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="4303d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="4303d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="4303d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="4303d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="4303d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="4303d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Stati >**</span><span class="sxs-lookup"><span data-stu-id="4303d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4303d-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4303d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4303d-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4303d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4303d-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4303d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4303d-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="4303d-115">Attributes</span></span>  
 <span data-ttu-id="4303d-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4303d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4303d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4303d-117">Child Elements</span></span>  
  
|<span data-ttu-id="4303d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4303d-118">Element</span></span>|<span data-ttu-id="4303d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4303d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4303d-120">\<state></span><span class="sxs-lookup"><span data-stu-id="4303d-120">\<state></span></span>](states.md)|<span data-ttu-id="4303d-121">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="4303d-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4303d-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4303d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4303d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4303d-123">Element</span></span>|<span data-ttu-id="4303d-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4303d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4303d-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="4303d-125">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="4303d-126">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="4303d-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4303d-127">Note</span><span class="sxs-lookup"><span data-stu-id="4303d-127">Remarks</span></span>  
 <span data-ttu-id="4303d-128">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="4303d-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="4303d-129">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4303d-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="4303d-130">Stato</span><span class="sxs-lookup"><span data-stu-id="4303d-130">State</span></span>|<span data-ttu-id="4303d-131">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4303d-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4303d-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="4303d-132">Aborted</span></span>|<span data-ttu-id="4303d-133">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="4303d-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="4303d-134">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="4303d-134">Completed</span></span>|<span data-ttu-id="4303d-135">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="4303d-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="4303d-136">Eliminato</span><span class="sxs-lookup"><span data-stu-id="4303d-136">Deleted</span></span>|<span data-ttu-id="4303d-137">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="4303d-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="4303d-138">Idle</span><span class="sxs-lookup"><span data-stu-id="4303d-138">Idle</span></span>|<span data-ttu-id="4303d-139">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="4303d-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="4303d-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="4303d-140">Persisted</span></span>|<span data-ttu-id="4303d-141">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="4303d-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="4303d-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="4303d-142">Resumed</span></span>|<span data-ttu-id="4303d-143">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="4303d-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="4303d-144">Started</span><span class="sxs-lookup"><span data-stu-id="4303d-144">Started</span></span>|<span data-ttu-id="4303d-145">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="4303d-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="4303d-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="4303d-146">UnhandledException</span></span>|<span data-ttu-id="4303d-147">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="4303d-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="4303d-148">Scaricato</span><span class="sxs-lookup"><span data-stu-id="4303d-148">Unloaded</span></span>|<span data-ttu-id="4303d-149">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="4303d-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="4303d-150">Annullato</span><span class="sxs-lookup"><span data-stu-id="4303d-150">Canceled</span></span>|<span data-ttu-id="4303d-151">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="4303d-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="4303d-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="4303d-152">Suspended</span></span>|<span data-ttu-id="4303d-153">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="4303d-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="4303d-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="4303d-154">Terminated</span></span>|<span data-ttu-id="4303d-155">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="4303d-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="4303d-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="4303d-156">Unsuspended</span></span>|<span data-ttu-id="4303d-157">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="4303d-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4303d-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="4303d-158">Example</span></span>  
 <span data-ttu-id="4303d-159">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="4303d-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4303d-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4303d-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4303d-161">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4303d-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4303d-162">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4303d-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
