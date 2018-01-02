---
title: '&lt;variables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49255241e7adc187c2df68407cae05573fc3d4d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltvariablesgt"></a><span data-ttu-id="4987b-102">&lt;variables&gt;</span><span class="sxs-lookup"><span data-stu-id="4987b-102">&lt;variables&gt;</span></span>
<span data-ttu-id="4987b-103">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="4987b-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="4987b-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4987b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4987b-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4987b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4987b-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="4987b-106">\<tracking></span></span>  
<span data-ttu-id="4987b-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4987b-107">\<trackingProfile></span></span>  
<span data-ttu-id="4987b-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="4987b-108">\<workflow></span></span>  
<span data-ttu-id="4987b-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="4987b-109">\<activityStateQueries></span></span>  
<span data-ttu-id="4987b-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="4987b-110">\<activityStateQuery></span></span>  
<span data-ttu-id="4987b-111">\<le variabili ></span><span class="sxs-lookup"><span data-stu-id="4987b-111">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4987b-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4987b-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4987b-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4987b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4987b-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4987b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4987b-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="4987b-115">Attributes</span></span>  
 <span data-ttu-id="4987b-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4987b-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4987b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4987b-117">Child Elements</span></span>  
  
|<span data-ttu-id="4987b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4987b-118">Element</span></span>|<span data-ttu-id="4987b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4987b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4987b-120">\<variabile ></span><span class="sxs-lookup"><span data-stu-id="4987b-120">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="4987b-121">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="4987b-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4987b-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4987b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4987b-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4987b-123">Element</span></span>|<span data-ttu-id="4987b-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4987b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4987b-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="4987b-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="4987b-126">Rappresenta un elemento di configurazione usato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="4987b-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4987b-127">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="4987b-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4987b-128">Note</span><span class="sxs-lookup"><span data-stu-id="4987b-128">Remarks</span></span>  
 <span data-ttu-id="4987b-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4987b-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="4987b-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4987b-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="4987b-131">È possibile utilizzare il [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi per estrarre qualsiasi variabile o argomento da qualsiasi attività di un flusso di lavoro. Nell'esempio seguente viene illustrata una query sullo stato di attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="4987b-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="4987b-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e pertanto vengono sottoscritti all'interno di un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="4987b-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4987b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4987b-133">See Also</span></span>  
 <span data-ttu-id="4987b-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4987b-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="4987b-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4987b-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="4987b-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4987b-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="4987b-137">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4987b-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
