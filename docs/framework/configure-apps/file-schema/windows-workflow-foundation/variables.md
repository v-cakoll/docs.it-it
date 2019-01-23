---
title: '&lt;variables&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: c3861eb02d7b19bde6932c67c3d5d19b82fd8fcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520538"
---
# <a name="ltvariablesgt"></a><span data-ttu-id="12a42-102">&lt;variables&gt;</span><span class="sxs-lookup"><span data-stu-id="12a42-102">&lt;variables&gt;</span></span>
<span data-ttu-id="12a42-103">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="12a42-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="12a42-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="12a42-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="12a42-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="12a42-105">\<system.serviceModel></span></span>  
<span data-ttu-id="12a42-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="12a42-106">\<tracking></span></span>  
<span data-ttu-id="12a42-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="12a42-107">\<trackingProfile></span></span>  
<span data-ttu-id="12a42-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="12a42-108">\<workflow></span></span>  
<span data-ttu-id="12a42-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="12a42-109">\<activityStateQueries></span></span>  
<span data-ttu-id="12a42-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="12a42-110">\<activityStateQuery></span></span>  
<span data-ttu-id="12a42-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="12a42-111">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a42-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12a42-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12a42-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="12a42-113">Attributes and Elements</span></span>  
 <span data-ttu-id="12a42-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="12a42-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12a42-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="12a42-115">Attributes</span></span>  
 <span data-ttu-id="12a42-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="12a42-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12a42-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12a42-117">Child Elements</span></span>  
  
|<span data-ttu-id="12a42-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="12a42-118">Element</span></span>|<span data-ttu-id="12a42-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12a42-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12a42-120">\<variable></span><span class="sxs-lookup"><span data-stu-id="12a42-120">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="12a42-121">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="12a42-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12a42-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="12a42-122">Parent Elements</span></span>  
  
|<span data-ttu-id="12a42-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="12a42-123">Element</span></span>|<span data-ttu-id="12a42-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12a42-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12a42-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="12a42-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="12a42-126">Rappresenta un elemento di configurazione usato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="12a42-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="12a42-127">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="12a42-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12a42-128">Note</span><span class="sxs-lookup"><span data-stu-id="12a42-128">Remarks</span></span>  
 <span data-ttu-id="12a42-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12a42-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="12a42-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12a42-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="12a42-131">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12a42-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="12a42-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="12a42-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="12a42-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="12a42-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12a42-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12a42-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="12a42-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="12a42-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="12a42-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="12a42-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
