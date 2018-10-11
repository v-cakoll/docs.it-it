---
title: '&lt;activityScheduledQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 9a53d72316dad0178f24e05656a4fb4531b88aec
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087765"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="602c1-102">&lt;activityScheduledQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="602c1-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="602c1-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="602c1-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="602c1-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="602c1-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="602c1-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="602c1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="602c1-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="602c1-106">\<system.serviceModel></span></span>  
<span data-ttu-id="602c1-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="602c1-107">\<tracking></span></span>  
<span data-ttu-id="602c1-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="602c1-108">\<trackingProfile></span></span>  
<span data-ttu-id="602c1-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="602c1-109">\<workflow></span></span>  
<span data-ttu-id="602c1-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="602c1-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="602c1-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="602c1-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602c1-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="602c1-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="602c1-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="602c1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="602c1-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="602c1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="602c1-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="602c1-115">Attributes</span></span>  
  
|<span data-ttu-id="602c1-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="602c1-116">Attribute</span></span>|<span data-ttu-id="602c1-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="602c1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="602c1-118">activityName</span><span class="sxs-lookup"><span data-stu-id="602c1-118">activityName</span></span>|<span data-ttu-id="602c1-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="602c1-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="602c1-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="602c1-120">childActivityName</span></span>|<span data-ttu-id="602c1-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="602c1-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="602c1-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="602c1-122">Child Elements</span></span>  
 <span data-ttu-id="602c1-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="602c1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="602c1-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="602c1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="602c1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="602c1-125">Element</span></span>|<span data-ttu-id="602c1-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="602c1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="602c1-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="602c1-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="602c1-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="602c1-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="602c1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="602c1-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="602c1-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="602c1-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="602c1-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="602c1-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
