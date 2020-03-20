---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674769"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ ha rifiutato il messaggio.  
  
## <a name="description"></a>Descrizione  
 Questa traccia indica che è stato rifiutato un messaggio MSMQ.  
  
 I messaggi MSMQ possono essere rifiutati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli. Tali messaggi vengono definiti messaggi non elaborabili. Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`. Un messaggio rifiutato viene recapitato alla coda di [messaggi non recapitabili](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)del mittente.  
  
 Per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere Gestione dei [messaggi non elaborabili](../../feature-details/poison-message-handling.md).  
  
 Per ulteriori informazioni sul significato di un messaggio rifiutato in MSMQ, vedere [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Gestione dei messaggi non elaborabili](../../feature-details/poison-message-handling.md)
- [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))
