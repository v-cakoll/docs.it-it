---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: c388a9dc3569e20639de09abc5f4941b73c561ad
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578051"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ ha rifiutato il messaggio.  
  
## <a name="description"></a>Descrizione  
 Questa traccia indica che è stato rifiutato un messaggio MSMQ.  
  
 I messaggi MSMQ possono essere rifiutati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli. Tali messaggi vengono definiti messaggi non elaborabili. Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`. Un messaggio rifiutato viene restituito alla coda dei messaggi non [recapitabili](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)del mittente.  
  
 Per ulteriori informazioni sul momento in cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere [gestione di messaggi non elaborabili](../../feature-details/poison-message-handling.md).  
  
 Per ulteriori informazioni sul significato di un messaggio rifiutato in MSMQ, vedere [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../index.md)
- [Gestione dei messaggi non elaborabili](../../feature-details/poison-message-handling.md)
- [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))
