---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215313"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="05c85-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="05c85-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="05c85-102">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="05c85-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="05c85-103">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="05c85-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="05c85-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="05c85-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="05c85-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="05c85-105">\<system.serviceModel></span></span>  
<span data-ttu-id="05c85-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="05c85-106">\<tracking></span></span>  
<span data-ttu-id="05c85-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="05c85-107">\<trackingProfile></span></span>  
<span data-ttu-id="05c85-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="05c85-108">\<workflow></span></span>  
<span data-ttu-id="05c85-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="05c85-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="05c85-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="05c85-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c85-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05c85-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05c85-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="05c85-112">Attributes and Elements</span></span>  
 <span data-ttu-id="05c85-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="05c85-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05c85-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="05c85-114">Attributes</span></span>  
  
|<span data-ttu-id="05c85-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="05c85-115">Attribute</span></span>|<span data-ttu-id="05c85-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05c85-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05c85-117">activityName</span><span class="sxs-lookup"><span data-stu-id="05c85-117">activityName</span></span>|<span data-ttu-id="05c85-118">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="05c85-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="05c85-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="05c85-119">childActivityName</span></span>|<span data-ttu-id="05c85-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="05c85-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05c85-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="05c85-121">Child Elements</span></span>  
 <span data-ttu-id="05c85-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="05c85-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05c85-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="05c85-123">Parent Elements</span></span>  
  
|<span data-ttu-id="05c85-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="05c85-124">Element</span></span>|<span data-ttu-id="05c85-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05c85-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c85-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="05c85-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="05c85-127">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="05c85-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="05c85-128">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="05c85-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05c85-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05c85-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="05c85-130">Rilevamento e traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="05c85-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="05c85-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="05c85-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
