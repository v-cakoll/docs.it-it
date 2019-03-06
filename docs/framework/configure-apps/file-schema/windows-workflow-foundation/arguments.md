---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 3e9fc4f286e7aba6406ce61910da9e614e13ffca
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368090"
---
# <a name="arguments"></a><span data-ttu-id="0c7bd-101">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="0c7bd-101">\<arguments></span></span>
<span data-ttu-id="0c7bd-102">Rappresenta una raccolta di argomenti associati a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="0c7bd-103">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0c7bd-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0c7bd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0c7bd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0c7bd-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="0c7bd-105">\<tracking></span></span>  
<span data-ttu-id="0c7bd-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0c7bd-106">\<trackingProfile></span></span>  
<span data-ttu-id="0c7bd-107">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="0c7bd-107">\<workflow></span></span>  
<span data-ttu-id="0c7bd-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="0c7bd-108">\<activityStateQueries></span></span>  
<span data-ttu-id="0c7bd-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="0c7bd-109">\<activityStateQuery></span></span>  
<span data-ttu-id="0c7bd-110">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="0c7bd-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c7bd-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c7bd-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c7bd-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0c7bd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0c7bd-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c7bd-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="0c7bd-114">Attributes</span></span>  
 <span data-ttu-id="0c7bd-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c7bd-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0c7bd-116">Child Elements</span></span>  
  
|<span data-ttu-id="0c7bd-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c7bd-117">Element</span></span>|<span data-ttu-id="0c7bd-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c7bd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c7bd-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="0c7bd-119">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="0c7bd-120">Argomento associato a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c7bd-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0c7bd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0c7bd-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c7bd-122">Element</span></span>|<span data-ttu-id="0c7bd-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c7bd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c7bd-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="0c7bd-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="0c7bd-125">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0c7bd-126">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c7bd-127">Note</span><span class="sxs-lookup"><span data-stu-id="0c7bd-127">Remarks</span></span>  
 <span data-ttu-id="0c7bd-128">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0c7bd-129">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0c7bd-130">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="0c7bd-131">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0c7bd-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0c7bd-132">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="0c7bd-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c7bd-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c7bd-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0c7bd-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0c7bd-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0c7bd-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0c7bd-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
