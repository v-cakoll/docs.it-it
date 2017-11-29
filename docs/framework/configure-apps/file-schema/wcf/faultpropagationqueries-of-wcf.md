---
title: '&lt;faultPropagationQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e122e8c6194545a02f6db429d550eabed5d49b27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="aff1c-102">&lt;faultPropagationQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="aff1c-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="aff1c-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="aff1c-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="aff1c-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="aff1c-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="aff1c-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="aff1c-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="aff1c-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="aff1c-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="aff1c-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="aff1c-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="aff1c-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aff1c-108">\<system.serviceModel></span></span>  
<span data-ttu-id="aff1c-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="aff1c-109">\<tracking></span></span>  
<span data-ttu-id="aff1c-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="aff1c-110">\<trackingProfile></span></span>  
<span data-ttu-id="aff1c-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="aff1c-111">\<workflow></span></span>  
<span data-ttu-id="aff1c-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="aff1c-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff1c-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aff1c-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aff1c-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aff1c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="aff1c-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aff1c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aff1c-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="aff1c-116">Attributes</span></span>  
 <span data-ttu-id="aff1c-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="aff1c-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aff1c-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aff1c-118">Child Elements</span></span>  
  
|<span data-ttu-id="aff1c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="aff1c-119">Element</span></span>|<span data-ttu-id="aff1c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aff1c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff1c-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="aff1c-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="aff1c-122">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="aff1c-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="aff1c-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="aff1c-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aff1c-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aff1c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="aff1c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="aff1c-125">Element</span></span>|<span data-ttu-id="aff1c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aff1c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff1c-127">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="aff1c-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="aff1c-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="aff1c-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aff1c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aff1c-129">See Also</span></span>  
 <span data-ttu-id="aff1c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="aff1c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="aff1c-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="aff1c-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="aff1c-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aff1c-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="aff1c-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="aff1c-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
