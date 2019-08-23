---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: e6e567e8a657b4c1683ae4abfb14f96a0f272e4a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934585"
---
# <a name="udpdiscoveryendpoint"></a><span data-ttu-id="5cf01-101">\<udpDiscoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="5cf01-101">\<udpDiscoveryEndpoint></span></span>
<span data-ttu-id="5cf01-102">Questo elemento di configurazione definisce un endpoint standard preconfigurato per le operazioni di individuazione su un'associazione multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="5cf01-102">This configuration element defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="5cf01-103">Questo endpoint dispone di un contratto fisso e supporta due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="5cf01-103">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="5cf01-104">Dispone inoltre di un'associazione UDP fissa e di un indirizzo predefinito come indicato nelle specifiche WS-Discovery (WS-Discovery aprile 2005 o WS-Discovery V1.1).</span><span class="sxs-lookup"><span data-stu-id="5cf01-104">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>  
  
 <span data-ttu-id="5cf01-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5cf01-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5cf01-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5cf01-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf01-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cf01-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cf01-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5cf01-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5cf01-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5cf01-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cf01-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="5cf01-110">Attributes</span></span>  
  
|<span data-ttu-id="5cf01-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="5cf01-111">Attribute</span></span>|<span data-ttu-id="5cf01-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5cf01-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5cf01-113">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="5cf01-113">discoveryMode</span></span>|<span data-ttu-id="5cf01-114">Stringa che specifica la modalità del protocollo di individuazione.</span><span class="sxs-lookup"><span data-stu-id="5cf01-114">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="5cf01-115">I valori validi sono "Adhoc" e "Managed".</span><span class="sxs-lookup"><span data-stu-id="5cf01-115">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="5cf01-116">Nella modalità gestita il protocollo si basa su un proxy di individuazione che viene usato come un repository di servizi individuabili.</span><span class="sxs-lookup"><span data-stu-id="5cf01-116">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="5cf01-117">Con la modalità Adhoc è necessario che il protocollo utilizzi il meccanismo multicast UDP per l'individuazione dei servizi disponibili.</span><span class="sxs-lookup"><span data-stu-id="5cf01-117">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="5cf01-118">Questo valore è di tipo <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span><span class="sxs-lookup"><span data-stu-id="5cf01-118">This value is of type <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span></span>|  
|<span data-ttu-id="5cf01-119">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="5cf01-119">discoveryVersion</span></span>|<span data-ttu-id="5cf01-120">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="5cf01-120">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="5cf01-121">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="5cf01-121">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="5cf01-122">Questo valore è di tipo <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="5cf01-122">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="5cf01-123">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="5cf01-123">maxResponseDelay</span></span>|<span data-ttu-id="5cf01-124">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di determinati messaggi, ad esempio Probe Match o Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="5cf01-124">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="5cf01-125">Se tutti i messaggi ProbeMatch vengono inviati contemporaneamente, potrebbero verificarsi problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="5cf01-125">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="5cf01-126">Per evitare questo problema, i messaggi ProbeMatch vengono inviati con un ritardo casuale tra ogni ProbeMatch.</span><span class="sxs-lookup"><span data-stu-id="5cf01-126">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="5cf01-127">Il ritardo casuale è compreso nell'intervallo tra 0 e il valore impostato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="5cf01-127">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="5cf01-128">Se questo attributo viene impostato su 0, i messaggi ProbeMatch vengono inviati in un ciclo breve senza alcun ritardo.</span><span class="sxs-lookup"><span data-stu-id="5cf01-128">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="5cf01-129">In caso contrario, i messaggi ProbeMatch vengono inviati con un ritardo casuale, in modo che il tempo totale richiesto per l'invio di tutti i messaggi ProbeMatch non superi il valore di maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="5cf01-129">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="5cf01-130">Questo valore è importante solo per i servizi e non viene usato dai client.</span><span class="sxs-lookup"><span data-stu-id="5cf01-130">This value is only relevant for services, it is not used by clients.</span></span>|  
|<span data-ttu-id="5cf01-131">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="5cf01-131">multicastAddress</span></span>|<span data-ttu-id="5cf01-132">URI che specifica un indirizzo multicast da usare per l'invio e la ricezione dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="5cf01-132">A Uri that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="5cf01-133">Il valore predefinito è l'indirizzo multicast conforme alla specifica del protocollo.</span><span class="sxs-lookup"><span data-stu-id="5cf01-133">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|`name`|<span data-ttu-id="5cf01-134">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="5cf01-134">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="5cf01-135">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="5cf01-135">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cf01-136">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5cf01-136">Child Elements</span></span>  
  
|<span data-ttu-id="5cf01-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cf01-137">Element</span></span>|<span data-ttu-id="5cf01-138">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5cf01-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cf01-139">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="5cf01-139">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="5cf01-140">Raccolta di impostazioni che consentono di configurare il trasporto UDP per l'endpoint UDP.</span><span class="sxs-lookup"><span data-stu-id="5cf01-140">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cf01-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5cf01-141">Parent Elements</span></span>  
  
|<span data-ttu-id="5cf01-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cf01-142">Element</span></span>|<span data-ttu-id="5cf01-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5cf01-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cf01-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5cf01-144">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="5cf01-145">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="5cf01-145">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5cf01-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="5cf01-146">Example</span></span>  
 <span data-ttu-id="5cf01-147">Nell'esempio seguente viene illustrato un servizio in ascolto di messaggi di individuazione su un trasporto multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="5cf01-147">The following example demonstrates a service listening for discovery messages over a UDP multicast transport.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="5cf01-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cf01-148">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
