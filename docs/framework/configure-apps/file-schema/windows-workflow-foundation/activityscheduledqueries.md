---
title: '&lt;activityScheduledQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d860474c4a638a347f85c07862c330f58cc30c09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="c7338-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="c7338-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="c7338-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c7338-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="c7338-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="c7338-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="c7338-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c7338-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c7338-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c7338-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c7338-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="c7338-107">\<tracking></span></span>  
<span data-ttu-id="c7338-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c7338-108">\<trackingProfile></span></span>  
<span data-ttu-id="c7338-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="c7338-109">\<workflow></span></span>  
<span data-ttu-id="c7338-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="c7338-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7338-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7338-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7338-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c7338-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c7338-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c7338-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7338-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="c7338-114">Attributes</span></span>  
 <span data-ttu-id="c7338-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c7338-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c7338-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c7338-116">Child Elements</span></span>  
  
|<span data-ttu-id="c7338-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7338-117">Element</span></span>|<span data-ttu-id="c7338-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7338-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7338-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="c7338-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="c7338-120">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c7338-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7338-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c7338-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c7338-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7338-122">Element</span></span>|<span data-ttu-id="c7338-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7338-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7338-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="c7338-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c7338-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7338-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7338-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7338-126">See Also</span></span>  
 <span data-ttu-id="c7338-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c7338-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="c7338-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c7338-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="c7338-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c7338-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c7338-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c7338-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
