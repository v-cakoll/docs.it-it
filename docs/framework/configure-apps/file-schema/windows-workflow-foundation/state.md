---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398643"
---
# \<state>
<span data-ttu-id="f5235-101">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f5235-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="f5235-102">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f5235-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="f5235-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5235-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5235-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f5235-104">Attributes and Elements</span></span>  
 <span data-ttu-id="f5235-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f5235-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5235-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="f5235-106">Attributes</span></span>  
  
|<span data-ttu-id="f5235-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="f5235-107">Attribute</span></span>|<span data-ttu-id="f5235-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5235-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5235-109">name</span><span class="sxs-lookup"><span data-stu-id="f5235-109">name</span></span>|<span data-ttu-id="f5235-110">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f5235-110">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5235-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f5235-111">Child Elements</span></span>  
 <span data-ttu-id="f5235-112">No.</span><span class="sxs-lookup"><span data-stu-id="f5235-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5235-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f5235-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f5235-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5235-114">Element</span></span>|<span data-ttu-id="f5235-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5235-115">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="f5235-116">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f5235-116">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5235-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="f5235-117">Remarks</span></span>  
 <span data-ttu-id="f5235-118">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="f5235-118">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="f5235-119">I valori possibili dello stato sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f5235-119">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="f5235-120">State</span><span class="sxs-lookup"><span data-stu-id="f5235-120">State</span></span>|<span data-ttu-id="f5235-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5235-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f5235-122">Aborted</span><span class="sxs-lookup"><span data-stu-id="f5235-122">Aborted</span></span>|<span data-ttu-id="f5235-123">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="f5235-123">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="f5235-124">Completato</span><span class="sxs-lookup"><span data-stu-id="f5235-124">Completed</span></span>|<span data-ttu-id="f5235-125">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="f5235-125">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="f5235-126">Eliminata</span><span class="sxs-lookup"><span data-stu-id="f5235-126">Deleted</span></span>|<span data-ttu-id="f5235-127">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f5235-127">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="f5235-128">Idle</span><span class="sxs-lookup"><span data-stu-id="f5235-128">Idle</span></span>|<span data-ttu-id="f5235-129">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="f5235-129">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="f5235-130">Persisted</span><span class="sxs-lookup"><span data-stu-id="f5235-130">Persisted</span></span>|<span data-ttu-id="f5235-131">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="f5235-131">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="f5235-132">Resumed</span><span class="sxs-lookup"><span data-stu-id="f5235-132">Resumed</span></span>|<span data-ttu-id="f5235-133">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="f5235-133">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="f5235-134">Avviato</span><span class="sxs-lookup"><span data-stu-id="f5235-134">Started</span></span>|<span data-ttu-id="f5235-135">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="f5235-135">The workflow instance is started.</span></span>|  
|<span data-ttu-id="f5235-136">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="f5235-136">UnhandledException</span></span>|<span data-ttu-id="f5235-137">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="f5235-137">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="f5235-138">Unloaded</span><span class="sxs-lookup"><span data-stu-id="f5235-138">Unloaded</span></span>|<span data-ttu-id="f5235-139">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="f5235-139">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="f5235-140">Cancellati</span><span class="sxs-lookup"><span data-stu-id="f5235-140">Canceled</span></span>|<span data-ttu-id="f5235-141">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="f5235-141">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="f5235-142">Suspended</span><span class="sxs-lookup"><span data-stu-id="f5235-142">Suspended</span></span>|<span data-ttu-id="f5235-143">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="f5235-143">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="f5235-144">Terminato</span><span class="sxs-lookup"><span data-stu-id="f5235-144">Terminated</span></span>|<span data-ttu-id="f5235-145">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="f5235-145">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="f5235-146">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="f5235-146">Unsuspended</span></span>|<span data-ttu-id="f5235-147">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="f5235-147">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5235-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5235-148">Example</span></span>  
 <span data-ttu-id="f5235-149">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="f5235-149">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5235-150">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f5235-150">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f5235-151">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f5235-151">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f5235-152">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f5235-152">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
