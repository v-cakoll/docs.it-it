---
title: '&lt;cancelRequestedQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e532ea482108c9a5cabe13a99afddca10f8341d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="90e5c-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="90e5c-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="90e5c-103">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="90e5c-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="90e5c-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="90e5c-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="90e5c-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="90e5c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="90e5c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90e5c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="90e5c-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="90e5c-107">\<tracking></span></span>  
<span data-ttu-id="90e5c-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="90e5c-108">\<trackingProfile></span></span>  
<span data-ttu-id="90e5c-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="90e5c-109">\<workflow></span></span>  
<span data-ttu-id="90e5c-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="90e5c-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="90e5c-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="90e5c-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e5c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90e5c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90e5c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90e5c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="90e5c-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90e5c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90e5c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="90e5c-115">Attributes</span></span>  
  
|<span data-ttu-id="90e5c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="90e5c-116">Attribute</span></span>|<span data-ttu-id="90e5c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90e5c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90e5c-118">activityName</span><span class="sxs-lookup"><span data-stu-id="90e5c-118">activityName</span></span>|<span data-ttu-id="90e5c-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="90e5c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="90e5c-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="90e5c-120">childActivityName</span></span>|<span data-ttu-id="90e5c-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="90e5c-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90e5c-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90e5c-122">Child Elements</span></span>  
 <span data-ttu-id="90e5c-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90e5c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90e5c-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90e5c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="90e5c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="90e5c-125">Element</span></span>|<span data-ttu-id="90e5c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90e5c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90e5c-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="90e5c-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="90e5c-128">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="90e5c-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="90e5c-129">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="90e5c-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90e5c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90e5c-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="90e5c-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="90e5c-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="90e5c-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="90e5c-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
