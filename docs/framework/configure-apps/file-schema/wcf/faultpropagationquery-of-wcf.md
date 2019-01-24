---
title: '&lt;faultPropagationQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 1da2a95d27756296aab5a205a90fb028508c4b76
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601805"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="42356-102">&lt;faultPropagationQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="42356-102">&lt;faultPropagationQuery&gt; of WCF</span></span>

<span data-ttu-id="42356-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="42356-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="42356-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="42356-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="42356-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="42356-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="42356-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="42356-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="42356-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="42356-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="42356-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="42356-108">\<system.serviceModel></span></span>  
<span data-ttu-id="42356-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="42356-109">\<tracking></span></span>  
<span data-ttu-id="42356-110">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="42356-110">\<profiles></span></span>  
<span data-ttu-id="42356-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="42356-111">\<trackingProfile></span></span>  
<span data-ttu-id="42356-112">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="42356-112">\<workflow></span></span>  
<span data-ttu-id="42356-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="42356-113">\<faultPropagationQueries></span></span>  
<span data-ttu-id="42356-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="42356-114">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42356-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42356-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42356-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="42356-116">Attributes and elements</span></span>

<span data-ttu-id="42356-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="42356-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="42356-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="42356-118">Attributes</span></span>  
  
|<span data-ttu-id="42356-119">Attributo</span><span class="sxs-lookup"><span data-stu-id="42356-119">Attribute</span></span>|<span data-ttu-id="42356-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42356-120">Description</span></span>|  
|---------------|-----------------|  
|`faultSourceActivityName`|<span data-ttu-id="42356-121">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="42356-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="42356-122">Il valore predefinito è \*, che indica che i record di propagazione errore vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="42356-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|`faultHandlerActivityName`|<span data-ttu-id="42356-123">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="42356-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42356-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="42356-124">Child elements</span></span>

<span data-ttu-id="42356-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="42356-125">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="42356-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="42356-126">Parent elements</span></span>  
  
|<span data-ttu-id="42356-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="42356-127">Element</span></span>|<span data-ttu-id="42356-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42356-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42356-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="42356-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="42356-130">Rappresenta un elenco di elementi di configurazione usati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="42356-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="42356-131">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="42356-131">This event occurs each time a FaultHandler processes a fault.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="42356-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42356-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="42356-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="42356-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="42356-134">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="42356-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
