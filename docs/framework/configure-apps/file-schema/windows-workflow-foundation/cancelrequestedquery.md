---
title: '&lt;cancelRequestedQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: a3d24536589288ce9585901f3d955075bc856c97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520308"
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="0ffe0-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0ffe0-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="0ffe0-103">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0ffe0-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0ffe0-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0ffe0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0ffe0-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0ffe0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0ffe0-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="0ffe0-107">\<tracking></span></span>  
<span data-ttu-id="0ffe0-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0ffe0-108">\<trackingProfile></span></span>  
<span data-ttu-id="0ffe0-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="0ffe0-109">\<workflow></span></span>  
<span data-ttu-id="0ffe0-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="0ffe0-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="0ffe0-111">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="0ffe0-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ffe0-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ffe0-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ffe0-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ffe0-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0ffe0-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ffe0-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ffe0-115">Attributes</span></span>  
  
|<span data-ttu-id="0ffe0-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="0ffe0-116">Attribute</span></span>|<span data-ttu-id="0ffe0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ffe0-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ffe0-118">activityName</span><span class="sxs-lookup"><span data-stu-id="0ffe0-118">activityName</span></span>|<span data-ttu-id="0ffe0-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="0ffe0-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="0ffe0-120">childActivityName</span></span>|<span data-ttu-id="0ffe0-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ffe0-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ffe0-122">Child Elements</span></span>  
 <span data-ttu-id="0ffe0-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ffe0-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ffe0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0ffe0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ffe0-125">Element</span></span>|<span data-ttu-id="0ffe0-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ffe0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ffe0-127">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="0ffe0-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="0ffe0-128">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0ffe0-129">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ffe0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ffe0-130">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0ffe0-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0ffe0-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0ffe0-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0ffe0-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
