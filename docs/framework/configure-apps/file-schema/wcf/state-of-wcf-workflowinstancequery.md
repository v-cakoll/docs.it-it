---
title: <state>di WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854958"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="b4546-102">\<state>di WCF,\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="b4546-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="b4546-103">Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b4546-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="b4546-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b4546-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="b4546-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4546-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4546-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b4546-106">Attributes and elements</span></span>

<span data-ttu-id="b4546-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b4546-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b4546-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="b4546-108">Attributes</span></span>

|<span data-ttu-id="b4546-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="b4546-109">Attribute</span></span>|<span data-ttu-id="b4546-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4546-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b4546-111">Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b4546-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4546-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b4546-112">Child elements</span></span>

<span data-ttu-id="b4546-113">No.</span><span class="sxs-lookup"><span data-stu-id="b4546-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b4546-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b4546-114">Parent elements</span></span>

|<span data-ttu-id="b4546-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4546-115">Element</span></span>|<span data-ttu-id="b4546-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4546-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="b4546-117">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b4546-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4546-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="b4546-118">Remarks</span></span>  

<span data-ttu-id="b4546-119">I record restituiti vengono filtrati in base agli stati di questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="b4546-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="b4546-120">Nella tabella seguente sono descritti i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="b4546-120">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="b4546-121">State</span><span class="sxs-lookup"><span data-stu-id="b4546-121">State</span></span>|<span data-ttu-id="b4546-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4546-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b4546-123">Aborted</span><span class="sxs-lookup"><span data-stu-id="b4546-123">Aborted</span></span>|<span data-ttu-id="b4546-124">L'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="b4546-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="b4546-125">Completato</span><span class="sxs-lookup"><span data-stu-id="b4546-125">Completed</span></span>|<span data-ttu-id="b4546-126">L'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="b4546-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="b4546-127">Eliminata</span><span class="sxs-lookup"><span data-stu-id="b4546-127">Deleted</span></span>|<span data-ttu-id="b4546-128">L'istanza del flusso di lavoro viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="b4546-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="b4546-129">Idle</span><span class="sxs-lookup"><span data-stu-id="b4546-129">Idle</span></span>|<span data-ttu-id="b4546-130">L'istanza del flusso di lavoro è inattiva.</span><span class="sxs-lookup"><span data-stu-id="b4546-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="b4546-131">Persisted</span><span class="sxs-lookup"><span data-stu-id="b4546-131">Persisted</span></span>|<span data-ttu-id="b4546-132">L'istanza del flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="b4546-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="b4546-133">Resumed</span><span class="sxs-lookup"><span data-stu-id="b4546-133">Resumed</span></span>|<span data-ttu-id="b4546-134">L'istanza del flusso di lavoro viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="b4546-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="b4546-135">Avviato</span><span class="sxs-lookup"><span data-stu-id="b4546-135">Started</span></span>|<span data-ttu-id="b4546-136">L'istanza del flusso di lavoro è avviata.</span><span class="sxs-lookup"><span data-stu-id="b4546-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="b4546-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="b4546-137">UnhandledException</span></span>|<span data-ttu-id="b4546-138">L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="b4546-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="b4546-139">Unloaded</span><span class="sxs-lookup"><span data-stu-id="b4546-139">Unloaded</span></span>|<span data-ttu-id="b4546-140">L'istanza del flusso di lavoro viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="b4546-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="b4546-141">Cancellati</span><span class="sxs-lookup"><span data-stu-id="b4546-141">Canceled</span></span>|<span data-ttu-id="b4546-142">L'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="b4546-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="b4546-143">Suspended</span><span class="sxs-lookup"><span data-stu-id="b4546-143">Suspended</span></span>|<span data-ttu-id="b4546-144">L'istanza del flusso di lavoro è sospesa.</span><span class="sxs-lookup"><span data-stu-id="b4546-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="b4546-145">Terminato</span><span class="sxs-lookup"><span data-stu-id="b4546-145">Terminated</span></span>|<span data-ttu-id="b4546-146">L'istanza del flusso di lavoro è terminata.</span><span class="sxs-lookup"><span data-stu-id="b4546-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="b4546-147">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="b4546-147">Unsuspended</span></span>|<span data-ttu-id="b4546-148">L'istanza del flusso di lavoro non è sospesa.</span><span class="sxs-lookup"><span data-stu-id="b4546-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b4546-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4546-149">Example</span></span>

<span data-ttu-id="b4546-150">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="b4546-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="b4546-151">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b4546-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b4546-152">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b4546-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b4546-153">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b4546-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
