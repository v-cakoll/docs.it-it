---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: a5eb00d1e094484e3ec01e0db18719ec50e4b953
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515069"
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="fdf6c-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="fdf6c-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="fdf6c-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="fdf6c-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="fdf6c-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fdf6c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="fdf6c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fdf6c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="fdf6c-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="fdf6c-107">\<tracking></span></span>  
<span data-ttu-id="fdf6c-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="fdf6c-108">\<trackingProfile></span></span>  
<span data-ttu-id="fdf6c-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="fdf6c-109">\<workflow></span></span>  
<span data-ttu-id="fdf6c-110">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="fdf6c-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="fdf6c-111">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="fdf6c-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf6c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdf6c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdf6c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fdf6c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fdf6c-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdf6c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="fdf6c-115">Attributes</span></span>  
  
|<span data-ttu-id="fdf6c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="fdf6c-116">Attribute</span></span>|<span data-ttu-id="fdf6c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdf6c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdf6c-118">name</span><span class="sxs-lookup"><span data-stu-id="fdf6c-118">name</span></span>|<span data-ttu-id="fdf6c-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdf6c-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fdf6c-120">Child Elements</span></span>  
 <span data-ttu-id="fdf6c-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fdf6c-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fdf6c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fdf6c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdf6c-123">Element</span></span>|<span data-ttu-id="fdf6c-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdf6c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdf6c-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="fdf6c-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="fdf6c-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fdf6c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdf6c-127">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fdf6c-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fdf6c-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fdf6c-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="fdf6c-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
