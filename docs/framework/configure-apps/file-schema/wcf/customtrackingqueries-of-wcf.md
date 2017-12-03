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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a7a69b481da7315c8d26b00c171d030f77d9b63
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="cc6e1-102">&lt;customTrackingQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="cc6e1-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="cc6e1-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="cc6e1-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="cc6e1-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="cc6e1-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="cc6e1-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cc6e1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="cc6e1-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cc6e1-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cc6e1-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="cc6e1-107">\<tracking></span></span>  
<span data-ttu-id="cc6e1-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="cc6e1-108">\<trackingProfile></span></span>  
<span data-ttu-id="cc6e1-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="cc6e1-109">\<workflow></span></span>  
<span data-ttu-id="cc6e1-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="cc6e1-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc6e1-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc6e1-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc6e1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cc6e1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cc6e1-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cc6e1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc6e1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="cc6e1-114">Attributes</span></span>  
 <span data-ttu-id="cc6e1-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cc6e1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cc6e1-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cc6e1-116">Child Elements</span></span>  
  
|<span data-ttu-id="cc6e1-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc6e1-117">Element</span></span>|<span data-ttu-id="cc6e1-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc6e1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc6e1-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="cc6e1-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="cc6e1-120">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="cc6e1-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc6e1-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cc6e1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cc6e1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc6e1-122">Element</span></span>|<span data-ttu-id="cc6e1-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc6e1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc6e1-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="cc6e1-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="cc6e1-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="cc6e1-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc6e1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc6e1-126">See Also</span></span>  
 <span data-ttu-id="cc6e1-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cc6e1-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="cc6e1-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cc6e1-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="cc6e1-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cc6e1-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cc6e1-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="cc6e1-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
