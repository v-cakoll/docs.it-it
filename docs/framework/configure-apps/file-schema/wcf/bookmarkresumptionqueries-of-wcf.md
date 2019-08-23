---
title: <bookmarkResumptionQueries>di WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 5ec9827e9862866096265da576c91b10573012d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919746"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="1ff54-102">\<> bookmarkResumptionQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="1ff54-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="1ff54-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ff54-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1ff54-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="1ff54-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="1ff54-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1ff54-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="1ff54-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1ff54-106">\<system.serviceModel></span></span>  
<span data-ttu-id="1ff54-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="1ff54-107">\<tracking></span></span>  
<span data-ttu-id="1ff54-108">\<profili ></span><span class="sxs-lookup"><span data-stu-id="1ff54-108">\<profiles></span></span>  
<span data-ttu-id="1ff54-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1ff54-109">\<trackingProfile></span></span>  
<span data-ttu-id="1ff54-110">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1ff54-110">\<workflow></span></span>  
<span data-ttu-id="1ff54-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="1ff54-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="1ff54-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="1ff54-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff54-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ff54-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ff54-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1ff54-114">Attributes and elements</span></span>  
  
<span data-ttu-id="1ff54-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1ff54-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ff54-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ff54-116">Attributes</span></span>  
  
<span data-ttu-id="1ff54-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1ff54-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ff54-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ff54-118">Child elements</span></span>  
  
|<span data-ttu-id="1ff54-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ff54-119">Element</span></span>|<span data-ttu-id="1ff54-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ff54-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ff54-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="1ff54-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="1ff54-122">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ff54-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1ff54-123">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="1ff54-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ff54-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1ff54-124">Parent elements</span></span>  
  
|<span data-ttu-id="1ff54-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ff54-125">Element</span></span>|<span data-ttu-id="1ff54-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1ff54-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ff54-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1ff54-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="1ff54-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="1ff54-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ff54-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ff54-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1ff54-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1ff54-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1ff54-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="1ff54-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
