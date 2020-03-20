---
title: <behavior>di <serviceBehaviors> flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 071cff8e9f6ec3fa0546a07d19160869d8b43f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152320"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="9d6ab-102">\<comportamento> \<di serviceBehaviors> del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9d6ab-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="9d6ab-103">L'elemento **behavior** contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="9d6ab-104">Ogni comportamento viene indicizzato in base al **nome**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="9d6ab-105">I servizi possono collegarsi a ogni comportamento tramite questo nome usando l'attributo **behaviorConfiguration** [ \<dell'elemento endpoint>.](../wcf/endpoint-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d6ab-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="9d6ab-106">In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="9d6ab-107">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d6ab-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9d6ab-108">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9d6ab-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9d6ab-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamenti>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9d6ab-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="9d6ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9d6ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="9d6ab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di comportamento**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d6ab-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d6ab-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d6ab-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9d6ab-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9d6ab-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d6ab-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="9d6ab-115">Attributes</span></span>  
  
|<span data-ttu-id="9d6ab-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="9d6ab-116">Attribute</span></span>|<span data-ttu-id="9d6ab-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d6ab-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d6ab-118">name</span><span class="sxs-lookup"><span data-stu-id="9d6ab-118">name</span></span>|<span data-ttu-id="9d6ab-119">Stringa univoca che contiene il nome di configurazione del comportamento.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="9d6ab-120">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d6ab-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9d6ab-121">Child Elements</span></span>  
  
|<span data-ttu-id="9d6ab-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d6ab-122">Element</span></span>|<span data-ttu-id="9d6ab-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d6ab-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d6ab-124">\<>bufferReceive</span><span class="sxs-lookup"><span data-stu-id="9d6ab-124">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="9d6ab-125">Comportamento del servizio che consente a un servizio di utilizzare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-125">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="9d6ab-126">\<>di routing</span><span class="sxs-lookup"><span data-stu-id="9d6ab-126">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="9d6ab-127">Comportamento del servizio che consente a un servizio di utilizzare il rilevamento ETW mediante un oggetto <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-127">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="9d6ab-128">\<>sendMessageChannelCache</span><span class="sxs-lookup"><span data-stu-id="9d6ab-128">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="9d6ab-129">Comportamento del servizio che consente la personalizzazione dei livelli di condivisione della cache, delle impostazioni della cache della channel factory e delle impostazioni della cache del canale per flussi di lavoro che inviano messaggi a endpoint di servizio utilizzando attività della messaggistica di invio.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-129">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="9d6ab-130">\<>sqlWorkflowInstanceStore</span><span class="sxs-lookup"><span data-stu-id="9d6ab-130">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="9d6ab-131">Comportamento del servizio che consente di configurare la funzionalità <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> che supporta la persistenza delle informazioni sullo stato per le istanze del servizio flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-131">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="9d6ab-132">\<>workflowIdle</span><span class="sxs-lookup"><span data-stu-id="9d6ab-132">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="9d6ab-133">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-133">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="9d6ab-134">\<workflowIstanzaGestione></span><span class="sxs-lookup"><span data-stu-id="9d6ab-134">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="9d6ab-135">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-135">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="9d6ab-136">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="9d6ab-136">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="9d6ab-137">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-137">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d6ab-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9d6ab-138">Parent Elements</span></span>  
  
|<span data-ttu-id="9d6ab-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d6ab-139">Element</span></span>|<span data-ttu-id="9d6ab-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d6ab-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d6ab-141">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9d6ab-141">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="9d6ab-142">Raccolta di elementi di comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-142">A collection of service behavior elements.</span></span>|
