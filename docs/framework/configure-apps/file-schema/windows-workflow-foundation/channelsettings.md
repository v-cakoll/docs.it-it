---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f6a57e2cc1e7c5e114fd38ee3534ab7c4e629b36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152274"
---
# <a name="channelsettings"></a><span data-ttu-id="d7412-101">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="d7412-101">\<channelSettings></span></span>
<span data-ttu-id="d7412-102">Specifica le impostazioni della cache del canale.</span><span class="sxs-lookup"><span data-stu-id="d7412-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="d7412-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d7412-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d7412-104">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d7412-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="d7412-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamenti>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d7412-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="d7412-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d7412-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="d7412-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di comportamento**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d7412-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="d7412-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>sendMessageChannelCache**](sendmessagechannelcache.md)</span><span class="sxs-lookup"><span data-stu-id="d7412-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)</span></span>\
<span data-ttu-id="d7412-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<canaleImpostazioni di>sistema**</span><span class="sxs-lookup"><span data-stu-id="d7412-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7412-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7412-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7412-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d7412-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d7412-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d7412-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7412-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="d7412-113">Attributes</span></span>  
  
|<span data-ttu-id="d7412-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="d7412-114">Attribute</span></span>|<span data-ttu-id="d7412-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7412-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7412-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="d7412-116">idleTimeout</span></span>|<span data-ttu-id="d7412-117">Valore TimeSpan che specifica l'intervallo di tempo massimo durante il quale l'oggetto può rimanere inattivo nella cache prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="d7412-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="d7412-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="d7412-118">leaseTimeout</span></span>|<span data-ttu-id="d7412-119">Valore TimeSpan che specifica l'intervallo di tempo trascorso il quale l'oggetto viene rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="d7412-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="d7412-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="d7412-120">maxItemsInCache</span></span>|<span data-ttu-id="d7412-121">Integer che specifica il numero massimo di oggetti che possono essere memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="d7412-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7412-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d7412-122">Child Elements</span></span>  
 <span data-ttu-id="d7412-123">No.</span><span class="sxs-lookup"><span data-stu-id="d7412-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7412-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d7412-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d7412-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7412-125">Element</span></span>|<span data-ttu-id="d7412-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7412-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7412-127">\<>sendMessageChannelCache</span><span class="sxs-lookup"><span data-stu-id="d7412-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="d7412-128">Comportamento del servizio che consente la personalizzazione dei livelli di condivisione della cache, delle impostazioni della cache della channel factory e delle impostazioni della cache del canale per flussi di lavoro che inviano messaggi a endpoint di servizio utilizzando attività della messaggistica di invio.</span><span class="sxs-lookup"><span data-stu-id="d7412-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7412-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d7412-129">Remarks</span></span>  
 <span data-ttu-id="d7412-130">Questo comportamento del servizio è designato per flussi di lavoro che inviano messaggi a endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7412-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="d7412-131">Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d7412-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="d7412-132">Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache usata da attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa attraverso tutte le istanze del flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host).</span><span class="sxs-lookup"><span data-stu-id="d7412-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="d7412-133">Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza).</span><span class="sxs-lookup"><span data-stu-id="d7412-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="d7412-134">Per impostazione predefinita, la memorizzazione nella cache è disabilitata per qualsiasi attività di invio nel flusso di lavoro che dispone di endpoint definiti nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7412-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="d7412-135">Per ulteriori informazioni su come modificare i livelli di condivisione della cache e le impostazioni della cache predefiniti per la channel factory e la cache dei canali, vedere Modifica dei livelli di [condivisione della cache per le attività](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)di invio .</span><span class="sxs-lookup"><span data-stu-id="d7412-135">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7412-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7412-136">Example</span></span>  
 <span data-ttu-id="d7412-137">In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7412-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="d7412-138">A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio.</span><span class="sxs-lookup"><span data-stu-id="d7412-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="d7412-139">Nell'esempio seguente viene illustrato il contenuto `MyChannelCacheBehavior` di un file di configurazione che contiene il comportamento del servizio con le impostazioni personalizzate della cache di factory e della cache dei canali.</span><span class="sxs-lookup"><span data-stu-id="d7412-139">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="d7412-140">Questo comportamento del servizio viene `behaviorConfiguration` aggiunto al servizio tramite l'attributo .</span><span class="sxs-lookup"><span data-stu-id="d7412-140">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>  
    <!-- List of other config sections here -->
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7412-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7412-141">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="d7412-142">Modifica dei livelli di condivisione della cache per le attività Send</span><span class="sxs-lookup"><span data-stu-id="d7412-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
