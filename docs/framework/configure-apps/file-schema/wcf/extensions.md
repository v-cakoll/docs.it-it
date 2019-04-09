---
title: <extensions>
ms.date: 03/30/2017
ms.assetid: bcfe5c44-04ef-4a20-96a5-90bfadf39623
ms.openlocfilehash: bb0df4535560a509d6e3511815196c126a95d0c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205251"
---
# <a name="extensions"></a><span data-ttu-id="8af7d-101">\<extensions></span><span class="sxs-lookup"><span data-stu-id="8af7d-101">\<extensions></span></span>
<span data-ttu-id="8af7d-102">Questo elemento di configurazione contiene una raccolta di elementi XML contenenti metadati personalizzati da pubblicare insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, Scope e ListenURI).</span><span class="sxs-lookup"><span data-stu-id="8af7d-102">This configuration element contains a collection of XML elements that contain custom metadata to be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span> <span data-ttu-id="8af7d-103">Di seguito viene riportato un esempio di utilizzo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8af7d-103">The following is an example of using this configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8af7d-104">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8af7d-104">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
