---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 9605f5d050baf046ff3c549c19191934299a65e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945745"
---
# <a name="customtrackingquery"></a><span data-ttu-id="f24e8-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f24e8-101">\<customTrackingQuery></span></span>
<span data-ttu-id="f24e8-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="f24e8-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f24e8-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f24e8-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f24e8-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f24e8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f24e8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f24e8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f24e8-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="f24e8-106">\<tracking></span></span>  
<span data-ttu-id="f24e8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f24e8-107">\<trackingProfile></span></span>  
<span data-ttu-id="f24e8-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f24e8-108">\<workflow></span></span>  
<span data-ttu-id="f24e8-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="f24e8-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="f24e8-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f24e8-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f24e8-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f24e8-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f24e8-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f24e8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f24e8-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f24e8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f24e8-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="f24e8-114">Attributes</span></span>  
  
|<span data-ttu-id="f24e8-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="f24e8-115">Attribute</span></span>|<span data-ttu-id="f24e8-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f24e8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f24e8-117">activityName</span><span class="sxs-lookup"><span data-stu-id="f24e8-117">activityName</span></span>|<span data-ttu-id="f24e8-118">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f24e8-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="f24e8-119">name</span><span class="sxs-lookup"><span data-stu-id="f24e8-119">name</span></span>|<span data-ttu-id="f24e8-120">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="f24e8-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f24e8-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f24e8-121">Child Elements</span></span>  
 <span data-ttu-id="f24e8-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f24e8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f24e8-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f24e8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f24e8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f24e8-124">Element</span></span>|<span data-ttu-id="f24e8-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f24e8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f24e8-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f24e8-126">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="f24e8-127">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="f24e8-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f24e8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f24e8-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f24e8-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f24e8-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f24e8-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f24e8-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
