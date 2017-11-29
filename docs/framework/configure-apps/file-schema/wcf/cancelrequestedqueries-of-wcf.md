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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7a5501965f746fe85ad07e396f005beb8e12f3d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="bdc05-102">&lt;cancelRequestedQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="bdc05-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="bdc05-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="bdc05-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="bdc05-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="bdc05-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="bdc05-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bdc05-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="bdc05-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bdc05-106">\<system.serviceModel></span></span>  
<span data-ttu-id="bdc05-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="bdc05-107">\<tracking></span></span>  
<span data-ttu-id="bdc05-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="bdc05-108">\<trackingProfile></span></span>  
<span data-ttu-id="bdc05-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="bdc05-109">\<workflow></span></span>  
<span data-ttu-id="bdc05-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="bdc05-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc05-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdc05-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bdc05-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bdc05-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bdc05-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bdc05-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdc05-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="bdc05-114">Attributes</span></span>  
 <span data-ttu-id="bdc05-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bdc05-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bdc05-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bdc05-116">Child Elements</span></span>  
  
|<span data-ttu-id="bdc05-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdc05-117">Element</span></span>|<span data-ttu-id="bdc05-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdc05-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdc05-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="bdc05-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="bdc05-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="bdc05-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bdc05-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bdc05-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bdc05-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdc05-122">Element</span></span>|<span data-ttu-id="bdc05-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdc05-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdc05-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="bdc05-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="bdc05-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="bdc05-125">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdc05-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdc05-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="bdc05-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="bdc05-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="bdc05-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="bdc05-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
