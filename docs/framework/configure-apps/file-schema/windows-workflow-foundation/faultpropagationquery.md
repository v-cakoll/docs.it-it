---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398723"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="36e82-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="36e82-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="36e82-102">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="36e82-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="36e82-103">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="36e82-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="36e82-104">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="36e82-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="36e82-105">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="36e82-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="36e82-106">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="36e82-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="36e82-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36e82-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36e82-108">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="36e82-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="36e82-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="36e82-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="36e82-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="36e82-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="36e82-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="36e82-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="36e82-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> faultPropagationQueries**](faultpropagationqueries.md)</span><span class="sxs-lookup"><span data-stu-id="36e82-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)</span></span>\
<span data-ttu-id="36e82-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oggetto FaultPropagationQuery**</span><span class="sxs-lookup"><span data-stu-id="36e82-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>

## <a name="syntax"></a><span data-ttu-id="36e82-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36e82-114">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="36e82-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="36e82-115">Attributes and Elements</span></span>

<span data-ttu-id="36e82-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="36e82-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="36e82-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="36e82-117">Attributes</span></span>

|<span data-ttu-id="36e82-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="36e82-118">Attribute</span></span>|<span data-ttu-id="36e82-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36e82-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="36e82-120">activityName</span><span class="sxs-lookup"><span data-stu-id="36e82-120">activityName</span></span>|<span data-ttu-id="36e82-121">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="36e82-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="36e82-122">L'impostazione predefinita è \* che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="36e82-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="36e82-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="36e82-123">faultHandlerActivityName</span></span>|<span data-ttu-id="36e82-124">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="36e82-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="36e82-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="36e82-125">Child Elements</span></span>

<span data-ttu-id="36e82-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="36e82-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36e82-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="36e82-127">Parent Elements</span></span>

|<span data-ttu-id="36e82-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="36e82-128">Element</span></span>|<span data-ttu-id="36e82-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36e82-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="36e82-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="36e82-130">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="36e82-131">Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="36e82-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="36e82-132">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="36e82-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="36e82-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36e82-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="36e82-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="36e82-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="36e82-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="36e82-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
