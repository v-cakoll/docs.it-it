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
ms.openlocfilehash: 32b0e1b068e1f6fef3ce18b0e4dfa628ccaa8a79
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="3705c-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3705c-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="3705c-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3705c-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3705c-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3705c-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="3705c-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3705c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3705c-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3705c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3705c-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="3705c-107">\<tracking></span></span>  
<span data-ttu-id="3705c-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3705c-108">\<trackingProfile></span></span>  
<span data-ttu-id="3705c-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="3705c-109">\<workflow></span></span>  
<span data-ttu-id="3705c-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="3705c-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="3705c-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="3705c-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3705c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3705c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3705c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3705c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3705c-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3705c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3705c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="3705c-115">Attributes</span></span>  
  
|<span data-ttu-id="3705c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="3705c-116">Attribute</span></span>|<span data-ttu-id="3705c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3705c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3705c-118">activityName</span><span class="sxs-lookup"><span data-stu-id="3705c-118">activityName</span></span>|<span data-ttu-id="3705c-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="3705c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3705c-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3705c-120">childActivityName</span></span>|<span data-ttu-id="3705c-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="3705c-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3705c-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3705c-122">Child Elements</span></span>  
 <span data-ttu-id="3705c-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3705c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3705c-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3705c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3705c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3705c-125">Element</span></span>|<span data-ttu-id="3705c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3705c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3705c-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="3705c-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="3705c-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3705c-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3705c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3705c-129">See Also</span></span>  
 <span data-ttu-id="3705c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3705c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3705c-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3705c-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3705c-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3705c-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3705c-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3705c-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
