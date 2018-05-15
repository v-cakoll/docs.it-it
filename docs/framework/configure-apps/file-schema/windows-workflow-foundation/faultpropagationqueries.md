---
title: '&lt;faultPropagationQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 5fd6ffc9560247089c7fbb60b0e5a7d3a417ea6f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltfaultpropagationqueriesgt"></a><span data-ttu-id="10e51-102">&lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="10e51-102">&lt;faultPropagationQueries&gt;</span></span>
<span data-ttu-id="10e51-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="10e51-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="10e51-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="10e51-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="10e51-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="10e51-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="10e51-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="10e51-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="10e51-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="10e51-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="10e51-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="10e51-108">\<system.serviceModel></span></span>  
<span data-ttu-id="10e51-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="10e51-109">\<tracking></span></span>  
<span data-ttu-id="10e51-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="10e51-110">\<trackingProfile></span></span>  
<span data-ttu-id="10e51-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="10e51-111">\<workflow></span></span>  
<span data-ttu-id="10e51-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="10e51-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e51-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10e51-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10e51-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="10e51-114">Attributes and Elements</span></span>  
 <span data-ttu-id="10e51-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="10e51-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10e51-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="10e51-116">Attributes</span></span>  
 <span data-ttu-id="10e51-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="10e51-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10e51-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="10e51-118">Child Elements</span></span>  
  
|<span data-ttu-id="10e51-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="10e51-119">Element</span></span>|<span data-ttu-id="10e51-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10e51-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10e51-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="10e51-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="10e51-122">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="10e51-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="10e51-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="10e51-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10e51-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="10e51-124">Parent Elements</span></span>  
  
|<span data-ttu-id="10e51-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="10e51-125">Element</span></span>|<span data-ttu-id="10e51-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10e51-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10e51-127">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="10e51-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="10e51-128">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="10e51-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10e51-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10e51-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="10e51-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="10e51-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="10e51-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="10e51-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
