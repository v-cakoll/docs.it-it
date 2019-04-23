---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 61a786efc67f4e9afa585864e1f62b966b5cdff8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105378"
---
# <a name="variables"></a><span data-ttu-id="948fc-101">\<variables></span><span class="sxs-lookup"><span data-stu-id="948fc-101">\<variables></span></span>
<span data-ttu-id="948fc-102">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="948fc-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="948fc-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="948fc-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="948fc-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="948fc-104">\<system.serviceModel></span></span>  
<span data-ttu-id="948fc-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="948fc-105">\<tracking></span></span>  
<span data-ttu-id="948fc-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="948fc-106">\<trackingProfile></span></span>  
<span data-ttu-id="948fc-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="948fc-107">\<workflow></span></span>  
<span data-ttu-id="948fc-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="948fc-108">\<activityStateQueries></span></span>  
<span data-ttu-id="948fc-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="948fc-109">\<activityStateQuery></span></span>  
<span data-ttu-id="948fc-110">\<variables></span><span class="sxs-lookup"><span data-stu-id="948fc-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="948fc-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="948fc-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="948fc-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="948fc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="948fc-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="948fc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="948fc-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="948fc-114">Attributes</span></span>  
 <span data-ttu-id="948fc-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="948fc-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="948fc-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="948fc-116">Child Elements</span></span>  
  
|<span data-ttu-id="948fc-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="948fc-117">Element</span></span>|<span data-ttu-id="948fc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="948fc-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="948fc-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="948fc-119">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="948fc-120">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="948fc-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="948fc-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="948fc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="948fc-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="948fc-122">Element</span></span>|<span data-ttu-id="948fc-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="948fc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="948fc-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="948fc-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="948fc-125">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="948fc-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="948fc-126">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="948fc-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="948fc-127">Note</span><span class="sxs-lookup"><span data-stu-id="948fc-127">Remarks</span></span>  
 <span data-ttu-id="948fc-128">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="948fc-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="948fc-129">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="948fc-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="948fc-130">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="948fc-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="948fc-131">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="948fc-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="948fc-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="948fc-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="948fc-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="948fc-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="948fc-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="948fc-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="948fc-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="948fc-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
