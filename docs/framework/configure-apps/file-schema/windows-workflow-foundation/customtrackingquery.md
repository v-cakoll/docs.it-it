---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 695fccf88ac0d8a672e710ccc632ea58dd2fc693
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398774"
---
# <a name="customtrackingquery"></a><span data-ttu-id="f1ca4-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f1ca4-101">\<customTrackingQuery></span></span>
<span data-ttu-id="f1ca4-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="f1ca4-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f1ca4-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f1ca4-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f1ca4-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f1ca4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f1ca4-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f1ca4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f1ca4-106">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f1ca4-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="f1ca4-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="f1ca4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="f1ca4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="f1ca4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="f1ca4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f1ca4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="f1ca4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> customTrackingQueries**](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="f1ca4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="f1ca4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customTrackingQuery**</span><span class="sxs-lookup"><span data-stu-id="f1ca4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ca4-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1ca4-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1ca4-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1ca4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f1ca4-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f1ca4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1ca4-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1ca4-115">Attributes</span></span>  
  
|<span data-ttu-id="f1ca4-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="f1ca4-116">Attribute</span></span>|<span data-ttu-id="f1ca4-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f1ca4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1ca4-118">activityName</span><span class="sxs-lookup"><span data-stu-id="f1ca4-118">activityName</span></span>|<span data-ttu-id="f1ca4-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f1ca4-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="f1ca4-120">name</span><span class="sxs-lookup"><span data-stu-id="f1ca4-120">name</span></span>|<span data-ttu-id="f1ca4-121">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="f1ca4-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1ca4-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1ca4-122">Child Elements</span></span>  
 <span data-ttu-id="f1ca4-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f1ca4-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1ca4-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1ca4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f1ca4-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1ca4-125">Element</span></span>|<span data-ttu-id="f1ca4-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1ca4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1ca4-127">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f1ca4-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="f1ca4-128">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="f1ca4-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1ca4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1ca4-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f1ca4-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f1ca4-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f1ca4-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f1ca4-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
