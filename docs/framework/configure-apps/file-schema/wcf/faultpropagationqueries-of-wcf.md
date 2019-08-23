---
title: <faultPropagationQueries>di WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: aeb964fc8c96c8cb9aeb316bb95f9565fc4a7f18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918949"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="b4843-102">\<> faultPropagationQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="b4843-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="b4843-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="b4843-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b4843-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="b4843-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="b4843-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="b4843-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="b4843-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="b4843-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="b4843-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b4843-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b4843-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b4843-108">\<system.serviceModel></span></span>  
<span data-ttu-id="b4843-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="b4843-109">\<tracking></span></span>  
<span data-ttu-id="b4843-110">\<profili ></span><span class="sxs-lookup"><span data-stu-id="b4843-110">\<profiles></span></span>  
<span data-ttu-id="b4843-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b4843-111">\<trackingProfile></span></span>  
<span data-ttu-id="b4843-112">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b4843-112">\<workflow></span></span>  
<span data-ttu-id="b4843-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="b4843-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4843-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4843-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4843-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b4843-115">Attributes and elements</span></span>

<span data-ttu-id="b4843-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b4843-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b4843-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="b4843-117">Attributes</span></span>

<span data-ttu-id="b4843-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b4843-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="b4843-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b4843-119">Child elements</span></span>

|<span data-ttu-id="b4843-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4843-120">Element</span></span>|<span data-ttu-id="b4843-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4843-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4843-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="b4843-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="b4843-123">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="b4843-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b4843-124">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="b4843-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4843-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b4843-125">Parent elements</span></span>  
  
|<span data-ttu-id="b4843-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4843-126">Element</span></span>|<span data-ttu-id="b4843-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b4843-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4843-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b4843-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="b4843-129">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="b4843-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4843-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4843-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b4843-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b4843-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b4843-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b4843-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
