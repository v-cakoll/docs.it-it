---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: dc04405204be7c5484d47b4a3767f846b11abf9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945508"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="26bc7-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="26bc7-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="26bc7-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="26bc7-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="26bc7-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="26bc7-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="26bc7-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="26bc7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="26bc7-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="26bc7-105">\<system.serviceModel></span></span>  
<span data-ttu-id="26bc7-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="26bc7-106">\<tracking></span></span>  
<span data-ttu-id="26bc7-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="26bc7-107">\<trackingProfile></span></span>  
<span data-ttu-id="26bc7-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="26bc7-108">\<workflow></span></span>  
<span data-ttu-id="26bc7-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="26bc7-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="26bc7-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="26bc7-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26bc7-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26bc7-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26bc7-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="26bc7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="26bc7-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="26bc7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26bc7-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="26bc7-114">Attributes</span></span>  
  
|<span data-ttu-id="26bc7-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="26bc7-115">Attribute</span></span>|<span data-ttu-id="26bc7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26bc7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26bc7-117">activityName</span><span class="sxs-lookup"><span data-stu-id="26bc7-117">activityName</span></span>|<span data-ttu-id="26bc7-118">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="26bc7-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="26bc7-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="26bc7-119">childActivityName</span></span>|<span data-ttu-id="26bc7-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="26bc7-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26bc7-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="26bc7-121">Child Elements</span></span>  
 <span data-ttu-id="26bc7-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="26bc7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26bc7-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="26bc7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="26bc7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="26bc7-124">Element</span></span>|<span data-ttu-id="26bc7-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="26bc7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26bc7-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="26bc7-126">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="26bc7-127">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="26bc7-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26bc7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26bc7-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="26bc7-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="26bc7-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="26bc7-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="26bc7-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
