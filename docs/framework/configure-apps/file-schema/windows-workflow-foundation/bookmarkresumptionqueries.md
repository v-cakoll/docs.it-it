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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fb3cf8457dc19081e9eb51091453764513da8ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="9338a-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="9338a-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="9338a-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9338a-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9338a-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="9338a-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="9338a-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9338a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9338a-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9338a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9338a-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="9338a-107">\<tracking></span></span>  
<span data-ttu-id="9338a-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9338a-108">\<trackingProfile></span></span>  
<span data-ttu-id="9338a-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="9338a-109">\<workflow></span></span>  
<span data-ttu-id="9338a-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="9338a-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="9338a-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="9338a-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9338a-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9338a-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9338a-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9338a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9338a-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9338a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9338a-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="9338a-115">Attributes</span></span>  
 <span data-ttu-id="9338a-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9338a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9338a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9338a-117">Child Elements</span></span>  
  
|<span data-ttu-id="9338a-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9338a-118">Element</span></span>|<span data-ttu-id="9338a-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9338a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9338a-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="9338a-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="9338a-121">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9338a-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9338a-122">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="9338a-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9338a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9338a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9338a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9338a-124">Element</span></span>|<span data-ttu-id="9338a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9338a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9338a-126">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="9338a-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9338a-127">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="9338a-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9338a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9338a-128">See Also</span></span>  
 <span data-ttu-id="9338a-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9338a-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="9338a-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9338a-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="9338a-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9338a-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9338a-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9338a-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
