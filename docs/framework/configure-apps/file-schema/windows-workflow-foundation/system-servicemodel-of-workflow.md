---
title: < System. ServiceModel > del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 005a274df9e9ab99227a3748b7a25c9d465d020f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768862"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="20975-102">\<System. ServiceModel > del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="20975-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="20975-103">Contenuto della sezione di configurazione sono contenuti tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="20975-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20975-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20975-104">Syntax</span></span>  
  
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
          honstLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionaction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20975-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="20975-105">Attributes and Elements</span></span>  
 <span data-ttu-id="20975-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="20975-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20975-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="20975-107">Attributes</span></span>  
 <span data-ttu-id="20975-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="20975-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20975-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="20975-109">Child Elements</span></span>  
  
|<span data-ttu-id="20975-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="20975-110">Element</span></span>|<span data-ttu-id="20975-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20975-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20975-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="20975-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="20975-113">Questa sezione definisce i **serviceBehaviors** raccolta.</span><span class="sxs-lookup"><span data-stu-id="20975-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="20975-114">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="20975-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="20975-115">Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.</span><span class="sxs-lookup"><span data-stu-id="20975-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="20975-116">\<tracking></span><span class="sxs-lookup"><span data-stu-id="20975-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="20975-117">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="20975-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="20975-118">Per altre informazioni sul rilevamento del flusso di lavoro e la relativa configurazione, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [configurazione del rilevamento per un flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="20975-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20975-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="20975-119">Parent Elements</span></span>  
  
|<span data-ttu-id="20975-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="20975-120">Element</span></span>|<span data-ttu-id="20975-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20975-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20975-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="20975-122">\<configuration></span></span>|<span data-ttu-id="20975-123">Elemento radice di tutti gli elementi di configurazione contenuti in un file di configurazione .NET.</span><span class="sxs-lookup"><span data-stu-id="20975-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
