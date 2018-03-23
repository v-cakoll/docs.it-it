---
title: '&lt;trackingProfile&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6acc4e5b71d94b712ae27e540df073828285b0aa
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2018
---
# <a name="lttrackingprofilegt"></a><span data-ttu-id="ac620-102">&lt;trackingProfile&gt;</span><span class="sxs-lookup"><span data-stu-id="ac620-102">&lt;trackingProfile&gt;</span></span>
<span data-ttu-id="ac620-103">Rappresenta una sezione di configurazione per la creazione di una sottoscrizione di record di rilevamento in un partecipante del rilevamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac620-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="ac620-104">Un profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ac620-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="ac620-105">Le query definite all'interno della sezione del profilo di rilevamento definiscono i tipi di eventi restituiti dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac620-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="ac620-106">Per altre informazioni, vedere rilevamento del flusso di lavoro e la relativa configurazione, vedere [flusso di lavoro rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ac620-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ac620-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ac620-107">\<system.serviceModel></span></span>  
<span data-ttu-id="ac620-108">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="ac620-108">\<tracking></span></span>  
<span data-ttu-id="ac620-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ac620-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac620-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac620-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac620-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ac620-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ac620-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ac620-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac620-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ac620-113">Attributes</span></span>  
  
|<span data-ttu-id="ac620-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ac620-114">Attribute</span></span>|<span data-ttu-id="ac620-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac620-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac620-116">name</span><span class="sxs-lookup"><span data-stu-id="ac620-116">name</span></span>|<span data-ttu-id="ac620-117">Stringa che specifica il nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ac620-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac620-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ac620-118">Child Elements</span></span>  
  
|<span data-ttu-id="ac620-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac620-119">Element</span></span>|<span data-ttu-id="ac620-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac620-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac620-121">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="ac620-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="ac620-122">Un elemento di configurazione che contiene tutte le query in un flusso di lavoro specifico identificato dal **un collegamento ipertestuale "http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac620-122">A configuration element that contains all queries for a specific workflow identified by the **a HYPERLINK "http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx"ctivityDefinitionId** property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac620-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ac620-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ac620-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac620-124">Element</span></span>|<span data-ttu-id="ac620-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac620-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac620-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ac620-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="ac620-127">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac620-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac620-128">Note</span><span class="sxs-lookup"><span data-stu-id="ac620-128">Remarks</span></span>  
 <span data-ttu-id="ac620-129">I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ac620-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="ac620-130">A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac620-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="ac620-131">Viceversa, è possibile creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ac620-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="ac620-132">I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici.</span><span class="sxs-lookup"><span data-stu-id="ac620-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="ac620-133">Esistono un numero limitato di tipi di query che consentono di sottoscrivere classi differenti di un collegamento ipertestuale "http://msdn.microsoft.com/library/system.activities.tracking.trackingrecord(VS.100).aspx" oggetti TrackingRecord.</span><span class="sxs-lookup"><span data-stu-id="ac620-133">There are a handful of query types that allow you subscribe to different classes of  HYPERLINK "http://msdn.microsoft.com/library/system.activities.tracking.trackingrecord(VS.100).aspx" TrackingRecord objects.</span></span> <span data-ttu-id="ac620-134">Per un elenco completo delle query, vedere [ \<partecipanti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) e [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="ac620-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="ac620-135">Nell'esempio seguente viene illustrato un profilo di rilevamento in un file di configurazione che consente a un partecipante di rilevamento sottoscrivere il `Started` e `Completed` gli eventi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac620-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac620-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac620-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="ac620-137">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ac620-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ac620-138">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ac620-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
