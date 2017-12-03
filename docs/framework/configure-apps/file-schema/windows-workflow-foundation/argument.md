---
title: '&lt;argomento&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3625d3bf6aa415c34b9c05bebdec390bcb51f69
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltargumentgt"></a><span data-ttu-id="0d5a3-102">&lt;argomento&gt;</span><span class="sxs-lookup"><span data-stu-id="0d5a3-102">&lt;argument&gt;</span></span>
<span data-ttu-id="0d5a3-103">Elemento di configurazione che rappresenta un argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="0d5a3-104">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0d5a3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0d5a3-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0d5a3-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-106">\<tracking></span></span>  
<span data-ttu-id="0d5a3-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-107">\<trackingProfile></span></span>  
<span data-ttu-id="0d5a3-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-108">\<workflow></span></span>  
<span data-ttu-id="0d5a3-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-109">\<activityStateQueries></span></span>  
<span data-ttu-id="0d5a3-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-110">\<activityStateQuery></span></span>  
<span data-ttu-id="0d5a3-111">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-111">\<arguments></span></span>  
<span data-ttu-id="0d5a3-112">\<argomento ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d5a3-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d5a3-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d5a3-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0d5a3-114">Attributes and Elements</span></span>  
 <span data-ttu-id="0d5a3-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d5a3-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="0d5a3-116">Attributes</span></span>  
  
|<span data-ttu-id="0d5a3-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="0d5a3-117">Attribute</span></span>|<span data-ttu-id="0d5a3-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d5a3-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d5a3-119">name</span><span class="sxs-lookup"><span data-stu-id="0d5a3-119">name</span></span>|<span data-ttu-id="0d5a3-120">Stringa che specifica il nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d5a3-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0d5a3-121">Child Elements</span></span>  
 <span data-ttu-id="0d5a3-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d5a3-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0d5a3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0d5a3-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d5a3-124">Element</span></span>|<span data-ttu-id="0d5a3-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d5a3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d5a3-126">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="0d5a3-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="0d5a3-127">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d5a3-128">Note</span><span class="sxs-lookup"><span data-stu-id="0d5a3-128">Remarks</span></span>  
 <span data-ttu-id="0d5a3-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0d5a3-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0d5a3-131">È possibile utilizzare il [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi per estrarre qualsiasi variabile o argomento da qualsiasi attività di un flusso di lavoro. Nell'esempio seguente viene illustrata una query sullo stato di attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="0d5a3-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0d5a3-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e pertanto vengono sottoscritti all'interno di un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="0d5a3-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0d5a3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d5a3-133">See Also</span></span>  
 <span data-ttu-id="0d5a3-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0d5a3-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="0d5a3-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0d5a3-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="0d5a3-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d5a3-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0d5a3-137">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0d5a3-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
