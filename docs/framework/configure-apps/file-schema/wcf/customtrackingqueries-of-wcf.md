---
title: '&lt;customTrackingQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d1d87a5b95d7679018c7e50af3c8e1c0265a3d4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="b0f84-102">&lt;customTrackingQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="b0f84-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="b0f84-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="b0f84-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="b0f84-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b0f84-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="b0f84-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b0f84-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="b0f84-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b0f84-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b0f84-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="b0f84-107">\<tracking></span></span>  
<span data-ttu-id="b0f84-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b0f84-108">\<trackingProfile></span></span>  
<span data-ttu-id="b0f84-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="b0f84-109">\<workflow></span></span>  
<span data-ttu-id="b0f84-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="b0f84-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f84-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0f84-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0f84-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b0f84-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b0f84-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b0f84-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0f84-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="b0f84-114">Attributes</span></span>  
 <span data-ttu-id="b0f84-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b0f84-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0f84-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b0f84-116">Child Elements</span></span>  
  
|<span data-ttu-id="b0f84-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0f84-117">Element</span></span>|<span data-ttu-id="b0f84-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0f84-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0f84-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="b0f84-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="b0f84-120">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="b0f84-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0f84-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b0f84-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b0f84-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0f84-122">Element</span></span>|<span data-ttu-id="b0f84-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0f84-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0f84-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="b0f84-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b0f84-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="b0f84-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0f84-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0f84-126">See Also</span></span>  
 <span data-ttu-id="b0f84-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b0f84-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="b0f84-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b0f84-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="b0f84-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b0f84-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b0f84-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b0f84-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
