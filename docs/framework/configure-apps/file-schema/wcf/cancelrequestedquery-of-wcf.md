---
title: '&lt;cancelRequestedQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 3943d604b586eec37a1d153f10ac049fc9bd5747
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347569"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="a0949-102">&lt;cancelRequestedQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="a0949-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>

<span data-ttu-id="a0949-103">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="a0949-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a0949-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="a0949-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="a0949-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a0949-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="a0949-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a0949-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a0949-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="a0949-107">\<tracking></span></span>  
<span data-ttu-id="a0949-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="a0949-108">\<profiles></span></span>  
<span data-ttu-id="a0949-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a0949-109">\<trackingProfile></span></span>  
<span data-ttu-id="a0949-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="a0949-110">\<workflow></span></span>  
<span data-ttu-id="a0949-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="a0949-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="a0949-112">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="a0949-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0949-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0949-113">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                              childActivityName="String"/>
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0949-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a0949-114">Attributes and elements</span></span>

<span data-ttu-id="a0949-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a0949-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0949-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="a0949-116">Attributes</span></span>  
  
|<span data-ttu-id="a0949-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="a0949-117">Attribute</span></span>|<span data-ttu-id="a0949-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0949-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="a0949-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="a0949-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="a0949-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="a0949-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0949-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a0949-121">Child elements</span></span>

<span data-ttu-id="a0949-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a0949-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="a0949-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a0949-123">Parent elements</span></span>
  
|<span data-ttu-id="a0949-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0949-124">Element</span></span>|<span data-ttu-id="a0949-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0949-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0949-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="a0949-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="a0949-127">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="a0949-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0949-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0949-128">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a0949-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a0949-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a0949-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="a0949-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
