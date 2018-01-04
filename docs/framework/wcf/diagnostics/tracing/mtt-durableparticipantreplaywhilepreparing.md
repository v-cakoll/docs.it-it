---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 375bb5902640ba0816217aec161834d79e9765ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Il servizio del protocollo WS-AT ha ricevuto un messaggio Replay da un partecipante durevole che non ha risposto a Prepare. Di conseguenza la transazione è stata interrotta.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato se viene ricevuto un messaggio Replay mentre un partecipante durevole è ancora in preparazione. Si tratta di un messaggio non valido per lo stato e la transazione sarà interrotta.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 La ricezione di questo errore può indicare che un partecipante durevole (tra cui un gestore transazioni subordinato) ha effettuato il ripristino a seguito di un errore, ci sono tuttavia dubbi sul risultato della transazione e ne viene richiesto lo stato.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
