---
title: 'Procedura: determinare la versione di individuazione di una richiesta del probe'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 6bd112be311eb9397ad89801be5358d67c7499fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332274"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="b5b66-102">Procedura: determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="b5b66-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="b5b66-103">È possibile che un proxy di individuazione esponga più endpoint di individuazione usando versioni di individuazione diverse.</span><span class="sxs-lookup"><span data-stu-id="b5b66-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="b5b66-104">Quando una richiesta del probe multicast UDP arriva al proxy, il proxy deve rispondere con un messaggio di soppressione multicast.</span><span class="sxs-lookup"><span data-stu-id="b5b66-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="b5b66-105">Per eseguire questa operazione è necessario che conosca la versione di individuazione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b5b66-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="b5b66-106">Per determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="b5b66-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1. <span data-ttu-id="b5b66-107">Nel metodo che risponde a una richiesta del probe (ad esempio <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) usare la proprietà statica <xref:System.ServiceModel.OperationContext.Current%2A> per cercare un elemento <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b5b66-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b5b66-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5b66-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="b5b66-109">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="b5b66-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
