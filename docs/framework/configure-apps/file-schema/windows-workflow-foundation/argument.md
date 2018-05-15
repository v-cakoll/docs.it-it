---
title: '&lt;Argomento&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: bfcb98085e0b2292d46acfd0a57096219afff606
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltargumentgt"></a><span data-ttu-id="47ee0-102">&lt;Argomento&gt;</span><span class="sxs-lookup"><span data-stu-id="47ee0-102">&lt;argument&gt;</span></span>
<span data-ttu-id="47ee0-103">Elemento di configurazione che rappresenta un argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="47ee0-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="47ee0-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="47ee0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="47ee0-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="47ee0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="47ee0-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="47ee0-106">\<tracking></span></span>  
<span data-ttu-id="47ee0-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="47ee0-107">\<trackingProfile></span></span>  
<span data-ttu-id="47ee0-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="47ee0-108">\<workflow></span></span>  
<span data-ttu-id="47ee0-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="47ee0-109">\<activityStateQueries></span></span>  
<span data-ttu-id="47ee0-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="47ee0-110">\<activityStateQuery></span></span>  
<span data-ttu-id="47ee0-111">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="47ee0-111">\<arguments></span></span>  
<span data-ttu-id="47ee0-112">\<argomento ></span><span class="sxs-lookup"><span data-stu-id="47ee0-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ee0-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47ee0-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47ee0-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="47ee0-114">Attributes and Elements</span></span>  
 <span data-ttu-id="47ee0-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="47ee0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47ee0-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="47ee0-116">Attributes</span></span>  
  
|<span data-ttu-id="47ee0-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="47ee0-117">Attribute</span></span>|<span data-ttu-id="47ee0-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47ee0-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47ee0-119">name</span><span class="sxs-lookup"><span data-stu-id="47ee0-119">name</span></span>|<span data-ttu-id="47ee0-120">Stringa che specifica il nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="47ee0-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47ee0-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="47ee0-121">Child Elements</span></span>  
 <span data-ttu-id="47ee0-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="47ee0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47ee0-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="47ee0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="47ee0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="47ee0-124">Element</span></span>|<span data-ttu-id="47ee0-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47ee0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47ee0-126">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="47ee0-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="47ee0-127">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="47ee0-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47ee0-128">Note</span><span class="sxs-lookup"><span data-stu-id="47ee0-128">Remarks</span></span>  
 <span data-ttu-id="47ee0-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="47ee0-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="47ee0-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="47ee0-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="47ee0-131">È possibile utilizzare il [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi per estrarre qualsiasi variabile o argomento da qualsiasi attività di un flusso di lavoro. Nell'esempio seguente viene illustrata una query sullo stato di attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="47ee0-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="47ee0-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e pertanto vengono sottoscritti all'interno di un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="47ee0-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="47ee0-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47ee0-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="47ee0-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="47ee0-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="47ee0-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="47ee0-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
