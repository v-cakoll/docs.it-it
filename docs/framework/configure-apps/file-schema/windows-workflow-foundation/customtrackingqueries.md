---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152261"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="1cb13-101">\<> customTrackingQueries</span><span class="sxs-lookup"><span data-stu-id="1cb13-101">\<customTrackingQueries></span></span>
<span data-ttu-id="1cb13-102">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="1cb13-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="1cb13-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1cb13-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="1cb13-104">Per altre informazioni sulle query del profilo di rilevamento, vedere [Profili di rilevamentoFor more](../../../windows-workflow-foundation/tracking-profiles.md) information on tracking profile queries, see Tracking Profiles</span><span class="sxs-lookup"><span data-stu-id="1cb13-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1cb13-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1cb13-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1cb13-106">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1cb13-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1cb13-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1cb13-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1cb13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1cb13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1cb13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1cb13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1cb13-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>customTrackingQueries**</span><span class="sxs-lookup"><span data-stu-id="1cb13-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cb13-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cb13-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cb13-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1cb13-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1cb13-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1cb13-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cb13-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="1cb13-114">Attributes</span></span>  
 <span data-ttu-id="1cb13-115">No.</span><span class="sxs-lookup"><span data-stu-id="1cb13-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1cb13-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1cb13-116">Child Elements</span></span>  
  
|<span data-ttu-id="1cb13-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cb13-117">Element</span></span>|<span data-ttu-id="1cb13-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cb13-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cb13-119">\<>customTrackingQuery</span><span class="sxs-lookup"><span data-stu-id="1cb13-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="1cb13-120">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="1cb13-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1cb13-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1cb13-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1cb13-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cb13-122">Element</span></span>|<span data-ttu-id="1cb13-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cb13-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cb13-124">\<>del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1cb13-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1cb13-125">Elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dalla proprietà **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="1cb13-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cb13-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cb13-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1cb13-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1cb13-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1cb13-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="1cb13-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
