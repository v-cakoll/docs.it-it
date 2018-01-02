---
title: '&lt;variabile&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 971e3e366c2383828dde8e8f152660fb39c886ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="990e0-102">&lt;variabile&gt;</span><span class="sxs-lookup"><span data-stu-id="990e0-102">&lt;variable&gt;</span></span>
<span data-ttu-id="990e0-103">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="990e0-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="990e0-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="990e0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="990e0-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="990e0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="990e0-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="990e0-106">\<tracking></span></span>  
<span data-ttu-id="990e0-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="990e0-107">\<profiles></span></span>  
<span data-ttu-id="990e0-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="990e0-108">\<trackingProfile></span></span>  
<span data-ttu-id="990e0-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="990e0-109">\<workflow></span></span>  
<span data-ttu-id="990e0-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="990e0-110">\<activityStateQueries></span></span>  
<span data-ttu-id="990e0-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="990e0-111">\<activityStateQuery></span></span>  
<span data-ttu-id="990e0-112">\<le variabili ></span><span class="sxs-lookup"><span data-stu-id="990e0-112">\<variables></span></span>  
<span data-ttu-id="990e0-113">\<variabile ></span><span class="sxs-lookup"><span data-stu-id="990e0-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="990e0-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="990e0-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="990e0-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="990e0-115">Attributes and Elements</span></span>  
 <span data-ttu-id="990e0-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="990e0-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="990e0-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="990e0-117">Attributes</span></span>  
  
|<span data-ttu-id="990e0-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="990e0-118">Attribute</span></span>|<span data-ttu-id="990e0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="990e0-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="990e0-120">name</span><span class="sxs-lookup"><span data-stu-id="990e0-120">name</span></span>|<span data-ttu-id="990e0-121">Stringa che specifica il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="990e0-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="990e0-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="990e0-122">Child Elements</span></span>  
 <span data-ttu-id="990e0-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="990e0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="990e0-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="990e0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="990e0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="990e0-125">Element</span></span>|<span data-ttu-id="990e0-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="990e0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="990e0-127">\<variabile ></span><span class="sxs-lookup"><span data-stu-id="990e0-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="990e0-128">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="990e0-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="990e0-129">Note</span><span class="sxs-lookup"><span data-stu-id="990e0-129">Remarks</span></span>  
 <span data-ttu-id="990e0-130">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="990e0-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="990e0-131">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="990e0-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="990e0-132">È possibile utilizzare il [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi per estrarre qualsiasi variabile o argomento da qualsiasi attività di un flusso di lavoro. Nell'esempio seguente viene illustrata una query sullo stato di attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="990e0-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="990e0-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e pertanto vengono sottoscritti all'interno di un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="990e0-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="990e0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="990e0-134">See Also</span></span>  
 <span data-ttu-id="990e0-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="990e0-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="990e0-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="990e0-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="990e0-137">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="990e0-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="990e0-138">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="990e0-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
