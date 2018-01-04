---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1385995165308cb1c2f2e6bd6c8a800a88b7b79e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
