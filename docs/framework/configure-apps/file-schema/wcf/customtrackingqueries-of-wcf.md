---
title: <customTrackingQueries>di WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: abc0c7dfb426338ec6bca61b0a4b87754bb63588
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925944"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="dd97d-102">\<> customTrackingQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="dd97d-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="dd97d-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="dd97d-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="dd97d-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dd97d-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="dd97d-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dd97d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="dd97d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dd97d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dd97d-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dd97d-107">\<tracking></span></span>  
<span data-ttu-id="dd97d-108">\<profili ></span><span class="sxs-lookup"><span data-stu-id="dd97d-108">\<profiles></span></span>  
<span data-ttu-id="dd97d-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dd97d-109">\<trackingProfile></span></span>  
<span data-ttu-id="dd97d-110">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dd97d-110">\<workflow></span></span>  
<span data-ttu-id="dd97d-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="dd97d-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd97d-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd97d-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd97d-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd97d-113">Attributes and elements</span></span>

<span data-ttu-id="dd97d-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd97d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd97d-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd97d-115">Attributes</span></span>

<span data-ttu-id="dd97d-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dd97d-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="dd97d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd97d-117">Child elements</span></span>
  
|<span data-ttu-id="dd97d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd97d-118">Element</span></span>|<span data-ttu-id="dd97d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd97d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd97d-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="dd97d-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="dd97d-121">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="dd97d-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd97d-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd97d-122">Parent elements</span></span>  
  
|<span data-ttu-id="dd97d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd97d-123">Element</span></span>|<span data-ttu-id="dd97d-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dd97d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd97d-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="dd97d-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="dd97d-126">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="dd97d-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd97d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd97d-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dd97d-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dd97d-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dd97d-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dd97d-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
