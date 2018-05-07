---
title: Eccezioni di transazione
ms.date: 03/30/2017
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
ms.openlocfilehash: 85d8d043a5610743d6cbad4d950330ed4bedb502
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-exceptions"></a>Eccezioni di transazione
In questo argomento vengono elencate tutte le eccezioni generate dalla transazione di Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|Le informazioni sui criteri importate dai metadati specificano valori diversi per TransactionProtocol tra le operazioni. È supportato un solo TransactionProtocol per ogni endpoint.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete non può essere false, a meno che InstanceContextMode del servizio non sia PerSession. È stato trovato un errore nell'implementazione del contratto e dell'operazione specificati.|  
|SFxTransactionInvalidSetTransactionComplete|OperationContext.SetTransactionComplete può essere chiamato in un'operazione solo quando TransactionAutoComplete è impostato su false e TransactionScopeRequired è impostato su true. Questo scenario non è valido e la transazione corrente è stata terminata.|  
|TransactionFlowRequiredIssuedTokens|Per poter propagare una transazione, deve essere supportata anche la propagazione dei token rilasciati.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|La versione Trust configurata non supporta i token rilasciati. Utilizzare WSTrustFeb2005 o superiore.|
