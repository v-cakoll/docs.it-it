---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: d9c3f91edb41bd034bcd978b075d62f74b6e308d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945876"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="eb1e6-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="eb1e6-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="eb1e6-102">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="eb1e6-103">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="eb1e6-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="eb1e6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="eb1e6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eb1e6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="eb1e6-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="eb1e6-106">\<tracking></span></span>  
<span data-ttu-id="eb1e6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="eb1e6-107">\<trackingProfile></span></span>  
<span data-ttu-id="eb1e6-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eb1e6-108">\<workflow></span></span>  
<span data-ttu-id="eb1e6-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="eb1e6-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="eb1e6-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="eb1e6-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb1e6-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb1e6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb1e6-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eb1e6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="eb1e6-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb1e6-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="eb1e6-114">Attributes</span></span>  
  
|<span data-ttu-id="eb1e6-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="eb1e6-115">Attribute</span></span>|<span data-ttu-id="eb1e6-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb1e6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb1e6-117">activityName</span><span class="sxs-lookup"><span data-stu-id="eb1e6-117">activityName</span></span>|<span data-ttu-id="eb1e6-118">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="eb1e6-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="eb1e6-119">childActivityName</span></span>|<span data-ttu-id="eb1e6-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb1e6-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eb1e6-121">Child Elements</span></span>  
 <span data-ttu-id="eb1e6-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb1e6-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eb1e6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eb1e6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb1e6-124">Element</span></span>|<span data-ttu-id="eb1e6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb1e6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb1e6-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="eb1e6-126">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="eb1e6-127">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="eb1e6-128">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb1e6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb1e6-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eb1e6-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eb1e6-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eb1e6-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="eb1e6-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
