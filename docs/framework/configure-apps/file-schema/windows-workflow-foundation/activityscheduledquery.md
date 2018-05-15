---
title: '&lt;activityScheduledQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 0822d0ce7dd82ff396596a0ed2431a5f2084ad8f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="899eb-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="899eb-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="899eb-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="899eb-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="899eb-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="899eb-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="899eb-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="899eb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="899eb-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="899eb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="899eb-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="899eb-107">\<tracking></span></span>  
<span data-ttu-id="899eb-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="899eb-108">\<trackingProfile></span></span>  
<span data-ttu-id="899eb-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="899eb-109">\<workflow></span></span>  
<span data-ttu-id="899eb-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="899eb-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="899eb-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="899eb-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="899eb-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="899eb-112">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="899eb-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="899eb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="899eb-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="899eb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="899eb-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="899eb-115">Attributes</span></span>  
  
|<span data-ttu-id="899eb-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="899eb-116">Attribute</span></span>|<span data-ttu-id="899eb-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="899eb-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="899eb-118">activityName</span><span class="sxs-lookup"><span data-stu-id="899eb-118">activityName</span></span>|<span data-ttu-id="899eb-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="899eb-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="899eb-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="899eb-120">childActivityName</span></span>|<span data-ttu-id="899eb-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="899eb-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="899eb-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="899eb-122">Child Elements</span></span>  
 <span data-ttu-id="899eb-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="899eb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="899eb-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="899eb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="899eb-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="899eb-125">Element</span></span>|<span data-ttu-id="899eb-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="899eb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="899eb-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="899eb-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="899eb-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="899eb-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="899eb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="899eb-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="899eb-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="899eb-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="899eb-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="899eb-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
