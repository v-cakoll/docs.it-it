---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 2bd64263a2374c10a3514cbed75f9224542051dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33478946"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ ha rifiutato il messaggio.  
  
## <a name="description"></a>Descrizione  
 Questa traccia indica che è stato rifiutato un messaggio MSMQ.  
  
 I messaggi MSMQ possono essere rifiutati se Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli. Tali messaggi vengono definiti messaggi non elaborabili. Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`. Un messaggio respinto viene recapitato al mittente [recapitabili](http://go.microsoft.com/fwlink/?LinkID=99544).  
  
 Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.  
  
 Vedere [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) per ulteriori informazioni sul significato di un messaggio respinto in MSMQ.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)
