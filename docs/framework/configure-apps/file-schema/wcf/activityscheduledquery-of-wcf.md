---
title: <activityScheduledQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850472"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="7b978-102">\<> activityScheduledQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="7b978-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="7b978-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="7b978-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="7b978-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="7b978-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="7b978-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7b978-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7b978-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b978-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7b978-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7b978-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7b978-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7b978-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="7b978-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="7b978-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="7b978-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7b978-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="7b978-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7b978-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="7b978-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityScheduledQueries**](activityscheduledqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7b978-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)</span></span>\
<span data-ttu-id="7b978-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQuery**</span><span class="sxs-lookup"><span data-stu-id="7b978-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b978-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b978-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b978-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7b978-115">Attributes and elements</span></span>  

<span data-ttu-id="7b978-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7b978-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b978-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="7b978-117">Attributes</span></span>  
  
|<span data-ttu-id="7b978-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="7b978-118">Attribute</span></span>|<span data-ttu-id="7b978-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b978-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="7b978-120">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="7b978-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="7b978-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="7b978-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b978-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7b978-122">Child elements</span></span>

<span data-ttu-id="7b978-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7b978-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="7b978-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7b978-124">Parent elements</span></span>  
  
|<span data-ttu-id="7b978-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b978-125">Element</span></span>|<span data-ttu-id="7b978-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7b978-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b978-127">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="7b978-127">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="7b978-128">Raccolta di query utilizzate per tenere traccia di un'attività pianificata per l'esecuzione da un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="7b978-128">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b978-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b978-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="7b978-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="7b978-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7b978-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="7b978-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
