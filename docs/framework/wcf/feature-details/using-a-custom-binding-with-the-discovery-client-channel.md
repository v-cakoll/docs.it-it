---
title: Uso di un'associazione personalizzata con il canale client di individuazione
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a5c80a257efb5f6006a0cf6394a1079cf92d2471
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a>Uso di un'associazione personalizzata con il canale client di individuazione
In caso di utilizzo di un'associazione personalizzata con <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, è necessario definire un elemento <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> che crea istanze <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.  
  
## <a name="creating-a-discoveryendpointprovider"></a>Creazione di un elemento DiscoveryEndpointProvider  
 Il <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> è responsabile della creazione <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> istanze su richiesta. Per definire un provider di endpoint di individuazione, derivare una classe da <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ed eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>, quindi restituire un nuovo endpoint di individuazione. Nell'esempio seguente viene mostrato come creare un provider di endpoint di individuazione.  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel   
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 Una volta definito il provider di endpoint di individuazione, è possibile creare un'associazione personalizzata e aggiungere <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, che fa riferimento al provider di endpoint di individuazione, come indicato nell'esempio seguente.  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 Per ulteriori informazioni sull'utilizzo del canale client di individuazione, vedere [usando il canale Client di individuazione](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md). Per un esempio di codice completo, vedere [esempio di elemento di associazione di individuazione](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Utilizzo del canale client di individuazione](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 [Esempio di elemento di associazione di individuazione](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)
