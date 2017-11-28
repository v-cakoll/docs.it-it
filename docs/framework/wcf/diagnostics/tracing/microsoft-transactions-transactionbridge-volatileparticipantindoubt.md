---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b497231326c640b93b96500df39732104e0f0c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a>Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
Il servizio del protocollo WS-AT ha ricevuto un messaggio Prepared o Replay da un partecipante volatile non riconosciuto. Al partecipante è stato restituito un errore che dichiara che il risultato della transazione è in dubbio.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato quando il gestore transazioni locale riceve un messaggio Prepared o Replay da un elenco volatile che ha già dimenticato.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Analizzare le cause potenziali di ritardo dei messaggi provenienti dal partecipante volatile.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Utilizzo delle tracce per risolvere i problemi dell'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
