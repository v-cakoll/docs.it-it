---
title: <activityStateQuery>di WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 233bd3a2fa161222977902cc1053f964e8171173
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850481"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="f9404-102">\<> activityStateQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="f9404-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="f9404-103">Rappresenta una query usata per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f9404-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="f9404-104">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f9404-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="f9404-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="f9404-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="f9404-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="f9404-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="f9404-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f9404-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="f9404-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9404-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f9404-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f9404-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f9404-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f9404-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="f9404-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="f9404-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="f9404-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f9404-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="f9404-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f9404-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="f9404-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f9404-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)</span></span>\
<span data-ttu-id="f9404-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityStateQuery**</span><span class="sxs-lookup"><span data-stu-id="f9404-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9404-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9404-116">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9404-117">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f9404-117">Attributes and elements</span></span>  

<span data-ttu-id="f9404-118">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9404-118">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9404-119">Attributi</span><span class="sxs-lookup"><span data-stu-id="f9404-119">Attributes</span></span>  
  
|<span data-ttu-id="f9404-120">Attributo</span><span class="sxs-lookup"><span data-stu-id="f9404-120">Attribute</span></span>|<span data-ttu-id="f9404-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9404-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9404-122">activityName</span><span class="sxs-lookup"><span data-stu-id="f9404-122">activityName</span></span>|<span data-ttu-id="f9404-123">Stringa che specifica il nome dell'attività per la quale filtrare istanze di <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="f9404-123">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9404-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f9404-124">Child elements</span></span>  
  
|<span data-ttu-id="f9404-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9404-125">Element</span></span>|<span data-ttu-id="f9404-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f9404-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9404-127">\<Argomenti ></span><span class="sxs-lookup"><span data-stu-id="f9404-127">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="f9404-128">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="f9404-128">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="f9404-129">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="f9404-129">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="f9404-130">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f9404-130">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="f9404-131">\<Stati ></span><span class="sxs-lookup"><span data-stu-id="f9404-131">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="f9404-132">Raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="f9404-132">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9404-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f9404-133">Parent elements</span></span>  
  
|<span data-ttu-id="f9404-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9404-134">Element</span></span>|<span data-ttu-id="f9404-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9404-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9404-136">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="f9404-136">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="f9404-137">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="f9404-137">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f9404-138">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="f9404-138">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9404-139">Note</span><span class="sxs-lookup"><span data-stu-id="f9404-139">Remarks</span></span>

<span data-ttu-id="f9404-140">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f9404-140">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="f9404-141">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f9404-141">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="f9404-142">Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](../windows-workflow-foundation/arguments.md), [ \<gli Stati >](../windows-workflow-foundation/states.md) e [ \<gli Stati >](../windows-workflow-foundation/states.md) elementi. Nell'esempio seguente viene illustrata una query sullo stato dell'attività che estrae variabili e argomenti `Closed` quando viene generato il record di rilevamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f9404-142">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="f9404-143">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](../windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="f9404-143">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="f9404-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9404-144">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="f9404-145">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f9404-145">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f9404-146">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f9404-146">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
