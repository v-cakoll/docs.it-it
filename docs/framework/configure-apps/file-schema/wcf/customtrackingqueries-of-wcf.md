---
title: '&lt;customTrackingQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 11ad4281d2925a48508c6a3e8258b0b1cd49a326
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="90417-102">&lt;customTrackingQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="90417-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="90417-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="90417-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="90417-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="90417-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="90417-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="90417-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="90417-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90417-106">\<system.serviceModel></span></span>  
<span data-ttu-id="90417-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="90417-107">\<tracking></span></span>  
<span data-ttu-id="90417-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="90417-108">\<trackingProfile></span></span>  
<span data-ttu-id="90417-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="90417-109">\<workflow></span></span>  
<span data-ttu-id="90417-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="90417-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90417-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90417-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90417-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90417-112">Attributes and Elements</span></span>  
 <span data-ttu-id="90417-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90417-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90417-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="90417-114">Attributes</span></span>  
 <span data-ttu-id="90417-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90417-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90417-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90417-116">Child Elements</span></span>  
  
|<span data-ttu-id="90417-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="90417-117">Element</span></span>|<span data-ttu-id="90417-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90417-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90417-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="90417-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="90417-120">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="90417-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90417-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90417-121">Parent Elements</span></span>  
  
|<span data-ttu-id="90417-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="90417-122">Element</span></span>|<span data-ttu-id="90417-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90417-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90417-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="90417-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="90417-125">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="90417-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90417-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90417-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="90417-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="90417-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="90417-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="90417-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
