---
title: '&lt;Variabile&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 7d41d80bfe83cfafca01509d50709e21730bcb97
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756787"
---
# <a name="ltvariablegt"></a><span data-ttu-id="e9bed-102">&lt;Variabile&gt;</span><span class="sxs-lookup"><span data-stu-id="e9bed-102">&lt;variable&gt;</span></span>
<span data-ttu-id="e9bed-103">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="e9bed-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="e9bed-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e9bed-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e9bed-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e9bed-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e9bed-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="e9bed-106">\<tracking></span></span>  
<span data-ttu-id="e9bed-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="e9bed-107">\<profiles></span></span>  
<span data-ttu-id="e9bed-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e9bed-108">\<trackingProfile></span></span>  
<span data-ttu-id="e9bed-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e9bed-109">\<workflow></span></span>  
<span data-ttu-id="e9bed-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="e9bed-110">\<activityStateQueries></span></span>  
<span data-ttu-id="e9bed-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="e9bed-111">\<activityStateQuery></span></span>  
<span data-ttu-id="e9bed-112">\<le variabili ></span><span class="sxs-lookup"><span data-stu-id="e9bed-112">\<variables></span></span>  
<span data-ttu-id="e9bed-113">\<variabile ></span><span class="sxs-lookup"><span data-stu-id="e9bed-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9bed-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9bed-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9bed-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9bed-115">Attributes and Elements</span></span>  
 <span data-ttu-id="e9bed-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9bed-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9bed-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9bed-117">Attributes</span></span>  
  
|<span data-ttu-id="e9bed-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="e9bed-118">Attribute</span></span>|<span data-ttu-id="e9bed-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9bed-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9bed-120">name</span><span class="sxs-lookup"><span data-stu-id="e9bed-120">name</span></span>|<span data-ttu-id="e9bed-121">Stringa che specifica il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="e9bed-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9bed-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9bed-122">Child Elements</span></span>  
 <span data-ttu-id="e9bed-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e9bed-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9bed-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9bed-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e9bed-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9bed-125">Element</span></span>|<span data-ttu-id="e9bed-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9bed-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9bed-127">\<variabile ></span><span class="sxs-lookup"><span data-stu-id="e9bed-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="e9bed-128">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e9bed-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9bed-129">Note</span><span class="sxs-lookup"><span data-stu-id="e9bed-129">Remarks</span></span>  
 <span data-ttu-id="e9bed-130">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e9bed-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="e9bed-131">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9bed-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="e9bed-132">È possibile utilizzare il [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi per estrarre qualsiasi variabile o argomento da qualsiasi attività di un flusso di lavoro. Nell'esempio seguente viene illustrata una query sullo stato di attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e9bed-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="e9bed-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e pertanto vengono sottoscritti all'interno di un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="e9bed-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9bed-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9bed-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="e9bed-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e9bed-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e9bed-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e9bed-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
