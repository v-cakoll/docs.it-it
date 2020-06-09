---
title: 'Procedura: determinare la versione di individuazione di una richiesta del probe'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 2b7e42714ae1d16a84bcb6f0fc79cf5b376a7a16
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595414"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="b8d6b-102">Procedura: determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="b8d6b-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="b8d6b-103">È possibile che un proxy di individuazione esponga più endpoint di individuazione usando versioni di individuazione diverse.</span><span class="sxs-lookup"><span data-stu-id="b8d6b-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="b8d6b-104">Quando una richiesta del probe multicast UDP arriva al proxy, il proxy deve rispondere con un messaggio di eliminazione multicast.</span><span class="sxs-lookup"><span data-stu-id="b8d6b-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="b8d6b-105">Per eseguire questa operazione, è necessario che conosca la versione di individuazione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b8d6b-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="b8d6b-106">Per determinare la versione di individuazione di una richiesta del probe</span><span class="sxs-lookup"><span data-stu-id="b8d6b-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="b8d6b-107">Nel metodo che risponde a una richiesta di probe, ad esempio <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> , usare la <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> proprietà statica per cercare un oggetto <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b8d6b-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="b8d6b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8d6b-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="b8d6b-109">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="b8d6b-109">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)
