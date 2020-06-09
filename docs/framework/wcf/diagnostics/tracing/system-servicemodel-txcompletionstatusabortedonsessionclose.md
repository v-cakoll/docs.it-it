---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: c398fc52d5924c033500b95924f9287b43cc9e9d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576603"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
La transazione specificata è stata interrotta perché non era stata completata alla chiusura della sessione e TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute era impostato su False.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato se la sessione attiva corrente è stata chiusa prima del completamento della transazione e se TransactionAutoCompleteOnSessionClose è impostato su `false`.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Questa traccia indica un bug potenziale dell'applicazione che deve essere esaminato.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../index.md)
