---
title: <faultPropagationQueries> di WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: bc016827c5bb243bc83dbb53c1eda7eec1bfd8c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704011"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="dbfae-102">\<faultPropagationQueries> of WCF</span><span class="sxs-lookup"><span data-stu-id="dbfae-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="dbfae-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="dbfae-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dbfae-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="dbfae-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="dbfae-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="dbfae-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="dbfae-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="dbfae-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="dbfae-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dbfae-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="dbfae-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dbfae-108">\<system.serviceModel></span></span>  
<span data-ttu-id="dbfae-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="dbfae-109">\<tracking></span></span>  
<span data-ttu-id="dbfae-110">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="dbfae-110">\<profiles></span></span>  
<span data-ttu-id="dbfae-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dbfae-111">\<trackingProfile></span></span>  
<span data-ttu-id="dbfae-112">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="dbfae-112">\<workflow></span></span>  
<span data-ttu-id="dbfae-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="dbfae-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbfae-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbfae-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbfae-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dbfae-115">Attributes and elements</span></span>

<span data-ttu-id="dbfae-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dbfae-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="dbfae-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="dbfae-117">Attributes</span></span>

<span data-ttu-id="dbfae-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dbfae-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="dbfae-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dbfae-119">Child elements</span></span>

|<span data-ttu-id="dbfae-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbfae-120">Element</span></span>|<span data-ttu-id="dbfae-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbfae-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbfae-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="dbfae-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="dbfae-123">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="dbfae-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dbfae-124">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="dbfae-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dbfae-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dbfae-125">Parent elements</span></span>  
  
|<span data-ttu-id="dbfae-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbfae-126">Element</span></span>|<span data-ttu-id="dbfae-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbfae-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbfae-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="dbfae-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="dbfae-129">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="dbfae-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbfae-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbfae-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dbfae-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dbfae-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dbfae-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dbfae-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
