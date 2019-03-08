---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f3e281ff8a9de9be41dd6ad9d01ab52798d8e89e
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679359"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="c345c-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c345c-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="c345c-102">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="c345c-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c345c-103">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="c345c-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="c345c-104">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="c345c-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="c345c-105">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="c345c-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="c345c-106">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c345c-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="c345c-107">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="c345c-107">\<system.serviceModel>\\</span></span>
<span data-ttu-id="c345c-108">\<tracking>\\</span><span class="sxs-lookup"><span data-stu-id="c345c-108">\<tracking>\\</span></span>
<span data-ttu-id="c345c-109">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="c345c-109">\<trackingProfile>\\</span></span>
<span data-ttu-id="c345c-110">\<flusso di lavoro > \\</span><span class="sxs-lookup"><span data-stu-id="c345c-110">\<workflow>\\</span></span>
<span data-ttu-id="c345c-111">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="c345c-111">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="c345c-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c345c-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="c345c-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c345c-113">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="c345c-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c345c-114">Attributes and Elements</span></span>

<span data-ttu-id="c345c-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c345c-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c345c-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="c345c-116">Attributes</span></span>

|<span data-ttu-id="c345c-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="c345c-117">Attribute</span></span>|<span data-ttu-id="c345c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c345c-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="c345c-119">activityName</span><span class="sxs-lookup"><span data-stu-id="c345c-119">activityName</span></span>|<span data-ttu-id="c345c-120">Stringa che specifica il nome dell'attività del gestore fault che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="c345c-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="c345c-121">L'impostazione predefinita è \* che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="c345c-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="c345c-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="c345c-122">faultHandlerActivityName</span></span>|<span data-ttu-id="c345c-123">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="c345c-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c345c-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c345c-124">Child Elements</span></span>

<span data-ttu-id="c345c-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c345c-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c345c-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c345c-126">Parent Elements</span></span>

|<span data-ttu-id="c345c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c345c-127">Element</span></span>|<span data-ttu-id="c345c-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c345c-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c345c-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c345c-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="c345c-130">Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="c345c-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c345c-131">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="c345c-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c345c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c345c-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c345c-133">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c345c-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c345c-134">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c345c-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
