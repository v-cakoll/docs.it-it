---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: b8052138a729fcba7cb158d81a63126f59e0c4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69988730"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="592a9-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="592a9-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="592a9-102">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="592a9-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="592a9-103">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="592a9-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="592a9-104">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="592a9-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="592a9-105">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="592a9-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="592a9-106">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="592a9-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="592a9-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="592a9-107">\<system.serviceModel></span></span>  
<span data-ttu-id="592a9-108">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="592a9-108">\<tracking></span></span>  
<span data-ttu-id="592a9-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="592a9-109">\<trackingProfile></span></span>  
<span data-ttu-id="592a9-110">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="592a9-110">\<workflow></span></span>  
<span data-ttu-id="592a9-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="592a9-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="592a9-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="592a9-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="592a9-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="592a9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="592a9-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="592a9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="592a9-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="592a9-115">Attributes</span></span>  
 <span data-ttu-id="592a9-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="592a9-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="592a9-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="592a9-117">Child Elements</span></span>  
  
|<span data-ttu-id="592a9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="592a9-118">Element</span></span>|<span data-ttu-id="592a9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="592a9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="592a9-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="592a9-120">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="592a9-121">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="592a9-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="592a9-122">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="592a9-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="592a9-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="592a9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="592a9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="592a9-124">Element</span></span>|<span data-ttu-id="592a9-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="592a9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="592a9-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="592a9-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="592a9-127">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="592a9-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="592a9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="592a9-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="592a9-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="592a9-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="592a9-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="592a9-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
