---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e52b4ef5104397d3c4b8abc89a1d637b17fcde9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="20115-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="20115-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="20115-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="20115-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="20115-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="20115-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="20115-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="20115-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="20115-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="20115-106">\<system.serviceModel></span></span>  
<span data-ttu-id="20115-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="20115-107">\<tracking></span></span>  
<span data-ttu-id="20115-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="20115-108">\<trackingProfile></span></span>  
<span data-ttu-id="20115-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="20115-109">\<workflow></span></span>  
<span data-ttu-id="20115-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="20115-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="20115-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="20115-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20115-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20115-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20115-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="20115-113">Attributes and Elements</span></span>  
 <span data-ttu-id="20115-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="20115-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20115-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="20115-115">Attributes</span></span>  
  
|<span data-ttu-id="20115-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="20115-116">Attribute</span></span>|<span data-ttu-id="20115-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20115-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20115-118">name</span><span class="sxs-lookup"><span data-stu-id="20115-118">name</span></span>|<span data-ttu-id="20115-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="20115-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20115-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="20115-120">Child Elements</span></span>  
 <span data-ttu-id="20115-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="20115-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20115-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="20115-122">Parent Elements</span></span>  
  
|<span data-ttu-id="20115-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="20115-123">Element</span></span>|<span data-ttu-id="20115-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20115-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20115-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="20115-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="20115-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="20115-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20115-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20115-127">See Also</span></span>  
 <span data-ttu-id="20115-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="20115-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="20115-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="20115-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="20115-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="20115-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="20115-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="20115-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
