---
title: <extensions>
ms.date: 03/30/2017
ms.assetid: bcfe5c44-04ef-4a20-96a5-90bfadf39623
ms.openlocfilehash: feac4999438a67043899eef98bb8b49644ee30d9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270017"
---
# <a name="extensions"></a><span data-ttu-id="553f7-101">\<extensions></span><span class="sxs-lookup"><span data-stu-id="553f7-101">\<extensions></span></span>
<span data-ttu-id="553f7-102">Questo elemento di configurazione contiene una raccolta di elementi XML contenenti metadati personalizzati da pubblicare insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, Scope e ListenURI).</span><span class="sxs-lookup"><span data-stu-id="553f7-102">This configuration element contains a collection of XML elements that contain custom metadata to be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span> <span data-ttu-id="553f7-103">Di seguito viene riportato un esempio di utilizzo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="553f7-103">The following is an example of using this configuration element.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enable="true">
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="553f7-104">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="553f7-104">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
