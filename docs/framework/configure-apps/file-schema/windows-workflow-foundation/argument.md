---
title: '&lt;argomento&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: 8172093f36bd09ea33b1a447ee61dc36afb1b358
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154229"
---
# <a name="ltargumentgt"></a><span data-ttu-id="a8bf6-102">&lt;argomento&gt;</span><span class="sxs-lookup"><span data-stu-id="a8bf6-102">&lt;argument&gt;</span></span>
<span data-ttu-id="a8bf6-103">Elemento di configurazione che rappresenta un argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="a8bf6-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a8bf6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a8bf6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a8bf6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a8bf6-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="a8bf6-106">\<tracking></span></span>  
<span data-ttu-id="a8bf6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a8bf6-107">\<trackingProfile></span></span>  
<span data-ttu-id="a8bf6-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="a8bf6-108">\<workflow></span></span>  
<span data-ttu-id="a8bf6-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a8bf6-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a8bf6-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a8bf6-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a8bf6-111">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="a8bf6-111">\<arguments></span></span>  
<span data-ttu-id="a8bf6-112">\<argomento ></span><span class="sxs-lookup"><span data-stu-id="a8bf6-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bf6-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8bf6-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8bf6-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a8bf6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a8bf6-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8bf6-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="a8bf6-116">Attributes</span></span>  
  
|<span data-ttu-id="a8bf6-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="a8bf6-117">Attribute</span></span>|<span data-ttu-id="a8bf6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8bf6-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8bf6-119">name</span><span class="sxs-lookup"><span data-stu-id="a8bf6-119">name</span></span>|<span data-ttu-id="a8bf6-120">Stringa che specifica il nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8bf6-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a8bf6-121">Child Elements</span></span>  
 <span data-ttu-id="a8bf6-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8bf6-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a8bf6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a8bf6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8bf6-124">Element</span></span>|<span data-ttu-id="a8bf6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8bf6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8bf6-126">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="a8bf6-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="a8bf6-127">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8bf6-128">Note</span><span class="sxs-lookup"><span data-stu-id="a8bf6-128">Remarks</span></span>  
 <span data-ttu-id="a8bf6-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a8bf6-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a8bf6-131">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="a8bf6-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a8bf6-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a8bf6-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a8bf6-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8bf6-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8bf6-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="a8bf6-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a8bf6-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a8bf6-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="a8bf6-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
