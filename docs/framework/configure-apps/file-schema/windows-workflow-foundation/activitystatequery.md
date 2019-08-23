---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 560df771b44fc8ba8d192657677bf0496283b539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945421"
---
# <a name="activitystatequery"></a><span data-ttu-id="f93c3-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="f93c3-101">\<activityStateQuery></span></span>
<span data-ttu-id="f93c3-102">Rappresenta una query usata per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f93c3-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="f93c3-103">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f93c3-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="f93c3-104">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="f93c3-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="f93c3-105">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="f93c3-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="f93c3-106">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f93c3-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f93c3-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f93c3-107">\<system.serviceModel></span></span>  
<span data-ttu-id="f93c3-108">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="f93c3-108">\<tracking></span></span>  
<span data-ttu-id="f93c3-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f93c3-109">\<trackingProfile></span></span>  
<span data-ttu-id="f93c3-110">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f93c3-110">\<workflow></span></span>  
<span data-ttu-id="f93c3-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="f93c3-111">\<activityStateQueries></span></span>  
<span data-ttu-id="f93c3-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="f93c3-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f93c3-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f93c3-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f93c3-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f93c3-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f93c3-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f93c3-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f93c3-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="f93c3-116">Attributes</span></span>  
  
|<span data-ttu-id="f93c3-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="f93c3-117">Attribute</span></span>|<span data-ttu-id="f93c3-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f93c3-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f93c3-119">activityName</span><span class="sxs-lookup"><span data-stu-id="f93c3-119">activityName</span></span>|<span data-ttu-id="f93c3-120">Stringa che specifica il nome dell'attività per la quale filtrare istanze di <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="f93c3-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f93c3-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f93c3-121">Child Elements</span></span>  
  
|<span data-ttu-id="f93c3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f93c3-122">Element</span></span>|<span data-ttu-id="f93c3-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f93c3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f93c3-124">\<Argomenti ></span><span class="sxs-lookup"><span data-stu-id="f93c3-124">\<arguments></span></span>](arguments.md)|<span data-ttu-id="f93c3-125">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="f93c3-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="f93c3-126">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="f93c3-126">\<states></span></span>](states.md)|<span data-ttu-id="f93c3-127">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f93c3-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="f93c3-128">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="f93c3-128">\<states></span></span>](states.md)|<span data-ttu-id="f93c3-129">Raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="f93c3-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f93c3-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f93c3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f93c3-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="f93c3-131">Element</span></span>|<span data-ttu-id="f93c3-132">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f93c3-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f93c3-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="f93c3-133">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="f93c3-134">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="f93c3-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f93c3-135">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="f93c3-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f93c3-136">Note</span><span class="sxs-lookup"><span data-stu-id="f93c3-136">Remarks</span></span>  
 <span data-ttu-id="f93c3-137">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f93c3-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="f93c3-138">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f93c3-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="f93c3-139">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](arguments.md), [ \<gli Stati >](states.md) e [ \<gli Stati >](states.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="f93c3-139">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="f93c3-140">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f93c3-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="f93c3-141">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="f93c3-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f93c3-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f93c3-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f93c3-143">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f93c3-143">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f93c3-144">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f93c3-144">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
