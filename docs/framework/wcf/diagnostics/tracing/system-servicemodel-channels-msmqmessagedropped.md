---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674803"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ ha rilasciato il messaggio.  
  
## <a name="description"></a>Descrizione  
 La traccia indica che è stato eliminato un messaggio MSMQ. I messaggi MSMQ possono essere eliminati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli. Tali messaggi vengono definiti messaggi non elaborabili.  
  
 Un messaggio non elaborabile viene rilasciato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Drop`. Un messaggio eliminato viene rimosso dalla coda e non è più recuperabile.  
  
 Per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere Gestione dei [messaggi non elaborabili](../../feature-details/poison-message-handling.md).  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Gestione dei messaggi non elaborabili](../../feature-details/poison-message-handling.md)
