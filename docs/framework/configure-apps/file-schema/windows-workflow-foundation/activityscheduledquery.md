---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152411"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="52ace-101">\<> activityScheduledQuery</span><span class="sxs-lookup"><span data-stu-id="52ace-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="52ace-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="52ace-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="52ace-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="52ace-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="52ace-104">Per altre informazioni sulle query del profilo di rilevamento, vedere [Profili di rilevamentoFor more](../../../windows-workflow-foundation/tracking-profiles.md) information on tracking profile queries, see Tracking Profiles</span><span class="sxs-lookup"><span data-stu-id="52ace-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="52ace-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52ace-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52ace-106">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="52ace-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="52ace-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="52ace-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="52ace-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="52ace-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="52ace-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="52ace-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="52ace-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>activityScheduledQueries**](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="52ace-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="52ace-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span><span class="sxs-lookup"><span data-stu-id="52ace-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ace-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52ace-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52ace-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="52ace-113">Attributes and Elements</span></span>  
 <span data-ttu-id="52ace-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="52ace-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52ace-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="52ace-115">Attributes</span></span>  
  
|<span data-ttu-id="52ace-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="52ace-116">Attribute</span></span>|<span data-ttu-id="52ace-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52ace-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52ace-118">activityName</span><span class="sxs-lookup"><span data-stu-id="52ace-118">activityName</span></span>|<span data-ttu-id="52ace-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="52ace-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="52ace-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="52ace-120">childActivityName</span></span>|<span data-ttu-id="52ace-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="52ace-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52ace-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="52ace-122">Child Elements</span></span>  
 <span data-ttu-id="52ace-123">No.</span><span class="sxs-lookup"><span data-stu-id="52ace-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52ace-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="52ace-124">Parent Elements</span></span>  
  
|<span data-ttu-id="52ace-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="52ace-125">Element</span></span>|<span data-ttu-id="52ace-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52ace-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52ace-127">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="52ace-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="52ace-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="52ace-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52ace-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52ace-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="52ace-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="52ace-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="52ace-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="52ace-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
