---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 5878720f51f4b5cfe3163abf316a867ccda31342
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397772"
---
# <a name="variable"></a><span data-ttu-id="e5eb6-101">\<> variabile</span><span class="sxs-lookup"><span data-stu-id="e5eb6-101">\<variable></span></span>
<span data-ttu-id="e5eb6-102">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="e5eb6-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e5eb6-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e5eb6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5eb6-105">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e5eb6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="e5eb6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="e5eb6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="e5eb6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="e5eb6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQuery**](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="e5eb6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<variabili >** ](variables.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)</span></span>\
<span data-ttu-id="e5eb6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> variabile**</span><span class="sxs-lookup"><span data-stu-id="e5eb6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5eb6-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5eb6-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5eb6-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e5eb6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="e5eb6-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5eb6-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="e5eb6-116">Attributes</span></span>  
  
|<span data-ttu-id="e5eb6-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="e5eb6-117">Attribute</span></span>|<span data-ttu-id="e5eb6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5eb6-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5eb6-119">name</span><span class="sxs-lookup"><span data-stu-id="e5eb6-119">name</span></span>|<span data-ttu-id="e5eb6-120">Stringa che specifica il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5eb6-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e5eb6-121">Child Elements</span></span>  
 <span data-ttu-id="e5eb6-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5eb6-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e5eb6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e5eb6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5eb6-124">Element</span></span>|<span data-ttu-id="e5eb6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5eb6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5eb6-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="e5eb6-126">\<variable></span></span>](variable.md)|<span data-ttu-id="e5eb6-127">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5eb6-128">Note</span><span class="sxs-lookup"><span data-stu-id="e5eb6-128">Remarks</span></span>  
 <span data-ttu-id="e5eb6-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="e5eb6-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="e5eb6-131">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="e5eb6-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="e5eb6-133">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="e5eb6-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5eb6-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5eb6-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e5eb6-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e5eb6-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e5eb6-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e5eb6-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
