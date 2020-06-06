---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: fe57cb84cfa70b1f6b92abf1dbac89ddad9d4dc8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69925706"
---
# \<endpointExtensions>
<span data-ttu-id="55df7-101">Contenuto della sezione viene registrato un nuovo endpoint standard nella sezione delle estensioni di un file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="55df7-101">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="55df7-102">È possibile aggiungere un endpoint standard a questa raccolta usando la parola chiave `add` e impostando l'attributo `type` dell'elemento sul tipo di endpoint, nonché l'attributo `name` sul nome dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="55df7-102">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="55df7-103">Nell'esempio seguente viene usato l'elemento `add` e l'attributo `name` per aggiungere un endpoint standard alla sezione `<endpointExtensions>` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="55df7-103">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="55df7-104">Dopo aver registrato l'endpoint standard, sarà possibile usarlo come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="55df7-104">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="55df7-105">Nell' [\<endpoint>](endpoint-element.md) elemento l' `kind` attributo specifica il tipo di endpoint standard che è stato registrato nella `<endpointExtensions>` sezione.</span><span class="sxs-lookup"><span data-stu-id="55df7-105">In the [\<endpoint>](endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="55df7-106">L' `endpointConfiguration` attributo sarà identico all' `name` attributo dell'elemento di configurazione dell'endpoint standard nella `<standardEndpoints>` sezione.</span><span class="sxs-lookup"><span data-stu-id="55df7-106">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
