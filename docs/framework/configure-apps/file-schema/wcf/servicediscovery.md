---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399639"
---
# \<serviceDiscovery>
<span data-ttu-id="9a6a7-101">Specifica l'individuabilità degli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-101">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="9a6a7-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a6a7-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a6a7-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9a6a7-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9a6a7-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a6a7-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="9a6a7-105">Attributes</span></span>  
 <span data-ttu-id="9a6a7-106">No.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a6a7-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9a6a7-107">Child Elements</span></span>  
  
|<span data-ttu-id="9a6a7-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a6a7-108">Element</span></span>|<span data-ttu-id="9a6a7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a6a7-109">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="9a6a7-110">Raccolta di endpoint per agli annunci.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-110">A collection of announcement endpoints.</span></span> <span data-ttu-id="9a6a7-111">Usare questa sezione per specificare gli endpoint da usare per l'invio di messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-111">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="9a6a7-112">Raccolta di endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-112">A collection of discovery endpoints.</span></span> <span data-ttu-id="9a6a7-113">Usare questa sezione per specificare gli endpoint sui quali stare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-113">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a6a7-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9a6a7-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9a6a7-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a6a7-115">Element</span></span>|<span data-ttu-id="9a6a7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a6a7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9a6a7-117">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a6a7-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="9a6a7-118">Remarks</span></span>  
 <span data-ttu-id="9a6a7-119">Quando viene aggiunto alla configurazione del comportamento di un servizio, questo elemento di configurazione rende individuabili tutti gli endpoint di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-119">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="9a6a7-120">È possibile configurare ulteriormente le funzionalità di individuazione di tali endpoint usando gli [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) elementi figlio o.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-120">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="9a6a7-121">Utilizzare la [\<announcementEndpoint>](announcementendpoint.md) sezione per configurare gli annunci specificando la configurazione dell'endpoint da utilizzare per inviare annunci di servizio (online/Hello e offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="9a6a7-121">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="9a6a7-122">Utilizzare la [\<discoveryEndpoint>](discoveryendpoint.md) sezione per specificare manualmente l'endpoint sul quale restare in ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-122">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a6a7-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a6a7-123">Example</span></span>  
 <span data-ttu-id="9a6a7-124">Nell'esempio di configurazione seguente viene specificato che CalculatorService è individuabile e viene specificato facoltativamente l'endpoint per gli annunci da usare.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-124">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a6a7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a6a7-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
