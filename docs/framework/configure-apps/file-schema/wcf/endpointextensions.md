---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: fe57cb84cfa70b1f6b92abf1dbac89ddad9d4dc8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925706"
---
# <a name="endpointextensions"></a>\<endpointExtensions>
Contenuto della sezione viene registrato un nuovo endpoint standard nella sezione delle estensioni di un file di configurazione di un computer o di un'applicazione. È possibile aggiungere un endpoint standard a questa raccolta usando la parola chiave `add` e impostando l'attributo `type` dell'elemento sul tipo di endpoint, nonché l'attributo `name` sul nome dell'endpoint standard.  
  
 Nell'esempio seguente viene usato l'elemento `add` e l'attributo `name` per aggiungere un endpoint standard alla sezione `<endpointExtensions>` del file di configurazione.  
  
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
  
 Dopo aver registrato l'endpoint standard, sarà possibile usarlo come illustrato nell'esempio seguente. Nell'elemento `kind` `<endpointExtensions>` > dell' [ endpoint,l'attributospecificailtipodiendpointstandardcheèstatoregistratonellasezione.\<](endpoint-element.md) L' `endpointConfiguration` attributo sarà identico `name` all'attributo dell'elemento di configurazione dell'endpoint standard nella `<standardEndpoints>` sezione.  
  
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
