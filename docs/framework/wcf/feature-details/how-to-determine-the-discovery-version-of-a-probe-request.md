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
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Procedura: determinare la versione di individuazione di una richiesta del probe
È possibile che un proxy di individuazione esponga più endpoint di individuazione usando versioni di individuazione diverse. Quando una richiesta del probe multicast UDP arriva al proxy, il proxy deve rispondere con un messaggio di soppressione multicast. Per eseguire questa operazione è necessario che conosca la versione di individuazione della richiesta.  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Per determinare la versione di individuazione di una richiesta del probe  
  
1. Nel metodo che risponde a una richiesta del probe (ad esempio <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) usare la proprietà statica <xref:System.ServiceModel.OperationContext.Current%2A> per cercare un elemento <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> come mostrato nel codice seguente.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementazione di un proxy di individuazione](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
