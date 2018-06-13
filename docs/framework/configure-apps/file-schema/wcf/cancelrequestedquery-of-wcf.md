---
title: '&lt;cancelRequestedQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 41964561a460babc41de755e213971593047b707
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748518"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="107a6-102">&lt;cancelRequestedQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="107a6-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="107a6-103">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="107a6-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="107a6-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="107a6-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="107a6-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="107a6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="107a6-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="107a6-106">\<system.serviceModel></span></span>  
<span data-ttu-id="107a6-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="107a6-107">\<tracking></span></span>  
<span data-ttu-id="107a6-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="107a6-108">\<trackingProfile></span></span>  
<span data-ttu-id="107a6-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="107a6-109">\<workflow></span></span>  
<span data-ttu-id="107a6-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="107a6-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="107a6-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="107a6-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="107a6-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="107a6-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="107a6-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="107a6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="107a6-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="107a6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="107a6-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="107a6-115">Attributes</span></span>  
  
|<span data-ttu-id="107a6-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="107a6-116">Attribute</span></span>|<span data-ttu-id="107a6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107a6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="107a6-118">activityName</span><span class="sxs-lookup"><span data-stu-id="107a6-118">activityName</span></span>|<span data-ttu-id="107a6-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="107a6-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="107a6-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="107a6-120">childActivityName</span></span>|<span data-ttu-id="107a6-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="107a6-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="107a6-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="107a6-122">Child Elements</span></span>  
 <span data-ttu-id="107a6-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="107a6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="107a6-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="107a6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="107a6-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="107a6-125">Element</span></span>|<span data-ttu-id="107a6-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107a6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="107a6-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="107a6-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="107a6-128">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="107a6-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="107a6-129">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="107a6-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="107a6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="107a6-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="107a6-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="107a6-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="107a6-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="107a6-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
