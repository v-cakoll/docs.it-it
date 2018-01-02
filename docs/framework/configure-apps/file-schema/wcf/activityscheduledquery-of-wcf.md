---
title: '&lt;activityScheduledQuery&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: afb421993c39e66e437a0ecbb35091532df61716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="67697-102">&lt;activityScheduledQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="67697-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="67697-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="67697-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="67697-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="67697-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="67697-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="67697-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="67697-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="67697-106">\<system.serviceModel></span></span>  
<span data-ttu-id="67697-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="67697-107">\<tracking></span></span>  
<span data-ttu-id="67697-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="67697-108">\<trackingProfile></span></span>  
<span data-ttu-id="67697-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="67697-109">\<workflow></span></span>  
<span data-ttu-id="67697-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="67697-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="67697-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="67697-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67697-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67697-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67697-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="67697-113">Attributes and Elements</span></span>  
 <span data-ttu-id="67697-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="67697-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67697-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="67697-115">Attributes</span></span>  
  
|<span data-ttu-id="67697-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="67697-116">Attribute</span></span>|<span data-ttu-id="67697-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67697-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67697-118">activityName</span><span class="sxs-lookup"><span data-stu-id="67697-118">activityName</span></span>|<span data-ttu-id="67697-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="67697-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="67697-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="67697-120">childActivityName</span></span>|<span data-ttu-id="67697-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="67697-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67697-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="67697-122">Child Elements</span></span>  
 <span data-ttu-id="67697-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="67697-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67697-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="67697-124">Parent Elements</span></span>  
  
|<span data-ttu-id="67697-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="67697-125">Element</span></span>|<span data-ttu-id="67697-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67697-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67697-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="67697-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="67697-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="67697-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67697-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67697-129">See Also</span></span>  
 <span data-ttu-id="67697-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span><span class="sxs-lookup"><span data-stu-id="67697-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span></span>     
 <span data-ttu-id="67697-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="67697-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="67697-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="67697-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="67697-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="67697-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
