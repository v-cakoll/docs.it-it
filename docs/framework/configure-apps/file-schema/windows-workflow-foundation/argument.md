---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: a920d60d703fe262bee96d75c420c526d54f88ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210646"
---
# <a name="argument"></a><span data-ttu-id="be780-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="be780-101">\<argument></span></span>
<span data-ttu-id="be780-102">Elemento di configurazione che rappresenta un argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="be780-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="be780-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="be780-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="be780-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="be780-104">\<system.serviceModel></span></span>  
<span data-ttu-id="be780-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="be780-105">\<tracking></span></span>  
<span data-ttu-id="be780-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="be780-106">\<trackingProfile></span></span>  
<span data-ttu-id="be780-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="be780-107">\<workflow></span></span>  
<span data-ttu-id="be780-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="be780-108">\<activityStateQueries></span></span>  
<span data-ttu-id="be780-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="be780-109">\<activityStateQuery></span></span>  
<span data-ttu-id="be780-110">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="be780-110">\<arguments></span></span>  
<span data-ttu-id="be780-111">\<argument></span><span class="sxs-lookup"><span data-stu-id="be780-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be780-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be780-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be780-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="be780-113">Attributes and Elements</span></span>  
 <span data-ttu-id="be780-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="be780-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be780-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="be780-115">Attributes</span></span>  
  
|<span data-ttu-id="be780-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="be780-116">Attribute</span></span>|<span data-ttu-id="be780-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be780-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be780-118">name</span><span class="sxs-lookup"><span data-stu-id="be780-118">name</span></span>|<span data-ttu-id="be780-119">Stringa che specifica il nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="be780-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be780-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="be780-120">Child Elements</span></span>  
 <span data-ttu-id="be780-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="be780-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be780-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="be780-122">Parent Elements</span></span>  
  
|<span data-ttu-id="be780-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="be780-123">Element</span></span>|<span data-ttu-id="be780-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be780-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be780-125">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="be780-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="be780-126">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="be780-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be780-127">Note</span><span class="sxs-lookup"><span data-stu-id="be780-127">Remarks</span></span>  
 <span data-ttu-id="be780-128">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="be780-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="be780-129">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="be780-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="be780-130">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="be780-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="be780-131">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="be780-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="be780-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="be780-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be780-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be780-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="be780-134">Rilevamento e traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="be780-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="be780-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="be780-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
