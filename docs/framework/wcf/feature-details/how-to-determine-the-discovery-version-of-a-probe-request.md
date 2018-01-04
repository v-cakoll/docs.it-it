---
title: 'Procedura: determinare la versione di individuazione di una richiesta del probe'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f51f48d6eefcc0f8ae5129526477d6e2a5b2385
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="35246-102">Procedura: determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="35246-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="35246-103">È possibile che un proxy di individuazione esponga più endpoint di individuazione usando versioni di individuazione diverse.</span><span class="sxs-lookup"><span data-stu-id="35246-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="35246-104">Quando una richiesta del probe multicast UDP arriva al proxy, il proxy deve rispondere con un messaggio di soppressione multicast.</span><span class="sxs-lookup"><span data-stu-id="35246-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="35246-105">Per eseguire questa operazione è necessario che conosca la versione di individuazione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="35246-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="35246-106">Per determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="35246-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1.  <span data-ttu-id="35246-107">Nel metodo che risponde a una richiesta del probe (ad esempio <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) usare la proprietà statica <xref:System.ServiceModel.OperationContext.Current%2A> per cercare un elemento <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="35246-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="35246-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35246-108">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [<span data-ttu-id="35246-109">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="35246-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [<span data-ttu-id="35246-110">Esempio relativo al proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="35246-110">Discovery Proxy Sample</span></span>](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)
