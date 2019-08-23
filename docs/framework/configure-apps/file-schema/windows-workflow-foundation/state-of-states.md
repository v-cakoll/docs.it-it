---
title: <state> di <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 7c7326b2fd5ae39ca4c0f39fac05444802fa3d49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947488"
---
# <a name="state-of-states"></a><span data-ttu-id="9a29a-102">\<stato > degli \<Stati ></span><span class="sxs-lookup"><span data-stu-id="9a29a-102">\<state> of \<states></span></span>
<span data-ttu-id="9a29a-103">Elemento di configurazione contenente lo stato dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="9a29a-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="9a29a-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9a29a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9a29a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9a29a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9a29a-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="9a29a-106">\<tracking></span></span>  
<span data-ttu-id="9a29a-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9a29a-107">\<trackingProfile></span></span>  
<span data-ttu-id="9a29a-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a29a-108">\<workflow></span></span>  
<span data-ttu-id="9a29a-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="9a29a-109">\<activityStateQueries></span></span>  
<span data-ttu-id="9a29a-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="9a29a-110">\<activityStateQuery></span></span>  
<span data-ttu-id="9a29a-111">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="9a29a-111">\<states></span></span>  
<span data-ttu-id="9a29a-112">\<> di stato</span><span class="sxs-lookup"><span data-stu-id="9a29a-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a29a-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a29a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a29a-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9a29a-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9a29a-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9a29a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a29a-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="9a29a-116">Attributes</span></span>  
  
|<span data-ttu-id="9a29a-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="9a29a-117">Attribute</span></span>|<span data-ttu-id="9a29a-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9a29a-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a29a-119">name</span><span class="sxs-lookup"><span data-stu-id="9a29a-119">name</span></span>|<span data-ttu-id="9a29a-120">Stringa che specifica lo stato dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="9a29a-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a29a-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9a29a-121">Child Elements</span></span>  
 <span data-ttu-id="9a29a-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9a29a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a29a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9a29a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9a29a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a29a-124">Element</span></span>|<span data-ttu-id="9a29a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a29a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a29a-126">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="9a29a-126">\<states></span></span>](states-of-activitystatequery.md)|<span data-ttu-id="9a29a-127">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="9a29a-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a29a-128">Note</span><span class="sxs-lookup"><span data-stu-id="9a29a-128">Remarks</span></span>  
 <span data-ttu-id="9a29a-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9a29a-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="9a29a-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9a29a-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="9a29a-131">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="9a29a-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="9a29a-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="9a29a-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="9a29a-133">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="9a29a-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a29a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a29a-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9a29a-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9a29a-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9a29a-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9a29a-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
