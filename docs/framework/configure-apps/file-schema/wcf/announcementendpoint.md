---
title: '&lt;announcementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 8e180d53260ccf3364ab3c8d7b076f78917526d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729879"
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="86b1e-102">&lt;announcementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="86b1e-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="86b1e-103">Questo elemento di configurazione definisce un endpoint standard con un contratto di annuncio fisso.</span><span class="sxs-lookup"><span data-stu-id="86b1e-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="86b1e-104">Un servizio può annunciare la propria disponibilità inviando un messaggio di annuncio online oppure offline rispettivamente quando viene aperto o chiuso.</span><span class="sxs-lookup"><span data-stu-id="86b1e-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="86b1e-105">Un servizio Windows Communication Foundation (WCF) consente di specificare gli endpoint di annuncio nel [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento e Usa AnnouncementClient per eseguire gli annunci.</span><span class="sxs-lookup"><span data-stu-id="86b1e-105">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="86b1e-106">Un client che desidera stare in ascolto per l'annuncio da altro servizio in realtà funge da un servizio WCF; pertanto è necessario configurare l'endpoint annunci per tale client nella [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="86b1e-106">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="86b1e-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="86b1e-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="86b1e-108">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="86b1e-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86b1e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86b1e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86b1e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="86b1e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86b1e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="86b1e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86b1e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="86b1e-112">Attributes</span></span>  
  
|<span data-ttu-id="86b1e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="86b1e-113">Attribute</span></span>|<span data-ttu-id="86b1e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86b1e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86b1e-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="86b1e-115">discoveryVersion</span></span>|<span data-ttu-id="86b1e-116">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="86b1e-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="86b1e-117">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="86b1e-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="86b1e-118">Questo valore è di tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="86b1e-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="86b1e-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="86b1e-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="86b1e-120">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di un messaggio Hello.</span><span class="sxs-lookup"><span data-stu-id="86b1e-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="86b1e-121">Prima dell'invio dei messaggi, trascorrerà un periodo di attesa il cui valore casuale è compreso tra 0 e il valore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="86b1e-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="86b1e-122">Questo attributo viene usato per impostare un ritardo casuale limitato che consente di evitare problemi di rete quando la rete si arresta e tutti i servizi ritornano online contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="86b1e-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="86b1e-123">name</span><span class="sxs-lookup"><span data-stu-id="86b1e-123">name</span></span>|<span data-ttu-id="86b1e-124">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="86b1e-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="86b1e-125">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="86b1e-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86b1e-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="86b1e-126">Child Elements</span></span>  
 <span data-ttu-id="86b1e-127">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="86b1e-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86b1e-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="86b1e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="86b1e-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="86b1e-129">Element</span></span>|<span data-ttu-id="86b1e-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86b1e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86b1e-131">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="86b1e-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="86b1e-132">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="86b1e-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="86b1e-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="86b1e-133">Example</span></span>  
 <span data-ttu-id="86b1e-134">Nell'esempio seguente viene illustrato un client in ascolto di messaggi di annuncio su http e peernet.</span><span class="sxs-lookup"><span data-stu-id="86b1e-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86b1e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86b1e-135">See also</span></span>
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
