---
title: <activityStateQueries>di WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850576"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="59438-102">\<> activityStateQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="59438-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="59438-103">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="59438-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="59438-104">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="59438-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="59438-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="59438-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="59438-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="59438-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="59438-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="59438-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="59438-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59438-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59438-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="59438-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="59438-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="59438-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="59438-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="59438-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="59438-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="59438-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="59438-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="59438-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="59438-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityStateQueries**</span><span class="sxs-lookup"><span data-stu-id="59438-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59438-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59438-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="59438-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="59438-116">Attributes and elements</span></span>

<span data-ttu-id="59438-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="59438-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="59438-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="59438-118">Attributes</span></span>  

<span data-ttu-id="59438-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="59438-119">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="59438-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="59438-120">Child elements</span></span>

|<span data-ttu-id="59438-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="59438-121">Element</span></span>|<span data-ttu-id="59438-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59438-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59438-123">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="59438-123">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="59438-124">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="59438-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="59438-125">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="59438-125">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="59438-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="59438-126">Parent elements</span></span>

|<span data-ttu-id="59438-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="59438-127">Element</span></span>|<span data-ttu-id="59438-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59438-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59438-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="59438-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="59438-130">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="59438-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="59438-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59438-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="59438-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="59438-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="59438-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="59438-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
