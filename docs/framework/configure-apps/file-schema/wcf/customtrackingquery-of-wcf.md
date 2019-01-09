---
title: '&lt;customTrackingQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 234703e677f838dcdccdf857ba38b8729d25a488
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146381"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="b937b-102">&lt;customTrackingQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="b937b-102">&lt;customTrackingQuery&gt; of WCF</span></span>

<span data-ttu-id="b937b-103">Rappresenta una query che viene utilizzata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="b937b-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="b937b-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b937b-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="b937b-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b937b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b937b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b937b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b937b-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="b937b-107">\<tracking></span></span>  
<span data-ttu-id="b937b-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="b937b-108">\<profiles></span></span>  
<span data-ttu-id="b937b-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b937b-109">\<trackingProfile></span></span>  
<span data-ttu-id="b937b-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="b937b-110">\<workflow></span></span>  
<span data-ttu-id="b937b-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="b937b-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="b937b-112">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="b937b-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b937b-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b937b-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b937b-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b937b-114">Attributes and elements</span></span>  

<span data-ttu-id="b937b-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b937b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b937b-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="b937b-116">Attributes</span></span>  
  
|<span data-ttu-id="b937b-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="b937b-117">Attribute</span></span>|<span data-ttu-id="b937b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b937b-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b937b-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b937b-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="b937b-120">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="b937b-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b937b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b937b-121">Child elements</span></span>

<span data-ttu-id="b937b-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b937b-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b937b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b937b-123">Parent elements</span></span>

|<span data-ttu-id="b937b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b937b-124">Element</span></span>|<span data-ttu-id="b937b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b937b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b937b-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="b937b-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="b937b-127">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="b937b-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="b937b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b937b-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b937b-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b937b-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b937b-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b937b-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
