---
title: <workflowInstanceQueries>di WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854778"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="c23fa-102">\<workflowInstanceQueries>di WCF</span><span class="sxs-lookup"><span data-stu-id="c23fa-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="c23fa-103">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="c23fa-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="c23fa-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c23fa-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="c23fa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c23fa-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c23fa-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c23fa-106">Attributes and elements</span></span>

<span data-ttu-id="c23fa-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c23fa-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c23fa-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="c23fa-108">Attributes</span></span>  

<span data-ttu-id="c23fa-109">No.</span><span class="sxs-lookup"><span data-stu-id="c23fa-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c23fa-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c23fa-110">Child elements</span></span>  
  
|<span data-ttu-id="c23fa-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="c23fa-111">Element</span></span>|<span data-ttu-id="c23fa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c23fa-112">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="c23fa-113">Query usata per rilevare modifiche del ciclo di vita dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c23fa-113">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c23fa-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c23fa-114">Parent elements</span></span>  
  
|<span data-ttu-id="c23fa-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c23fa-115">Element</span></span>|<span data-ttu-id="c23fa-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c23fa-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="c23fa-117">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà [ActivityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="c23fa-117">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c23fa-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="c23fa-118">Remarks</span></span>

<span data-ttu-id="c23fa-119">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="c23fa-119">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="c23fa-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="c23fa-120">Example</span></span>  

<span data-ttu-id="c23fa-121">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="c23fa-121">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="c23fa-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c23fa-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c23fa-123">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c23fa-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c23fa-124">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c23fa-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
