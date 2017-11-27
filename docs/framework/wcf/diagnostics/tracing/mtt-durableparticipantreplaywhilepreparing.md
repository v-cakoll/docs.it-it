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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a00a6a06fd5214f1f65bdb6369839d717078da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Il servizio del protocollo WS-AT ha ricevuto un messaggio Replay da un partecipante durevole che non ha risposto a Prepare. Di conseguenza la transazione è stata interrotta.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato se viene ricevuto un messaggio Replay mentre un partecipante durevole è ancora in preparazione. Si tratta di un messaggio non valido per lo stato e la transazione sarà interrotta.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 La ricezione di questo errore può indicare che un partecipante durevole (tra cui un gestore transazioni subordinato) ha effettuato il ripristino a seguito di un errore, ci sono tuttavia dubbi sul risultato della transazione e ne viene richiesto lo stato.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Utilizzo delle tracce per risolvere i problemi dell'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
