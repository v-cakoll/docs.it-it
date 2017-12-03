---
title: '&lt;customTrackingQuery&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 350ebbd0cc7be66f27ed2f70e1369e249267f359
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="28b3b-102">&lt;customTrackingQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="28b3b-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="28b3b-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="28b3b-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="28b3b-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="28b3b-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="28b3b-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="28b3b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="28b3b-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="28b3b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="28b3b-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="28b3b-107">\<tracking></span></span>  
<span data-ttu-id="28b3b-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="28b3b-108">\<trackingProfile></span></span>  
<span data-ttu-id="28b3b-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="28b3b-109">\<workflow></span></span>  
<span data-ttu-id="28b3b-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="28b3b-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="28b3b-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="28b3b-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28b3b-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28b3b-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28b3b-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="28b3b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="28b3b-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="28b3b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28b3b-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="28b3b-115">Attributes</span></span>  
  
|<span data-ttu-id="28b3b-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="28b3b-116">Attribute</span></span>|<span data-ttu-id="28b3b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28b3b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28b3b-118">activityName</span><span class="sxs-lookup"><span data-stu-id="28b3b-118">activityName</span></span>|<span data-ttu-id="28b3b-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="28b3b-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="28b3b-120">name</span><span class="sxs-lookup"><span data-stu-id="28b3b-120">name</span></span>|<span data-ttu-id="28b3b-121">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="28b3b-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28b3b-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="28b3b-122">Child Elements</span></span>  
 <span data-ttu-id="28b3b-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="28b3b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28b3b-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="28b3b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="28b3b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="28b3b-125">Element</span></span>|<span data-ttu-id="28b3b-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28b3b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28b3b-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="28b3b-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="28b3b-128">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="28b3b-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28b3b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28b3b-129">See Also</span></span>  
 <span data-ttu-id="28b3b-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="28b3b-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="28b3b-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="28b3b-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="28b3b-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="28b3b-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="28b3b-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="28b3b-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
