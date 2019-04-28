---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: c85f3c57739c48566c97c8b1debfb7f2c3912bdf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613521"
---
# <a name="variable"></a><span data-ttu-id="f8093-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="f8093-101">\<variable></span></span>
<span data-ttu-id="f8093-102">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="f8093-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="f8093-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f8093-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f8093-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f8093-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f8093-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="f8093-105">\<tracking></span></span>  
<span data-ttu-id="f8093-106">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="f8093-106">\<profiles></span></span>  
<span data-ttu-id="f8093-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f8093-107">\<trackingProfile></span></span>  
<span data-ttu-id="f8093-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="f8093-108">\<workflow></span></span>  
<span data-ttu-id="f8093-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="f8093-109">\<activityStateQueries></span></span>  
<span data-ttu-id="f8093-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="f8093-110">\<activityStateQuery></span></span>  
<span data-ttu-id="f8093-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="f8093-111">\<variables></span></span>  
<span data-ttu-id="f8093-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="f8093-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8093-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8093-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8093-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8093-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f8093-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8093-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8093-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8093-116">Attributes</span></span>  
  
|<span data-ttu-id="f8093-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8093-117">Attribute</span></span>|<span data-ttu-id="f8093-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8093-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8093-119">name</span><span class="sxs-lookup"><span data-stu-id="f8093-119">name</span></span>|<span data-ttu-id="f8093-120">Stringa che specifica il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="f8093-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8093-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8093-121">Child Elements</span></span>  
 <span data-ttu-id="f8093-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f8093-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8093-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8093-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f8093-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8093-124">Element</span></span>|<span data-ttu-id="f8093-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8093-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8093-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="f8093-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="f8093-127">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f8093-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8093-128">Note</span><span class="sxs-lookup"><span data-stu-id="f8093-128">Remarks</span></span>  
 <span data-ttu-id="f8093-129">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f8093-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="f8093-130">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8093-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="f8093-131">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f8093-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="f8093-132">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f8093-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="f8093-133">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="f8093-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8093-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8093-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f8093-135">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f8093-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f8093-136">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f8093-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
