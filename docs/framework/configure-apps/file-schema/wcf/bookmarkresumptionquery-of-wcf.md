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
ms.openlocfilehash: 124b05d8e1ce9831a1efb3c6e62cc5e9fd3058fc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="065f4-102">&lt;bookmarkResumptionQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="065f4-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="065f4-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="065f4-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="065f4-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="065f4-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="065f4-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="065f4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="065f4-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="065f4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="065f4-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="065f4-107">\<tracking></span></span>  
<span data-ttu-id="065f4-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="065f4-108">\<trackingProfile></span></span>  
<span data-ttu-id="065f4-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="065f4-109">\<workflow></span></span>  
<span data-ttu-id="065f4-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="065f4-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="065f4-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="065f4-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="065f4-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="065f4-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="065f4-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="065f4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="065f4-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="065f4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="065f4-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="065f4-115">Attributes</span></span>  
  
|<span data-ttu-id="065f4-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="065f4-116">Attribute</span></span>|<span data-ttu-id="065f4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="065f4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="065f4-118">name</span><span class="sxs-lookup"><span data-stu-id="065f4-118">name</span></span>|<span data-ttu-id="065f4-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="065f4-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="065f4-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="065f4-120">Child Elements</span></span>  
 <span data-ttu-id="065f4-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="065f4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="065f4-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="065f4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="065f4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="065f4-123">Element</span></span>|<span data-ttu-id="065f4-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="065f4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="065f4-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="065f4-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="065f4-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="065f4-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="065f4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="065f4-127">See Also</span></span>  
 <span data-ttu-id="065f4-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="065f4-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="065f4-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="065f4-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="065f4-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="065f4-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="065f4-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="065f4-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
