---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: ed08f5533cd6b3839775d061452cb17110cc627e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398897"
---
# <a name="argument"></a><span data-ttu-id="3ba7d-101">\<> argomento</span><span class="sxs-lookup"><span data-stu-id="3ba7d-101">\<argument></span></span>
<span data-ttu-id="3ba7d-102">Elemento di configurazione che rappresenta un argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="3ba7d-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3ba7d-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3ba7d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ba7d-105">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="3ba7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="3ba7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="3ba7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="3ba7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="3ba7d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQuery**](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="3ba7d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Argomenti >** ](arguments.md)</span><span class="sxs-lookup"><span data-stu-id="3ba7d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)</span></span>\
<span data-ttu-id="3ba7d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> argomento**</span><span class="sxs-lookup"><span data-stu-id="3ba7d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba7d-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ba7d-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ba7d-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3ba7d-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3ba7d-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ba7d-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="3ba7d-116">Attributes</span></span>  
  
|<span data-ttu-id="3ba7d-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="3ba7d-117">Attribute</span></span>|<span data-ttu-id="3ba7d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ba7d-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ba7d-119">name</span><span class="sxs-lookup"><span data-stu-id="3ba7d-119">name</span></span>|<span data-ttu-id="3ba7d-120">Stringa che specifica il nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ba7d-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3ba7d-121">Child Elements</span></span>  
 <span data-ttu-id="3ba7d-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ba7d-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3ba7d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3ba7d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ba7d-124">Element</span></span>|<span data-ttu-id="3ba7d-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ba7d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ba7d-126">\<Argomenti ></span><span class="sxs-lookup"><span data-stu-id="3ba7d-126">\<arguments></span></span>](arguments.md)|<span data-ttu-id="3ba7d-127">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ba7d-128">Note</span><span class="sxs-lookup"><span data-stu-id="3ba7d-128">Remarks</span></span>  
 <span data-ttu-id="3ba7d-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="3ba7d-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="3ba7d-131">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="3ba7d-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3ba7d-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="3ba7d-133">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="3ba7d-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ba7d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ba7d-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3ba7d-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3ba7d-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3ba7d-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3ba7d-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
