---
title: <factorySettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: 8ee874d4f92ee398dc9752d3c1d1f22610b17097
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422909"
---
# <a name="factorysettings"></a><span data-ttu-id="9b51a-101">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="9b51a-101">\<factorySettings></span></span>
<span data-ttu-id="9b51a-102">Specifica le impostazioni della cache della channel factory.</span><span class="sxs-lookup"><span data-stu-id="9b51a-102">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="9b51a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9b51a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9b51a-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9b51a-104">\<behaviors></span></span>  
<span data-ttu-id="9b51a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9b51a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9b51a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9b51a-106">\<behavior></span></span>  
<span data-ttu-id="9b51a-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="9b51a-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="9b51a-108">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="9b51a-108">\<factorySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b51a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b51a-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b51a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9b51a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9b51a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9b51a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b51a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9b51a-112">Attributes</span></span>  
  
|<span data-ttu-id="9b51a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9b51a-113">Attribute</span></span>|<span data-ttu-id="9b51a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b51a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b51a-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="9b51a-115">idleTimeout</span></span>|<span data-ttu-id="9b51a-116">Valore TimeSpan che specifica l'intervallo di tempo massimo durante il quale l'oggetto può rimanere inattivo nella cache prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="9b51a-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="9b51a-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="9b51a-117">leaseTimeout</span></span>|<span data-ttu-id="9b51a-118">Valore TimeSpan che specifica l'intervallo di tempo dopo il quale un oggetto viene rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="9b51a-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="9b51a-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="9b51a-119">maxItemsInCache</span></span>|<span data-ttu-id="9b51a-120">Integer che specifica il numero massimo di oggetti che possono essere memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="9b51a-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b51a-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9b51a-121">Child Elements</span></span>  
 <span data-ttu-id="9b51a-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9b51a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b51a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9b51a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9b51a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b51a-124">Element</span></span>|<span data-ttu-id="9b51a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b51a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b51a-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="9b51a-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="9b51a-127">Comportamento del servizio che consente la personalizzazione della cache di condivisione a livelli, le impostazioni della cache della channel factory e le impostazioni della cache del canale per flussi di lavoro che inviano messaggi agli endpoint di servizio usando attività della messaggistica di invio.</span><span class="sxs-lookup"><span data-stu-id="9b51a-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b51a-128">Note</span><span class="sxs-lookup"><span data-stu-id="9b51a-128">Remarks</span></span>  
 <span data-ttu-id="9b51a-129">Questo comportamento del servizio è designato per flussi di lavoro che inviano messaggi a endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="9b51a-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="9b51a-130">Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="9b51a-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="9b51a-131">Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache usata da attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa attraverso tutte le istanze del flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host).</span><span class="sxs-lookup"><span data-stu-id="9b51a-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="9b51a-132">Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza).</span><span class="sxs-lookup"><span data-stu-id="9b51a-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="9b51a-133">Per impostazione predefinita, la memorizzazione nella cache è disabilitata per qualsiasi attività di invio nel flusso di lavoro che dispone di endpoint definiti nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="9b51a-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="9b51a-134">Per altre informazioni su come modificare la cache predefinita condivisione a livelli e le impostazioni della cache per la channel factory e cache del canale, vedere [modifica dei livelli di condivisione della Cache per le attività Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="9b51a-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b51a-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b51a-135">Example</span></span>  
 <span data-ttu-id="9b51a-136">In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b51a-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="9b51a-137">A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio.</span><span class="sxs-lookup"><span data-stu-id="9b51a-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="9b51a-138">L'esempio seguente mostra il contenuto del file di configurazione che contiene il `MyChannelCacheBehavior` comportamento del servizio con le impostazioni della cache factory personalizzata della cache e del canale.</span><span class="sxs-lookup"><span data-stu-id="9b51a-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="9b51a-139">Questo comportamento viene aggiunto al servizio tramite il `behaviorConfiguration` attributo.</span><span class="sxs-lookup"><span data-stu-id="9b51a-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b51a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b51a-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="9b51a-141">Modifica dei livelli di condivisione della cache per le attività Send</span><span class="sxs-lookup"><span data-stu-id="9b51a-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
