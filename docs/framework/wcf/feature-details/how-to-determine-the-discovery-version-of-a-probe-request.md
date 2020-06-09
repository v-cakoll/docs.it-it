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
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Procedura: determinare la versione di individuazione di una richiesta del probe

È possibile che un proxy di individuazione esponga più endpoint di individuazione usando versioni di individuazione diverse. Quando una richiesta del probe multicast UDP arriva al proxy, il proxy deve rispondere con un messaggio di eliminazione multicast. Per eseguire questa operazione, è necessario che conosca la versione di individuazione della richiesta.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Per determinare la versione di individuazione di una richiesta del probe

Nel metodo che risponde a una richiesta di probe, ad esempio <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> , usare la <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> proprietà statica per cercare un oggetto <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , come illustrato nel codice seguente.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementazione di un proxy di individuazione](implementing-a-discovery-proxy.md)
