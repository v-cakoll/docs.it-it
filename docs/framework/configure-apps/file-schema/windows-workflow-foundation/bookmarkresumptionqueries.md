---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: ae6a81123379ecd0e7fdc72f4e115a462f81eb90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555037"
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="4aedf-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="4aedf-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="4aedf-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4aedf-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4aedf-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="4aedf-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="4aedf-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4aedf-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4aedf-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4aedf-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4aedf-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4aedf-107">\<tracking></span></span>  
<span data-ttu-id="4aedf-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4aedf-108">\<trackingProfile></span></span>  
<span data-ttu-id="4aedf-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="4aedf-109">\<workflow></span></span>  
<span data-ttu-id="4aedf-110">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="4aedf-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="4aedf-111">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="4aedf-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aedf-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aedf-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aedf-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4aedf-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4aedf-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4aedf-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aedf-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="4aedf-115">Attributes</span></span>  
 <span data-ttu-id="4aedf-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4aedf-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4aedf-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4aedf-117">Child Elements</span></span>  
  
|<span data-ttu-id="4aedf-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4aedf-118">Element</span></span>|<span data-ttu-id="4aedf-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aedf-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4aedf-120">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="4aedf-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="4aedf-121">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4aedf-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4aedf-122">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="4aedf-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4aedf-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4aedf-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4aedf-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4aedf-124">Element</span></span>|<span data-ttu-id="4aedf-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aedf-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4aedf-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4aedf-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="4aedf-127">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="4aedf-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4aedf-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aedf-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4aedf-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4aedf-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4aedf-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4aedf-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
