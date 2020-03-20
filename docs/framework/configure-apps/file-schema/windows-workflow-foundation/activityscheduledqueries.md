---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152424"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="27625-101">\<> ActivityScheduledQueries</span><span class="sxs-lookup"><span data-stu-id="27625-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="27625-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="27625-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="27625-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="27625-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="27625-104">Per altre informazioni sulle query del profilo di rilevamento, vedere [Profili di rilevamentoFor more](../../../windows-workflow-foundation/tracking-profiles.md) information on tracking profile queries, see Tracking Profiles</span><span class="sxs-lookup"><span data-stu-id="27625-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="27625-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27625-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27625-106">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="27625-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="27625-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="27625-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="27625-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="27625-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="27625-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="27625-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="27625-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>activityScheduledQueries**</span><span class="sxs-lookup"><span data-stu-id="27625-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27625-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27625-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27625-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="27625-112">Attributes and Elements</span></span>  
 <span data-ttu-id="27625-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="27625-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27625-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="27625-114">Attributes</span></span>  
 <span data-ttu-id="27625-115">No.</span><span class="sxs-lookup"><span data-stu-id="27625-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="27625-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="27625-116">Child Elements</span></span>  
  
|<span data-ttu-id="27625-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="27625-117">Element</span></span>|<span data-ttu-id="27625-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27625-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27625-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="27625-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="27625-120">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="27625-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27625-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="27625-121">Parent Elements</span></span>  
  
|<span data-ttu-id="27625-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="27625-122">Element</span></span>|<span data-ttu-id="27625-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27625-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27625-124">\<>del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="27625-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="27625-125">Elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dalla proprietà **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="27625-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27625-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27625-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="27625-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="27625-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="27625-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="27625-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
