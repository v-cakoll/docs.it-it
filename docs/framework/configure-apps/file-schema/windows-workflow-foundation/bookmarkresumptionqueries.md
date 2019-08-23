---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: f048612673a9b6b69c3cdded6526c76359c444e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945982"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="d2b2a-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="d2b2a-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="d2b2a-102">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d2b2a-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d2b2a-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="d2b2a-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="d2b2a-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d2b2a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d2b2a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d2b2a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d2b2a-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="d2b2a-106">\<tracking></span></span>  
<span data-ttu-id="d2b2a-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d2b2a-107">\<trackingProfile></span></span>  
<span data-ttu-id="d2b2a-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d2b2a-108">\<workflow></span></span>  
<span data-ttu-id="d2b2a-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="d2b2a-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="d2b2a-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="d2b2a-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b2a-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2b2a-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2b2a-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d2b2a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d2b2a-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d2b2a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2b2a-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="d2b2a-114">Attributes</span></span>  
 <span data-ttu-id="d2b2a-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d2b2a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2b2a-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d2b2a-116">Child Elements</span></span>  
  
|<span data-ttu-id="d2b2a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2b2a-117">Element</span></span>|<span data-ttu-id="d2b2a-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2b2a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2b2a-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="d2b2a-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="d2b2a-120">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d2b2a-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d2b2a-121">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="d2b2a-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2b2a-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d2b2a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d2b2a-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2b2a-123">Element</span></span>|<span data-ttu-id="d2b2a-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2b2a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2b2a-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d2b2a-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="d2b2a-126">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="d2b2a-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2b2a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b2a-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d2b2a-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d2b2a-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d2b2a-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d2b2a-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
