---
title: <tracking>di WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: e8f74d635299a965b754536234e6be28e4e7a104
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399427"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="dc877-102">\<tracking>di WCF</span><span class="sxs-lookup"><span data-stu-id="dc877-102">\<tracking> of WCF</span></span>
<span data-ttu-id="dc877-103">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc877-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="dc877-104">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [rilevamento e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) e [configurazione del rilevamento per un flusso di lavoro](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="dc877-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="dc877-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc877-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc877-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dc877-106">Attributes and Elements</span></span>  
 <span data-ttu-id="dc877-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dc877-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc877-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="dc877-108">Attributes</span></span>  
 <span data-ttu-id="dc877-109">No.</span><span class="sxs-lookup"><span data-stu-id="dc877-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc877-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dc877-110">Child Elements</span></span>  
  
|<span data-ttu-id="dc877-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc877-111">Element</span></span>|<span data-ttu-id="dc877-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc877-112">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="dc877-113">Raccolta di elementi di configurazione che definiscono partecipanti che sottoscrivono record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dc877-113">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="dc877-114">I partecipanti del rilevamento contengono la logica per elaborare il payload dai record di rilevamento, ad esempio possono scegliere di scrivere in un file.</span><span class="sxs-lookup"><span data-stu-id="dc877-114">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="dc877-115">Profilo di rilevamento che consente di filtrare i record di rilevamento generati da un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc877-115">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc877-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dc877-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dc877-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc877-117">Element</span></span>|<span data-ttu-id="dc877-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc877-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc877-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc877-119">system.ServiceModel</span></span>|<span data-ttu-id="dc877-120">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc877-120">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc877-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="dc877-121">Remarks</span></span>  
 <span data-ttu-id="dc877-122">Il rilevamento consente di esaminare l'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc877-122">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="dc877-123">L'infrastruttura di rilevamento del flusso di lavoro instrumenta un flusso di lavoro per generare record che riflettono gli eventi principali che si verificano durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc877-123">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="dc877-124">Vengono ad esempio generati record di rilevamento quando viene avviata o completata un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc877-124">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="dc877-125">Il rilevamento consente inoltre di estrarre dati aziendali rilevanti associati alle variabili del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc877-125">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="dc877-126">Se, ad esempio, il flusso di lavoro rappresenta un sistema di elaborazione degli ordini, è possibile estrarre l'ID dell'ordine insieme al record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="dc877-126">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="dc877-127">In generale, l'abilitazione del rilevamento WF semplifica la diagnostica o l'analisi aziendale dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc877-127">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc877-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="dc877-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="dc877-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dc877-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
