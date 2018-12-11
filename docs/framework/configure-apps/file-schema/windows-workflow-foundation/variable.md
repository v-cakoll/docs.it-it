---
title: '&lt;Variabile&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: c65b377d85783f29ca2a8223e97eb10b073cee0a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155236"
---
# <a name="ltvariablegt"></a><span data-ttu-id="8c060-102">&lt;Variabile&gt;</span><span class="sxs-lookup"><span data-stu-id="8c060-102">&lt;variable&gt;</span></span>
<span data-ttu-id="8c060-103">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="8c060-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="8c060-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8c060-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8c060-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c060-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8c060-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="8c060-106">\<tracking></span></span>  
<span data-ttu-id="8c060-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="8c060-107">\<profiles></span></span>  
<span data-ttu-id="8c060-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8c060-108">\<trackingProfile></span></span>  
<span data-ttu-id="8c060-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8c060-109">\<workflow></span></span>  
<span data-ttu-id="8c060-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="8c060-110">\<activityStateQueries></span></span>  
<span data-ttu-id="8c060-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="8c060-111">\<activityStateQuery></span></span>  
<span data-ttu-id="8c060-112">\<le variabili ></span><span class="sxs-lookup"><span data-stu-id="8c060-112">\<variables></span></span>  
<span data-ttu-id="8c060-113">\<variabile ></span><span class="sxs-lookup"><span data-stu-id="8c060-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c060-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c060-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c060-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c060-115">Attributes and Elements</span></span>  
 <span data-ttu-id="8c060-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c060-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c060-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c060-117">Attributes</span></span>  
  
|<span data-ttu-id="8c060-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="8c060-118">Attribute</span></span>|<span data-ttu-id="8c060-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c060-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c060-120">name</span><span class="sxs-lookup"><span data-stu-id="8c060-120">name</span></span>|<span data-ttu-id="8c060-121">Stringa che specifica il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="8c060-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c060-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c060-122">Child Elements</span></span>  
 <span data-ttu-id="8c060-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8c060-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c060-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c060-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8c060-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c060-125">Element</span></span>|<span data-ttu-id="8c060-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c060-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c060-127">\<variabile ></span><span class="sxs-lookup"><span data-stu-id="8c060-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="8c060-128">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8c060-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c060-129">Note</span><span class="sxs-lookup"><span data-stu-id="8c060-129">Remarks</span></span>  
 <span data-ttu-id="8c060-130">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c060-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8c060-131">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8c060-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8c060-132">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c060-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="8c060-133">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8c060-133">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8c060-134">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="8c060-134">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c060-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c060-135">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="8c060-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8c060-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8c060-137">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8c060-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
