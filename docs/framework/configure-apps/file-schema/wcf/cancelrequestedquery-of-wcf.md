---
title: '&lt;cancelRequestedQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 38d946a213131e8dcb6f4100d0ad67f7c167f342
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086401"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="dda09-102">&lt;cancelRequestedQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="dda09-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="dda09-103">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="dda09-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="dda09-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="dda09-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="dda09-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dda09-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="dda09-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dda09-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dda09-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dda09-107">\<tracking></span></span>  
<span data-ttu-id="dda09-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dda09-108">\<trackingProfile></span></span>  
<span data-ttu-id="dda09-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="dda09-109">\<workflow></span></span>  
<span data-ttu-id="dda09-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="dda09-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="dda09-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="dda09-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda09-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dda09-112">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="dda09-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dda09-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dda09-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dda09-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dda09-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="dda09-115">Attributes</span></span>  
  
|<span data-ttu-id="dda09-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="dda09-116">Attribute</span></span>|<span data-ttu-id="dda09-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dda09-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dda09-118">activityName</span><span class="sxs-lookup"><span data-stu-id="dda09-118">activityName</span></span>|<span data-ttu-id="dda09-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="dda09-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="dda09-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="dda09-120">childActivityName</span></span>|<span data-ttu-id="dda09-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="dda09-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dda09-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dda09-122">Child Elements</span></span>  
 <span data-ttu-id="dda09-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dda09-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dda09-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dda09-124">Parent Elements</span></span>  
  
|<span data-ttu-id="dda09-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="dda09-125">Element</span></span>|<span data-ttu-id="dda09-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dda09-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dda09-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="dda09-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="dda09-128">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="dda09-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="dda09-129">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="dda09-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dda09-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dda09-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="dda09-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dda09-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dda09-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dda09-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
