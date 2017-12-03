---
title: '&lt;serviceDiscovery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9bdd16e02742baa14d1ebd11ea95591df7093705
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="0c56e-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="0c56e-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="0c56e-103">Specifica l'individuabilità degli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c56e-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="0c56e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0c56e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c56e-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="0c56e-105">\<behaviors></span></span>  
<span data-ttu-id="0c56e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0c56e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0c56e-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="0c56e-107">\<behavior></span></span>  
<span data-ttu-id="0c56e-108">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="0c56e-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c56e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c56e-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String" 
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String" 
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c56e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0c56e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0c56e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0c56e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c56e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="0c56e-112">Attributes</span></span>  
 <span data-ttu-id="0c56e-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0c56e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c56e-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0c56e-114">Child Elements</span></span>  
  
|<span data-ttu-id="0c56e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c56e-115">Element</span></span>|<span data-ttu-id="0c56e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c56e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c56e-117">\<announcementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="0c56e-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="0c56e-118">Raccolta di endpoint per agli annunci.</span><span class="sxs-lookup"><span data-stu-id="0c56e-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="0c56e-119">Usare questa sezione per specificare gli endpoint da usare per l'invio di messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="0c56e-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="0c56e-120">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="0c56e-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="0c56e-121">Raccolta di endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="0c56e-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="0c56e-122">Usare questa sezione per specificare gli endpoint sui quali stare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="0c56e-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c56e-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0c56e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0c56e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c56e-124">Element</span></span>|<span data-ttu-id="0c56e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c56e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c56e-126">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="0c56e-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0c56e-127">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="0c56e-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c56e-128">Note</span><span class="sxs-lookup"><span data-stu-id="0c56e-128">Remarks</span></span>  
 <span data-ttu-id="0c56e-129">Quando viene aggiunto alla configurazione del comportamento di un servizio, questo elemento di configurazione rende individuabili tutti gli endpoint di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="0c56e-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="0c56e-130">È possibile configurare ulteriormente la funzionalità di individuazione di tali endpoint tramite il [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) o [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="0c56e-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="0c56e-131">Utilizzare il [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) sezione per configurare gli annunci specificando la configurazione dell'endpoint da utilizzare per inviare annunci di servizio (online/Hello e Bye offline /).</span><span class="sxs-lookup"><span data-stu-id="0c56e-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="0c56e-132">Utilizzare il [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) sezione per specificare manualmente l'endpoint in cui è in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="0c56e-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c56e-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c56e-133">Example</span></span>  
 <span data-ttu-id="0c56e-134">Nell'esempio di configurazione seguente viene specificato che CalculatorService è individuabile e viene specificato facoltativamente l'endpoint per gli annunci da usare.</span><span class="sxs-lookup"><span data-stu-id="0c56e-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
  ...  
  </service>  
</services>  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="udpEndpoint"  
                        kind="udpAnnouncementEndpoint" />  
        </announcementEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c56e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c56e-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
