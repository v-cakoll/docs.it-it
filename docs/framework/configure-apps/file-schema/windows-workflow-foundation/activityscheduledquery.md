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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 779ac3995d4d5fb1b63de6ae6b9db7103691d6f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="fb373-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="fb373-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="fb373-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="fb373-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="fb373-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="fb373-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="fb373-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fb373-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="fb373-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fb373-106">\<system.serviceModel></span></span>  
<span data-ttu-id="fb373-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="fb373-107">\<tracking></span></span>  
<span data-ttu-id="fb373-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="fb373-108">\<trackingProfile></span></span>  
<span data-ttu-id="fb373-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="fb373-109">\<workflow></span></span>  
<span data-ttu-id="fb373-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="fb373-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="fb373-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="fb373-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb373-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb373-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb373-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fb373-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fb373-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fb373-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb373-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="fb373-115">Attributes</span></span>  
  
|<span data-ttu-id="fb373-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="fb373-116">Attribute</span></span>|<span data-ttu-id="fb373-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb373-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb373-118">activityName</span><span class="sxs-lookup"><span data-stu-id="fb373-118">activityName</span></span>|<span data-ttu-id="fb373-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="fb373-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="fb373-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="fb373-120">childActivityName</span></span>|<span data-ttu-id="fb373-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="fb373-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb373-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fb373-122">Child Elements</span></span>  
 <span data-ttu-id="fb373-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fb373-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb373-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fb373-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fb373-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb373-125">Element</span></span>|<span data-ttu-id="fb373-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb373-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb373-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="fb373-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="fb373-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="fb373-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb373-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb373-129">See Also</span></span>  
 <span data-ttu-id="fb373-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fb373-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="fb373-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fb373-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="fb373-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fb373-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="fb373-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="fb373-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
