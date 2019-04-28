---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 7217fb886cc96e1ad19f96e2c6542277cfc7979e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790429"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="b5281-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="b5281-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="b5281-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="b5281-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b5281-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b5281-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="b5281-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b5281-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b5281-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b5281-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b5281-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b5281-106">\<tracking></span></span>  
<span data-ttu-id="b5281-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b5281-107">\<trackingProfile></span></span>  
<span data-ttu-id="b5281-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="b5281-108">\<workflow></span></span>  
<span data-ttu-id="b5281-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="b5281-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5281-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5281-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5281-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b5281-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b5281-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b5281-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5281-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b5281-113">Attributes</span></span>  
 <span data-ttu-id="b5281-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b5281-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b5281-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b5281-115">Child Elements</span></span>  
  
|<span data-ttu-id="b5281-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5281-116">Element</span></span>|<span data-ttu-id="b5281-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5281-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5281-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="b5281-118">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="b5281-119">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="b5281-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5281-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b5281-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b5281-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5281-121">Element</span></span>|<span data-ttu-id="b5281-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5281-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5281-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b5281-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b5281-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5281-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5281-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5281-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b5281-126">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b5281-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b5281-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b5281-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
