---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 54a9833f56927568af711a103bd3831b767711e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788414"
---
# <a name="servicediscovery"></a><span data-ttu-id="54f8f-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="54f8f-101">\<serviceDiscovery></span></span>
<span data-ttu-id="54f8f-102">Specifica l'individuabilità degli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="54f8f-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="54f8f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="54f8f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="54f8f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="54f8f-104">\<behaviors></span></span>  
<span data-ttu-id="54f8f-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="54f8f-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="54f8f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="54f8f-106">\<behavior></span></span>  
<span data-ttu-id="54f8f-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="54f8f-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f8f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54f8f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54f8f-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="54f8f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="54f8f-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="54f8f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54f8f-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="54f8f-111">Attributes</span></span>  
 <span data-ttu-id="54f8f-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="54f8f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="54f8f-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="54f8f-113">Child Elements</span></span>  
  
|<span data-ttu-id="54f8f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="54f8f-114">Element</span></span>|<span data-ttu-id="54f8f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54f8f-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54f8f-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="54f8f-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="54f8f-117">Raccolta di endpoint per agli annunci.</span><span class="sxs-lookup"><span data-stu-id="54f8f-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="54f8f-118">Usare questa sezione per specificare gli endpoint da usare per l'invio di messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="54f8f-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="54f8f-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="54f8f-119">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="54f8f-120">Raccolta di endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="54f8f-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="54f8f-121">Usare questa sezione per specificare gli endpoint sui quali stare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="54f8f-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54f8f-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="54f8f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="54f8f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="54f8f-123">Element</span></span>|<span data-ttu-id="54f8f-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54f8f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54f8f-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="54f8f-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="54f8f-126">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="54f8f-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54f8f-127">Note</span><span class="sxs-lookup"><span data-stu-id="54f8f-127">Remarks</span></span>  
 <span data-ttu-id="54f8f-128">Quando viene aggiunto alla configurazione del comportamento di un servizio, questo elemento di configurazione rende individuabili tutti gli endpoint di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="54f8f-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="54f8f-129">È possibile configurare ulteriormente le funzionalità di individuazione di tali endpoint usando il [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) oppure [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="54f8f-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="54f8f-130">Usare la [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) sezione per configurare gli annunci specificando la configurazione dell'endpoint da usare per inviare annunci di servizio (online/Hello e offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="54f8f-130">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="54f8f-131">Usare la [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) sezione per specificare manualmente l'endpoint su cui rimanere in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="54f8f-131">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54f8f-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="54f8f-132">Example</span></span>  
 <span data-ttu-id="54f8f-133">Nell'esempio di configurazione seguente viene specificato che CalculatorService è individuabile e viene specificato facoltativamente l'endpoint per gli annunci da usare.</span><span class="sxs-lookup"><span data-stu-id="54f8f-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54f8f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f8f-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
