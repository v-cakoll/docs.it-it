---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3ff568c267331538fb9be0e6cb40eebbca44d882
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375662"
---
# <a name="variables"></a><span data-ttu-id="06803-101">\<variables></span><span class="sxs-lookup"><span data-stu-id="06803-101">\<variables></span></span>
<span data-ttu-id="06803-102">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="06803-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="06803-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="06803-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="06803-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="06803-104">\<system.serviceModel></span></span>  
<span data-ttu-id="06803-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="06803-105">\<tracking></span></span>  
<span data-ttu-id="06803-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="06803-106">\<trackingProfile></span></span>  
<span data-ttu-id="06803-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="06803-107">\<workflow></span></span>  
<span data-ttu-id="06803-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="06803-108">\<activityStateQueries></span></span>  
<span data-ttu-id="06803-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="06803-109">\<activityStateQuery></span></span>  
<span data-ttu-id="06803-110">\<variables></span><span class="sxs-lookup"><span data-stu-id="06803-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06803-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06803-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06803-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="06803-112">Attributes and Elements</span></span>  
 <span data-ttu-id="06803-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="06803-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06803-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="06803-114">Attributes</span></span>  
 <span data-ttu-id="06803-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="06803-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="06803-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="06803-116">Child Elements</span></span>  
  
|<span data-ttu-id="06803-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="06803-117">Element</span></span>|<span data-ttu-id="06803-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06803-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06803-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="06803-119">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="06803-120">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="06803-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06803-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="06803-121">Parent Elements</span></span>  
  
|<span data-ttu-id="06803-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="06803-122">Element</span></span>|<span data-ttu-id="06803-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06803-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06803-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="06803-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="06803-125">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="06803-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="06803-126">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="06803-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06803-127">Note</span><span class="sxs-lookup"><span data-stu-id="06803-127">Remarks</span></span>  
 <span data-ttu-id="06803-128">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="06803-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="06803-129">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="06803-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="06803-130">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="06803-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="06803-131">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="06803-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="06803-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="06803-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="06803-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06803-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="06803-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="06803-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="06803-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="06803-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
