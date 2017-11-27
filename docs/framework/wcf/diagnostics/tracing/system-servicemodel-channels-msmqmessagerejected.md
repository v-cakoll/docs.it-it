---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecbbd8bc0e798388f994432ea2d3f25396f7de97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ ha rifiutato il messaggio.  
  
## <a name="description"></a>Descrizione  
 Questa traccia indica che è stato rifiutato un messaggio MSMQ.  
  
 I messaggi MSMQ possono essere rifiutati quando [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli. Tali messaggi vengono definiti messaggi non elaborabili. Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`. Un messaggio respinto viene recapitato al mittente [recapitabili](http://go.microsoft.com/fwlink/?LinkID=99544).  
  
 Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.  
  
 Vedere [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) per ulteriori informazioni sul significato di un messaggio respinto in MSMQ.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Utilizzo delle tracce per risolvere i problemi dell'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)
