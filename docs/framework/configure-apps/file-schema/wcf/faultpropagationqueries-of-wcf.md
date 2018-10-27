---
title: '&lt;faultPropagationQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 1db99a8d80fad5c0eca93777d87047b43371d048
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044411"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="4814c-102">&lt;faultPropagationQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="4814c-102">&lt;faultPropagationQueries&gt; of WCF</span></span>

<span data-ttu-id="4814c-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4814c-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4814c-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="4814c-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="4814c-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4814c-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="4814c-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="4814c-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="4814c-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4814c-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4814c-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4814c-108">\<system.serviceModel></span></span>  
<span data-ttu-id="4814c-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="4814c-109">\<tracking></span></span>  
<span data-ttu-id="4814c-110">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="4814c-110">\<profiles></span></span>  
<span data-ttu-id="4814c-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4814c-111">\<trackingProfile></span></span>  
<span data-ttu-id="4814c-112">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="4814c-112">\<workflow></span></span>  
<span data-ttu-id="4814c-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="4814c-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4814c-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4814c-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="4814c-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4814c-115">Attributes and elements</span></span>

<span data-ttu-id="4814c-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4814c-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4814c-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="4814c-117">Attributes</span></span>

<span data-ttu-id="4814c-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4814c-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="4814c-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4814c-119">Child elements</span></span>

|<span data-ttu-id="4814c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4814c-120">Element</span></span>|<span data-ttu-id="4814c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4814c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4814c-122">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="4814c-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="4814c-123">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4814c-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4814c-124">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="4814c-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4814c-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4814c-125">Parent elements</span></span>  
  
|<span data-ttu-id="4814c-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="4814c-126">Element</span></span>|<span data-ttu-id="4814c-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4814c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4814c-128">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="4814c-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="4814c-129">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="4814c-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4814c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4814c-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4814c-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4814c-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4814c-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4814c-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
