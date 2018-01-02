---
title: '&lt;bookmarkResumptionQuery&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3240fcf026869aee7540c0e792ccd81e2592e620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="deeb4-102">&lt;bookmarkResumptionQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="deeb4-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="deeb4-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="deeb4-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="deeb4-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="deeb4-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="deeb4-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="deeb4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="deeb4-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="deeb4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="deeb4-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="deeb4-107">\<tracking></span></span>  
<span data-ttu-id="deeb4-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="deeb4-108">\<trackingProfile></span></span>  
<span data-ttu-id="deeb4-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="deeb4-109">\<workflow></span></span>  
<span data-ttu-id="deeb4-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="deeb4-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="deeb4-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="deeb4-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deeb4-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="deeb4-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="deeb4-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="deeb4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="deeb4-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="deeb4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="deeb4-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="deeb4-115">Attributes</span></span>  
  
|<span data-ttu-id="deeb4-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="deeb4-116">Attribute</span></span>|<span data-ttu-id="deeb4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="deeb4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="deeb4-118">name</span><span class="sxs-lookup"><span data-stu-id="deeb4-118">name</span></span>|<span data-ttu-id="deeb4-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="deeb4-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="deeb4-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="deeb4-120">Child Elements</span></span>  
 <span data-ttu-id="deeb4-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="deeb4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="deeb4-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="deeb4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="deeb4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="deeb4-123">Element</span></span>|<span data-ttu-id="deeb4-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="deeb4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="deeb4-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="deeb4-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="deeb4-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="deeb4-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="deeb4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deeb4-127">See Also</span></span>  
 <span data-ttu-id="deeb4-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="deeb4-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="deeb4-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="deeb4-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="deeb4-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="deeb4-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="deeb4-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="deeb4-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
