---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be874cc0b3fb15f80bb5cd6b97174b515703385c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a>Microsoft.Transactions.TransactionBridge.CommitMessageRetry
Tentativo di invio di un messaggio Commit a un partecipante che non risponde.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Commit a un partecipante subordinato perché non ha ricevuto una risposta entro un determinato periodo di tempo.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.  La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi. Entrambi i problemi ridurranno drasticamente la velocità effettiva delle transazioni all'interno del sistema.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Utilizzo delle tracce per risolvere i problemi dell'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
