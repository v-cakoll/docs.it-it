---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: decaaa1cea5345ff971b16cbb20a85dd803a52d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850293"
---
# <a name="announcementendpoint"></a><span data-ttu-id="0e296-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="0e296-101">\<announcementEndpoint></span></span>
<span data-ttu-id="0e296-102">Questo elemento di configurazione definisce un endpoint standard con un contratto di annuncio fisso.</span><span class="sxs-lookup"><span data-stu-id="0e296-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="0e296-103">Un servizio può annunciare la propria disponibilità inviando un messaggio di annuncio online oppure offline rispettivamente quando viene aperto o chiuso.</span><span class="sxs-lookup"><span data-stu-id="0e296-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="0e296-104">Un servizio Windows Communication Foundation (WCF) specifica gli endpoint dell'annuncio nell' [ \<elemento > serviceDiscovery](servicediscovery.md) e usa il AnnouncementClient per eseguire gli annunci.</span><span class="sxs-lookup"><span data-stu-id="0e296-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="0e296-105">Un client che desidera restare in ascolto dell'annuncio da un altro servizio funziona effettivamente come servizio WCF; è quindi necessario configurare gli endpoint degli annunci per il client nella [ \<sezione Servizi >](services.md) .</span><span class="sxs-lookup"><span data-stu-id="0e296-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="0e296-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e296-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0e296-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0e296-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0e296-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="0e296-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="0e296-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> announcementEndpoint**</span><span class="sxs-lookup"><span data-stu-id="0e296-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e296-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e296-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e296-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e296-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0e296-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e296-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e296-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e296-113">Attributes</span></span>  
  
|<span data-ttu-id="0e296-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="0e296-114">Attribute</span></span>|<span data-ttu-id="0e296-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e296-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e296-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="0e296-116">discoveryVersion</span></span>|<span data-ttu-id="0e296-117">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="0e296-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="0e296-118">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="0e296-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="0e296-119">Questo valore è di tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="0e296-119">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="0e296-120">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="0e296-120">maxAnnouncementDelay</span></span>|<span data-ttu-id="0e296-121">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di un messaggio Hello.</span><span class="sxs-lookup"><span data-stu-id="0e296-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="0e296-122">Prima dell'invio dei messaggi, trascorrerà un periodo di attesa il cui valore casuale è compreso tra 0 e il valore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="0e296-122">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="0e296-123">Questo attributo viene usato per impostare un ritardo casuale limitato che consente di evitare problemi di rete quando la rete si arresta e tutti i servizi ritornano online contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0e296-123">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="0e296-124">name</span><span class="sxs-lookup"><span data-stu-id="0e296-124">name</span></span>|<span data-ttu-id="0e296-125">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="0e296-125">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="0e296-126">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="0e296-126">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e296-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e296-127">Child Elements</span></span>  
 <span data-ttu-id="0e296-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0e296-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e296-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e296-129">Parent Elements</span></span>  
  
|<span data-ttu-id="0e296-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e296-130">Element</span></span>|<span data-ttu-id="0e296-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e296-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e296-132">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0e296-132">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="0e296-133">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="0e296-133">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0e296-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e296-134">Example</span></span>  
 <span data-ttu-id="0e296-135">Nell'esempio seguente viene illustrato un client in ascolto di messaggi di annuncio su http e peernet.</span><span class="sxs-lookup"><span data-stu-id="0e296-135">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="0e296-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e296-136">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
