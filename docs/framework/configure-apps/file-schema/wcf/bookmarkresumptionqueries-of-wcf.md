---
title: '&lt;bookmarkResumptionQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 8a83f521e444838b6495221c00211710dd99ab6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753040"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="414d9-102">&lt;bookmarkResumptionQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="414d9-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="414d9-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="414d9-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="414d9-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="414d9-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="414d9-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="414d9-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="414d9-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="414d9-106">\<system.serviceModel></span></span>  
<span data-ttu-id="414d9-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="414d9-107">\<tracking></span></span>  
<span data-ttu-id="414d9-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="414d9-108">\<trackingProfile></span></span>  
<span data-ttu-id="414d9-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="414d9-109">\<workflow></span></span>  
<span data-ttu-id="414d9-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="414d9-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="414d9-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="414d9-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="414d9-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="414d9-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="414d9-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="414d9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="414d9-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="414d9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="414d9-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="414d9-115">Attributes</span></span>  
 <span data-ttu-id="414d9-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="414d9-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="414d9-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="414d9-117">Child Elements</span></span>  
  
|<span data-ttu-id="414d9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="414d9-118">Element</span></span>|<span data-ttu-id="414d9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="414d9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="414d9-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="414d9-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="414d9-121">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="414d9-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="414d9-122">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="414d9-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="414d9-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="414d9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="414d9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="414d9-124">Element</span></span>|<span data-ttu-id="414d9-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="414d9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="414d9-126">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="414d9-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="414d9-127">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="414d9-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="414d9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="414d9-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="414d9-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="414d9-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="414d9-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="414d9-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
