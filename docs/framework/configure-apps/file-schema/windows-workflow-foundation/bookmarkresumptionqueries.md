---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5bf209525bcc9748e9a5f5b71a0407a4eca1a897
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="1d444-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="1d444-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="1d444-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1d444-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1d444-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="1d444-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="1d444-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1d444-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1d444-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1d444-106">\<system.serviceModel></span></span>  
<span data-ttu-id="1d444-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="1d444-107">\<tracking></span></span>  
<span data-ttu-id="1d444-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1d444-108">\<trackingProfile></span></span>  
<span data-ttu-id="1d444-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="1d444-109">\<workflow></span></span>  
<span data-ttu-id="1d444-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="1d444-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="1d444-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="1d444-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d444-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d444-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d444-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1d444-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1d444-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1d444-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d444-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="1d444-115">Attributes</span></span>  
 <span data-ttu-id="1d444-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1d444-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d444-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1d444-117">Child Elements</span></span>  
  
|<span data-ttu-id="1d444-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d444-118">Element</span></span>|<span data-ttu-id="1d444-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d444-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d444-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="1d444-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="1d444-121">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1d444-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1d444-122">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="1d444-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d444-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1d444-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1d444-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d444-124">Element</span></span>|<span data-ttu-id="1d444-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d444-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d444-126">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="1d444-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1d444-127">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="1d444-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d444-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d444-128">See Also</span></span>  
 <span data-ttu-id="1d444-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1d444-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="1d444-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1d444-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="1d444-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1d444-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1d444-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="1d444-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
