---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: a8f66f950db1edf8cd6ec21400785fb7e01b878e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947268"
---
# <a name="variable"></a><span data-ttu-id="df200-101">\<> variabile</span><span class="sxs-lookup"><span data-stu-id="df200-101">\<variable></span></span>
<span data-ttu-id="df200-102">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="df200-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="df200-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="df200-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="df200-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="df200-104">\<system.serviceModel></span></span>  
<span data-ttu-id="df200-105">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="df200-105">\<tracking></span></span>  
<span data-ttu-id="df200-106">\<profili ></span><span class="sxs-lookup"><span data-stu-id="df200-106">\<profiles></span></span>  
<span data-ttu-id="df200-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="df200-107">\<trackingProfile></span></span>  
<span data-ttu-id="df200-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="df200-108">\<workflow></span></span>  
<span data-ttu-id="df200-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="df200-109">\<activityStateQueries></span></span>  
<span data-ttu-id="df200-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="df200-110">\<activityStateQuery></span></span>  
<span data-ttu-id="df200-111">\<variabili ></span><span class="sxs-lookup"><span data-stu-id="df200-111">\<variables></span></span>  
<span data-ttu-id="df200-112">\<> variabile</span><span class="sxs-lookup"><span data-stu-id="df200-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df200-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df200-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df200-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="df200-114">Attributes and Elements</span></span>  
 <span data-ttu-id="df200-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="df200-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df200-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="df200-116">Attributes</span></span>  
  
|<span data-ttu-id="df200-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="df200-117">Attribute</span></span>|<span data-ttu-id="df200-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="df200-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df200-119">name</span><span class="sxs-lookup"><span data-stu-id="df200-119">name</span></span>|<span data-ttu-id="df200-120">Stringa che specifica il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="df200-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df200-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="df200-121">Child Elements</span></span>  
 <span data-ttu-id="df200-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="df200-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df200-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="df200-123">Parent Elements</span></span>  
  
|<span data-ttu-id="df200-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="df200-124">Element</span></span>|<span data-ttu-id="df200-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="df200-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df200-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="df200-126">\<variable></span></span>](variable.md)|<span data-ttu-id="df200-127">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="df200-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df200-128">Note</span><span class="sxs-lookup"><span data-stu-id="df200-128">Remarks</span></span>  
 <span data-ttu-id="df200-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="df200-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="df200-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="df200-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="df200-131">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="df200-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="df200-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="df200-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="df200-133">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="df200-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="df200-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df200-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="df200-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="df200-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="df200-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="df200-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
