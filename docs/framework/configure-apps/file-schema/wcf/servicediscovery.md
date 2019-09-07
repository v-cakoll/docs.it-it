---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399639"
---
# <a name="servicediscovery"></a><span data-ttu-id="c238f-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="c238f-101">\<serviceDiscovery></span></span>
<span data-ttu-id="c238f-102">Specifica l'individuabilità degli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="c238f-102">Specifies the discoverability of service endpoints.</span></span>  
  
<span data-ttu-id="c238f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c238f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c238f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c238f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c238f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c238f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c238f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c238f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="c238f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c238f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="c238f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceDiscovery**</span><span class="sxs-lookup"><span data-stu-id="c238f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c238f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c238f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c238f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c238f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c238f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c238f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c238f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c238f-112">Attributes</span></span>  
 <span data-ttu-id="c238f-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c238f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c238f-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c238f-114">Child Elements</span></span>  
  
|<span data-ttu-id="c238f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c238f-115">Element</span></span>|<span data-ttu-id="c238f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c238f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c238f-117">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="c238f-117">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="c238f-118">Raccolta di endpoint per agli annunci.</span><span class="sxs-lookup"><span data-stu-id="c238f-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="c238f-119">Usare questa sezione per specificare gli endpoint da usare per l'invio di messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="c238f-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="c238f-120">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="c238f-120">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="c238f-121">Raccolta di endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="c238f-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="c238f-122">Usare questa sezione per specificare gli endpoint sui quali stare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="c238f-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c238f-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c238f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c238f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c238f-124">Element</span></span>|<span data-ttu-id="c238f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c238f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c238f-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c238f-126">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c238f-127">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="c238f-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c238f-128">Note</span><span class="sxs-lookup"><span data-stu-id="c238f-128">Remarks</span></span>  
 <span data-ttu-id="c238f-129">Quando viene aggiunto alla configurazione del comportamento di un servizio, questo elemento di configurazione rende individuabili tutti gli endpoint di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="c238f-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="c238f-130">È possibile configurare ulteriormente le funzionalità di individuazione di tali endpoint usando gli [ \<elementi figlio DiscoveryEndpoint >](discoveryendpoint.md) o [ \<announcementEndpoint >](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="c238f-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="c238f-131">Utilizzare la [ \<sezione announcementEndpoint >](announcementendpoint.md) per configurare gli annunci specificando la configurazione dell'endpoint da utilizzare per inviare annunci di servizio (online/Hello e offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="c238f-131">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="c238f-132">Utilizzare la [ \<sezione DiscoveryEndpoint >](discoveryendpoint.md) per specificare manualmente l'endpoint sul quale restare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="c238f-132">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c238f-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="c238f-133">Example</span></span>  
 <span data-ttu-id="c238f-134">Nell'esempio di configurazione seguente viene specificato che CalculatorService è individuabile e viene specificato facoltativamente l'endpoint per gli annunci da usare.</span><span class="sxs-lookup"><span data-stu-id="c238f-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c238f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c238f-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
