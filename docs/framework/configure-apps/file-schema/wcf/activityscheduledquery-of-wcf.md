---
title: '&lt;activityScheduledQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 4efd6ba13e8a54d3338c25b077477d4abdbe9ab5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="cfa20-102">&lt;activityScheduledQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="cfa20-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="cfa20-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="cfa20-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="cfa20-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cfa20-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="cfa20-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cfa20-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="cfa20-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cfa20-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cfa20-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="cfa20-107">\<tracking></span></span>  
<span data-ttu-id="cfa20-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cfa20-108">\<trackingProfile></span></span>  
<span data-ttu-id="cfa20-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="cfa20-109">\<workflow></span></span>  
<span data-ttu-id="cfa20-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="cfa20-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="cfa20-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="cfa20-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa20-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfa20-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfa20-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cfa20-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cfa20-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cfa20-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfa20-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="cfa20-115">Attributes</span></span>  
  
|<span data-ttu-id="cfa20-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="cfa20-116">Attribute</span></span>|<span data-ttu-id="cfa20-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfa20-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfa20-118">activityName</span><span class="sxs-lookup"><span data-stu-id="cfa20-118">activityName</span></span>|<span data-ttu-id="cfa20-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="cfa20-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="cfa20-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="cfa20-120">childActivityName</span></span>|<span data-ttu-id="cfa20-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="cfa20-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfa20-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cfa20-122">Child Elements</span></span>  
 <span data-ttu-id="cfa20-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cfa20-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfa20-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cfa20-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cfa20-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfa20-125">Element</span></span>|<span data-ttu-id="cfa20-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfa20-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfa20-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="cfa20-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="cfa20-128">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="cfa20-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfa20-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfa20-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="cfa20-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cfa20-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cfa20-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="cfa20-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
