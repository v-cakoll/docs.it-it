---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398612"
---
# \<states>
<span data-ttu-id="f9c96-101">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f9c96-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="f9c96-102">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f9c96-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="f9c96-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9c96-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9c96-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f9c96-104">Attributes and Elements</span></span>  
 <span data-ttu-id="f9c96-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9c96-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9c96-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="f9c96-106">Attributes</span></span>  
 <span data-ttu-id="f9c96-107">No.</span><span class="sxs-lookup"><span data-stu-id="f9c96-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9c96-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f9c96-108">Child Elements</span></span>  
  
|<span data-ttu-id="f9c96-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9c96-109">Element</span></span>|<span data-ttu-id="f9c96-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9c96-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="f9c96-111">Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.</span><span class="sxs-lookup"><span data-stu-id="f9c96-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9c96-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f9c96-112">Parent Elements</span></span>  
  
|<span data-ttu-id="f9c96-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9c96-113">Element</span></span>|<span data-ttu-id="f9c96-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9c96-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="f9c96-115">Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="f9c96-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9c96-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="f9c96-116">Remarks</span></span>  
 <span data-ttu-id="f9c96-117">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="f9c96-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="f9c96-118">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f9c96-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="f9c96-119">State</span><span class="sxs-lookup"><span data-stu-id="f9c96-119">State</span></span>|<span data-ttu-id="f9c96-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9c96-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f9c96-121">Aborted</span><span class="sxs-lookup"><span data-stu-id="f9c96-121">Aborted</span></span>|<span data-ttu-id="f9c96-122">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="f9c96-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="f9c96-123">Completato</span><span class="sxs-lookup"><span data-stu-id="f9c96-123">Completed</span></span>|<span data-ttu-id="f9c96-124">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="f9c96-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="f9c96-125">Eliminata</span><span class="sxs-lookup"><span data-stu-id="f9c96-125">Deleted</span></span>|<span data-ttu-id="f9c96-126">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f9c96-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="f9c96-127">Idle</span><span class="sxs-lookup"><span data-stu-id="f9c96-127">Idle</span></span>|<span data-ttu-id="f9c96-128">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="f9c96-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="f9c96-129">Persisted</span><span class="sxs-lookup"><span data-stu-id="f9c96-129">Persisted</span></span>|<span data-ttu-id="f9c96-130">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="f9c96-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="f9c96-131">Resumed</span><span class="sxs-lookup"><span data-stu-id="f9c96-131">Resumed</span></span>|<span data-ttu-id="f9c96-132">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="f9c96-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="f9c96-133">Avviato</span><span class="sxs-lookup"><span data-stu-id="f9c96-133">Started</span></span>|<span data-ttu-id="f9c96-134">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="f9c96-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="f9c96-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="f9c96-135">UnhandledException</span></span>|<span data-ttu-id="f9c96-136">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="f9c96-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="f9c96-137">Unloaded</span><span class="sxs-lookup"><span data-stu-id="f9c96-137">Unloaded</span></span>|<span data-ttu-id="f9c96-138">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="f9c96-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="f9c96-139">Cancellati</span><span class="sxs-lookup"><span data-stu-id="f9c96-139">Canceled</span></span>|<span data-ttu-id="f9c96-140">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="f9c96-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="f9c96-141">Suspended</span><span class="sxs-lookup"><span data-stu-id="f9c96-141">Suspended</span></span>|<span data-ttu-id="f9c96-142">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="f9c96-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="f9c96-143">Terminato</span><span class="sxs-lookup"><span data-stu-id="f9c96-143">Terminated</span></span>|<span data-ttu-id="f9c96-144">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="f9c96-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="f9c96-145">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="f9c96-145">Unsuspended</span></span>|<span data-ttu-id="f9c96-146">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="f9c96-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f9c96-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9c96-147">Example</span></span>  
 <span data-ttu-id="f9c96-148">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="f9c96-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9c96-149">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f9c96-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f9c96-150">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f9c96-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f9c96-151">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f9c96-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
