---
title: <behavior> di <serviceBehaviors> del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 09bd54f4a7d56dc1215b1acd36ff131ba4cba12c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268262"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="d6b43-102">\<comportamento > di \<serviceBehaviors > del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d6b43-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="d6b43-103">Il **comportamento** elemento contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="d6b43-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="d6b43-104">Ogni comportamento viene indicizzato dal relativo **nome**.</span><span class="sxs-lookup"><span data-stu-id="d6b43-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="d6b43-105">Servizi possono essere collegati a ciascun comportamento tramite tale nome usando il **behaviorConfiguration** attributo il [ \<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d6b43-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="d6b43-106">In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d6b43-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="d6b43-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6b43-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6b43-108">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d6b43-108">\<behaviors></span></span>  
<span data-ttu-id="d6b43-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d6b43-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="d6b43-110">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d6b43-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b43-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6b43-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6b43-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6b43-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d6b43-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6b43-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6b43-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6b43-114">Attributes</span></span>  
  
|<span data-ttu-id="d6b43-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="d6b43-115">Attribute</span></span>|<span data-ttu-id="d6b43-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6b43-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6b43-117">name</span><span class="sxs-lookup"><span data-stu-id="d6b43-117">name</span></span>|<span data-ttu-id="d6b43-118">Stringa univoca che contiene il nome di configurazione del comportamento.</span><span class="sxs-lookup"><span data-stu-id="d6b43-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="d6b43-119">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d6b43-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6b43-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6b43-120">Child Elements</span></span>  
  
|<span data-ttu-id="d6b43-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6b43-121">Element</span></span>|<span data-ttu-id="d6b43-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6b43-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6b43-123">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="d6b43-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="d6b43-124">Comportamento del servizio che consente a un servizio di usare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="d6b43-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="d6b43-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="d6b43-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="d6b43-126">Comportamento del servizio che consente a un servizio utilizzare rilevamento ETW mediante un <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="d6b43-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="d6b43-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="d6b43-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="d6b43-128">Comportamento del servizio che consente la personalizzazione della cache di condivisione a livelli, le impostazioni della cache della channel factory e le impostazioni della cache del canale per flussi di lavoro che inviano messaggi agli endpoint di servizio usando attività della messaggistica di invio.</span><span class="sxs-lookup"><span data-stu-id="d6b43-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="d6b43-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="d6b43-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="d6b43-130">Comportamento del servizio che consente di configurare il <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> funzionalità che supporta la persistenza delle informazioni di stato per le istanze di servizio del flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d6b43-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="d6b43-131">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="d6b43-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="d6b43-132">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="d6b43-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="d6b43-133">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="d6b43-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="d6b43-134">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="d6b43-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="d6b43-135">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="d6b43-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="d6b43-136">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d6b43-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6b43-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6b43-137">Parent Elements</span></span>  
  
|<span data-ttu-id="d6b43-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6b43-138">Element</span></span>|<span data-ttu-id="d6b43-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6b43-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6b43-140">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d6b43-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="d6b43-141">Raccolta di elementi di comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="d6b43-141">A collection of service behavior elements.</span></span>|
