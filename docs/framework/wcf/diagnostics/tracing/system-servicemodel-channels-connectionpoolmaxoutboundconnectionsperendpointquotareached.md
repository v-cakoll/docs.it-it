---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 742e80a3115e8f8caa728e0d8c460ee8b964ddc9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84588717"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
Impossibile inserire il servizio del protocollo WS-AT in una transazione utilizzando il contesto di coordinamento fornito.  
  
## <a name="description"></a>Descrizione  
 Traccia eseguita quando l'integrazione di MSDTC in una transazione non riesce per un protocollo 2pc specificato.  Questa situazione può verificarsi se la transazione non esiste più, se l'integrazione non è più consentita o se sono già presenti troppi elenchi.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Controllare la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../index.md)
