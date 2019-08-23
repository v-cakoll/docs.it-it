---
title: <bookmarkResumptionQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: ee8457645a0b54e21ef27c2891ebea97d6cc547b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926350"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="d73ac-102">\<> oggetto BookmarkResumptionQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="d73ac-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="d73ac-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d73ac-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d73ac-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="d73ac-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="d73ac-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d73ac-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="d73ac-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d73ac-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d73ac-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="d73ac-107">\<tracking></span></span>  
<span data-ttu-id="d73ac-108">\<profili ></span><span class="sxs-lookup"><span data-stu-id="d73ac-108">\<profiles></span></span>  
<span data-ttu-id="d73ac-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d73ac-109">\<trackingProfile></span></span>  
<span data-ttu-id="d73ac-110">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d73ac-110">\<workflow></span></span>  
<span data-ttu-id="d73ac-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="d73ac-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="d73ac-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="d73ac-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d73ac-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d73ac-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d73ac-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d73ac-114">Attributes and elements</span></span>

<span data-ttu-id="d73ac-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d73ac-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d73ac-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="d73ac-116">Attributes</span></span>  
  
|<span data-ttu-id="d73ac-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="d73ac-117">Attribute</span></span>|<span data-ttu-id="d73ac-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d73ac-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d73ac-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="d73ac-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d73ac-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d73ac-120">Child elements</span></span>

<span data-ttu-id="d73ac-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d73ac-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="d73ac-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d73ac-122">Parent elements</span></span>  
  
|<span data-ttu-id="d73ac-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d73ac-123">Element</span></span>|<span data-ttu-id="d73ac-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d73ac-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d73ac-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="d73ac-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="d73ac-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d73ac-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d73ac-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d73ac-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d73ac-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d73ac-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d73ac-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d73ac-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
