---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: ab1c2c8afe3a66536810a614cc6deac12519cb9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599633"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a>Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
Il servizio del protocollo WS-AT ha ricevuto un messaggio Prepared o Replay da un partecipante volatile non riconosciuto. Al partecipante è stato restituito un errore che dichiara che il risultato della transazione è in dubbio.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato quando il gestore transazioni locale riceve un messaggio Prepared o Replay da un elenco volatile che ha già dimenticato.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Analizzare le cause potenziali di ritardo dei messaggi provenienti dal partecipante volatile.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../index.md)
