---
title: '&lt;cancelRequestedQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e1697b245f9ab61cab3e4b26b1756259f0eba9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="29dfc-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="29dfc-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="29dfc-103">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="29dfc-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="29dfc-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="29dfc-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="29dfc-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="29dfc-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="29dfc-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="29dfc-106">\<system.serviceModel></span></span>  
<span data-ttu-id="29dfc-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="29dfc-107">\<tracking></span></span>  
<span data-ttu-id="29dfc-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="29dfc-108">\<trackingProfile></span></span>  
<span data-ttu-id="29dfc-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="29dfc-109">\<workflow></span></span>  
<span data-ttu-id="29dfc-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="29dfc-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="29dfc-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="29dfc-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29dfc-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29dfc-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29dfc-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="29dfc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="29dfc-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="29dfc-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29dfc-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="29dfc-115">Attributes</span></span>  
  
|<span data-ttu-id="29dfc-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="29dfc-116">Attribute</span></span>|<span data-ttu-id="29dfc-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29dfc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29dfc-118">activityName</span><span class="sxs-lookup"><span data-stu-id="29dfc-118">activityName</span></span>|<span data-ttu-id="29dfc-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="29dfc-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="29dfc-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="29dfc-120">childActivityName</span></span>|<span data-ttu-id="29dfc-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="29dfc-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29dfc-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="29dfc-122">Child Elements</span></span>  
 <span data-ttu-id="29dfc-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="29dfc-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29dfc-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="29dfc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="29dfc-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="29dfc-125">Element</span></span>|<span data-ttu-id="29dfc-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29dfc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29dfc-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="29dfc-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="29dfc-128">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="29dfc-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="29dfc-129">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="29dfc-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29dfc-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29dfc-130">See Also</span></span>  
 <span data-ttu-id="29dfc-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="29dfc-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="29dfc-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="29dfc-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="29dfc-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="29dfc-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="29dfc-134">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="29dfc-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
