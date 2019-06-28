---
title: 'Procedura: determinare la versione di individuazione di una richiesta del probe'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425260"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="b90ab-102">Procedura: determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="b90ab-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="b90ab-103">È possibile che un proxy di individuazione esponga più endpoint di individuazione usando versioni di individuazione diverse.</span><span class="sxs-lookup"><span data-stu-id="b90ab-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="b90ab-104">Quando un multicast UDP richiesta del Probe arriva al proxy, il proxy deve rispondere con un messaggio di eliminazione multicast.</span><span class="sxs-lookup"><span data-stu-id="b90ab-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="b90ab-105">Per eseguire questa operazione, sarebbe necessario conoscere la versione di individuazione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b90ab-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="b90ab-106">Per determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="b90ab-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="b90ab-107">Nel metodo che risponde a una richiesta del Probe (ad esempio <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) usare il metodo statico <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> proprietà da ricercare una <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b90ab-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="b90ab-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b90ab-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="b90ab-109">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="b90ab-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
