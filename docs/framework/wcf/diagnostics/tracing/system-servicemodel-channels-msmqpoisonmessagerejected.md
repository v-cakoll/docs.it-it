---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 562399c1d45dc73c7c88bd165e9f95ee1bcfa19d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125082"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
Messaggio non elaborabile rifiutato.  
  
## <a name="description"></a>Descrizione  
 La traccia indica che è stato rilevato e successivamente rifiutato un messaggio non elaborabile. Ciò accade quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`. Un messaggio rifiutato viene recapitato al mittente [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).  
  
 Visualizzare [dei messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkId=99546) per altri dettagli su cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato. Visualizzare [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) per altri dettagli sul significato di un messaggio rifiutato in MSMQ.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkId=99546)
- [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548)
