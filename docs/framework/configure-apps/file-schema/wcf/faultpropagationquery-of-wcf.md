---
title: '&lt;faultPropagationQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: c3853c470a9243835e071d35008dfff5b885591d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123319"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="22490-102">&lt;faultPropagationQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="22490-102">&lt;faultPropagationQuery&gt; of WCF</span></span>

<span data-ttu-id="22490-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="22490-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="22490-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="22490-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="22490-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="22490-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="22490-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="22490-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="22490-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="22490-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="22490-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="22490-108">\<system.serviceModel></span></span>  
<span data-ttu-id="22490-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="22490-109">\<tracking></span></span>  
<span data-ttu-id="22490-110">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="22490-110">\<profiles></span></span>  
<span data-ttu-id="22490-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="22490-111">\<trackingProfile></span></span>  
<span data-ttu-id="22490-112">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="22490-112">\<workflow></span></span>  
<span data-ttu-id="22490-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="22490-113">\<faultPropagationQueries></span></span>  
<span data-ttu-id="22490-114">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="22490-114">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22490-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22490-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22490-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="22490-116">Attributes and elements</span></span>

<span data-ttu-id="22490-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="22490-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="22490-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="22490-118">Attributes</span></span>  
  
|<span data-ttu-id="22490-119">Attributo</span><span class="sxs-lookup"><span data-stu-id="22490-119">Attribute</span></span>|<span data-ttu-id="22490-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22490-120">Description</span></span>|  
|---------------|-----------------|  
|`faultSourceActivityName`|<span data-ttu-id="22490-121">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="22490-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="22490-122">Il valore predefinito è \*, che indica che i record di propagazione errore vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="22490-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|`faultHandlerActivityName`|<span data-ttu-id="22490-123">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="22490-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22490-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="22490-124">Child elements</span></span>

<span data-ttu-id="22490-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="22490-125">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="22490-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="22490-126">Parent elements</span></span>  
  
|<span data-ttu-id="22490-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="22490-127">Element</span></span>|<span data-ttu-id="22490-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22490-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22490-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="22490-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="22490-130">Rappresenta un elenco di elementi di configurazione usati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="22490-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="22490-131">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="22490-131">This event occurs each time a FaultHandler processes a fault.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="22490-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22490-132">See also</span></span>  
 
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="22490-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="22490-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="22490-134">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="22490-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
