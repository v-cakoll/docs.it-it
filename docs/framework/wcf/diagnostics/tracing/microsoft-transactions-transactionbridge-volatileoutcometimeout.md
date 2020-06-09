---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: dd2a0b67ec140aa2e6fe1abad8e85c0206abd8ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579021"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a>Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
Il servizio del protocollo WS-AT è andato in timeout durante l'attesa di una risposta a un messaggio in uscita da parte di un partecipante volatile. Il risultato della transazione può essere incerto se il partecipante risponde.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato quando un partecipante volatile ha deciso di eseguire il commit o di interrompere ma non ha risposto a un commit o a una richiesta di rollback entro un determinato periodo di tempo.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Assicurarsi che tutti i partecipanti volatili siano in grado di rispondere entro il periodo di tempo specificato. Il periodo di tempo predefinito è 180 secondi.  Se è insufficiente, aumentare il criterio del timer `VolatileOutcomeDelay` per WS-AT.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../index.md)
