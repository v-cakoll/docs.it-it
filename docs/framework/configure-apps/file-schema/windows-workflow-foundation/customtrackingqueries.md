---
title: '&lt;customTrackingQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 19a4a58a15db72129f17655e7043f2ee3ae7ffa2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="6d0a4-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="6d0a4-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="6d0a4-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6d0a4-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6d0a4-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6d0a4-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="6d0a4-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6d0a4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6d0a4-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6d0a4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6d0a4-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="6d0a4-107">\<tracking></span></span>  
<span data-ttu-id="6d0a4-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6d0a4-108">\<trackingProfile></span></span>  
<span data-ttu-id="6d0a4-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="6d0a4-109">\<workflow></span></span>  
<span data-ttu-id="6d0a4-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="6d0a4-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d0a4-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d0a4-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d0a4-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6d0a4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6d0a4-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6d0a4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d0a4-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="6d0a4-114">Attributes</span></span>  
 <span data-ttu-id="6d0a4-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6d0a4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6d0a4-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6d0a4-116">Child Elements</span></span>  
  
|<span data-ttu-id="6d0a4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d0a4-117">Element</span></span>|<span data-ttu-id="6d0a4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d0a4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d0a4-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="6d0a4-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="6d0a4-120">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6d0a4-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d0a4-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6d0a4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6d0a4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d0a4-122">Element</span></span>|<span data-ttu-id="6d0a4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d0a4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d0a4-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="6d0a4-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6d0a4-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d0a4-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d0a4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d0a4-126">See Also</span></span>  
 <span data-ttu-id="6d0a4-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d0a4-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="6d0a4-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d0a4-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="6d0a4-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6d0a4-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6d0a4-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6d0a4-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
