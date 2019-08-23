---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936280"
---
# <a name="servicediscovery"></a><span data-ttu-id="68622-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="68622-101">\<serviceDiscovery></span></span>
<span data-ttu-id="68622-102">Specifica l'individuabilità degli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="68622-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="68622-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="68622-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="68622-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="68622-104">\<behaviors></span></span>  
<span data-ttu-id="68622-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="68622-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="68622-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="68622-106">\<behavior></span></span>  
<span data-ttu-id="68622-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="68622-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68622-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68622-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68622-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="68622-109">Attributes and Elements</span></span>  
 <span data-ttu-id="68622-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="68622-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68622-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="68622-111">Attributes</span></span>  
 <span data-ttu-id="68622-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="68622-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="68622-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="68622-113">Child Elements</span></span>  
  
|<span data-ttu-id="68622-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="68622-114">Element</span></span>|<span data-ttu-id="68622-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68622-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68622-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="68622-116">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="68622-117">Raccolta di endpoint per agli annunci.</span><span class="sxs-lookup"><span data-stu-id="68622-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="68622-118">Usare questa sezione per specificare gli endpoint da usare per l'invio di messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="68622-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="68622-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="68622-119">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="68622-120">Raccolta di endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="68622-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="68622-121">Usare questa sezione per specificare gli endpoint sui quali stare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="68622-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68622-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="68622-122">Parent Elements</span></span>  
  
|<span data-ttu-id="68622-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="68622-123">Element</span></span>|<span data-ttu-id="68622-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="68622-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68622-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="68622-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="68622-126">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="68622-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68622-127">Note</span><span class="sxs-lookup"><span data-stu-id="68622-127">Remarks</span></span>  
 <span data-ttu-id="68622-128">Quando viene aggiunto alla configurazione del comportamento di un servizio, questo elemento di configurazione rende individuabili tutti gli endpoint di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="68622-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="68622-129">È possibile configurare ulteriormente le funzionalità di individuazione di tali endpoint usando gli [ \<elementi figlio DiscoveryEndpoint >](discoveryendpoint.md) o [ \<announcementEndpoint >](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="68622-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="68622-130">Utilizzare la [ \<sezione announcementEndpoint >](announcementendpoint.md) per configurare gli annunci specificando la configurazione dell'endpoint da utilizzare per inviare annunci di servizio (online/Hello e offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="68622-130">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="68622-131">Utilizzare la [ \<sezione DiscoveryEndpoint >](discoveryendpoint.md) per specificare manualmente l'endpoint sul quale restare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="68622-131">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68622-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="68622-132">Example</span></span>  
 <span data-ttu-id="68622-133">Nell'esempio di configurazione seguente viene specificato che CalculatorService è individuabile e viene specificato facoltativamente l'endpoint per gli annunci da usare.</span><span class="sxs-lookup"><span data-stu-id="68622-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68622-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68622-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
