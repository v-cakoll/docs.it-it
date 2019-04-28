---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 186990577ec4eedc7cae3710c455816c3162fc94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790286"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="e81c3-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="e81c3-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="e81c3-102">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e81c3-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e81c3-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="e81c3-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="e81c3-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e81c3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e81c3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e81c3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e81c3-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e81c3-106">\<tracking></span></span>  
<span data-ttu-id="e81c3-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e81c3-107">\<trackingProfile></span></span>  
<span data-ttu-id="e81c3-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e81c3-108">\<workflow></span></span>  
<span data-ttu-id="e81c3-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="e81c3-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="e81c3-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="e81c3-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81c3-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e81c3-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e81c3-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e81c3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e81c3-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e81c3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e81c3-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e81c3-114">Attributes</span></span>  
 <span data-ttu-id="e81c3-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e81c3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e81c3-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e81c3-116">Child Elements</span></span>  
  
|<span data-ttu-id="e81c3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e81c3-117">Element</span></span>|<span data-ttu-id="e81c3-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e81c3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e81c3-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="e81c3-119">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="e81c3-120">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e81c3-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e81c3-121">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="e81c3-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e81c3-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e81c3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e81c3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e81c3-123">Element</span></span>|<span data-ttu-id="e81c3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e81c3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e81c3-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="e81c3-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e81c3-126">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="e81c3-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e81c3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e81c3-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e81c3-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e81c3-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e81c3-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e81c3-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
