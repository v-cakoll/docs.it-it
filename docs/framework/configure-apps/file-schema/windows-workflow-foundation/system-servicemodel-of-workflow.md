---
title: <> system.serviceModel del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151949"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="50e97-102">\<system.serviceModel> del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="50e97-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="50e97-103">Contenuto della sezione di configurazione sono contenuti tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="50e97-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="50e97-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="50e97-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="50e97-105">&nbsp;&nbsp;**\<Sistema.>ServiceModelServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="50e97-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e97-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50e97-106">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore
          connectionStringName="String"
          hostLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionAction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>
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
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50e97-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="50e97-107">Attributes and Elements</span></span>  
 <span data-ttu-id="50e97-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="50e97-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50e97-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="50e97-109">Attributes</span></span>  
 <span data-ttu-id="50e97-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="50e97-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50e97-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="50e97-111">Child Elements</span></span>  
  
|<span data-ttu-id="50e97-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="50e97-112">Element</span></span>|<span data-ttu-id="50e97-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50e97-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50e97-114">\<comportamenti></span><span class="sxs-lookup"><span data-stu-id="50e97-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="50e97-115">Questa sezione definisce la raccolta **serviceBehaviors.**</span><span class="sxs-lookup"><span data-stu-id="50e97-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="50e97-116">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="50e97-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="50e97-117">Ogni elemento behavior è identificato dal relativo attributo **name** univoco.</span><span class="sxs-lookup"><span data-stu-id="50e97-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="50e97-118">\<>di tracciamento</span><span class="sxs-lookup"><span data-stu-id="50e97-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="50e97-119">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="50e97-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="50e97-120">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [Rilevamento e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) e Configurazione del [rilevamento per un flusso di lavoro](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="50e97-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50e97-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="50e97-121">Parent Elements</span></span>  
  
|<span data-ttu-id="50e97-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="50e97-122">Element</span></span>|<span data-ttu-id="50e97-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50e97-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50e97-124">\<>di configurazione</span><span class="sxs-lookup"><span data-stu-id="50e97-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="50e97-125">Elemento radice di tutti gli elementi di configurazione contenuti in un file di configurazione .NET.</span><span class="sxs-lookup"><span data-stu-id="50e97-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
