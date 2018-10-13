---
title: '&lt;bookmarkResumptionQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: f0721e7e14d543b1ff212fe59ed6a2de0a8a9968
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308430"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="2187e-102">&lt;bookmarkResumptionQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="2187e-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>

<span data-ttu-id="2187e-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2187e-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2187e-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="2187e-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="2187e-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2187e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="2187e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2187e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2187e-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="2187e-107">\<tracking></span></span>  
<span data-ttu-id="2187e-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="2187e-108">\<profiles></span></span>  
<span data-ttu-id="2187e-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2187e-109">\<trackingProfile></span></span>  
<span data-ttu-id="2187e-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="2187e-110">\<workflow></span></span>  
<span data-ttu-id="2187e-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="2187e-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="2187e-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="2187e-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2187e-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2187e-113">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="2187e-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2187e-114">Attributes and elements</span></span>

<span data-ttu-id="2187e-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2187e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2187e-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="2187e-116">Attributes</span></span>  
  
|<span data-ttu-id="2187e-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="2187e-117">Attribute</span></span>|<span data-ttu-id="2187e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2187e-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="2187e-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="2187e-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2187e-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2187e-120">Child elements</span></span>

<span data-ttu-id="2187e-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2187e-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="2187e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2187e-122">Parent elements</span></span>  
  
|<span data-ttu-id="2187e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="2187e-123">Element</span></span>|<span data-ttu-id="2187e-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2187e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2187e-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="2187e-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="2187e-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2187e-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2187e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2187e-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2187e-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2187e-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2187e-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2187e-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
