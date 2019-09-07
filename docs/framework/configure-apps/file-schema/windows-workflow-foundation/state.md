---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398643"
---
# <a name="state"></a><span data-ttu-id="1d465-101">\<> di stato</span><span class="sxs-lookup"><span data-stu-id="1d465-101">\<state></span></span>
<span data-ttu-id="1d465-102">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1d465-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="1d465-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1d465-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1d465-105">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1d465-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1d465-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1d465-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1d465-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="1d465-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="1d465-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Stati >** ](states.md)</span><span class="sxs-lookup"><span data-stu-id="1d465-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)</span></span>\
<span data-ttu-id="1d465-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di stato**</span><span class="sxs-lookup"><span data-stu-id="1d465-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d465-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d465-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d465-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1d465-114">Attributes and Elements</span></span>  
 <span data-ttu-id="1d465-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1d465-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d465-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="1d465-116">Attributes</span></span>  
  
|<span data-ttu-id="1d465-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="1d465-117">Attribute</span></span>|<span data-ttu-id="1d465-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d465-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d465-119">name</span><span class="sxs-lookup"><span data-stu-id="1d465-119">name</span></span>|<span data-ttu-id="1d465-120">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1d465-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d465-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1d465-121">Child Elements</span></span>  
 <span data-ttu-id="1d465-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1d465-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d465-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1d465-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1d465-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d465-124">Element</span></span>|<span data-ttu-id="1d465-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1d465-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d465-126">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="1d465-126">\<states></span></span>](states.md)|<span data-ttu-id="1d465-127">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1d465-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d465-128">Note</span><span class="sxs-lookup"><span data-stu-id="1d465-128">Remarks</span></span>  
 <span data-ttu-id="1d465-129">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="1d465-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="1d465-130">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1d465-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="1d465-131">Stato</span><span class="sxs-lookup"><span data-stu-id="1d465-131">State</span></span>|<span data-ttu-id="1d465-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d465-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1d465-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="1d465-133">Aborted</span></span>|<span data-ttu-id="1d465-134">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="1d465-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="1d465-135">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="1d465-135">Completed</span></span>|<span data-ttu-id="1d465-136">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="1d465-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="1d465-137">Eliminato</span><span class="sxs-lookup"><span data-stu-id="1d465-137">Deleted</span></span>|<span data-ttu-id="1d465-138">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="1d465-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="1d465-139">Idle</span><span class="sxs-lookup"><span data-stu-id="1d465-139">Idle</span></span>|<span data-ttu-id="1d465-140">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="1d465-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="1d465-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="1d465-141">Persisted</span></span>|<span data-ttu-id="1d465-142">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="1d465-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="1d465-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="1d465-143">Resumed</span></span>|<span data-ttu-id="1d465-144">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="1d465-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="1d465-145">Started</span><span class="sxs-lookup"><span data-stu-id="1d465-145">Started</span></span>|<span data-ttu-id="1d465-146">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="1d465-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="1d465-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="1d465-147">UnhandledException</span></span>|<span data-ttu-id="1d465-148">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1d465-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="1d465-149">Scaricato</span><span class="sxs-lookup"><span data-stu-id="1d465-149">Unloaded</span></span>|<span data-ttu-id="1d465-150">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="1d465-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="1d465-151">Annullato</span><span class="sxs-lookup"><span data-stu-id="1d465-151">Canceled</span></span>|<span data-ttu-id="1d465-152">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="1d465-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="1d465-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="1d465-153">Suspended</span></span>|<span data-ttu-id="1d465-154">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="1d465-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="1d465-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="1d465-155">Terminated</span></span>|<span data-ttu-id="1d465-156">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="1d465-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="1d465-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="1d465-157">Unsuspended</span></span>|<span data-ttu-id="1d465-158">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="1d465-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d465-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d465-159">Example</span></span>  
 <span data-ttu-id="1d465-160">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="1d465-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d465-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d465-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1d465-162">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1d465-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1d465-163">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="1d465-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
