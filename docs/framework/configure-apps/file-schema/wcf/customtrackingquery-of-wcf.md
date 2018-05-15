---
title: '&lt;customTrackingQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: ed29ff039cd7fd4eb0acccea1b0adf8995c3e1f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="7dd0c-102">&lt;customTrackingQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="7dd0c-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="7dd0c-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="7dd0c-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="7dd0c-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7dd0c-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="7dd0c-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7dd0c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="7dd0c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7dd0c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7dd0c-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="7dd0c-107">\<tracking></span></span>  
<span data-ttu-id="7dd0c-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7dd0c-108">\<trackingProfile></span></span>  
<span data-ttu-id="7dd0c-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="7dd0c-109">\<workflow></span></span>  
<span data-ttu-id="7dd0c-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="7dd0c-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="7dd0c-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="7dd0c-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd0c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7dd0c-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7dd0c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7dd0c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7dd0c-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7dd0c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dd0c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="7dd0c-115">Attributes</span></span>  
  
|<span data-ttu-id="7dd0c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="7dd0c-116">Attribute</span></span>|<span data-ttu-id="7dd0c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dd0c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dd0c-118">activityName</span><span class="sxs-lookup"><span data-stu-id="7dd0c-118">activityName</span></span>|<span data-ttu-id="7dd0c-119">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="7dd0c-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="7dd0c-120">name</span><span class="sxs-lookup"><span data-stu-id="7dd0c-120">name</span></span>|<span data-ttu-id="7dd0c-121">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="7dd0c-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dd0c-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7dd0c-122">Child Elements</span></span>  
 <span data-ttu-id="7dd0c-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7dd0c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dd0c-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7dd0c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7dd0c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7dd0c-125">Element</span></span>|<span data-ttu-id="7dd0c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dd0c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dd0c-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="7dd0c-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="7dd0c-128">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="7dd0c-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7dd0c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dd0c-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>      
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="7dd0c-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="7dd0c-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7dd0c-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="7dd0c-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
