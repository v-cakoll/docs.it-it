---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 5bc2e3ffeb93bdfcd45638d6b50e218c03706f42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520685"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="6d08c-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="6d08c-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="6d08c-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="6d08c-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6d08c-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="6d08c-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="6d08c-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6d08c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6d08c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6d08c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6d08c-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6d08c-107">\<tracking></span></span>  
<span data-ttu-id="6d08c-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6d08c-108">\<trackingProfile></span></span>  
<span data-ttu-id="6d08c-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="6d08c-109">\<workflow></span></span>  
<span data-ttu-id="6d08c-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="6d08c-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d08c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d08c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d08c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6d08c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6d08c-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6d08c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d08c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="6d08c-114">Attributes</span></span>  
 <span data-ttu-id="6d08c-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6d08c-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6d08c-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6d08c-116">Child Elements</span></span>  
  
|<span data-ttu-id="6d08c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d08c-117">Element</span></span>|<span data-ttu-id="6d08c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d08c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d08c-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="6d08c-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="6d08c-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="6d08c-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d08c-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6d08c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6d08c-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d08c-122">Element</span></span>|<span data-ttu-id="6d08c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d08c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d08c-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6d08c-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6d08c-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d08c-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d08c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d08c-126">See also</span></span>
- [<span data-ttu-id="6d08c-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6d08c-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6d08c-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6d08c-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
