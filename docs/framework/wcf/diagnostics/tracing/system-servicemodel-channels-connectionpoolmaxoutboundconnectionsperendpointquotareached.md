---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 93c96d94aaeddeb7e7b04ea80645b8de95b0343e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143325"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
Impossibile inserire il servizio del protocollo WS-AT in una transazione utilizzando il contesto di coordinamento fornito.  
  
## <a name="description"></a>Descrizione  
 Traccia eseguita quando l'integrazione di MSDTC in una transazione non riesce per un protocollo 2pc specificato.  Questa situazione può verificarsi se la transazione non esiste più, se l'integrazione non è più consentita o se sono già presenti troppi elenchi.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Controllare la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
