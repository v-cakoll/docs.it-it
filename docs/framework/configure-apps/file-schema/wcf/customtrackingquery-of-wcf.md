---
title: <customTrackingQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855429"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="bfa3d-102">\<> customTrackingQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="bfa3d-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="bfa3d-103">Rappresenta una query utilizzata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="bfa3d-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="bfa3d-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="bfa3d-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="bfa3d-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bfa3d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bfa3d-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bfa3d-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bfa3d-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bfa3d-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bfa3d-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bfa3d-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="bfa3d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="bfa3d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="bfa3d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bfa3d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="bfa3d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bfa3d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="bfa3d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> customTrackingQueries**](customtrackingqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bfa3d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)</span></span>\
<span data-ttu-id="bfa3d-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customTrackingQuery**</span><span class="sxs-lookup"><span data-stu-id="bfa3d-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa3d-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfa3d-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfa3d-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bfa3d-115">Attributes and elements</span></span>  

<span data-ttu-id="bfa3d-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bfa3d-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfa3d-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="bfa3d-117">Attributes</span></span>  
  
|<span data-ttu-id="bfa3d-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="bfa3d-118">Attribute</span></span>|<span data-ttu-id="bfa3d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfa3d-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="bfa3d-120">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="bfa3d-120">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="bfa3d-121">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="bfa3d-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfa3d-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bfa3d-122">Child elements</span></span>

<span data-ttu-id="bfa3d-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bfa3d-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bfa3d-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bfa3d-124">Parent elements</span></span>

|<span data-ttu-id="bfa3d-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfa3d-125">Element</span></span>|<span data-ttu-id="bfa3d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfa3d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfa3d-127">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="bfa3d-127">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="bfa3d-128">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="bfa3d-128">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="bfa3d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfa3d-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bfa3d-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="bfa3d-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bfa3d-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="bfa3d-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
