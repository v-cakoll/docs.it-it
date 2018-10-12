---
title: '&lt;activityScheduledQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: a3c4c8b338921c9d949edd83deb4d6073eb26b55
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123371"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="469df-102">&lt;activityScheduledQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="469df-102">&lt;activityScheduledQuery&gt; of WCF</span></span>

<span data-ttu-id="469df-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="469df-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="469df-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="469df-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="469df-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="469df-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="469df-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="469df-106">\<system.serviceModel></span></span>  
<span data-ttu-id="469df-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="469df-107">\<tracking></span></span>  
<span data-ttu-id="469df-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="469df-108">\<profiles></span></span>  
<span data-ttu-id="469df-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="469df-109">\<trackingProfile></span></span>  
<span data-ttu-id="469df-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="469df-110">\<workflow></span></span>  
<span data-ttu-id="469df-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="469df-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="469df-112">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="469df-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469df-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="469df-113">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"   
                                  childActivityName="String"/>
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking> 
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="469df-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="469df-114">Attributes and elements</span></span>  

<span data-ttu-id="469df-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="469df-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="469df-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="469df-116">Attributes</span></span>  
  
|<span data-ttu-id="469df-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="469df-117">Attribute</span></span>|<span data-ttu-id="469df-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="469df-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="469df-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="469df-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="469df-120">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="469df-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="469df-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="469df-121">Child elements</span></span>

<span data-ttu-id="469df-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="469df-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="469df-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="469df-123">Parent elements</span></span>  
  
|<span data-ttu-id="469df-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="469df-124">Element</span></span>|<span data-ttu-id="469df-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="469df-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="469df-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="469df-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="469df-127">Una raccolta di query che vengono usati per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="469df-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="469df-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="469df-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="469df-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="469df-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="469df-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="469df-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
