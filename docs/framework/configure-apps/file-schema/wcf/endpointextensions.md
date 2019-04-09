---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 12ac8d9a7b0ed584fb1308e56d197a03b1c53e51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174928"
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
  
 Dopo aver registrato l'endpoint standard, sarà possibile usarlo come illustrato nell'esempio seguente. Nel [ \<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento, il `kind` attributo specifica il tipo di endpoint standard che è stato registrato nel `<endpointExtensions>` sezione. Il `endpointConfiguration` sarà identico all'attributo il `name` attributo dell'elemento di configurazione dell'endpoint standard nella `<standardEndpoints>` sezione.  
  
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
