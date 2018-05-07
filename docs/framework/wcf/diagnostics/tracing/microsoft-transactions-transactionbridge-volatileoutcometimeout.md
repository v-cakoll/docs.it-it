---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: b64f61d25c3be87019151cbf560becd3384ec182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a>Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
Il servizio del protocollo WS-AT è andato in timeout durante l'attesa di una risposta a un messaggio in uscita da parte di un partecipante volatile. Il risultato della transazione può essere incerto se il partecipante risponde.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato quando un partecipante volatile ha deciso di eseguire il commit o di interrompere ma non ha risposto a un commit o a una richiesta di rollback entro un determinato periodo di tempo.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Assicurarsi che tutti i partecipanti volatili siano in grado di rispondere entro il periodo di tempo specificato. Il periodo di tempo predefinito è 180 secondi.  Se è insufficiente, aumentare il criterio del timer `VolatileOutcomeDelay` per WS-AT.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
