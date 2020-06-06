---
title: <System. serviceModel> del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151949"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="77319-102">\<system.serviceModel>del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="77319-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="77319-103">Contenuto della sezione di configurazione sono contenuti tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="77319-103">This configuration section contains all the workflow configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.ServiceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="77319-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77319-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77319-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77319-105">Attributes and Elements</span></span>  
 <span data-ttu-id="77319-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77319-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77319-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="77319-107">Attributes</span></span>  
 <span data-ttu-id="77319-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="77319-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="77319-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77319-109">Child Elements</span></span>  
  
|<span data-ttu-id="77319-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="77319-110">Element</span></span>|<span data-ttu-id="77319-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77319-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors-of-workflow.md)|<span data-ttu-id="77319-112">Questa sezione definisce la raccolta **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="77319-112">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="77319-113">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="77319-113">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="77319-114">Ogni elemento di comportamento è identificato dall'attributo del **nome** univoco.</span><span class="sxs-lookup"><span data-stu-id="77319-114">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[\<tracking>](tracking.md)|<span data-ttu-id="77319-115">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="77319-115">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="77319-116">Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [rilevamento e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) e [configurazione del rilevamento per un flusso di lavoro](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="77319-116">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77319-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77319-117">Parent Elements</span></span>  
  
|<span data-ttu-id="77319-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="77319-118">Element</span></span>|<span data-ttu-id="77319-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77319-119">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="77319-120">Elemento radice di tutti gli elementi di configurazione contenuti in un file di configurazione .NET.</span><span class="sxs-lookup"><span data-stu-id="77319-120">The root element for all configuration elements in a .NET configuration file.</span></span>|
