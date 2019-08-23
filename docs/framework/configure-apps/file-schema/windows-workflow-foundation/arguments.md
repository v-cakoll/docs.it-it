---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: bb7ae702209df3c0297ec2cfac6b09ee47ad9558
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946122"
---
# <a name="arguments"></a><span data-ttu-id="986de-101">\<Argomenti ></span><span class="sxs-lookup"><span data-stu-id="986de-101">\<arguments></span></span>
<span data-ttu-id="986de-102">Rappresenta una raccolta di argomenti associati a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="986de-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="986de-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="986de-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="986de-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="986de-104">\<system.serviceModel></span></span>  
<span data-ttu-id="986de-105">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="986de-105">\<tracking></span></span>  
<span data-ttu-id="986de-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="986de-106">\<trackingProfile></span></span>  
<span data-ttu-id="986de-107">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="986de-107">\<workflow></span></span>  
<span data-ttu-id="986de-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="986de-108">\<activityStateQueries></span></span>  
<span data-ttu-id="986de-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="986de-109">\<activityStateQuery></span></span>  
<span data-ttu-id="986de-110">\<Argomenti ></span><span class="sxs-lookup"><span data-stu-id="986de-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="986de-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="986de-111">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="986de-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="986de-112">Attributes and Elements</span></span>  
 <span data-ttu-id="986de-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="986de-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="986de-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="986de-114">Attributes</span></span>  
 <span data-ttu-id="986de-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="986de-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="986de-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="986de-116">Child Elements</span></span>  
  
|<span data-ttu-id="986de-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="986de-117">Element</span></span>|<span data-ttu-id="986de-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="986de-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="986de-119">\<> argomento</span><span class="sxs-lookup"><span data-stu-id="986de-119">\<argument></span></span>](argument.md)|<span data-ttu-id="986de-120">Argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="986de-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="986de-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="986de-121">Parent Elements</span></span>  
  
|<span data-ttu-id="986de-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="986de-122">Element</span></span>|<span data-ttu-id="986de-123">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="986de-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="986de-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="986de-124">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="986de-125">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="986de-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="986de-126">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="986de-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="986de-127">Note</span><span class="sxs-lookup"><span data-stu-id="986de-127">Remarks</span></span>  
 <span data-ttu-id="986de-128">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="986de-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="986de-129">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="986de-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="986de-130">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="986de-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="986de-131">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="986de-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="986de-132">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="986de-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="986de-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="986de-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="986de-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="986de-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="986de-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="986de-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
