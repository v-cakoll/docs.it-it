---
title: '&lt;bookmarkResumptionQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: d2b3365f3793c114003bbd9b9da664448bbac243
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147646"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="af17f-102">&lt;bookmarkResumptionQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="af17f-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>

<span data-ttu-id="af17f-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="af17f-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="af17f-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="af17f-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="af17f-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="af17f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="af17f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="af17f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="af17f-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="af17f-107">\<tracking></span></span>  
<span data-ttu-id="af17f-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="af17f-108">\<profiles></span></span>  
<span data-ttu-id="af17f-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="af17f-109">\<trackingProfile></span></span>  
<span data-ttu-id="af17f-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="af17f-110">\<workflow></span></span>  
<span data-ttu-id="af17f-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="af17f-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="af17f-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="af17f-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af17f-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af17f-113">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="af17f-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af17f-114">Attributes and elements</span></span>

<span data-ttu-id="af17f-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af17f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af17f-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="af17f-116">Attributes</span></span>

<span data-ttu-id="af17f-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="af17f-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af17f-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af17f-118">Child elements</span></span>  
  
|<span data-ttu-id="af17f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="af17f-119">Element</span></span>|<span data-ttu-id="af17f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af17f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af17f-121">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="af17f-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="af17f-122">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="af17f-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="af17f-123">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="af17f-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af17f-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af17f-124">Parent elements</span></span>  
  
|<span data-ttu-id="af17f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="af17f-125">Element</span></span>|<span data-ttu-id="af17f-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af17f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af17f-127">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="af17f-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="af17f-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="af17f-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af17f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af17f-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType> 
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="af17f-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="af17f-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="af17f-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="af17f-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
