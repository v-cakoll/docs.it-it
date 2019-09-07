---
title: <tracking>di WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: e8f74d635299a965b754536234e6be28e4e7a104
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399427"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="715cb-102">\<rilevamento > di WCF</span><span class="sxs-lookup"><span data-stu-id="715cb-102">\<tracking> of WCF</span></span>
<span data-ttu-id="715cb-103">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="715cb-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="715cb-104">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [rilevamento e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) e [configurazione del rilevamento per un flusso di lavoro](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="715cb-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="715cb-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="715cb-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="715cb-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="715cb-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="715cb-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<rilevamento >**</span><span class="sxs-lookup"><span data-stu-id="715cb-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="715cb-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="715cb-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
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
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="715cb-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="715cb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="715cb-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="715cb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="715cb-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="715cb-111">Attributes</span></span>  
 <span data-ttu-id="715cb-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="715cb-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="715cb-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="715cb-113">Child Elements</span></span>  
  
|<span data-ttu-id="715cb-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="715cb-114">Element</span></span>|<span data-ttu-id="715cb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="715cb-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="715cb-116">\<participants></span><span class="sxs-lookup"><span data-stu-id="715cb-116">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="715cb-117">Raccolta di elementi di configurazione che definiscono i partecipanti che sottoscrivono i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="715cb-117">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="715cb-118">I partecipanti del rilevamento contengono la logica per elaborare il payload dai record di rilevamento, ad esempio possono scegliere di scrivere in un file.</span><span class="sxs-lookup"><span data-stu-id="715cb-118">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="715cb-119">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="715cb-119">\<trackingProfile></span></span>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="715cb-120">Profilo di rilevamento che consente di filtrare i record di rilevamento generati da un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="715cb-120">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="715cb-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="715cb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="715cb-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="715cb-122">Element</span></span>|<span data-ttu-id="715cb-123">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="715cb-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="715cb-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="715cb-124">system.ServiceModel</span></span>|<span data-ttu-id="715cb-125">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="715cb-125">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="715cb-126">Note</span><span class="sxs-lookup"><span data-stu-id="715cb-126">Remarks</span></span>  
 <span data-ttu-id="715cb-127">Il rilevamento consente di esaminare l'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="715cb-127">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="715cb-128">L'infrastruttura di rilevamento del flusso di lavoro instrumenta un flusso di lavoro per generare record che riflettono gli eventi principali che si verificano durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="715cb-128">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="715cb-129">Vengono ad esempio generati record di rilevamento quando viene avviata o completata un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="715cb-129">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="715cb-130">Il rilevamento consente inoltre di estrarre dati aziendali rilevanti associati alle variabili del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="715cb-130">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="715cb-131">Se, ad esempio, il flusso di lavoro rappresenta un sistema di elaborazione degli ordini, è possibile estrarre l'ID dell'ordine insieme al record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="715cb-131">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="715cb-132">In generale, l'abilitazione del rilevamento WF semplifica la diagnostica o l'analisi aziendale dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="715cb-132">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="715cb-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="715cb-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="715cb-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="715cb-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
