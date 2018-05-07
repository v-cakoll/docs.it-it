---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 7dc1e4120caae7c4a592067f5e77ed4f56e82e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
Messaggio non elaborabile rifiutato.  
  
## <a name="description"></a>Descrizione  
 La traccia indica che è stato rilevato e successivamente rifiutato un messaggio non elaborabile. Ciò accade quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`. Un messaggio respinto viene recapitato al mittente [recapitabili](http://go.microsoft.com/fwlink/?LinkId=99544).  
  
 Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkId=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato. Vedere [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) per ulteriori informazioni sul significato di un messaggio respinto in MSMQ.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)
