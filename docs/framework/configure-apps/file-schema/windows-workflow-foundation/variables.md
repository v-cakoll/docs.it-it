---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3e48256ab1127d45e95c557aa9c2434419d9ea59
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397586"
---
# <a name="variables"></a><span data-ttu-id="fdd22-101">\<variabili ></span><span class="sxs-lookup"><span data-stu-id="fdd22-101">\<variables></span></span>
<span data-ttu-id="fdd22-102">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="fdd22-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="fdd22-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fdd22-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="fdd22-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fdd22-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fdd22-105">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fdd22-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="fdd22-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="fdd22-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="fdd22-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="fdd22-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="fdd22-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fdd22-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="fdd22-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="fdd22-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="fdd22-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQuery**](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="fdd22-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="fdd22-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<variabili >**</span><span class="sxs-lookup"><span data-stu-id="fdd22-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdd22-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdd22-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdd22-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fdd22-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fdd22-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fdd22-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdd22-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="fdd22-115">Attributes</span></span>  
 <span data-ttu-id="fdd22-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fdd22-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fdd22-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fdd22-117">Child Elements</span></span>  
  
|<span data-ttu-id="fdd22-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdd22-118">Element</span></span>|<span data-ttu-id="fdd22-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="fdd22-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdd22-120">\<variable></span><span class="sxs-lookup"><span data-stu-id="fdd22-120">\<variable></span></span>](variable.md)|<span data-ttu-id="fdd22-121">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="fdd22-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fdd22-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fdd22-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fdd22-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdd22-123">Element</span></span>|<span data-ttu-id="fdd22-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdd22-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdd22-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="fdd22-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="fdd22-126">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="fdd22-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="fdd22-127">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="fdd22-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdd22-128">Note</span><span class="sxs-lookup"><span data-stu-id="fdd22-128">Remarks</span></span>  
 <span data-ttu-id="fdd22-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fdd22-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="fdd22-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fdd22-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="fdd22-131">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="fdd22-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="fdd22-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="fdd22-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="fdd22-133">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="fdd22-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fdd22-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdd22-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fdd22-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fdd22-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fdd22-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="fdd22-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
