---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 0424c01397a95803b9e8502d90a55d1bd4c3b5e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269393"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="613de-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="613de-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="613de-102">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="613de-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="613de-103">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="613de-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="613de-104">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="613de-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="613de-105">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="613de-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="613de-106">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="613de-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="613de-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="613de-107">\<system.serviceModel></span></span>  
<span data-ttu-id="613de-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="613de-108">\<tracking></span></span>  
<span data-ttu-id="613de-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="613de-109">\<trackingProfile></span></span>  
<span data-ttu-id="613de-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="613de-110">\<workflow></span></span>  
<span data-ttu-id="613de-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="613de-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="613de-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="613de-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="613de-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="613de-113">Attributes and Elements</span></span>  
 <span data-ttu-id="613de-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="613de-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="613de-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="613de-115">Attributes</span></span>  
 <span data-ttu-id="613de-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="613de-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="613de-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="613de-117">Child Elements</span></span>  
  
|<span data-ttu-id="613de-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="613de-118">Element</span></span>|<span data-ttu-id="613de-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="613de-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="613de-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="613de-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="613de-121">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="613de-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="613de-122">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="613de-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="613de-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="613de-123">Parent Elements</span></span>  
  
|<span data-ttu-id="613de-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="613de-124">Element</span></span>|<span data-ttu-id="613de-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="613de-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="613de-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="613de-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="613de-127">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="613de-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="613de-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="613de-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="613de-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="613de-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="613de-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="613de-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
