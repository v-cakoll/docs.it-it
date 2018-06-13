---
title: '&lt;bookmarkResumptionQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 083b42efdd2b10dad870b6590fc20331a090f8aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748256"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="27f65-102">&lt;bookmarkResumptionQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="27f65-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="27f65-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="27f65-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="27f65-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="27f65-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="27f65-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="27f65-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="27f65-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="27f65-106">\<system.serviceModel></span></span>  
<span data-ttu-id="27f65-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="27f65-107">\<tracking></span></span>  
<span data-ttu-id="27f65-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="27f65-108">\<trackingProfile></span></span>  
<span data-ttu-id="27f65-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="27f65-109">\<workflow></span></span>  
<span data-ttu-id="27f65-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="27f65-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="27f65-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="27f65-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f65-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27f65-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="27f65-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="27f65-113">Attributes and Elements</span></span>  
 <span data-ttu-id="27f65-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="27f65-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27f65-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="27f65-115">Attributes</span></span>  
  
|<span data-ttu-id="27f65-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="27f65-116">Attribute</span></span>|<span data-ttu-id="27f65-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27f65-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27f65-118">name</span><span class="sxs-lookup"><span data-stu-id="27f65-118">name</span></span>|<span data-ttu-id="27f65-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="27f65-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27f65-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="27f65-120">Child Elements</span></span>  
 <span data-ttu-id="27f65-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="27f65-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27f65-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="27f65-122">Parent Elements</span></span>  
  
|<span data-ttu-id="27f65-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="27f65-123">Element</span></span>|<span data-ttu-id="27f65-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27f65-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27f65-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="27f65-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="27f65-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="27f65-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27f65-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27f65-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="27f65-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="27f65-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="27f65-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="27f65-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
