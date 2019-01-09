---
title: '&lt;faultPropagationQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 77a38f8474b5e2ac8634d6ea91bc80c6044ff3ed
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144964"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="132f3-102">&lt;faultPropagationQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="132f3-102">&lt;faultPropagationQueries&gt; of WCF</span></span>

<span data-ttu-id="132f3-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="132f3-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="132f3-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="132f3-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="132f3-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="132f3-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="132f3-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="132f3-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="132f3-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="132f3-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="132f3-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="132f3-108">\<system.serviceModel></span></span>  
<span data-ttu-id="132f3-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="132f3-109">\<tracking></span></span>  
<span data-ttu-id="132f3-110">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="132f3-110">\<profiles></span></span>  
<span data-ttu-id="132f3-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="132f3-111">\<trackingProfile></span></span>  
<span data-ttu-id="132f3-112">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="132f3-112">\<workflow></span></span>  
<span data-ttu-id="132f3-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="132f3-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="132f3-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="132f3-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="132f3-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="132f3-115">Attributes and elements</span></span>

<span data-ttu-id="132f3-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="132f3-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="132f3-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="132f3-117">Attributes</span></span>

<span data-ttu-id="132f3-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="132f3-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="132f3-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="132f3-119">Child elements</span></span>

|<span data-ttu-id="132f3-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="132f3-120">Element</span></span>|<span data-ttu-id="132f3-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="132f3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="132f3-122">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="132f3-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="132f3-123">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="132f3-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="132f3-124">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="132f3-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="132f3-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="132f3-125">Parent elements</span></span>  
  
|<span data-ttu-id="132f3-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="132f3-126">Element</span></span>|<span data-ttu-id="132f3-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="132f3-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="132f3-128">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="132f3-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="132f3-129">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="132f3-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="132f3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="132f3-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="132f3-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="132f3-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="132f3-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="132f3-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
