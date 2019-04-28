---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 539ce0ba72ae7a8d568cdea3a1a3aab3eec1001b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790390"
---
# <a name="activitystatequery"></a><span data-ttu-id="ef6da-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ef6da-101">\<activityStateQuery></span></span>
<span data-ttu-id="ef6da-102">Rappresenta una query usata per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef6da-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ef6da-103">Ad esempio, è possibile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef6da-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ef6da-104">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="ef6da-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ef6da-105">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="ef6da-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="ef6da-106">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ef6da-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ef6da-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ef6da-107">\<system.serviceModel></span></span>  
<span data-ttu-id="ef6da-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ef6da-108">\<tracking></span></span>  
<span data-ttu-id="ef6da-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ef6da-109">\<trackingProfile></span></span>  
<span data-ttu-id="ef6da-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="ef6da-110">\<workflow></span></span>  
<span data-ttu-id="ef6da-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ef6da-111">\<activityStateQueries></span></span>  
<span data-ttu-id="ef6da-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ef6da-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6da-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef6da-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef6da-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef6da-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ef6da-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef6da-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef6da-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef6da-116">Attributes</span></span>  
  
|<span data-ttu-id="ef6da-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="ef6da-117">Attribute</span></span>|<span data-ttu-id="ef6da-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef6da-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef6da-119">activityName</span><span class="sxs-lookup"><span data-stu-id="ef6da-119">activityName</span></span>|<span data-ttu-id="ef6da-120">Stringa che specifica il nome dell'attività per la quale filtrare istanze di <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="ef6da-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef6da-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef6da-121">Child Elements</span></span>  
  
|<span data-ttu-id="ef6da-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef6da-122">Element</span></span>|<span data-ttu-id="ef6da-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef6da-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef6da-124">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="ef6da-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="ef6da-125">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="ef6da-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="ef6da-126">\<states></span><span class="sxs-lookup"><span data-stu-id="ef6da-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="ef6da-127">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ef6da-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="ef6da-128">\<states></span><span class="sxs-lookup"><span data-stu-id="ef6da-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="ef6da-129">Raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="ef6da-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef6da-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef6da-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ef6da-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef6da-131">Element</span></span>|<span data-ttu-id="ef6da-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef6da-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef6da-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ef6da-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="ef6da-134">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="ef6da-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ef6da-135">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="ef6da-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef6da-136">Note</span><span class="sxs-lookup"><span data-stu-id="ef6da-136">Remarks</span></span>  
 <span data-ttu-id="ef6da-137">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef6da-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ef6da-138">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ef6da-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ef6da-139">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef6da-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ef6da-140">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ef6da-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ef6da-141">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="ef6da-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ef6da-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef6da-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ef6da-143">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef6da-143">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef6da-144">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ef6da-144">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
