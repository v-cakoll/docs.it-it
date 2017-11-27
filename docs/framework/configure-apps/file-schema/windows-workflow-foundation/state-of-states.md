---
title: '&lt;stato&gt; di &lt;stati&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0985c9ea84cc29b1cb8883411d3b9b1e52de97b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="dd73c-102">&lt;stato&gt; di &lt;stati&gt;</span><span class="sxs-lookup"><span data-stu-id="dd73c-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="dd73c-103">Elemento di configurazione contenente lo stato dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dd73c-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="dd73c-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dd73c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="dd73c-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dd73c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="dd73c-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="dd73c-106">\<tracking></span></span>  
<span data-ttu-id="dd73c-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dd73c-107">\<trackingProfile></span></span>  
<span data-ttu-id="dd73c-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="dd73c-108">\<workflow></span></span>  
<span data-ttu-id="dd73c-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="dd73c-109">\<activityStateQueries></span></span>  
<span data-ttu-id="dd73c-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="dd73c-110">\<activityStateQuery></span></span>  
<span data-ttu-id="dd73c-111">\<stati ></span><span class="sxs-lookup"><span data-stu-id="dd73c-111">\<states></span></span>  
<span data-ttu-id="dd73c-112">\<stato ></span><span class="sxs-lookup"><span data-stu-id="dd73c-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd73c-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd73c-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd73c-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd73c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="dd73c-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd73c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd73c-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd73c-116">Attributes</span></span>  
  
|<span data-ttu-id="dd73c-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="dd73c-117">Attribute</span></span>|<span data-ttu-id="dd73c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd73c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd73c-119">name</span><span class="sxs-lookup"><span data-stu-id="dd73c-119">name</span></span>|<span data-ttu-id="dd73c-120">Stringa che specifica lo stato dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dd73c-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd73c-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd73c-121">Child Elements</span></span>  
 <span data-ttu-id="dd73c-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dd73c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd73c-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd73c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dd73c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd73c-124">Element</span></span>|<span data-ttu-id="dd73c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd73c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd73c-126">\<stati ></span><span class="sxs-lookup"><span data-stu-id="dd73c-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="dd73c-127">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dd73c-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd73c-128">Note</span><span class="sxs-lookup"><span data-stu-id="dd73c-128">Remarks</span></span>  
 <span data-ttu-id="dd73c-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dd73c-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="dd73c-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dd73c-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="dd73c-131">È possibile utilizzare il [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi per estrarre qualsiasi variabile o argomento da qualsiasi attività di un flusso di lavoro. Nell'esempio seguente viene illustrata una query sullo stato di attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dd73c-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="dd73c-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e pertanto vengono sottoscritti all'interno di un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="dd73c-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd73c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd73c-133">See Also</span></span>  
 <span data-ttu-id="dd73c-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dd73c-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dd73c-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dd73c-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="dd73c-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dd73c-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dd73c-137">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dd73c-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
