---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 04f5fb27a0da7e553ff3c0308f7fb2e2df2e0b20
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210009"
---
# <a name="udpannouncementendpoint"></a><span data-ttu-id="91a66-101">\<udpAnnouncementEndpoint></span><span class="sxs-lookup"><span data-stu-id="91a66-101">\<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="91a66-102">Questo elemento di configurazione definisce un endpoint standard usato dai servizi per inviare messaggi di annuncio su un'associazione UDP.</span><span class="sxs-lookup"><span data-stu-id="91a66-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="91a66-103">Dispone di un contratto fisso e supporta due versioni di individuazione.</span><span class="sxs-lookup"><span data-stu-id="91a66-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="91a66-104">Dispone inoltre di un'associazione UDP fissa e di un valore dell'indirizzo predefinito come indicato nelle specifiche WS-Discovery (WS-Discovery aprile 2005 o versione WS-Discovery 1.1).</span><span class="sxs-lookup"><span data-stu-id="91a66-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="91a66-105">È possibile specificare l'indirizzo multicast da usare per l'invio e la ricezione dei messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="91a66-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="91a66-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="91a66-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="91a66-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="91a66-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a66-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91a66-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91a66-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91a66-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91a66-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91a66-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91a66-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="91a66-111">Attributes</span></span>  
  
|<span data-ttu-id="91a66-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="91a66-112">Attribute</span></span>|<span data-ttu-id="91a66-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a66-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91a66-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="91a66-114">discoveryVersion</span></span>|<span data-ttu-id="91a66-115">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="91a66-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="91a66-116">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="91a66-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="91a66-117">Questo valore è di tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="91a66-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="91a66-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="91a66-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="91a66-119">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di un messaggio Hello.</span><span class="sxs-lookup"><span data-stu-id="91a66-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="91a66-120">Prima dell'invio dei messaggi, trascorrerà un periodo di attesa il cui valore casuale è compreso tra 0 e il valore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="91a66-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="91a66-121">Questo attributo viene usato per impostare un ritardo casuale limitato che consente di evitare problemi di rete quando la rete si arresta e tutti i servizi ritornano online contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="91a66-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="91a66-122">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="91a66-122">multicastAddress</span></span>|<span data-ttu-id="91a66-123">URI che specifica un indirizzo multicast da usare per l'invio e la ricezione dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="91a66-123">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="91a66-124">Il valore predefinito è l'indirizzo multicast conforme alla specifica del protocollo.</span><span class="sxs-lookup"><span data-stu-id="91a66-124">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="91a66-125">name</span><span class="sxs-lookup"><span data-stu-id="91a66-125">name</span></span>|<span data-ttu-id="91a66-126">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="91a66-126">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="91a66-127">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="91a66-127">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91a66-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91a66-128">Child Elements</span></span>  
  
|<span data-ttu-id="91a66-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="91a66-129">Element</span></span>|<span data-ttu-id="91a66-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a66-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91a66-131">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="91a66-131">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="91a66-132">Raccolta di impostazioni che consentono di configurare il trasporto UDP per l'endpoint UDP.</span><span class="sxs-lookup"><span data-stu-id="91a66-132">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91a66-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91a66-133">Parent Elements</span></span>  
  
|<span data-ttu-id="91a66-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="91a66-134">Element</span></span>|<span data-ttu-id="91a66-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a66-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91a66-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="91a66-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="91a66-137">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="91a66-137">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="91a66-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="91a66-138">Example</span></span>  
 <span data-ttu-id="91a66-139">Nell'esempio seguente viene illustrato un client in ascolto di un annuncio su un trasporto multicast UDP con indirizzo multicast predefinito e trasporto multicast UDP con indirizzo multicast specificato.</span><span class="sxs-lookup"><span data-stu-id="91a66-139">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="udpAnnouncementEndpointStandard"
              kind="udpAnnouncementEndpoint"
              bindingConfiguration="..." />
    <endpoint name="udpAnnouncementEndpoint2"
              kind="udpAnnouncementEndpoint"
              endpointConfiguration="AnnouncementConfiguration3702"
              bindingConfiguration="..." />
    ...
  </service>
</services>
<standardEndpoints>
  <udpAnnouncementEndpoint>
    <standardEndpoint name="AnnouncementConfiguration2"
                      version="WSDiscoveryApril2005"
                      multicastAddress="soap.udp://239.255.255.250:3703"/>
  </udpAnnouncementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="91a66-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91a66-140">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
