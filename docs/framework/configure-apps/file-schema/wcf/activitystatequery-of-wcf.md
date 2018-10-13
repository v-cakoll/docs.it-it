---
title: '&lt;activityStateQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: a0dae6b90659bd3f53386459513abf92f25b005b
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308315"
---
# <a name="ltactivitystatequerygt-of-wcf"></a><span data-ttu-id="12086-102">&lt;activityStateQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="12086-102">&lt;activityStateQuery&gt; of WCF</span></span>

<span data-ttu-id="12086-103">Rappresenta una query usata per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12086-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="12086-104">Ad esempio, è possibile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12086-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="12086-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="12086-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="12086-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="12086-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="12086-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="12086-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="12086-108">\<System. ServiceModel > \<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="12086-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="12086-109">\<i profili > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="12086-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="12086-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="12086-110">\<workflow></span></span>  
<span data-ttu-id="12086-111">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="12086-111">\<activityStateQueries></span></span>  
<span data-ttu-id="12086-112">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="12086-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12086-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12086-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12086-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="12086-114">Attributes and elements</span></span>  

<span data-ttu-id="12086-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="12086-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12086-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="12086-116">Attributes</span></span>  
  
|<span data-ttu-id="12086-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="12086-117">Attribute</span></span>|<span data-ttu-id="12086-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12086-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12086-119">activityName</span><span class="sxs-lookup"><span data-stu-id="12086-119">activityName</span></span>|<span data-ttu-id="12086-120">Stringa che specifica il nome dell'attività per la quale filtrare istanze di <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="12086-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12086-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12086-121">Child elements</span></span>  
  
|<span data-ttu-id="12086-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="12086-122">Element</span></span>|<span data-ttu-id="12086-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12086-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12086-124">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="12086-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="12086-125">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="12086-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="12086-126">\<stati ></span><span class="sxs-lookup"><span data-stu-id="12086-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="12086-127">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="12086-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="12086-128">\<stati ></span><span class="sxs-lookup"><span data-stu-id="12086-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="12086-129">Raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="12086-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12086-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="12086-130">Parent elements</span></span>  
  
|<span data-ttu-id="12086-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="12086-131">Element</span></span>|<span data-ttu-id="12086-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12086-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12086-133">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="12086-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="12086-134">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="12086-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="12086-135">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="12086-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12086-136">Note</span><span class="sxs-lookup"><span data-stu-id="12086-136">Remarks</span></span>

<span data-ttu-id="12086-137">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12086-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="12086-138">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12086-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="12086-139">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro. L'esempio seguente mostra una query sullo stato dell'attività che estrae variabili e argomenti quando l'attività `Closed` viene generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="12086-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="12086-140">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="12086-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12086-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12086-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="12086-142">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="12086-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="12086-143">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="12086-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
