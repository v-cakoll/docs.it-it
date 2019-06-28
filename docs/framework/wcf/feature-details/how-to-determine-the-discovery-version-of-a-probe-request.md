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
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Procedura: determinare la versione di individuazione di una richiesta del probe

È possibile che un proxy di individuazione esponga più endpoint di individuazione usando versioni di individuazione diverse. Quando un multicast UDP richiesta del Probe arriva al proxy, il proxy deve rispondere con un messaggio di eliminazione multicast. Per eseguire questa operazione, sarebbe necessario conoscere la versione di individuazione della richiesta.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Per determinare la versione di individuazione di una richiesta del probe

Nel metodo che risponde a una richiesta del Probe (ad esempio <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) usare il metodo statico <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> proprietà da ricercare una <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, come illustrato nel codice seguente.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementazione di un proxy di individuazione](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
