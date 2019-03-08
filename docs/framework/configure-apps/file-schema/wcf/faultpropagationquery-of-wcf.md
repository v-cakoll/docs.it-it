---
title: <faultPropagationQuery> di WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: e5793852d49a052d05f6cb2f4efbe166d67afc62
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675407"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="3ba45-102">\<faultPropagationQuery> of WCF</span><span class="sxs-lookup"><span data-stu-id="3ba45-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="3ba45-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="3ba45-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3ba45-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="3ba45-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="3ba45-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="3ba45-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="3ba45-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="3ba45-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="3ba45-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3ba45-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="3ba45-108">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="3ba45-108">\<system.serviceModel>\\</span></span>
<span data-ttu-id="3ba45-109">\<tracking>\\</span><span class="sxs-lookup"><span data-stu-id="3ba45-109">\<tracking>\\</span></span>
<span data-ttu-id="3ba45-110">\<i profili > \\</span><span class="sxs-lookup"><span data-stu-id="3ba45-110">\<profiles>\\</span></span>
<span data-ttu-id="3ba45-111">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="3ba45-111">\<trackingProfile>\\</span></span>
<span data-ttu-id="3ba45-112">\<flusso di lavoro > \\</span><span class="sxs-lookup"><span data-stu-id="3ba45-112">\<workflow>\\</span></span>
<span data-ttu-id="3ba45-113">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="3ba45-113">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="3ba45-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="3ba45-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="3ba45-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ba45-115">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3ba45-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3ba45-116">Attributes and elements</span></span>

<span data-ttu-id="3ba45-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3ba45-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3ba45-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="3ba45-118">Attributes</span></span>

|<span data-ttu-id="3ba45-119">Attributo</span><span class="sxs-lookup"><span data-stu-id="3ba45-119">Attribute</span></span>|<span data-ttu-id="3ba45-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ba45-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="3ba45-121">Stringa che specifica il nome dell'attività del gestore fault che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="3ba45-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="3ba45-122">Il valore predefinito è \*, che indica che i record di propagazione errore vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="3ba45-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="3ba45-123">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="3ba45-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3ba45-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3ba45-124">Child elements</span></span>

<span data-ttu-id="3ba45-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3ba45-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3ba45-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3ba45-126">Parent elements</span></span>

|<span data-ttu-id="3ba45-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ba45-127">Element</span></span>|<span data-ttu-id="3ba45-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ba45-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3ba45-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="3ba45-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="3ba45-130">Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="3ba45-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3ba45-131">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="3ba45-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3ba45-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ba45-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3ba45-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3ba45-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3ba45-134">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3ba45-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
