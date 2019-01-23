---
title: '&lt;argument&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: 3744781f844d4a1728ba1e9846b2b8c56c0ad8fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554603"
---
# <a name="ltargumentgt"></a><span data-ttu-id="34981-102">&lt;argument&gt;</span><span class="sxs-lookup"><span data-stu-id="34981-102">&lt;argument&gt;</span></span>
<span data-ttu-id="34981-103">Elemento di configurazione che rappresenta un argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="34981-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="34981-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="34981-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="34981-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="34981-105">\<system.serviceModel></span></span>  
<span data-ttu-id="34981-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="34981-106">\<tracking></span></span>  
<span data-ttu-id="34981-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="34981-107">\<trackingProfile></span></span>  
<span data-ttu-id="34981-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="34981-108">\<workflow></span></span>  
<span data-ttu-id="34981-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="34981-109">\<activityStateQueries></span></span>  
<span data-ttu-id="34981-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="34981-110">\<activityStateQuery></span></span>  
<span data-ttu-id="34981-111">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="34981-111">\<arguments></span></span>  
<span data-ttu-id="34981-112">\<argument></span><span class="sxs-lookup"><span data-stu-id="34981-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34981-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34981-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34981-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="34981-114">Attributes and Elements</span></span>  
 <span data-ttu-id="34981-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="34981-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34981-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="34981-116">Attributes</span></span>  
  
|<span data-ttu-id="34981-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="34981-117">Attribute</span></span>|<span data-ttu-id="34981-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34981-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34981-119">name</span><span class="sxs-lookup"><span data-stu-id="34981-119">name</span></span>|<span data-ttu-id="34981-120">Stringa che specifica il nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="34981-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34981-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="34981-121">Child Elements</span></span>  
 <span data-ttu-id="34981-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="34981-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34981-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="34981-123">Parent Elements</span></span>  
  
|<span data-ttu-id="34981-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="34981-124">Element</span></span>|<span data-ttu-id="34981-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34981-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34981-126">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="34981-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="34981-127">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="34981-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34981-128">Note</span><span class="sxs-lookup"><span data-stu-id="34981-128">Remarks</span></span>  
 <span data-ttu-id="34981-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="34981-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="34981-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34981-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="34981-131">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="34981-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="34981-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="34981-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="34981-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="34981-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34981-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34981-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="34981-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="34981-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="34981-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="34981-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
