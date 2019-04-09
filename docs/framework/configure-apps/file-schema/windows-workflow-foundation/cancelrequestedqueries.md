---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163163"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="573d7-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="573d7-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="573d7-102">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="573d7-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="573d7-103">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="573d7-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="573d7-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="573d7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="573d7-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="573d7-105">\<system.serviceModel></span></span>  
<span data-ttu-id="573d7-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="573d7-106">\<tracking></span></span>  
<span data-ttu-id="573d7-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="573d7-107">\<trackingProfile></span></span>  
<span data-ttu-id="573d7-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="573d7-108">\<workflow></span></span>  
<span data-ttu-id="573d7-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="573d7-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573d7-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="573d7-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="573d7-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="573d7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="573d7-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="573d7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="573d7-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="573d7-113">Attributes</span></span>  
 <span data-ttu-id="573d7-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="573d7-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="573d7-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="573d7-115">Child Elements</span></span>  
  
|<span data-ttu-id="573d7-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="573d7-116">Element</span></span>|<span data-ttu-id="573d7-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="573d7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="573d7-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="573d7-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="573d7-119">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="573d7-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="573d7-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="573d7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="573d7-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="573d7-121">Element</span></span>|<span data-ttu-id="573d7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="573d7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="573d7-123">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="573d7-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="573d7-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="573d7-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="573d7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="573d7-125">See also</span></span>

- [<span data-ttu-id="573d7-126">Rilevamento e traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="573d7-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="573d7-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="573d7-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
