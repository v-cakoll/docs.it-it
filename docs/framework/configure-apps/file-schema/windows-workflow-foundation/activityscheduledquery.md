---
title: '&lt;activityScheduledQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51db0762c10459d67929867a0fe44908dc7ec750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="cc039-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="cc039-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="cc039-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="cc039-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="cc039-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cc039-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="cc039-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cc039-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cc039-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cc039-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cc039-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="cc039-107">\<tracking></span></span>  
<span data-ttu-id="cc039-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="cc039-108">\<trackingProfile></span></span>  
<span data-ttu-id="cc039-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="cc039-109">\<workflow></span></span>  
<span data-ttu-id="cc039-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="cc039-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="cc039-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="cc039-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc039-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc039-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc039-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cc039-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cc039-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cc039-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc039-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="cc039-115">Attributes</span></span>  
  
|<span data-ttu-id="cc039-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="cc039-116">Attribute</span></span>|<span data-ttu-id="cc039-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc039-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc039-118">activityName</span><span class="sxs-lookup"><span data-stu-id="cc039-118">activityName</span></span>|<span data-ttu-id="cc039-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="cc039-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="cc039-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="cc039-120">childActivityName</span></span>|<span data-ttu-id="cc039-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="cc039-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc039-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cc039-122">Child Elements</span></span>  
 <span data-ttu-id="cc039-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cc039-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc039-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cc039-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cc039-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc039-125">Element</span></span>|<span data-ttu-id="cc039-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc039-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc039-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="cc039-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="cc039-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="cc039-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc039-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc039-129">See Also</span></span>  
 <span data-ttu-id="cc039-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cc039-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="cc039-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cc039-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="cc039-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cc039-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cc039-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="cc039-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
