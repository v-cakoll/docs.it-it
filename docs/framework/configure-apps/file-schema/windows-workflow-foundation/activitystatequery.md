---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 5d3c35589330ab5bed5f89c0dafac006b9e3af55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398944"
---
# <a name="activitystatequery"></a><span data-ttu-id="2389e-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2389e-101">\<activityStateQuery></span></span>
<span data-ttu-id="2389e-102">Rappresenta una query usata per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2389e-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="2389e-103">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2389e-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="2389e-104">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="2389e-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="2389e-105">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="2389e-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="2389e-106">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2389e-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2389e-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2389e-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2389e-108">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2389e-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="2389e-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="2389e-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="2389e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="2389e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="2389e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2389e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="2389e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="2389e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="2389e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityStateQuery**</span><span class="sxs-lookup"><span data-stu-id="2389e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2389e-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2389e-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2389e-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2389e-115">Attributes and Elements</span></span>  
 <span data-ttu-id="2389e-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2389e-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2389e-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="2389e-117">Attributes</span></span>  
  
|<span data-ttu-id="2389e-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="2389e-118">Attribute</span></span>|<span data-ttu-id="2389e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2389e-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2389e-120">activityName</span><span class="sxs-lookup"><span data-stu-id="2389e-120">activityName</span></span>|<span data-ttu-id="2389e-121">Stringa che specifica il nome dell'attività per la quale filtrare istanze di <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="2389e-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2389e-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2389e-122">Child Elements</span></span>  
  
|<span data-ttu-id="2389e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="2389e-123">Element</span></span>|<span data-ttu-id="2389e-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2389e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2389e-125">\<Argomenti ></span><span class="sxs-lookup"><span data-stu-id="2389e-125">\<arguments></span></span>](arguments.md)|<span data-ttu-id="2389e-126">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="2389e-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="2389e-127">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="2389e-127">\<states></span></span>](states.md)|<span data-ttu-id="2389e-128">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2389e-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="2389e-129">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="2389e-129">\<states></span></span>](states.md)|<span data-ttu-id="2389e-130">Raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="2389e-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2389e-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2389e-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2389e-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="2389e-132">Element</span></span>|<span data-ttu-id="2389e-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2389e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2389e-134">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="2389e-134">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="2389e-135">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="2389e-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2389e-136">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="2389e-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2389e-137">Note</span><span class="sxs-lookup"><span data-stu-id="2389e-137">Remarks</span></span>  
 <span data-ttu-id="2389e-138">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2389e-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2389e-139">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2389e-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2389e-140">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="2389e-140">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="2389e-141">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2389e-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2389e-142">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="2389e-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2389e-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2389e-143">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2389e-144">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2389e-144">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2389e-145">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2389e-145">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
