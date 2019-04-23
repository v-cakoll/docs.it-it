---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 92060260075017359d8a5f0500d52e52c2217d3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076653"
---
# <a name="customtrackingquery"></a><span data-ttu-id="e5ebd-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="e5ebd-101">\<customTrackingQuery></span></span>
<span data-ttu-id="e5ebd-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e5ebd-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e5ebd-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e5ebd-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e5ebd-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e5ebd-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e5ebd-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e5ebd-106">\<tracking></span></span>  
<span data-ttu-id="e5ebd-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e5ebd-107">\<trackingProfile></span></span>  
<span data-ttu-id="e5ebd-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e5ebd-108">\<workflow></span></span>  
<span data-ttu-id="e5ebd-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="e5ebd-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="e5ebd-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="e5ebd-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ebd-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5ebd-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5ebd-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e5ebd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e5ebd-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5ebd-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e5ebd-114">Attributes</span></span>  
  
|<span data-ttu-id="e5ebd-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="e5ebd-115">Attribute</span></span>|<span data-ttu-id="e5ebd-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5ebd-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5ebd-117">activityName</span><span class="sxs-lookup"><span data-stu-id="e5ebd-117">activityName</span></span>|<span data-ttu-id="e5ebd-118">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="e5ebd-119">name</span><span class="sxs-lookup"><span data-stu-id="e5ebd-119">name</span></span>|<span data-ttu-id="e5ebd-120">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5ebd-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e5ebd-121">Child Elements</span></span>  
 <span data-ttu-id="e5ebd-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5ebd-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e5ebd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e5ebd-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5ebd-124">Element</span></span>|<span data-ttu-id="e5ebd-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5ebd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5ebd-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="e5ebd-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="e5ebd-127">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5ebd-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5ebd-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e5ebd-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e5ebd-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e5ebd-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e5ebd-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
