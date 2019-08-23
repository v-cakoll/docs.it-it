---
title: <faultPropagationQuery>di WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 6ba6478ca500c0a8ef150966a97898f8743ffdf8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925625"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="7f18e-102">\<> oggetto FaultPropagationQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="7f18e-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="7f18e-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="7f18e-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7f18e-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="7f18e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7f18e-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="7f18e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7f18e-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="7f18e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="7f18e-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7f18e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="7f18e-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7f18e-108">\<system.serviceModel></span></span>\
<span data-ttu-id="7f18e-109">\<rilevamento > </span><span class="sxs-lookup"><span data-stu-id="7f18e-109">\<tracking></span></span>\
<span data-ttu-id="7f18e-110">\<profili > </span><span class="sxs-lookup"><span data-stu-id="7f18e-110">\<profiles></span></span>\
<span data-ttu-id="7f18e-111">\<trackingProfile > </span><span class="sxs-lookup"><span data-stu-id="7f18e-111">\<trackingProfile></span></span>\
<span data-ttu-id="7f18e-112">\<> flusso di lavoro </span><span class="sxs-lookup"><span data-stu-id="7f18e-112">\<workflow></span></span>\
<span data-ttu-id="7f18e-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7f18e-113">\<faultPropagationQueries></span></span>\
<span data-ttu-id="7f18e-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="7f18e-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="7f18e-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f18e-115">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7f18e-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f18e-116">Attributes and elements</span></span>

<span data-ttu-id="7f18e-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f18e-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f18e-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f18e-118">Attributes</span></span>

|<span data-ttu-id="7f18e-119">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f18e-119">Attribute</span></span>|<span data-ttu-id="7f18e-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f18e-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="7f18e-121">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="7f18e-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="7f18e-122">Il valore predefinito \*è, che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="7f18e-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="7f18e-123">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="7f18e-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7f18e-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f18e-124">Child elements</span></span>

<span data-ttu-id="7f18e-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7f18e-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7f18e-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f18e-126">Parent elements</span></span>

|<span data-ttu-id="7f18e-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f18e-127">Element</span></span>|<span data-ttu-id="7f18e-128">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f18e-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f18e-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7f18e-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="7f18e-130">Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="7f18e-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7f18e-131">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="7f18e-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="7f18e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f18e-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7f18e-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="7f18e-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7f18e-134">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="7f18e-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
