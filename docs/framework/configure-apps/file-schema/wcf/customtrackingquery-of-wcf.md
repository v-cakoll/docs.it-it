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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c88a5d0e15acf67061976826a65faf5bfacb8384
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="3839f-102">&lt;customTrackingQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="3839f-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="3839f-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="3839f-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="3839f-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3839f-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="3839f-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3839f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="3839f-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3839f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3839f-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="3839f-107">\<tracking></span></span>  
<span data-ttu-id="3839f-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3839f-108">\<trackingProfile></span></span>  
<span data-ttu-id="3839f-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="3839f-109">\<workflow></span></span>  
<span data-ttu-id="3839f-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="3839f-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="3839f-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="3839f-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3839f-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3839f-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3839f-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3839f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3839f-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3839f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3839f-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="3839f-115">Attributes</span></span>  
  
|<span data-ttu-id="3839f-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="3839f-116">Attribute</span></span>|<span data-ttu-id="3839f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3839f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3839f-118">activityName</span><span class="sxs-lookup"><span data-stu-id="3839f-118">activityName</span></span>|<span data-ttu-id="3839f-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="3839f-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="3839f-120">name</span><span class="sxs-lookup"><span data-stu-id="3839f-120">name</span></span>|<span data-ttu-id="3839f-121">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="3839f-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3839f-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3839f-122">Child Elements</span></span>  
 <span data-ttu-id="3839f-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3839f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3839f-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3839f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3839f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3839f-125">Element</span></span>|<span data-ttu-id="3839f-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3839f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3839f-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="3839f-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="3839f-128">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="3839f-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3839f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3839f-129">See Also</span></span>  
 <span data-ttu-id="3839f-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3839f-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="3839f-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3839f-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3839f-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3839f-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3839f-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3839f-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
