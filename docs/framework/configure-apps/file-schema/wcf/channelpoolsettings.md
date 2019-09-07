---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 26537980a6be5c0fe12661d93a6ba5fe862ceb4e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398165"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="4e975-101">\<> channelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="4e975-101">\<channelPoolSettings></span></span>
<span data-ttu-id="4e975-102">Specifica le impostazioni del pool di canali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4e975-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
<span data-ttu-id="4e975-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e975-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e975-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4e975-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4e975-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4e975-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4e975-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4e975-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4e975-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="4e975-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4e975-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> oneWay**](oneway.md)</span><span class="sxs-lookup"><span data-stu-id="4e975-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)</span></span>\
<span data-ttu-id="4e975-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> channelPoolSettings**</span><span class="sxs-lookup"><span data-stu-id="4e975-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e975-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e975-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e975-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4e975-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4e975-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4e975-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e975-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="4e975-113">Attributes</span></span>  
  
|<span data-ttu-id="4e975-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="4e975-114">Attribute</span></span>|<span data-ttu-id="4e975-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4e975-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="4e975-116">Oggetto <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività dei canali nel pool prima della disconnessione.</span><span class="sxs-lookup"><span data-stu-id="4e975-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="4e975-117">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="4e975-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="4e975-118">Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo trascorso il quale un canale, dopo essere stato restituito al pool, viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="4e975-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="4e975-119">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="4e975-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="4e975-120">Numero intero positivo che specifica il numero massimo di canali che possono essere memorizzati nel pool per ogni endpoint remoto.</span><span class="sxs-lookup"><span data-stu-id="4e975-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="4e975-121">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="4e975-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e975-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4e975-122">Child Elements</span></span>  
 <span data-ttu-id="4e975-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4e975-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e975-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4e975-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4e975-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e975-125">Element</span></span>|<span data-ttu-id="4e975-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e975-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e975-127">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="4e975-127">\<oneWay></span></span>](oneway.md)|<span data-ttu-id="4e975-128">Attiva il routing dei pacchetti per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4e975-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e975-129">Note</span><span class="sxs-lookup"><span data-stu-id="4e975-129">Remarks</span></span>  
 <span data-ttu-id="4e975-130">Le quote sono usate come meccanismo di criterio per impedire un consumo eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="4e975-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="4e975-131">Impediscono attacchi di tipo Denial of Service (DoS), dannosi o non intenzionali.</span><span class="sxs-lookup"><span data-stu-id="4e975-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="4e975-132">Usare questo elemento durante l'impostazione delle quote dei canali in un canale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4e975-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="4e975-133">`ChannelPoolSettings` specifica tre quote:</span><span class="sxs-lookup"><span data-stu-id="4e975-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="4e975-134">La quota `idleTimeout` viene usata per ridurre il rischio di attacchi di tipo Denial of Service (DoS) nel server basati sul blocco di risorse per periodi di tempo prolungati.</span><span class="sxs-lookup"><span data-stu-id="4e975-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="4e975-135">Nel client, l'impostazione del valore corretto può aumentare l'affidabilità della connessione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="4e975-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="4e975-136">Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse.</span><span class="sxs-lookup"><span data-stu-id="4e975-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="4e975-137">È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4e975-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="4e975-138">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4e975-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="4e975-139">La quota `leaseTimeout` viene usata per l'integrazione con i servizi di bilanciamento del carico e per migliorare l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="4e975-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="4e975-140">Il valore predefinito è basato su un'allocazione conservativa di risorse.</span><span class="sxs-lookup"><span data-stu-id="4e975-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="4e975-141">È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4e975-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="4e975-142">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4e975-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="4e975-143">La quota `maxOutboundChannelsPerEndpoint` imposta limiti della cache sia nel server che nel client ed è usata per migliorare l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="4e975-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="4e975-144">Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse idonee per ambienti di sviluppo e scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4e975-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="4e975-145">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4e975-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e975-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e975-146">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4e975-147">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="4e975-147">\<oneWay></span></span>](oneway.md)
- [<span data-ttu-id="4e975-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4e975-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4e975-149">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4e975-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4e975-150">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4e975-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4e975-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4e975-151">\<customBinding></span></span>](custombinding.md)
