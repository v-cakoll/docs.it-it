---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: decaaa1cea5345ff971b16cbb20a85dd803a52d5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850293"
---
# \<announcementEndpoint>
<span data-ttu-id="aa712-101">Questo elemento di configurazione definisce un endpoint standard con un contratto di annuncio fisso.</span><span class="sxs-lookup"><span data-stu-id="aa712-101">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="aa712-102">Un servizio può annunciare la propria disponibilità inviando un messaggio di annuncio online oppure offline rispettivamente quando viene aperto o chiuso.</span><span class="sxs-lookup"><span data-stu-id="aa712-102">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="aa712-103">Un servizio Windows Communication Foundation (WCF) specifica gli endpoint dell'annuncio nell' [\<serviceDiscovery>](servicediscovery.md) elemento e USA AnnouncementClient per eseguire gli annunci.</span><span class="sxs-lookup"><span data-stu-id="aa712-103">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="aa712-104">Un client che desidera restare in ascolto dell'annuncio da un altro servizio funziona effettivamente come servizio WCF; è quindi necessario configurare gli endpoint dell'annuncio per il client nella [\<services>](services.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="aa712-104">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="aa712-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa712-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa712-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aa712-106">Attributes and Elements</span></span>  
 <span data-ttu-id="aa712-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aa712-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa712-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="aa712-108">Attributes</span></span>  
  
|<span data-ttu-id="aa712-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="aa712-109">Attribute</span></span>|<span data-ttu-id="aa712-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa712-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa712-111">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="aa712-111">discoveryVersion</span></span>|<span data-ttu-id="aa712-112">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="aa712-112">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="aa712-113">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="aa712-113">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="aa712-114">Questo valore è di tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="aa712-114">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="aa712-115">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="aa712-115">maxAnnouncementDelay</span></span>|<span data-ttu-id="aa712-116">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di un messaggio Hello.</span><span class="sxs-lookup"><span data-stu-id="aa712-116">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="aa712-117">Prima dell'invio dei messaggi, trascorrerà un periodo di attesa il cui valore casuale è compreso tra 0 e il valore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="aa712-117">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="aa712-118">Questo attributo viene usato per impostare un ritardo casuale limitato che consente di evitare problemi di rete quando la rete si arresta e tutti i servizi ritornano online contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="aa712-118">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="aa712-119">name</span><span class="sxs-lookup"><span data-stu-id="aa712-119">name</span></span>|<span data-ttu-id="aa712-120">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="aa712-120">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="aa712-121">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="aa712-121">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa712-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aa712-122">Child Elements</span></span>  
 <span data-ttu-id="aa712-123">No.</span><span class="sxs-lookup"><span data-stu-id="aa712-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa712-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aa712-124">Parent Elements</span></span>  
  
|<span data-ttu-id="aa712-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa712-125">Element</span></span>|<span data-ttu-id="aa712-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa712-126">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="aa712-127">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="aa712-127">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aa712-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa712-128">Example</span></span>  
 <span data-ttu-id="aa712-129">Nell'esempio seguente viene illustrato un client in ascolto di messaggi di annuncio su http e peernet.</span><span class="sxs-lookup"><span data-stu-id="aa712-129">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa712-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa712-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
