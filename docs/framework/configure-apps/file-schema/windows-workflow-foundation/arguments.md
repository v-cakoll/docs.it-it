---
title: '&lt;Argomenti&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: ae2fd4a05cc8ca93cd74ccceb08a7a077b504f0c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltargumentsgt"></a><span data-ttu-id="37f77-102">&lt;Argomenti&gt;</span><span class="sxs-lookup"><span data-stu-id="37f77-102">&lt;arguments&gt;</span></span>
<span data-ttu-id="37f77-103">Rappresenta una raccolta di argomenti associati a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="37f77-103">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="37f77-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="37f77-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="37f77-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="37f77-105">\<system.serviceModel></span></span>  
<span data-ttu-id="37f77-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="37f77-106">\<tracking></span></span>  
<span data-ttu-id="37f77-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="37f77-107">\<trackingProfile></span></span>  
<span data-ttu-id="37f77-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="37f77-108">\<workflow></span></span>  
<span data-ttu-id="37f77-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="37f77-109">\<activityStateQueries></span></span>  
<span data-ttu-id="37f77-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="37f77-110">\<activityStateQuery></span></span>  
<span data-ttu-id="37f77-111">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="37f77-111">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f77-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37f77-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37f77-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="37f77-113">Attributes and Elements</span></span>  
 <span data-ttu-id="37f77-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="37f77-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37f77-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="37f77-115">Attributes</span></span>  
 <span data-ttu-id="37f77-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="37f77-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="37f77-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="37f77-117">Child Elements</span></span>  
  
|<span data-ttu-id="37f77-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="37f77-118">Element</span></span>|<span data-ttu-id="37f77-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37f77-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37f77-120">\<argomento ></span><span class="sxs-lookup"><span data-stu-id="37f77-120">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="37f77-121">Argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="37f77-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37f77-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="37f77-122">Parent Elements</span></span>  
  
|<span data-ttu-id="37f77-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="37f77-123">Element</span></span>|<span data-ttu-id="37f77-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37f77-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37f77-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="37f77-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="37f77-126">Rappresenta un elemento di configurazione usato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="37f77-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="37f77-127">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="37f77-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37f77-128">Note</span><span class="sxs-lookup"><span data-stu-id="37f77-128">Remarks</span></span>  
 <span data-ttu-id="37f77-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="37f77-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="37f77-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="37f77-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="37f77-131">È possibile utilizzare il [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi per estrarre qualsiasi variabile o argomento da qualsiasi attività di un flusso di lavoro. Nell'esempio seguente viene illustrata una query sullo stato di attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="37f77-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="37f77-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e pertanto vengono sottoscritti all'interno di un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="37f77-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="37f77-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37f77-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="37f77-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="37f77-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="37f77-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="37f77-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
