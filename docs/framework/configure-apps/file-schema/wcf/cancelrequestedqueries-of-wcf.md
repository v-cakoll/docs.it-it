---
title: '&lt;cancelRequestedQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 9cf2761bdab36d95b5077e36174565659230b512
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145445"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="a3050-102">&lt;cancelRequestedQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="a3050-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="a3050-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="a3050-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a3050-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="a3050-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="a3050-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a3050-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a3050-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a3050-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a3050-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="a3050-107">\<tracking></span></span>  
<span data-ttu-id="a3050-108">\<i profili > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a3050-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="a3050-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="a3050-109">\<workflow></span></span>  
<span data-ttu-id="a3050-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="a3050-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3050-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3050-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3050-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a3050-112">Attributes and elements</span></span>  

<span data-ttu-id="a3050-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a3050-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3050-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="a3050-114">Attributes</span></span>

<span data-ttu-id="a3050-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a3050-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="a3050-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a3050-116">Child elements</span></span>
  
|<span data-ttu-id="a3050-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3050-117">Element</span></span>|<span data-ttu-id="a3050-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3050-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3050-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="a3050-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="a3050-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="a3050-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3050-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a3050-121">Parent elements</span></span>  
  
|<span data-ttu-id="a3050-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3050-122">Element</span></span>|<span data-ttu-id="a3050-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3050-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3050-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="a3050-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a3050-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="a3050-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3050-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3050-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="a3050-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a3050-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a3050-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="a3050-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
