---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 628dbf801cae5f61dc7d518c27df3380dd2d3d23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945941"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="1cc47-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="1cc47-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="1cc47-102">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="1cc47-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1cc47-103">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="1cc47-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="1cc47-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1cc47-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1cc47-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1cc47-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1cc47-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="1cc47-106">\<tracking></span></span>  
<span data-ttu-id="1cc47-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1cc47-107">\<trackingProfile></span></span>  
<span data-ttu-id="1cc47-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1cc47-108">\<workflow></span></span>  
<span data-ttu-id="1cc47-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="1cc47-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc47-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cc47-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cc47-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1cc47-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1cc47-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1cc47-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cc47-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1cc47-113">Attributes</span></span>  
 <span data-ttu-id="1cc47-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1cc47-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1cc47-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1cc47-115">Child Elements</span></span>  
  
|<span data-ttu-id="1cc47-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cc47-116">Element</span></span>|<span data-ttu-id="1cc47-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cc47-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cc47-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="1cc47-118">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="1cc47-119">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="1cc47-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1cc47-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1cc47-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1cc47-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cc47-121">Element</span></span>|<span data-ttu-id="1cc47-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cc47-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cc47-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1cc47-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1cc47-124">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="1cc47-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cc47-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cc47-125">See also</span></span>

- [<span data-ttu-id="1cc47-126">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1cc47-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1cc47-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="1cc47-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
