---
title: '&lt;bookmarkResumptionQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 6463404e17edff8eb1efe3f96e44b5b9997ffca3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147811"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="f1c98-102">&lt;bookmarkResumptionQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="f1c98-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>

<span data-ttu-id="f1c98-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1c98-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f1c98-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="f1c98-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="f1c98-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f1c98-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="f1c98-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f1c98-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f1c98-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="f1c98-107">\<tracking></span></span>  
<span data-ttu-id="f1c98-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="f1c98-108">\<profiles></span></span>  
<span data-ttu-id="f1c98-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f1c98-109">\<trackingProfile></span></span>  
<span data-ttu-id="f1c98-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="f1c98-110">\<workflow></span></span>  
<span data-ttu-id="f1c98-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="f1c98-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="f1c98-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="f1c98-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c98-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1c98-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1c98-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1c98-114">Attributes and elements</span></span>

<span data-ttu-id="f1c98-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f1c98-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1c98-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1c98-116">Attributes</span></span>  
  
|<span data-ttu-id="f1c98-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="f1c98-117">Attribute</span></span>|<span data-ttu-id="f1c98-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1c98-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="f1c98-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="f1c98-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1c98-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1c98-120">Child elements</span></span>

<span data-ttu-id="f1c98-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f1c98-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="f1c98-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1c98-122">Parent elements</span></span>  
  
|<span data-ttu-id="f1c98-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1c98-123">Element</span></span>|<span data-ttu-id="f1c98-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1c98-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1c98-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="f1c98-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="f1c98-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1c98-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1c98-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1c98-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f1c98-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f1c98-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f1c98-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f1c98-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
