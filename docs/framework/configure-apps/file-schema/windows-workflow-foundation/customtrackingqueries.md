---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 429940b2ed69d8be497626f634a21adca540b529
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945846"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="6dce8-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="6dce8-101">\<customTrackingQueries></span></span>
<span data-ttu-id="6dce8-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6dce8-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6dce8-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6dce8-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="6dce8-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6dce8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6dce8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6dce8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6dce8-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="6dce8-106">\<tracking></span></span>  
<span data-ttu-id="6dce8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6dce8-107">\<trackingProfile></span></span>  
<span data-ttu-id="6dce8-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6dce8-108">\<workflow></span></span>  
<span data-ttu-id="6dce8-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="6dce8-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dce8-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6dce8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6dce8-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6dce8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6dce8-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6dce8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6dce8-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="6dce8-113">Attributes</span></span>  
 <span data-ttu-id="6dce8-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6dce8-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6dce8-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6dce8-115">Child Elements</span></span>  
  
|<span data-ttu-id="6dce8-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="6dce8-116">Element</span></span>|<span data-ttu-id="6dce8-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6dce8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6dce8-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="6dce8-118">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="6dce8-119">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6dce8-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6dce8-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6dce8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6dce8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6dce8-121">Element</span></span>|<span data-ttu-id="6dce8-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6dce8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6dce8-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6dce8-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="6dce8-124">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="6dce8-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6dce8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dce8-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6dce8-126">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6dce8-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6dce8-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6dce8-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
