---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 746f98b54285f95bb63e15136508909327c0d140
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264609"
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
  
