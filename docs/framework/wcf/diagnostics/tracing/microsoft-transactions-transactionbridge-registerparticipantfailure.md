---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: b94c017f6ed3a76a6bc5ed2cb970877ad18ef9ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610422"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a>Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
Servizio del protocollo WS-AT: impossibile registrare un partecipante per un protocollo di controllo.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato se MSDTC rileva una richiesta di registrazione non valida. Può essere causato da più richieste di registrazione di completamento e da errori interni.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Non tentare la registrazione di completamento più di una volta.  Controllare inoltre la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.  
  
## <a name="see-also"></a>Vedere anche
- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
