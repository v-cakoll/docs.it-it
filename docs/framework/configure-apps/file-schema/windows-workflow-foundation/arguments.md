---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 2b0d982997ab590ce7f0fc4c482b1ddfa6bc758f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152802"
---
# <a name="arguments"></a><span data-ttu-id="e8e39-101">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="e8e39-101">\<arguments></span></span>
<span data-ttu-id="e8e39-102">Rappresenta una raccolta di argomenti associati a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e8e39-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="e8e39-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e8e39-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e8e39-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e8e39-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e8e39-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e8e39-105">\<tracking></span></span>  
<span data-ttu-id="e8e39-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e8e39-106">\<trackingProfile></span></span>  
<span data-ttu-id="e8e39-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="e8e39-107">\<workflow></span></span>  
<span data-ttu-id="e8e39-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="e8e39-108">\<activityStateQueries></span></span>  
<span data-ttu-id="e8e39-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="e8e39-109">\<activityStateQuery></span></span>  
<span data-ttu-id="e8e39-110">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="e8e39-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e39-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8e39-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8e39-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8e39-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e8e39-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8e39-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8e39-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8e39-114">Attributes</span></span>  
 <span data-ttu-id="e8e39-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e8e39-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8e39-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8e39-116">Child Elements</span></span>  
  
|<span data-ttu-id="e8e39-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8e39-117">Element</span></span>|<span data-ttu-id="e8e39-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8e39-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8e39-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="e8e39-119">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="e8e39-120">Argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e8e39-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8e39-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8e39-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e8e39-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8e39-122">Element</span></span>|<span data-ttu-id="e8e39-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8e39-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8e39-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="e8e39-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="e8e39-125">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e8e39-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e8e39-126">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="e8e39-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8e39-127">Note</span><span class="sxs-lookup"><span data-stu-id="e8e39-127">Remarks</span></span>  
 <span data-ttu-id="e8e39-128">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8e39-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="e8e39-129">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e8e39-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="e8e39-130">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8e39-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="e8e39-131">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e8e39-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="e8e39-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="e8e39-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e8e39-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8e39-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e8e39-134">Rilevamento e traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e8e39-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e8e39-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e8e39-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
