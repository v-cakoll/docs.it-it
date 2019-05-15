---
title: Conversione di un'applicazione NetTcpBinding in un'applicazione del canale peer
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: b89afbe59b73288ba357fa55ec5d55c1fb18352b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582793"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Conversione di un'applicazione NetTcpBinding in un'applicazione del canale peer
È possibile creare connessioni tra i client con [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] usando associazioni che descrivono i parametri della connessione. Conversione di un'applicazione .NET Framework di usare connessioni peer-to-peer richiede un'associazione che supporta tale tecnologia quando si effettuano le connessioni client. Il canale peer fornisce un'associazione denominata <xref:System.ServiceModel.NetPeerTcpBinding>utilizzabile in modo analogo a <xref:System.ServiceModel.NetTcpBinding>. Le differenze principali includono la specifica di un servizio resolver e la definizione di impostazioni di sicurezza.  
  
 Se per un'applicazione si usano il resolver e le impostazioni di sicurezza predefinite, la conversione di un'applicazione client/server normale per l'uso del canale peer comporta la modifica del nome dell'associazione da "NetTcpBinding" a "NetPeerTcpBinding" nel file di configurazione dell'applicazione. Non è necessario modificare la codebase dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di un'applicazione del canale peer](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
