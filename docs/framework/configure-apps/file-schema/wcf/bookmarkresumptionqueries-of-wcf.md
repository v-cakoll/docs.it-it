---
title: '&lt;bookmarkResumptionQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7afa80a0abfa29c02cdf2ec6c96d2049f98db436
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="2ec15-102">&lt;bookmarkResumptionQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="2ec15-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="2ec15-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ec15-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2ec15-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="2ec15-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="2ec15-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2ec15-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="2ec15-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2ec15-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2ec15-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="2ec15-107">\<tracking></span></span>  
<span data-ttu-id="2ec15-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2ec15-108">\<trackingProfile></span></span>  
<span data-ttu-id="2ec15-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="2ec15-109">\<workflow></span></span>  
<span data-ttu-id="2ec15-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="2ec15-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="2ec15-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="2ec15-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec15-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ec15-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2ec15-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2ec15-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2ec15-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2ec15-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ec15-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="2ec15-115">Attributes</span></span>  
 <span data-ttu-id="2ec15-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2ec15-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ec15-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2ec15-117">Child Elements</span></span>  
  
|<span data-ttu-id="2ec15-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ec15-118">Element</span></span>|<span data-ttu-id="2ec15-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ec15-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ec15-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="2ec15-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="2ec15-121">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ec15-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2ec15-122">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="2ec15-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ec15-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2ec15-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2ec15-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ec15-124">Element</span></span>|<span data-ttu-id="2ec15-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ec15-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ec15-126">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="2ec15-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2ec15-127">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="2ec15-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ec15-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ec15-128">See Also</span></span>  
 <span data-ttu-id="2ec15-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2ec15-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="2ec15-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2ec15-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="2ec15-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2ec15-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2ec15-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2ec15-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
