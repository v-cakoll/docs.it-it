---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: a43242e2f22c48a57c11f6f03657d7d3de27ff48
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398986"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="e4249-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="e4249-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="e4249-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e4249-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="e4249-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e4249-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="e4249-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e4249-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e4249-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e4249-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e4249-106">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e4249-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e4249-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="e4249-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="e4249-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="e4249-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="e4249-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e4249-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="e4249-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQueries**</span><span class="sxs-lookup"><span data-stu-id="e4249-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4249-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4249-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4249-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e4249-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e4249-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e4249-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4249-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e4249-114">Attributes</span></span>  
 <span data-ttu-id="e4249-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e4249-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e4249-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e4249-116">Child Elements</span></span>  
  
|<span data-ttu-id="e4249-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4249-117">Element</span></span>|<span data-ttu-id="e4249-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e4249-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4249-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="e4249-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="e4249-120">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e4249-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4249-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e4249-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e4249-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4249-122">Element</span></span>|<span data-ttu-id="e4249-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4249-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4249-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="e4249-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="e4249-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="e4249-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4249-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4249-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e4249-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e4249-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e4249-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e4249-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
