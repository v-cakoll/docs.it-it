---
title: '&lt;activityScheduledQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97726c7faa08477351d4496650b6c08b643cdb76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="8be10-102">&lt;activityScheduledQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="8be10-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="8be10-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="8be10-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8be10-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8be10-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="8be10-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8be10-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="8be10-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8be10-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8be10-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="8be10-107">\<tracking></span></span>  
<span data-ttu-id="8be10-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8be10-108">\<trackingProfile></span></span>  
<span data-ttu-id="8be10-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8be10-109">\<workflow></span></span>  
<span data-ttu-id="8be10-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="8be10-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be10-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8be10-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8be10-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8be10-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8be10-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8be10-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8be10-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="8be10-114">Attributes</span></span>  
 <span data-ttu-id="8be10-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8be10-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8be10-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8be10-116">Child Elements</span></span>  
  
|<span data-ttu-id="8be10-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="8be10-117">Element</span></span>|<span data-ttu-id="8be10-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8be10-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8be10-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="8be10-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="8be10-120">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="8be10-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8be10-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8be10-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8be10-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8be10-122">Element</span></span>|<span data-ttu-id="8be10-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8be10-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8be10-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8be10-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8be10-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="8be10-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8be10-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8be10-126">See Also</span></span>  
 <span data-ttu-id="8be10-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="8be10-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span></span>     
 <span data-ttu-id="8be10-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="8be10-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="8be10-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8be10-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8be10-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8be10-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
