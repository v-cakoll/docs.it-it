---
title: '&lt;activityScheduledQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 5430058049e8a09c1e2a289e1f997338c23b9d94
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492156"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="b6da2-102">&lt;activityScheduledQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="b6da2-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="b6da2-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="b6da2-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b6da2-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b6da2-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="b6da2-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b6da2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b6da2-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6da2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b6da2-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b6da2-107">\<tracking></span></span>  
<span data-ttu-id="b6da2-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="b6da2-108">\<profiles></span></span>  
<span data-ttu-id="b6da2-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b6da2-109">\<trackingProfile></span></span>  
<span data-ttu-id="b6da2-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="b6da2-110">\<workflow></span></span>  
<span data-ttu-id="b6da2-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="b6da2-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6da2-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6da2-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6da2-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6da2-113">Attributes and elements</span></span>  

<span data-ttu-id="b6da2-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6da2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6da2-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6da2-115">Attributes</span></span>  

<span data-ttu-id="b6da2-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b6da2-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6da2-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6da2-117">Child elements</span></span>  
  
|<span data-ttu-id="b6da2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6da2-118">Element</span></span>|<span data-ttu-id="b6da2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6da2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6da2-120">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="b6da2-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="b6da2-121">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="b6da2-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6da2-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6da2-122">Parent elements</span></span>  
  
|<span data-ttu-id="b6da2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6da2-123">Element</span></span>|<span data-ttu-id="b6da2-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6da2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6da2-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b6da2-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b6da2-126">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="b6da2-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6da2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6da2-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="b6da2-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b6da2-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b6da2-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b6da2-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
