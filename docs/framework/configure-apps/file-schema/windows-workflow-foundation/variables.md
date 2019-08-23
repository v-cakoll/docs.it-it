---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 563ce96f61bbb39f1590ca0f43c163ea2d3d7961
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947249"
---
# <a name="variables"></a><span data-ttu-id="95071-101">\<variabili ></span><span class="sxs-lookup"><span data-stu-id="95071-101">\<variables></span></span>
<span data-ttu-id="95071-102">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="95071-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="95071-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="95071-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="95071-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="95071-104">\<system.serviceModel></span></span>  
<span data-ttu-id="95071-105">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="95071-105">\<tracking></span></span>  
<span data-ttu-id="95071-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="95071-106">\<trackingProfile></span></span>  
<span data-ttu-id="95071-107">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="95071-107">\<workflow></span></span>  
<span data-ttu-id="95071-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="95071-108">\<activityStateQueries></span></span>  
<span data-ttu-id="95071-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="95071-109">\<activityStateQuery></span></span>  
<span data-ttu-id="95071-110">\<variabili ></span><span class="sxs-lookup"><span data-stu-id="95071-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95071-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95071-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95071-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="95071-112">Attributes and Elements</span></span>  
 <span data-ttu-id="95071-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="95071-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95071-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="95071-114">Attributes</span></span>  
 <span data-ttu-id="95071-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="95071-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95071-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="95071-116">Child Elements</span></span>  
  
|<span data-ttu-id="95071-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="95071-117">Element</span></span>|<span data-ttu-id="95071-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95071-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95071-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="95071-119">\<variable></span></span>](variable.md)|<span data-ttu-id="95071-120">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="95071-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95071-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="95071-121">Parent Elements</span></span>  
  
|<span data-ttu-id="95071-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="95071-122">Element</span></span>|<span data-ttu-id="95071-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95071-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95071-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="95071-124">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="95071-125">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="95071-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="95071-126">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="95071-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95071-127">Note</span><span class="sxs-lookup"><span data-stu-id="95071-127">Remarks</span></span>  
 <span data-ttu-id="95071-128">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="95071-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="95071-129">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95071-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="95071-130">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="95071-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="95071-131">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="95071-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="95071-132">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="95071-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="95071-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95071-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="95071-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="95071-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="95071-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="95071-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
