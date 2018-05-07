---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 0a28eec659b48d5add4c53bc8c16972892e65099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
Impossibile spostare o eliminare il messaggio.  
  
## <a name="description"></a>Descrizione  
 La traccia indica che si è verificato un errore durante il tentativo di spostare, eliminare o rifiutare un messaggio MSMQ.  
  
 I messaggi MSMQ vengono utilizzati da Windows Communication Foundation (WCF) (se utilizzato con NetMsmqBinding o MsmqIntegrationBinding). Questa traccia è correlata al valore scelto del `ReceiveErrorHandling` proprietà su NetMsmqBinding o MsmqIntegrationBinding.  
  
 Questa traccia non è indicativa di un errore di sistema complessivo. Tuttavia, indica che l'eliminazione del messaggio non elaborabile scelta ha avuto esito negativo per un messaggio. Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
