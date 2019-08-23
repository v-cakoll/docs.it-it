---
title: <states> di <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 50827577374859133e6c673e8850e145b4ccab73
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947424"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="9799e-102">\<Stati > di \<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="9799e-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="9799e-103">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="9799e-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="9799e-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9799e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9799e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9799e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9799e-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="9799e-106">\<tracking></span></span>  
<span data-ttu-id="9799e-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9799e-107">\<trackingProfile></span></span>  
<span data-ttu-id="9799e-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9799e-108">\<workflow></span></span>  
<span data-ttu-id="9799e-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="9799e-109">\<activityStateQueries></span></span>  
<span data-ttu-id="9799e-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="9799e-110">\<activityStateQuery></span></span>  
<span data-ttu-id="9799e-111">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="9799e-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9799e-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9799e-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9799e-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9799e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9799e-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9799e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9799e-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="9799e-115">Attributes</span></span>  
 <span data-ttu-id="9799e-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9799e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9799e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9799e-117">Child Elements</span></span>  
  
|<span data-ttu-id="9799e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9799e-118">Element</span></span>|<span data-ttu-id="9799e-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9799e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9799e-120">\<state></span><span class="sxs-lookup"><span data-stu-id="9799e-120">\<state></span></span>](state-of-states.md)|<span data-ttu-id="9799e-121">Elemento di configurazione contenente gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="9799e-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9799e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9799e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9799e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="9799e-123">Element</span></span>|<span data-ttu-id="9799e-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9799e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9799e-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="9799e-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="9799e-126">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="9799e-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9799e-127">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="9799e-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9799e-128">Note</span><span class="sxs-lookup"><span data-stu-id="9799e-128">Remarks</span></span>  
 <span data-ttu-id="9799e-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9799e-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="9799e-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9799e-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="9799e-131">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="9799e-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="9799e-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="9799e-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="9799e-133">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="9799e-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9799e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9799e-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9799e-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9799e-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9799e-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9799e-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
