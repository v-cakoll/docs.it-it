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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ea84694f054370f1e888263d826460c1bff28c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="945cf-102">&lt;faultPropagationQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="945cf-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="945cf-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="945cf-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="945cf-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="945cf-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="945cf-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="945cf-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="945cf-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="945cf-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="945cf-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="945cf-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="945cf-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="945cf-108">\<system.serviceModel></span></span>  
<span data-ttu-id="945cf-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="945cf-109">\<tracking></span></span>  
<span data-ttu-id="945cf-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="945cf-110">\<trackingProfile></span></span>  
<span data-ttu-id="945cf-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="945cf-111">\<workflow></span></span>  
<span data-ttu-id="945cf-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="945cf-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="945cf-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="945cf-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="945cf-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="945cf-114">Attributes and Elements</span></span>  
 <span data-ttu-id="945cf-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="945cf-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="945cf-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="945cf-116">Attributes</span></span>  
 <span data-ttu-id="945cf-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="945cf-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="945cf-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="945cf-118">Child Elements</span></span>  
  
|<span data-ttu-id="945cf-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="945cf-119">Element</span></span>|<span data-ttu-id="945cf-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="945cf-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="945cf-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="945cf-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="945cf-122">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="945cf-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="945cf-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="945cf-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="945cf-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="945cf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="945cf-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="945cf-125">Element</span></span>|<span data-ttu-id="945cf-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="945cf-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="945cf-127">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="945cf-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="945cf-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="945cf-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="945cf-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="945cf-129">See Also</span></span>  
 <span data-ttu-id="945cf-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="945cf-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="945cf-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="945cf-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="945cf-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="945cf-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="945cf-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="945cf-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
