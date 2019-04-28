---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790221"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="5bc5a-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="5bc5a-101">\<customTrackingQueries></span></span>
<span data-ttu-id="5bc5a-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="5bc5a-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="5bc5a-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5bc5a-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="5bc5a-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5bc5a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5bc5a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5bc5a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5bc5a-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="5bc5a-106">\<tracking></span></span>  
<span data-ttu-id="5bc5a-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5bc5a-107">\<trackingProfile></span></span>  
<span data-ttu-id="5bc5a-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="5bc5a-108">\<workflow></span></span>  
<span data-ttu-id="5bc5a-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="5bc5a-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc5a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bc5a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bc5a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5bc5a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5bc5a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5bc5a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bc5a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="5bc5a-113">Attributes</span></span>  
 <span data-ttu-id="5bc5a-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5bc5a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5bc5a-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5bc5a-115">Child Elements</span></span>  
  
|<span data-ttu-id="5bc5a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="5bc5a-116">Element</span></span>|<span data-ttu-id="5bc5a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bc5a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bc5a-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="5bc5a-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="5bc5a-119">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="5bc5a-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bc5a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5bc5a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5bc5a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5bc5a-121">Element</span></span>|<span data-ttu-id="5bc5a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bc5a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bc5a-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5bc5a-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5bc5a-124">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="5bc5a-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bc5a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bc5a-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5bc5a-126">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5bc5a-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5bc5a-127">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="5bc5a-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
