---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02831a83103f5a6bd83fc2aed474245bdeda65d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a>Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
Servizio del protocollo WS-AT: impossibile registrare un partecipante per un protocollo di controllo.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato se MSDTC rileva una richiesta di registrazione non valida. Può essere causato da più richieste di registrazione di completamento e da errori interni.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Non tentare la registrazione di completamento più di una volta.  Controllare inoltre la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
