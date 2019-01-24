---
title: '&lt;variable&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 185e7e7196f6679ec3d1fae8a2a256b934022ca9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647881"
---
# <a name="ltvariablegt"></a><span data-ttu-id="61de9-102">&lt;variable&gt;</span><span class="sxs-lookup"><span data-stu-id="61de9-102">&lt;variable&gt;</span></span>
<span data-ttu-id="61de9-103">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="61de9-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="61de9-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="61de9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="61de9-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="61de9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="61de9-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="61de9-106">\<tracking></span></span>  
<span data-ttu-id="61de9-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="61de9-107">\<profiles></span></span>  
<span data-ttu-id="61de9-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="61de9-108">\<trackingProfile></span></span>  
<span data-ttu-id="61de9-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="61de9-109">\<workflow></span></span>  
<span data-ttu-id="61de9-110">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="61de9-110">\<activityStateQueries></span></span>  
<span data-ttu-id="61de9-111">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="61de9-111">\<activityStateQuery></span></span>  
<span data-ttu-id="61de9-112">\<variables></span><span class="sxs-lookup"><span data-stu-id="61de9-112">\<variables></span></span>  
<span data-ttu-id="61de9-113">\<variable></span><span class="sxs-lookup"><span data-stu-id="61de9-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61de9-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61de9-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61de9-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="61de9-115">Attributes and Elements</span></span>  
 <span data-ttu-id="61de9-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="61de9-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61de9-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="61de9-117">Attributes</span></span>  
  
|<span data-ttu-id="61de9-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="61de9-118">Attribute</span></span>|<span data-ttu-id="61de9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61de9-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61de9-120">name</span><span class="sxs-lookup"><span data-stu-id="61de9-120">name</span></span>|<span data-ttu-id="61de9-121">Stringa che specifica il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="61de9-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61de9-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="61de9-122">Child Elements</span></span>  
 <span data-ttu-id="61de9-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="61de9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61de9-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="61de9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="61de9-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="61de9-125">Element</span></span>|<span data-ttu-id="61de9-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61de9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61de9-127">\<variable></span><span class="sxs-lookup"><span data-stu-id="61de9-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="61de9-128">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="61de9-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61de9-129">Note</span><span class="sxs-lookup"><span data-stu-id="61de9-129">Remarks</span></span>  
 <span data-ttu-id="61de9-130">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="61de9-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="61de9-131">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="61de9-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="61de9-132">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="61de9-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="61de9-133">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="61de9-133">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="61de9-134">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="61de9-134">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="61de9-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61de9-135">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="61de9-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="61de9-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="61de9-137">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="61de9-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
