---
title: <faultPropagationQuery>di WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855338"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="d2f8f-102">\<> oggetto FaultPropagationQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="d2f8f-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="d2f8f-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d2f8f-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="d2f8f-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d2f8f-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="d2f8f-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d2f8f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="d2f8f-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2f8f-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2f8f-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d2f8f-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d2f8f-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d2f8f-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="d2f8f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="d2f8f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="d2f8f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d2f8f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="d2f8f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d2f8f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="d2f8f-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> faultPropagationQueries**](faultpropagationqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="d2f8f-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)</span></span>\
<span data-ttu-id="d2f8f-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oggetto FaultPropagationQuery**</span><span class="sxs-lookup"><span data-stu-id="d2f8f-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d2f8f-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2f8f-116">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d2f8f-117">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d2f8f-117">Attributes and elements</span></span>

<span data-ttu-id="d2f8f-118">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-118">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2f8f-119">Attributi</span><span class="sxs-lookup"><span data-stu-id="d2f8f-119">Attributes</span></span>

|<span data-ttu-id="d2f8f-120">Attributo</span><span class="sxs-lookup"><span data-stu-id="d2f8f-120">Attribute</span></span>|<span data-ttu-id="d2f8f-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d2f8f-121">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="d2f8f-122">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-122">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="d2f8f-123">Il valore predefinito \*è, che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-123">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="d2f8f-124">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d2f8f-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d2f8f-125">Child elements</span></span>

<span data-ttu-id="d2f8f-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d2f8f-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d2f8f-127">Parent elements</span></span>

|<span data-ttu-id="d2f8f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2f8f-128">Element</span></span>|<span data-ttu-id="d2f8f-129">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d2f8f-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2f8f-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="d2f8f-130">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="d2f8f-131">Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d2f8f-132">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="d2f8f-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d2f8f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2f8f-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d2f8f-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d2f8f-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d2f8f-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d2f8f-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
