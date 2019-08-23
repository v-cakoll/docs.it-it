---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 89de9ef10449fbae78a8c5b558101a2cf6477b07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945528"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="c5b5c-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="c5b5c-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="c5b5c-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c5b5c-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="c5b5c-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="c5b5c-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="c5b5c-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c5b5c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c5b5c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c5b5c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c5b5c-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="c5b5c-106">\<tracking></span></span>  
<span data-ttu-id="c5b5c-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c5b5c-107">\<trackingProfile></span></span>  
<span data-ttu-id="c5b5c-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c5b5c-108">\<workflow></span></span>  
<span data-ttu-id="c5b5c-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="c5b5c-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b5c-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5b5c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5b5c-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c5b5c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c5b5c-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c5b5c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5b5c-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c5b5c-113">Attributes</span></span>  
 <span data-ttu-id="c5b5c-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c5b5c-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c5b5c-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c5b5c-115">Child Elements</span></span>  
  
|<span data-ttu-id="c5b5c-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5b5c-116">Element</span></span>|<span data-ttu-id="c5b5c-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c5b5c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5b5c-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c5b5c-118">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="c5b5c-119">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c5b5c-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5b5c-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c5b5c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c5b5c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5b5c-121">Element</span></span>|<span data-ttu-id="c5b5c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5b5c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5b5c-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c5b5c-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="c5b5c-124">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="c5b5c-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5b5c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5b5c-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c5b5c-126">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c5b5c-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c5b5c-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c5b5c-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
