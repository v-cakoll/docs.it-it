---
title: '&lt;gli stati&gt; di &lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: d43a2e93c046e4dc52de504932f768ece09af487
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143389"
---
# <a name="ltstatesgt-of-ltactivitystatequerygt"></a><span data-ttu-id="e0253-102">&lt;gli stati&gt; di &lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="e0253-102">&lt;states&gt; of &lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="e0253-103">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e0253-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="e0253-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e0253-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e0253-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e0253-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e0253-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="e0253-106">\<tracking></span></span>  
<span data-ttu-id="e0253-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e0253-107">\<trackingProfile></span></span>  
<span data-ttu-id="e0253-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e0253-108">\<workflow></span></span>  
<span data-ttu-id="e0253-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="e0253-109">\<activityStateQueries></span></span>  
<span data-ttu-id="e0253-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="e0253-110">\<activityStateQuery></span></span>  
<span data-ttu-id="e0253-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="e0253-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0253-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0253-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0253-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e0253-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e0253-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e0253-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0253-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="e0253-115">Attributes</span></span>  
 <span data-ttu-id="e0253-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e0253-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e0253-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e0253-117">Child Elements</span></span>  
  
|<span data-ttu-id="e0253-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e0253-118">Element</span></span>|<span data-ttu-id="e0253-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0253-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0253-120">\<stato ></span><span class="sxs-lookup"><span data-stu-id="e0253-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="e0253-121">Elemento di configurazione contenente gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e0253-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0253-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e0253-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e0253-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e0253-123">Element</span></span>|<span data-ttu-id="e0253-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0253-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0253-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="e0253-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="e0253-126">Rappresenta un elemento di configurazione usato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e0253-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e0253-127">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="e0253-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0253-128">Note</span><span class="sxs-lookup"><span data-stu-id="e0253-128">Remarks</span></span>  
 <span data-ttu-id="e0253-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e0253-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="e0253-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e0253-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="e0253-131">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e0253-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="e0253-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e0253-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="e0253-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="e0253-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0253-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0253-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>      
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="e0253-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e0253-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e0253-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e0253-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
