---
title: '&lt;bookmarkResumptionQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 07215347da19a05d5915296668d990853fdae646
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087791"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="aa8e7-102">&lt;bookmarkResumptionQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="aa8e7-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="aa8e7-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="aa8e7-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="aa8e7-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="aa8e7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="aa8e7-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aa8e7-106">\<system.serviceModel></span></span>  
<span data-ttu-id="aa8e7-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="aa8e7-107">\<tracking></span></span>  
<span data-ttu-id="aa8e7-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="aa8e7-108">\<trackingProfile></span></span>  
<span data-ttu-id="aa8e7-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="aa8e7-109">\<workflow></span></span>  
<span data-ttu-id="aa8e7-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="aa8e7-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="aa8e7-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="aa8e7-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8e7-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa8e7-112">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="aa8e7-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aa8e7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="aa8e7-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa8e7-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="aa8e7-115">Attributes</span></span>  
  
|<span data-ttu-id="aa8e7-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="aa8e7-116">Attribute</span></span>|<span data-ttu-id="aa8e7-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa8e7-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa8e7-118">name</span><span class="sxs-lookup"><span data-stu-id="aa8e7-118">name</span></span>|<span data-ttu-id="aa8e7-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa8e7-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aa8e7-120">Child Elements</span></span>  
 <span data-ttu-id="aa8e7-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa8e7-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aa8e7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="aa8e7-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa8e7-123">Element</span></span>|<span data-ttu-id="aa8e7-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa8e7-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa8e7-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="aa8e7-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="aa8e7-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aa8e7-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa8e7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa8e7-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="aa8e7-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aa8e7-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="aa8e7-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="aa8e7-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
