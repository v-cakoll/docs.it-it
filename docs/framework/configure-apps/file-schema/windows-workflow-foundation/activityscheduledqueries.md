---
title: '&lt;activityScheduledQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 2285dfae84f078483c03d85801051e29b79e74c3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561842"
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="8c7e4-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="8c7e4-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="8c7e4-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="8c7e4-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8c7e4-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8c7e4-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="8c7e4-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8c7e4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8c7e4-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c7e4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8c7e4-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="8c7e4-107">\<tracking></span></span>  
<span data-ttu-id="8c7e4-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8c7e4-108">\<trackingProfile></span></span>  
<span data-ttu-id="8c7e4-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8c7e4-109">\<workflow></span></span>  
<span data-ttu-id="8c7e4-110">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="8c7e4-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c7e4-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c7e4-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c7e4-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c7e4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8c7e4-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c7e4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c7e4-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c7e4-114">Attributes</span></span>  
 <span data-ttu-id="8c7e4-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8c7e4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c7e4-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c7e4-116">Child Elements</span></span>  
  
|<span data-ttu-id="8c7e4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c7e4-117">Element</span></span>|<span data-ttu-id="8c7e4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c7e4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c7e4-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="8c7e4-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="8c7e4-120">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="8c7e4-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c7e4-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c7e4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8c7e4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c7e4-122">Element</span></span>|<span data-ttu-id="8c7e4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c7e4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c7e4-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8c7e4-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8c7e4-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c7e4-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c7e4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c7e4-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8c7e4-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8c7e4-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8c7e4-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8c7e4-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
