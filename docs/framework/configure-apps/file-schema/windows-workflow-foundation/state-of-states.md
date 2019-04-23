---
title: <state> di <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: ff75895949c50cd369e4297ea77dc21106994067
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073936"
---
# <a name="state-of-states"></a><span data-ttu-id="fbc3a-102">\<stato > di \<stati ></span><span class="sxs-lookup"><span data-stu-id="fbc3a-102">\<state> of \<states></span></span>
<span data-ttu-id="fbc3a-103">Elemento di configurazione contenente lo stato dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="fbc3a-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fbc3a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="fbc3a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fbc3a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="fbc3a-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="fbc3a-106">\<tracking></span></span>  
<span data-ttu-id="fbc3a-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="fbc3a-107">\<trackingProfile></span></span>  
<span data-ttu-id="fbc3a-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="fbc3a-108">\<workflow></span></span>  
<span data-ttu-id="fbc3a-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="fbc3a-109">\<activityStateQueries></span></span>  
<span data-ttu-id="fbc3a-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="fbc3a-110">\<activityStateQuery></span></span>  
<span data-ttu-id="fbc3a-111">\<states></span><span class="sxs-lookup"><span data-stu-id="fbc3a-111">\<states></span></span>  
<span data-ttu-id="fbc3a-112">\<state></span><span class="sxs-lookup"><span data-stu-id="fbc3a-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbc3a-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbc3a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbc3a-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fbc3a-114">Attributes and Elements</span></span>  
 <span data-ttu-id="fbc3a-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbc3a-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="fbc3a-116">Attributes</span></span>  
  
|<span data-ttu-id="fbc3a-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="fbc3a-117">Attribute</span></span>|<span data-ttu-id="fbc3a-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbc3a-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbc3a-119">name</span><span class="sxs-lookup"><span data-stu-id="fbc3a-119">name</span></span>|<span data-ttu-id="fbc3a-120">Stringa che specifica lo stato dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbc3a-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fbc3a-121">Child Elements</span></span>  
 <span data-ttu-id="fbc3a-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbc3a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fbc3a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fbc3a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbc3a-124">Element</span></span>|<span data-ttu-id="fbc3a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbc3a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbc3a-126">\<states></span><span class="sxs-lookup"><span data-stu-id="fbc3a-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="fbc3a-127">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbc3a-128">Note</span><span class="sxs-lookup"><span data-stu-id="fbc3a-128">Remarks</span></span>  
 <span data-ttu-id="fbc3a-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="fbc3a-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="fbc3a-131">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="fbc3a-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="fbc3a-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="fbc3a-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fbc3a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbc3a-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fbc3a-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fbc3a-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fbc3a-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="fbc3a-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
