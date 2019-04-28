---
title: <activityScheduledQuery> di WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 5087d56092296f8c68b719ec0945993adeb3de0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704719"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="ee60f-102">\<activityScheduledQuery > di WCF</span><span class="sxs-lookup"><span data-stu-id="ee60f-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="ee60f-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="ee60f-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ee60f-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ee60f-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="ee60f-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ee60f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ee60f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ee60f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ee60f-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ee60f-107">\<tracking></span></span>  
<span data-ttu-id="ee60f-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="ee60f-108">\<profiles></span></span>  
<span data-ttu-id="ee60f-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ee60f-109">\<trackingProfile></span></span>  
<span data-ttu-id="ee60f-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="ee60f-110">\<workflow></span></span>  
<span data-ttu-id="ee60f-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="ee60f-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="ee60f-112">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="ee60f-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee60f-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee60f-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee60f-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ee60f-114">Attributes and elements</span></span>  

<span data-ttu-id="ee60f-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ee60f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee60f-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="ee60f-116">Attributes</span></span>  
  
|<span data-ttu-id="ee60f-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="ee60f-117">Attribute</span></span>|<span data-ttu-id="ee60f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee60f-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="ee60f-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee60f-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="ee60f-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee60f-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee60f-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ee60f-121">Child elements</span></span>

<span data-ttu-id="ee60f-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ee60f-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="ee60f-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ee60f-123">Parent elements</span></span>  
  
|<span data-ttu-id="ee60f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee60f-124">Element</span></span>|<span data-ttu-id="ee60f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee60f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee60f-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="ee60f-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="ee60f-127">Una raccolta di query che vengono usati per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="ee60f-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee60f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee60f-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="ee60f-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ee60f-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ee60f-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ee60f-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
