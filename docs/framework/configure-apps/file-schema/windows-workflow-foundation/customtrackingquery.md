---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152209"
---
# <a name="customtrackingquery"></a><span data-ttu-id="97ac3-101">\<> customTrackingQuery</span><span class="sxs-lookup"><span data-stu-id="97ac3-101">\<customTrackingQuery></span></span>
<span data-ttu-id="97ac3-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="97ac3-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="97ac3-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="97ac3-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="97ac3-104">Per altre informazioni sulle query del profilo di rilevamento, vedere [Profili di rilevamentoFor more](../../../windows-workflow-foundation/tracking-profiles.md) information on tracking profile queries, see Tracking Profiles</span><span class="sxs-lookup"><span data-stu-id="97ac3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="97ac3-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97ac3-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97ac3-106">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="97ac3-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="97ac3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="97ac3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="97ac3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="97ac3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="97ac3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="97ac3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="97ac3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>customTrackingQueries**](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="97ac3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="97ac3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>customTrackingQuery**</span><span class="sxs-lookup"><span data-stu-id="97ac3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ac3-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97ac3-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97ac3-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="97ac3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="97ac3-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="97ac3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97ac3-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="97ac3-115">Attributes</span></span>  
  
|<span data-ttu-id="97ac3-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="97ac3-116">Attribute</span></span>|<span data-ttu-id="97ac3-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97ac3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97ac3-118">activityName</span><span class="sxs-lookup"><span data-stu-id="97ac3-118">activityName</span></span>|<span data-ttu-id="97ac3-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="97ac3-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="97ac3-120">name</span><span class="sxs-lookup"><span data-stu-id="97ac3-120">name</span></span>|<span data-ttu-id="97ac3-121">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="97ac3-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97ac3-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="97ac3-122">Child Elements</span></span>  
 <span data-ttu-id="97ac3-123">No.</span><span class="sxs-lookup"><span data-stu-id="97ac3-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97ac3-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="97ac3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="97ac3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="97ac3-125">Element</span></span>|<span data-ttu-id="97ac3-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97ac3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97ac3-127">\<>customTrackingQuery</span><span class="sxs-lookup"><span data-stu-id="97ac3-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="97ac3-128">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="97ac3-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97ac3-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97ac3-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="97ac3-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="97ac3-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="97ac3-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="97ac3-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
