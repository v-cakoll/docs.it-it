---
title: <activityScheduledQueries>di WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850499"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="d2cd2-102">\<> activityScheduledQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="d2cd2-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="d2cd2-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="d2cd2-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d2cd2-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d2cd2-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="d2cd2-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d2cd2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d2cd2-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2cd2-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2cd2-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d2cd2-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d2cd2-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d2cd2-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="d2cd2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="d2cd2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="d2cd2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d2cd2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="d2cd2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d2cd2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="d2cd2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQueries**</span><span class="sxs-lookup"><span data-stu-id="d2cd2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2cd2-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2cd2-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2cd2-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d2cd2-114">Attributes and elements</span></span>  

<span data-ttu-id="d2cd2-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d2cd2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2cd2-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="d2cd2-116">Attributes</span></span>  

<span data-ttu-id="d2cd2-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d2cd2-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2cd2-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d2cd2-118">Child elements</span></span>  
  
|<span data-ttu-id="d2cd2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2cd2-119">Element</span></span>|<span data-ttu-id="d2cd2-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d2cd2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2cd2-121">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="d2cd2-121">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="d2cd2-122">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="d2cd2-122">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2cd2-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d2cd2-123">Parent elements</span></span>  
  
|<span data-ttu-id="d2cd2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2cd2-124">Element</span></span>|<span data-ttu-id="d2cd2-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d2cd2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2cd2-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d2cd2-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="d2cd2-127">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="d2cd2-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2cd2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2cd2-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="d2cd2-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d2cd2-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d2cd2-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d2cd2-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
