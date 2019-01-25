---
title: '&lt;serviceDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 73943f5f962a6963809e2c65ce8593f6181559f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587333"
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="b80a4-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="b80a4-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="b80a4-103">Specifica l'individuabilità degli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="b80a4-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="b80a4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b80a4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b80a4-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b80a4-105">\<behaviors></span></span>  
<span data-ttu-id="b80a4-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b80a4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b80a4-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b80a4-107">\<behavior></span></span>  
<span data-ttu-id="b80a4-108">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="b80a4-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80a4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b80a4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b80a4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b80a4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b80a4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b80a4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b80a4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b80a4-112">Attributes</span></span>  
 <span data-ttu-id="b80a4-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b80a4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b80a4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b80a4-114">Child Elements</span></span>  
  
|<span data-ttu-id="b80a4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b80a4-115">Element</span></span>|<span data-ttu-id="b80a4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b80a4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b80a4-117">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="b80a4-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="b80a4-118">Raccolta di endpoint per agli annunci.</span><span class="sxs-lookup"><span data-stu-id="b80a4-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="b80a4-119">Usare questa sezione per specificare gli endpoint da usare per l'invio di messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="b80a4-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="b80a4-120">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="b80a4-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="b80a4-121">Raccolta di endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="b80a4-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="b80a4-122">Usare questa sezione per specificare gli endpoint sui quali stare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="b80a4-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b80a4-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b80a4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b80a4-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b80a4-124">Element</span></span>|<span data-ttu-id="b80a4-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b80a4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b80a4-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b80a4-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b80a4-127">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="b80a4-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b80a4-128">Note</span><span class="sxs-lookup"><span data-stu-id="b80a4-128">Remarks</span></span>  
 <span data-ttu-id="b80a4-129">Quando viene aggiunto alla configurazione del comportamento di un servizio, questo elemento di configurazione rende individuabili tutti gli endpoint di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="b80a4-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="b80a4-130">È possibile configurare ulteriormente le funzionalità di individuazione di tali endpoint usando il [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) oppure [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="b80a4-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="b80a4-131">Usare la [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) sezione per configurare gli annunci specificando la configurazione dell'endpoint da usare per inviare annunci di servizio (online/Hello e offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="b80a4-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="b80a4-132">Usare la [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) sezione per specificare manualmente l'endpoint su cui rimanere in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="b80a4-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b80a4-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="b80a4-133">Example</span></span>  
 <span data-ttu-id="b80a4-134">Nell'esempio di configurazione seguente viene specificato che CalculatorService è individuabile e viene specificato facoltativamente l'endpoint per gli annunci da usare.</span><span class="sxs-lookup"><span data-stu-id="b80a4-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b80a4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b80a4-135">See also</span></span>
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
