---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120081"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="6caed-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="6caed-101">\<customTrackingQueries></span></span>
<span data-ttu-id="6caed-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6caed-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6caed-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6caed-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="6caed-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6caed-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6caed-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6caed-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6caed-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6caed-106">\<tracking></span></span>  
<span data-ttu-id="6caed-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6caed-107">\<trackingProfile></span></span>  
<span data-ttu-id="6caed-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="6caed-108">\<workflow></span></span>  
<span data-ttu-id="6caed-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="6caed-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6caed-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6caed-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6caed-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6caed-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6caed-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6caed-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6caed-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="6caed-113">Attributes</span></span>  
 <span data-ttu-id="6caed-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6caed-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6caed-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6caed-115">Child Elements</span></span>  
  
|<span data-ttu-id="6caed-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="6caed-116">Element</span></span>|<span data-ttu-id="6caed-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6caed-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6caed-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="6caed-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="6caed-119">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6caed-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6caed-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6caed-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6caed-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6caed-121">Element</span></span>|<span data-ttu-id="6caed-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6caed-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6caed-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6caed-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6caed-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="6caed-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6caed-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6caed-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6caed-126">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6caed-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6caed-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6caed-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
