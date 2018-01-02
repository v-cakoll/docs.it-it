---
title: '&lt;announcementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae03b5d4a82c08978a3456e80428ba6ad8ac532a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="f4614-102">&lt;announcementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="f4614-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="f4614-103">Questo elemento di configurazione definisce un endpoint standard con un contratto di annuncio fisso.</span><span class="sxs-lookup"><span data-stu-id="f4614-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="f4614-104">Un servizio può annunciare la propria disponibilità inviando un messaggio di annuncio online oppure offline rispettivamente quando viene aperto o chiuso.</span><span class="sxs-lookup"><span data-stu-id="f4614-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="f4614-105">Oggetto [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] servizio specifica gli endpoint di annuncio nel [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento e viene utilizzato AnnouncementClient per eseguire gli annunci.</span><span class="sxs-lookup"><span data-stu-id="f4614-105">A [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="f4614-106">Un client che desidera eseguire l'ascolto per l'annuncio da altro servizio effettivamente funge da un [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servizio; pertanto è necessario configurare gli endpoint di annuncio per quel client nel [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="f4614-106">A client wishing to listen for the announcement from other service is actually acting as a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="f4614-107">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f4614-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="f4614-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="f4614-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4614-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4614-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4614-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f4614-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f4614-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f4614-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4614-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f4614-112">Attributes</span></span>  
  
|<span data-ttu-id="f4614-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="f4614-113">Attribute</span></span>|<span data-ttu-id="f4614-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4614-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4614-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="f4614-115">discoveryVersion</span></span>|<span data-ttu-id="f4614-116">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f4614-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="f4614-117">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="f4614-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="f4614-118">Questo valore è di tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="f4614-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="f4614-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="f4614-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="f4614-120">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di un messaggio Hello.</span><span class="sxs-lookup"><span data-stu-id="f4614-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="f4614-121">Prima dell'invio dei messaggi, trascorrerà un periodo di attesa il cui valore casuale è compreso tra 0 e il valore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="f4614-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="f4614-122">Questo attributo viene usato per impostare un ritardo casuale limitato che consente di evitare problemi di rete quando la rete si arresta e tutti i servizi ritornano online contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f4614-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="f4614-123">name</span><span class="sxs-lookup"><span data-stu-id="f4614-123">name</span></span>|<span data-ttu-id="f4614-124">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="f4614-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="f4614-125">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="f4614-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4614-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f4614-126">Child Elements</span></span>  
 <span data-ttu-id="f4614-127">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f4614-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4614-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f4614-128">Parent Elements</span></span>  
  
|<span data-ttu-id="f4614-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="f4614-129">Element</span></span>|<span data-ttu-id="f4614-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4614-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4614-131">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="f4614-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="f4614-132">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="f4614-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f4614-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4614-133">Example</span></span>  
 <span data-ttu-id="f4614-134">Nell'esempio seguente viene illustrato un client in ascolto di messaggi di annuncio su http e peernet.</span><span class="sxs-lookup"><span data-stu-id="f4614-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f4614-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4614-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
