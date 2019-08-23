---
title: <cancelRequestedQuery>di WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 7952520edbf799e5fab6864e50962c6ec2860928
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919653"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="89d9e-102">\<> cancelRequestedQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="89d9e-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="89d9e-103">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="89d9e-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="89d9e-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="89d9e-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="89d9e-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="89d9e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="89d9e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="89d9e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="89d9e-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="89d9e-107">\<tracking></span></span>  
<span data-ttu-id="89d9e-108">\<profili ></span><span class="sxs-lookup"><span data-stu-id="89d9e-108">\<profiles></span></span>  
<span data-ttu-id="89d9e-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="89d9e-109">\<trackingProfile></span></span>  
<span data-ttu-id="89d9e-110">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="89d9e-110">\<workflow></span></span>  
<span data-ttu-id="89d9e-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="89d9e-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="89d9e-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="89d9e-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d9e-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89d9e-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89d9e-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89d9e-114">Attributes and elements</span></span>

<span data-ttu-id="89d9e-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89d9e-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="89d9e-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="89d9e-116">Attributes</span></span>  
  
|<span data-ttu-id="89d9e-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="89d9e-117">Attribute</span></span>|<span data-ttu-id="89d9e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89d9e-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="89d9e-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="89d9e-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="89d9e-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="89d9e-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89d9e-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89d9e-121">Child elements</span></span>

<span data-ttu-id="89d9e-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="89d9e-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="89d9e-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89d9e-123">Parent elements</span></span>
  
|<span data-ttu-id="89d9e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="89d9e-124">Element</span></span>|<span data-ttu-id="89d9e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89d9e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89d9e-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="89d9e-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="89d9e-127">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="89d9e-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89d9e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89d9e-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="89d9e-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="89d9e-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="89d9e-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="89d9e-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
