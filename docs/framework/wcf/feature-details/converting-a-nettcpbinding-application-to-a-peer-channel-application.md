---
title: Conversione di un'applicazione NetTcpBinding in un'applicazione del canale peer
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 930d5ed4f3adfb8e539cea5e84aa5e5c352e5018
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742906"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Conversione di un'applicazione NetTcpBinding in un'applicazione del canale peer
È possibile creare connessioni tra i client con [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] usando associazioni che descrivono i parametri della connessione. La conversione di un'applicazione [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per l'uso di connessioni peer-to-peer richiede un'associazione che supporti questa tecnologia quando si creano le connessioni client. Il canale peer fornisce un'associazione denominata <xref:System.ServiceModel.NetPeerTcpBinding>utilizzabile in modo analogo a <xref:System.ServiceModel.NetTcpBinding>. Le differenze principali includono la specifica di un servizio resolver e la definizione di impostazioni di sicurezza.  
  
 Se per un'applicazione si usano il resolver e le impostazioni di sicurezza predefinite, la conversione di un'applicazione client/server normale per l'uso del canale peer comporta la modifica del nome dell'associazione da "NetTcpBinding" a "NetPeerTcpBinding" nel file di configurazione dell'applicazione. Non è necessario modificare la codebase dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche
- [Creazione di un'applicazione del canale peer](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
