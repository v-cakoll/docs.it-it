---
title: <cancelRequestedQueries>di WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 0f04fc928358c96ca3112422f1a6ccd039269e47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926241"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="156df-102">\<> cancelRequestedQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="156df-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="156df-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="156df-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="156df-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="156df-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="156df-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="156df-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="156df-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="156df-106">\<system.serviceModel></span></span>  
<span data-ttu-id="156df-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="156df-107">\<tracking></span></span>  
<span data-ttu-id="156df-108">\<profili > \<> TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="156df-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="156df-109">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="156df-109">\<workflow></span></span>  
<span data-ttu-id="156df-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="156df-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="156df-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="156df-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="156df-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="156df-112">Attributes and elements</span></span>  

<span data-ttu-id="156df-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="156df-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="156df-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="156df-114">Attributes</span></span>

<span data-ttu-id="156df-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="156df-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="156df-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="156df-116">Child elements</span></span>
  
|<span data-ttu-id="156df-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="156df-117">Element</span></span>|<span data-ttu-id="156df-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="156df-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="156df-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="156df-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="156df-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="156df-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="156df-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="156df-121">Parent elements</span></span>  
  
|<span data-ttu-id="156df-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="156df-122">Element</span></span>|<span data-ttu-id="156df-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="156df-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="156df-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="156df-124">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="156df-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="156df-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="156df-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="156df-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="156df-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="156df-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="156df-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="156df-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
