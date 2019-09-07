---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: b18761f96b17523a50af4f5f2697841b15de0e03
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398803"
---
# <a name="channelsettings"></a><span data-ttu-id="80f7f-101">\<> channelSettings</span><span class="sxs-lookup"><span data-stu-id="80f7f-101">\<channelSettings></span></span>
<span data-ttu-id="80f7f-102">Specifica le impostazioni della cache del canale.</span><span class="sxs-lookup"><span data-stu-id="80f7f-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="80f7f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80f7f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80f7f-104">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="80f7f-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="80f7f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="80f7f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="80f7f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="80f7f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="80f7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="80f7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="80f7f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> sendMessageChannelCache**](sendmessagechannelcache.md)</span><span class="sxs-lookup"><span data-stu-id="80f7f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)</span></span>\
<span data-ttu-id="80f7f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> channelSettings**</span><span class="sxs-lookup"><span data-stu-id="80f7f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f7f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80f7f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80f7f-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="80f7f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="80f7f-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="80f7f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80f7f-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="80f7f-113">Attributes</span></span>  
  
|<span data-ttu-id="80f7f-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="80f7f-114">Attribute</span></span>|<span data-ttu-id="80f7f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80f7f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80f7f-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="80f7f-116">idleTimeout</span></span>|<span data-ttu-id="80f7f-117">Valore TimeSpan che specifica l'intervallo di tempo massimo durante il quale l'oggetto può rimanere inattivo nella cache prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="80f7f-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="80f7f-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="80f7f-118">leaseTimeout</span></span>|<span data-ttu-id="80f7f-119">Valore TimeSpan che specifica l'intervallo di tempo dopo il quale un oggetto viene rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="80f7f-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="80f7f-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="80f7f-120">maxItemsInCache</span></span>|<span data-ttu-id="80f7f-121">Integer che specifica il numero massimo di oggetti che possono essere memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="80f7f-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80f7f-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="80f7f-122">Child Elements</span></span>  
 <span data-ttu-id="80f7f-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="80f7f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80f7f-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="80f7f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="80f7f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="80f7f-125">Element</span></span>|<span data-ttu-id="80f7f-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80f7f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80f7f-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="80f7f-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="80f7f-128">Comportamento del servizio che consente la personalizzazione dei livelli di condivisione della cache, le impostazioni della cache della channel factory e le impostazioni della cache del canale per i flussi di lavoro che inviano messaggi agli endpoint di servizio utilizzando le attività Invia messaggistica.</span><span class="sxs-lookup"><span data-stu-id="80f7f-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80f7f-129">Note</span><span class="sxs-lookup"><span data-stu-id="80f7f-129">Remarks</span></span>  
 <span data-ttu-id="80f7f-130">Questo comportamento del servizio è designato per flussi di lavoro che inviano messaggi a endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="80f7f-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="80f7f-131">Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="80f7f-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="80f7f-132">Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache usata da attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa attraverso tutte le istanze del flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host).</span><span class="sxs-lookup"><span data-stu-id="80f7f-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="80f7f-133">Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza).</span><span class="sxs-lookup"><span data-stu-id="80f7f-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="80f7f-134">Per impostazione predefinita, la memorizzazione nella cache è disabilitata per qualsiasi attività di invio nel flusso di lavoro che dispone di endpoint definiti nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="80f7f-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="80f7f-135">Per ulteriori informazioni su come modificare i livelli di condivisione della cache predefiniti e le impostazioni della cache per la channel factory e la cache del canale, vedere [modifica dei livelli di condivisione della cache per le attività di invio](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="80f7f-135">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80f7f-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="80f7f-136">Example</span></span>  
 <span data-ttu-id="80f7f-137">In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="80f7f-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="80f7f-138">A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio.</span><span class="sxs-lookup"><span data-stu-id="80f7f-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="80f7f-139">Nell'esempio seguente viene illustrato il contenuto di un file di configurazione che `MyChannelCacheBehavior` contiene il comportamento del servizio con le impostazioni della cache factory e della cache del canale personalizzate.</span><span class="sxs-lookup"><span data-stu-id="80f7f-139">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="80f7f-140">Questo comportamento del servizio viene aggiunto al servizio tramite l' `behaviorConfiguration` attributo.</span><span class="sxs-lookup"><span data-stu-id="80f7f-140">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80f7f-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80f7f-141">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="80f7f-142">Modifica dei livelli di condivisione della cache per le attività Send</span><span class="sxs-lookup"><span data-stu-id="80f7f-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
