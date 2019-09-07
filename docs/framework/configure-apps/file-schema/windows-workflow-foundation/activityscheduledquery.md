---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: aa6ee435c66303b5089b459ecc4ed3023297636d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398963"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="08191-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="08191-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="08191-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="08191-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="08191-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="08191-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="08191-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="08191-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="08191-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="08191-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="08191-106">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="08191-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="08191-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="08191-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="08191-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="08191-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="08191-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="08191-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="08191-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityScheduledQueries**](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="08191-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="08191-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQuery**</span><span class="sxs-lookup"><span data-stu-id="08191-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08191-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08191-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08191-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="08191-113">Attributes and Elements</span></span>  
 <span data-ttu-id="08191-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="08191-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08191-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="08191-115">Attributes</span></span>  
  
|<span data-ttu-id="08191-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="08191-116">Attribute</span></span>|<span data-ttu-id="08191-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="08191-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08191-118">activityName</span><span class="sxs-lookup"><span data-stu-id="08191-118">activityName</span></span>|<span data-ttu-id="08191-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="08191-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="08191-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="08191-120">childActivityName</span></span>|<span data-ttu-id="08191-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="08191-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08191-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="08191-122">Child Elements</span></span>  
 <span data-ttu-id="08191-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="08191-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08191-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="08191-124">Parent Elements</span></span>  
  
|<span data-ttu-id="08191-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="08191-125">Element</span></span>|<span data-ttu-id="08191-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08191-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08191-127">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="08191-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="08191-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="08191-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08191-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08191-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="08191-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="08191-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="08191-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="08191-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
