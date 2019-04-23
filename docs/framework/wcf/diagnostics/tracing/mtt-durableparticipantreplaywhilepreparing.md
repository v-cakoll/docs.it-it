---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: f5d74d73cc43b500d3920ca03905f4eb7543619a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075535"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Il servizio del protocollo WS-AT ha ricevuto un messaggio Replay da un partecipante durevole che non ha risposto a Prepare. Di conseguenza la transazione è stata interrotta.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato se viene ricevuto un messaggio Replay mentre un partecipante durevole è ancora in preparazione. Si tratta di un messaggio non valido per lo stato e la transazione sarà interrotta.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 La ricezione di questo errore può indicare che un partecipante durevole (tra cui un gestore transazioni subordinato) ha effettuato il ripristino a seguito di un errore, ci sono tuttavia dubbi sul risultato della transazione e ne viene richiesto lo stato.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
