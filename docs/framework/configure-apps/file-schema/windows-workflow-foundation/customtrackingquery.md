---
title: '&lt;customTrackingQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 9ee5a4a25d379eafb936098597df1ec61ff09f0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725857"
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="bfbc1-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="bfbc1-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="bfbc1-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="bfbc1-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="bfbc1-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="bfbc1-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="bfbc1-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bfbc1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bfbc1-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bfbc1-106">\<system.serviceModel></span></span>  
<span data-ttu-id="bfbc1-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="bfbc1-107">\<tracking></span></span>  
<span data-ttu-id="bfbc1-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="bfbc1-108">\<trackingProfile></span></span>  
<span data-ttu-id="bfbc1-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="bfbc1-109">\<workflow></span></span>  
<span data-ttu-id="bfbc1-110">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="bfbc1-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="bfbc1-111">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="bfbc1-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfbc1-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfbc1-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfbc1-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bfbc1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bfbc1-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bfbc1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfbc1-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="bfbc1-115">Attributes</span></span>  
  
|<span data-ttu-id="bfbc1-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="bfbc1-116">Attribute</span></span>|<span data-ttu-id="bfbc1-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfbc1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bfbc1-118">activityName</span><span class="sxs-lookup"><span data-stu-id="bfbc1-118">activityName</span></span>|<span data-ttu-id="bfbc1-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="bfbc1-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="bfbc1-120">name</span><span class="sxs-lookup"><span data-stu-id="bfbc1-120">name</span></span>|<span data-ttu-id="bfbc1-121">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="bfbc1-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfbc1-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bfbc1-122">Child Elements</span></span>  
 <span data-ttu-id="bfbc1-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bfbc1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfbc1-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bfbc1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bfbc1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfbc1-125">Element</span></span>|<span data-ttu-id="bfbc1-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfbc1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfbc1-127">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="bfbc1-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="bfbc1-128">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="bfbc1-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfbc1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfbc1-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bfbc1-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="bfbc1-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bfbc1-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="bfbc1-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
