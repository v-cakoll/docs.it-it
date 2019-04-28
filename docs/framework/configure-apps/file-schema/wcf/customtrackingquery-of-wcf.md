---
title: <customTrackingQuery> di WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 0a5e7c034ce1ef12a8d7d5b1753e2e441e48e293
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673173"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="aad93-102">\<customTrackingQuery > di WCF</span><span class="sxs-lookup"><span data-stu-id="aad93-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="aad93-103">Rappresenta una query che viene utilizzata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="aad93-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="aad93-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="aad93-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="aad93-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="aad93-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="aad93-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aad93-106">\<system.serviceModel></span></span>  
<span data-ttu-id="aad93-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="aad93-107">\<tracking></span></span>  
<span data-ttu-id="aad93-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="aad93-108">\<profiles></span></span>  
<span data-ttu-id="aad93-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="aad93-109">\<trackingProfile></span></span>  
<span data-ttu-id="aad93-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="aad93-110">\<workflow></span></span>  
<span data-ttu-id="aad93-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="aad93-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="aad93-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="aad93-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aad93-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aad93-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aad93-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aad93-114">Attributes and elements</span></span>  

<span data-ttu-id="aad93-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aad93-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aad93-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="aad93-116">Attributes</span></span>  
  
|<span data-ttu-id="aad93-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="aad93-117">Attribute</span></span>|<span data-ttu-id="aad93-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aad93-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="aad93-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="aad93-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="aad93-120">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="aad93-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aad93-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aad93-121">Child elements</span></span>

<span data-ttu-id="aad93-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="aad93-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aad93-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aad93-123">Parent elements</span></span>

|<span data-ttu-id="aad93-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="aad93-124">Element</span></span>|<span data-ttu-id="aad93-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aad93-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aad93-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="aad93-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="aad93-127">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="aad93-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="aad93-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aad93-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aad93-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aad93-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aad93-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="aad93-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
