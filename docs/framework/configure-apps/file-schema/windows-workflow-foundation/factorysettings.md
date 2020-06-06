---
title: <factorySettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: afb129407bc9dff752375f6e9fd69c728a809b37
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152184"
---
# \<factorySettings>
<span data-ttu-id="6c9ed-101">Specifica le impostazioni della cache della channel factory.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-101">Specifies the settings of the channel factory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<factorySettings>**  
  
## <a name="syntax"></a><span data-ttu-id="6c9ed-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c9ed-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c9ed-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6c9ed-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6c9ed-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c9ed-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="6c9ed-105">Attributes</span></span>  
  
|<span data-ttu-id="6c9ed-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="6c9ed-106">Attribute</span></span>|<span data-ttu-id="6c9ed-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c9ed-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c9ed-108">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="6c9ed-108">idleTimeout</span></span>|<span data-ttu-id="6c9ed-109">Valore TimeSpan che specifica l'intervallo di tempo massimo durante il quale l'oggetto può rimanere inattivo nella cache prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-109">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="6c9ed-110">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="6c9ed-110">leaseTimeout</span></span>|<span data-ttu-id="6c9ed-111">Valore TimeSpan che specifica l'intervallo di tempo trascorso il quale l'oggetto viene rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-111">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="6c9ed-112">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="6c9ed-112">maxItemsInCache</span></span>|<span data-ttu-id="6c9ed-113">Integer che specifica il numero massimo di oggetti che possono essere memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-113">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c9ed-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6c9ed-114">Child Elements</span></span>  
 <span data-ttu-id="6c9ed-115">No.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c9ed-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6c9ed-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6c9ed-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c9ed-117">Element</span></span>|<span data-ttu-id="6c9ed-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c9ed-118">Description</span></span>|  
|-------------|-----------------|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="6c9ed-119">Comportamento del servizio che consente la personalizzazione dei livelli di condivisione della cache, delle impostazioni della cache della channel factory e delle impostazioni della cache del canale per flussi di lavoro che inviano messaggi a endpoint di servizio utilizzando attività della messaggistica di invio.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-119">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c9ed-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="6c9ed-120">Remarks</span></span>  
 <span data-ttu-id="6c9ed-121">Questo comportamento del servizio è designato per flussi di lavoro che inviano messaggi a endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-121">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="6c9ed-122">Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-122">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="6c9ed-123">Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache usata da attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa attraverso tutte le istanze del flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host).</span><span class="sxs-lookup"><span data-stu-id="6c9ed-123">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="6c9ed-124">Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza).</span><span class="sxs-lookup"><span data-stu-id="6c9ed-124">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="6c9ed-125">Per impostazione predefinita, la memorizzazione nella cache è disabilitata per qualsiasi attività di invio nel flusso di lavoro che dispone di endpoint definiti nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-125">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="6c9ed-126">Per ulteriori informazioni su come modificare i livelli di condivisione della cache predefiniti e le impostazioni della cache per la channel factory e la cache del canale, vedere [modifica dei livelli di condivisione della cache per le attività di invio](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="6c9ed-126">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c9ed-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c9ed-127">Example</span></span>  
 <span data-ttu-id="6c9ed-128">In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-128">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="6c9ed-129">A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-129">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="6c9ed-130">Nell'esempio seguente viene illustrato il contenuto di un file di configurazione che contiene il `MyChannelCacheBehavior` comportamento del servizio con le impostazioni della cache factory e della cache del canale personalizzate.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-130">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="6c9ed-131">Questo comportamento del servizio viene aggiunto al servizio tramite l' `behaviorConfiguration` attributo.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-131">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c9ed-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6c9ed-132">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="6c9ed-133">Modifica dei livelli di condivisione della cache per le attività Send</span><span class="sxs-lookup"><span data-stu-id="6c9ed-133">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
