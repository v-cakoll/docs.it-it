---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: a4689e55962cd32d738682129aaa0612a4684384
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264639"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="2998f-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="2998f-101">\<customTrackingQueries></span></span>
<span data-ttu-id="2998f-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="2998f-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="2998f-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2998f-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="2998f-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2998f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2998f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2998f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2998f-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2998f-106">\<tracking></span></span>  
<span data-ttu-id="2998f-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2998f-107">\<trackingProfile></span></span>  
<span data-ttu-id="2998f-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="2998f-108">\<workflow></span></span>  
<span data-ttu-id="2998f-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="2998f-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2998f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2998f-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2998f-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2998f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2998f-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2998f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2998f-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2998f-113">Attributes</span></span>  
 <span data-ttu-id="2998f-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2998f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2998f-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2998f-115">Child Elements</span></span>  
  
|<span data-ttu-id="2998f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="2998f-116">Element</span></span>|<span data-ttu-id="2998f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2998f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2998f-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="2998f-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="2998f-119">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="2998f-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2998f-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2998f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2998f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2998f-121">Element</span></span>|<span data-ttu-id="2998f-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2998f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2998f-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2998f-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2998f-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="2998f-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2998f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2998f-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2998f-126">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2998f-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2998f-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2998f-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
