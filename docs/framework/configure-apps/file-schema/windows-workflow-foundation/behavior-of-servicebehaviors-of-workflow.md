---
title: '&lt;comportamento&gt; di &lt;serviceBehaviors&gt; del flusso di lavoro'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 81dfde9a4b75caeea263cc0809f450cbc0c9a5e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a><span data-ttu-id="776af-102">&lt;comportamento&gt; di &lt;serviceBehaviors&gt; del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="776af-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt; of workflow</span></span>
<span data-ttu-id="776af-103">Il **comportamento** elemento contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="776af-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="776af-104">Ogni comportamento è indicizzato dai relativi **nome**.</span><span class="sxs-lookup"><span data-stu-id="776af-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="776af-105">Servizi è possono collegare a ciascun comportamento tramite questo nome utilizzando il **behaviorConfiguration**attributo del [ \<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="776af-105">Services can link to each behavior through this name using the **behaviorConfiguration**attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="776af-106">In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="776af-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="776af-107">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="776af-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="776af-108">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="776af-108">\<behaviors></span></span>  
<span data-ttu-id="776af-109">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="776af-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="776af-110">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="776af-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776af-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="776af-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String" 
                                  honstLockRenewalPeriod="TimeSpan" 
                                  instanceCompletionAction="DeleteNothing/DeleteAll" 
                                  instanceEncodingAction="None/GZip" 
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan" 
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="776af-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="776af-112">Attributes and Elements</span></span>  
 <span data-ttu-id="776af-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="776af-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="776af-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="776af-114">Attributes</span></span>  
  
|<span data-ttu-id="776af-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="776af-115">Attribute</span></span>|<span data-ttu-id="776af-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="776af-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="776af-117">name</span><span class="sxs-lookup"><span data-stu-id="776af-117">name</span></span>|<span data-ttu-id="776af-118">Stringa univoca che contiene il nome di configurazione del comportamento.</span><span class="sxs-lookup"><span data-stu-id="776af-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="776af-119">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="776af-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="776af-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="776af-120">Child Elements</span></span>  
  
|<span data-ttu-id="776af-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="776af-121">Element</span></span>|<span data-ttu-id="776af-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="776af-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="776af-123">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="776af-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="776af-124">Comportamento del servizio che consente a un servizio di usare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="776af-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="776af-125">\<routing ></span><span class="sxs-lookup"><span data-stu-id="776af-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="776af-126">Un comportamento del servizio che consente a un servizio di utilizzare rilevamento ETW usando un <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="776af-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="776af-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="776af-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="776af-128">Un comportamento del servizio che consente la personalizzazione della condivisione a livelli, le impostazioni della cache della channel factory e le impostazioni della cache del canale per i flussi di lavoro che inviano messaggi agli endpoint del servizio tramite l'attività di messaggistica di trasmissione della cache.</span><span class="sxs-lookup"><span data-stu-id="776af-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="776af-129">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="776af-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="776af-130">Un comportamento del servizio che consente di configurare il <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> funzionalità, che supporta mantenimento delle informazioni di stato per le istanze del servizio del flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="776af-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="776af-131">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="776af-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="776af-132">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="776af-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="776af-133">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="776af-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="776af-134">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="776af-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="776af-135">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="776af-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="776af-136">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="776af-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="776af-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="776af-137">Parent Elements</span></span>  
  
|<span data-ttu-id="776af-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="776af-138">Element</span></span>|<span data-ttu-id="776af-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="776af-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="776af-140">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="776af-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="776af-141">Raccolta di elementi di comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="776af-141">A collection of service behavior elements.</span></span>|
