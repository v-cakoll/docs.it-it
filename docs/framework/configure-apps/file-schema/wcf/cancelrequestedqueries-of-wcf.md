---
title: '&lt;cancelRequestedQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 4d746290f01e702979d1dd0165ad3fc5299e1b75
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087752"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="7d479-102">&lt;cancelRequestedQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="7d479-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="7d479-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="7d479-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7d479-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="7d479-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="7d479-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7d479-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="7d479-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7d479-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7d479-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="7d479-107">\<tracking></span></span>  
<span data-ttu-id="7d479-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7d479-108">\<trackingProfile></span></span>  
<span data-ttu-id="7d479-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="7d479-109">\<workflow></span></span>  
<span data-ttu-id="7d479-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="7d479-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d479-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d479-111">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="7d479-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d479-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7d479-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d479-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d479-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d479-114">Attributes</span></span>  
 <span data-ttu-id="7d479-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7d479-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d479-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d479-116">Child Elements</span></span>  
  
|<span data-ttu-id="7d479-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d479-117">Element</span></span>|<span data-ttu-id="7d479-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d479-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d479-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="7d479-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="7d479-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="7d479-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d479-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d479-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7d479-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d479-122">Element</span></span>|<span data-ttu-id="7d479-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d479-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d479-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="7d479-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="7d479-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="7d479-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d479-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d479-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="7d479-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="7d479-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7d479-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="7d479-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
