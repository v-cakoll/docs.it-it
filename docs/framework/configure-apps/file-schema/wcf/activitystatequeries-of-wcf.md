---
title: <activityStateQueries>di WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 415cd4a75ecab725f91bcd298f8a7966ea6079d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920292"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="dff14-102">\<> activityStateQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="dff14-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="dff14-103">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dff14-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="dff14-104">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dff14-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="dff14-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="dff14-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="dff14-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="dff14-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="dff14-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dff14-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="dff14-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dff14-108">\<system.serviceModel></span></span>  
<span data-ttu-id="dff14-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dff14-109">\<tracking></span></span>  
<span data-ttu-id="dff14-110">\<profili ></span><span class="sxs-lookup"><span data-stu-id="dff14-110">\<profiles></span></span>  
<span data-ttu-id="dff14-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dff14-111">\<trackingProfile></span></span>  
<span data-ttu-id="dff14-112">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dff14-112">\<workflow></span></span>  
<span data-ttu-id="dff14-113">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="dff14-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="dff14-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dff14-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="dff14-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dff14-115">Attributes and elements</span></span>

<span data-ttu-id="dff14-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dff14-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="dff14-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="dff14-117">Attributes</span></span>  

<span data-ttu-id="dff14-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dff14-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="dff14-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dff14-119">Child elements</span></span>

|<span data-ttu-id="dff14-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="dff14-120">Element</span></span>|<span data-ttu-id="dff14-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dff14-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dff14-122">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="dff14-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="dff14-123">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="dff14-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dff14-124">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="dff14-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dff14-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dff14-125">Parent elements</span></span>

|<span data-ttu-id="dff14-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="dff14-126">Element</span></span>|<span data-ttu-id="dff14-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dff14-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dff14-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="dff14-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="dff14-129">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="dff14-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="dff14-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dff14-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="dff14-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dff14-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dff14-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dff14-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
