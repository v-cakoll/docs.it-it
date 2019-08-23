---
title: <behavior>del <serviceBehaviors> flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 91883c42aa7bc0aa8fa0c63c3c45184ba69225d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946071"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="63832-102">\<comportamento > di \<serviceBehaviors > del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="63832-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="63832-103">L'elemento **Behavior** contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="63832-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="63832-104">Ogni comportamento è indicizzato in base al **nome**.</span><span class="sxs-lookup"><span data-stu-id="63832-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="63832-105">I servizi possono collegarsi a ogni comportamento tramite questo nome usando l'attributo **behaviorConfiguration** dell'elemento [ \<> dell'endpoint](../wcf/endpoint-element.md) .</span><span class="sxs-lookup"><span data-stu-id="63832-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="63832-106">In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="63832-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="63832-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="63832-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="63832-108">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="63832-108">\<behaviors></span></span>  
<span data-ttu-id="63832-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="63832-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="63832-110">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="63832-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63832-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63832-111">Syntax</span></span>  
  
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
                                  hostLockRenewalPeriod="TimeSpan" 
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63832-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="63832-112">Attributes and Elements</span></span>  
 <span data-ttu-id="63832-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="63832-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63832-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="63832-114">Attributes</span></span>  
  
|<span data-ttu-id="63832-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="63832-115">Attribute</span></span>|<span data-ttu-id="63832-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63832-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63832-117">name</span><span class="sxs-lookup"><span data-stu-id="63832-117">name</span></span>|<span data-ttu-id="63832-118">Stringa univoca che contiene il nome di configurazione del comportamento.</span><span class="sxs-lookup"><span data-stu-id="63832-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="63832-119">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="63832-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63832-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="63832-120">Child Elements</span></span>  
  
|<span data-ttu-id="63832-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="63832-121">Element</span></span>|<span data-ttu-id="63832-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63832-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63832-123">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="63832-123">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="63832-124">Comportamento del servizio che consente a un servizio di utilizzare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="63832-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="63832-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="63832-125">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="63832-126">Comportamento del servizio che consente a un servizio di utilizzare il rilevamento ETW utilizzando <xref:System.Activities.Tracking.EtwTrackingParticipant>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="63832-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="63832-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="63832-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="63832-128">Comportamento del servizio che consente la personalizzazione dei livelli di condivisione della cache, le impostazioni della cache della channel factory e le impostazioni della cache del canale per i flussi di lavoro che inviano messaggi agli endpoint di servizio utilizzando le attività Invia messaggistica.</span><span class="sxs-lookup"><span data-stu-id="63832-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="63832-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="63832-129">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="63832-130">Comportamento del servizio che consente di configurare la funzionalità <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> , che supporta la permanenza delle informazioni sullo stato per le istanze del servizio flusso di lavoro in un database SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="63832-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="63832-131">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="63832-131">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="63832-132">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="63832-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="63832-133">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="63832-133">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="63832-134">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="63832-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="63832-135">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="63832-135">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="63832-136">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="63832-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="63832-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="63832-137">Parent Elements</span></span>  
  
|<span data-ttu-id="63832-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="63832-138">Element</span></span>|<span data-ttu-id="63832-139">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="63832-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63832-140">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="63832-140">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="63832-141">Raccolta di elementi di comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="63832-141">A collection of service behavior elements.</span></span>|
