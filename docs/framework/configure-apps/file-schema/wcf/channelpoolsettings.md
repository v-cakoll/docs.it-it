---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 26537980a6be5c0fe12661d93a6ba5fe862ceb4e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398165"
---
# \<channelPoolSettings>
<span data-ttu-id="11505-101">Specifica le impostazioni del pool di canali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="11505-101">Specifies the channel pool settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="11505-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11505-102">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11505-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="11505-103">Attributes and Elements</span></span>  
 <span data-ttu-id="11505-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="11505-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11505-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="11505-105">Attributes</span></span>  
  
|<span data-ttu-id="11505-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="11505-106">Attribute</span></span>|<span data-ttu-id="11505-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11505-107">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="11505-108">Oggetto <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività dei canali nel pool prima della disconnessione.</span><span class="sxs-lookup"><span data-stu-id="11505-108">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="11505-109">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="11505-109">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="11505-110">Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo trascorso il quale un canale, dopo essere stato restituito al pool, viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="11505-110">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="11505-111">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="11505-111">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="11505-112">Numero intero positivo che specifica il numero massimo di canali che possono essere memorizzati nel pool per ogni endpoint remoto.</span><span class="sxs-lookup"><span data-stu-id="11505-112">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="11505-113">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="11505-113">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11505-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="11505-114">Child Elements</span></span>  
 <span data-ttu-id="11505-115">No.</span><span class="sxs-lookup"><span data-stu-id="11505-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11505-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="11505-116">Parent Elements</span></span>  
  
|<span data-ttu-id="11505-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="11505-117">Element</span></span>|<span data-ttu-id="11505-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11505-118">Description</span></span>|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|<span data-ttu-id="11505-119">Attiva il routing dei pacchetti per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="11505-119">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11505-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="11505-120">Remarks</span></span>  
 <span data-ttu-id="11505-121">Le quote sono usate come meccanismo di criterio per impedire un consumo eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="11505-121">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="11505-122">Impediscono attacchi di tipo Denial of Service (DoS), dannosi o non intenzionali.</span><span class="sxs-lookup"><span data-stu-id="11505-122">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="11505-123">Usare questo elemento durante l'impostazione delle quote dei canali in un canale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11505-123">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="11505-124">`ChannelPoolSettings` specifica tre quote:</span><span class="sxs-lookup"><span data-stu-id="11505-124">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="11505-125">La quota `idleTimeout` viene usata per ridurre il rischio di attacchi di tipo Denial of Service (DoS) nel server basati sul blocco di risorse per periodi di tempo prolungati.</span><span class="sxs-lookup"><span data-stu-id="11505-125">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="11505-126">Nel client, l'impostazione del valore corretto può aumentare l'affidabilità della connessione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="11505-126">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="11505-127">Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse.</span><span class="sxs-lookup"><span data-stu-id="11505-127">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="11505-128">È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="11505-128">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="11505-129">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="11505-129">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="11505-130">La quota `leaseTimeout` viene usata per l'integrazione con i servizi di bilanciamento del carico e per migliorare l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="11505-130">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="11505-131">Il valore predefinito è basato su un'allocazione conservativa di risorse.</span><span class="sxs-lookup"><span data-stu-id="11505-131">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="11505-132">È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="11505-132">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="11505-133">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="11505-133">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="11505-134">La quota `maxOutboundChannelsPerEndpoint` imposta limiti della cache sia nel server che nel client ed è usata per migliorare l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="11505-134">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="11505-135">Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse idonee per ambienti di sviluppo e scenari con installazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="11505-135">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="11505-136">Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="11505-136">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11505-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="11505-137">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [<span data-ttu-id="11505-138">Binding</span><span class="sxs-lookup"><span data-stu-id="11505-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="11505-139">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="11505-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="11505-140">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="11505-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
