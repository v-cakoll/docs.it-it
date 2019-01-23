---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 6218948e89288e76034d7c3f032f3c585e286c3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570538"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ ha rilasciato il messaggio.  
  
## <a name="description"></a>Descrizione  
 La traccia indica che è stato eliminato un messaggio MSMQ. I messaggi MSMQ possono essere eliminati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non riesce a elaborarli. Tali messaggi vengono definiti messaggi non elaborabili.  
  
 Un messaggio non elaborabile viene rilasciato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Drop`. Un messaggio eliminato viene rimosso dalla coda e non è più recuperabile.  
  
 Visualizzare [dei messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkID=99546) per altri dettagli su cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato.  
  
## <a name="see-also"></a>Vedere anche
- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkID=99546)
