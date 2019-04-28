---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: d49c6d933a09dce5d657746358f1a5f716ab639b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790416"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="6ea6b-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="6ea6b-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="6ea6b-102">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="6ea6b-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="6ea6b-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6ea6b-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="6ea6b-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6ea6b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6ea6b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6ea6b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6ea6b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6ea6b-106">\<tracking></span></span>  
<span data-ttu-id="6ea6b-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6ea6b-107">\<trackingProfile></span></span>  
<span data-ttu-id="6ea6b-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="6ea6b-108">\<workflow></span></span>  
<span data-ttu-id="6ea6b-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="6ea6b-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="6ea6b-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="6ea6b-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea6b-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ea6b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ea6b-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6ea6b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6ea6b-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6ea6b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ea6b-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="6ea6b-114">Attributes</span></span>  
  
|<span data-ttu-id="6ea6b-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="6ea6b-115">Attribute</span></span>|<span data-ttu-id="6ea6b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ea6b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ea6b-117">activityName</span><span class="sxs-lookup"><span data-stu-id="6ea6b-117">activityName</span></span>|<span data-ttu-id="6ea6b-118">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="6ea6b-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="6ea6b-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="6ea6b-119">childActivityName</span></span>|<span data-ttu-id="6ea6b-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="6ea6b-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ea6b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6ea6b-121">Child Elements</span></span>  
 <span data-ttu-id="6ea6b-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6ea6b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ea6b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6ea6b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6ea6b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ea6b-124">Element</span></span>|<span data-ttu-id="6ea6b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ea6b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ea6b-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="6ea6b-126">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="6ea6b-127">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="6ea6b-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ea6b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ea6b-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6ea6b-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6ea6b-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6ea6b-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6ea6b-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
