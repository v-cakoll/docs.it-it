---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 2ad1cba170a7ade06de4678651a8dfcb608d5c46
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607206"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="7ea24-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="7ea24-101">\<channelPoolSettings></span></span>
<span data-ttu-id="7ea24-102">Specifica le impostazioni del pool di canali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7ea24-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="7ea24-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7ea24-103">\<system.serviceModel></span></span>  
<span data-ttu-id="7ea24-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="7ea24-104">\<bindings></span></span>  
<span data-ttu-id="7ea24-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7ea24-105">\<customBinding></span></span>  
<span data-ttu-id="7ea24-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ea24-106">\<binding></span></span>  
<span data-ttu-id="7ea24-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="7ea24-107">\<oneWay></span></span>  
<span data-ttu-id="7ea24-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="7ea24-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ea24-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ea24-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ea24-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7ea24-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ea24-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7ea24-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ea24-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7ea24-112">Attributes</span></span>  
  
|<span data-ttu-id="7ea24-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7ea24-113">Attribute</span></span>|<span data-ttu-id="7ea24-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ea24-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="7ea24-115">Oggetto <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività dei canali nel pool prima della disconnessione.</span><span class="sxs-lookup"><span data-stu-id="7ea24-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="7ea24-116">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="7ea24-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="7ea24-117">Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo trascorso il quale un canale, dopo essere stato restituito al pool, viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="7ea24-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="7ea24-118">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="7ea24-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="7ea24-119">Numero intero positivo che specifica il numero massimo di canali che possono essere memorizzati nel pool per ogni endpoint remoto.</span><span class="sxs-lookup"><span data-stu-id="7ea24-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="7ea24-120">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="7ea24-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ea24-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7ea24-121">Child Elements</span></span>  
 <span data-ttu-id="7ea24-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7ea24-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ea24-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7ea24-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7ea24-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ea24-124">Element</span></span>|<span data-ttu-id="7ea24-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ea24-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ea24-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="7ea24-126">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="7ea24-127">Attiva il routing dei pacchetti per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7ea24-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ea24-128">Note</span><span class="sxs-lookup"><span data-stu-id="7ea24-128">Remarks</span></span>  
 <span data-ttu-id="7ea24-129">Le quote sono usate come meccanismo di criterio per impedire un consumo eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ea24-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="7ea24-130">Impediscono attacchi di tipo Denial of Service (DoS), dannosi o non intenzionali.</span><span class="sxs-lookup"><span data-stu-id="7ea24-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="7ea24-131">Usare questo elemento durante l'impostazione delle quote dei canali in un canale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7ea24-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="7ea24-132">`ChannelPoolSettings` specifica tre quote:</span><span class="sxs-lookup"><span data-stu-id="7ea24-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="7ea24-133">La quota `idleTimeout` viene usata per ridurre il rischio di attacchi di tipo Denial of Service (DoS) nel server basati sul blocco di risorse per periodi di tempo prolungati.</span><span class="sxs-lookup"><span data-stu-id="7ea24-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="7ea24-134">Nel client, l'impostazione del valore corretto può aumentare l'affidabilità della connessione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="7ea24-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="7ea24-135">Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ea24-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="7ea24-136">È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7ea24-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="7ea24-137">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7ea24-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="7ea24-138">La quota `leaseTimeout` viene usata per l'integrazione con i servizi di bilanciamento del carico e per migliorare l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="7ea24-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="7ea24-139">Il valore predefinito è basato su un'allocazione conservativa di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ea24-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="7ea24-140">È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7ea24-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="7ea24-141">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7ea24-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="7ea24-142">La quota `maxOutboundChannelsPerEndpoint` imposta limiti della cache sia nel server che nel client ed è usata per migliorare l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="7ea24-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="7ea24-143">Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse idonee per ambienti di sviluppo e scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7ea24-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="7ea24-144">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7ea24-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea24-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ea24-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7ea24-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="7ea24-146">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="7ea24-147">Associazioni</span><span class="sxs-lookup"><span data-stu-id="7ea24-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7ea24-148">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="7ea24-148">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7ea24-149">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="7ea24-149">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7ea24-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7ea24-150">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
