---
title: '&lt;cancelRequestedQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f31663d44774f84feab76f22f19400a955a3cf8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="268dd-102">&lt;cancelRequestedQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="268dd-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="268dd-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="268dd-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="268dd-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="268dd-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="268dd-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="268dd-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="268dd-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="268dd-106">\<system.serviceModel></span></span>  
<span data-ttu-id="268dd-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="268dd-107">\<tracking></span></span>  
<span data-ttu-id="268dd-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="268dd-108">\<trackingProfile></span></span>  
<span data-ttu-id="268dd-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="268dd-109">\<workflow></span></span>  
<span data-ttu-id="268dd-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="268dd-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="268dd-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="268dd-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="268dd-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="268dd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="268dd-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="268dd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="268dd-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="268dd-114">Attributes</span></span>  
 <span data-ttu-id="268dd-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="268dd-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="268dd-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="268dd-116">Child Elements</span></span>  
  
|<span data-ttu-id="268dd-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="268dd-117">Element</span></span>|<span data-ttu-id="268dd-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="268dd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="268dd-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="268dd-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="268dd-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="268dd-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="268dd-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="268dd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="268dd-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="268dd-122">Element</span></span>|<span data-ttu-id="268dd-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="268dd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="268dd-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="268dd-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="268dd-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="268dd-125">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="268dd-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="268dd-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="268dd-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="268dd-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="268dd-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="268dd-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
