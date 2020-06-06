---
title: <behavior>del <serviceBehaviors> flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 071cff8e9f6ec3fa0546a07d19160869d8b43f60
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152320"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="4ed10-102">\<behavior>del \<serviceBehaviors> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4ed10-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="4ed10-103">L'elemento **Behavior** contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="4ed10-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="4ed10-104">Ogni comportamento è indicizzato in base al **nome**.</span><span class="sxs-lookup"><span data-stu-id="4ed10-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="4ed10-105">I servizi possono collegarsi a ogni comportamento tramite questo nome usando l'attributo **behaviorConfiguration** dell' [\<endpoint>](../wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="4ed10-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="4ed10-106">In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4ed10-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="4ed10-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ed10-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ed10-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ed10-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4ed10-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ed10-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ed10-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ed10-110">Attributes</span></span>  
  
|<span data-ttu-id="4ed10-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4ed10-111">Attribute</span></span>|<span data-ttu-id="4ed10-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ed10-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ed10-113">name</span><span class="sxs-lookup"><span data-stu-id="4ed10-113">name</span></span>|<span data-ttu-id="4ed10-114">Stringa univoca che contiene il nome di configurazione del comportamento.</span><span class="sxs-lookup"><span data-stu-id="4ed10-114">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="4ed10-115">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4ed10-115">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ed10-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ed10-116">Child Elements</span></span>  
  
|<span data-ttu-id="4ed10-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ed10-117">Element</span></span>|<span data-ttu-id="4ed10-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ed10-118">Description</span></span>|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|<span data-ttu-id="4ed10-119">Comportamento del servizio che consente a un servizio di utilizzare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="4ed10-119">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="4ed10-120">Comportamento del servizio che consente a un servizio di utilizzare il rilevamento ETW mediante un oggetto <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="4ed10-120">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="4ed10-121">Comportamento del servizio che consente la personalizzazione dei livelli di condivisione della cache, delle impostazioni della cache della channel factory e delle impostazioni della cache del canale per flussi di lavoro che inviano messaggi a endpoint di servizio utilizzando attività della messaggistica di invio.</span><span class="sxs-lookup"><span data-stu-id="4ed10-121">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|<span data-ttu-id="4ed10-122">Comportamento del servizio che consente di configurare la funzionalità <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> che supporta la persistenza delle informazioni sullo stato per le istanze del servizio flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4ed10-122">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[\<workflowIdle>](workflowidle.md)|<span data-ttu-id="4ed10-123">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="4ed10-123">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|<span data-ttu-id="4ed10-124">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="4ed10-124">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|<span data-ttu-id="4ed10-125">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4ed10-125">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ed10-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ed10-126">Parent Elements</span></span>  
  
|<span data-ttu-id="4ed10-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ed10-127">Element</span></span>|<span data-ttu-id="4ed10-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ed10-128">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="4ed10-129">Raccolta di elementi di comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="4ed10-129">A collection of service behavior elements.</span></span>|
