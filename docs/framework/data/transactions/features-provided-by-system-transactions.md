---
title: Funzionalità offerte da System.Transactions
ms.date: 03/30/2017
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
ms.openlocfilehash: 6fc20f8249f37f69689fb3fc6b3144792badad3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793692"
---
# <a name="features-provided-by-systemtransactions"></a>Funzionalità offerte da System.Transactions
Questa sezione descrive come utilizzare le funzionalità fornite dallo spazio dei nomi <xref:System.Transactions> per scrivere applicazioni transazionali e gestori di risorse personalizzati. In particolare, questa sezione descrive come creare una transazione (locale o distribuita) e come integrarvi una o più risorse.  
  
## <a name="overview-of-systemtransactions"></a>Panoramica su System.Transactions  
 Grazie al supporto delle transazioni create in SQL Server, ADO.NET, MSMQ e Microsoft Distributed Transaction Coordinator (MSDTC), l'infrastruttura fornita dalle classi dello spazio dei nomi <xref:System.Transactions> rende la programmazione transazionale semplice ed efficiente. Lo spazio dei nomi <xref:System.Transactions> fornisce sia un modello di programmazione esplicito basato sulla classe <xref:System.Transactions.Transaction> sia un modello di programmazione implicito che utilizza la classe <xref:System.Transactions.TransactionScope>, in cui le transazioni vengono gestite automaticamente dall'infrastruttura. Per altre informazioni su come creare un'applicazione transazionale utilizzando questi due modelli, vedere [scrittura di un'applicazione transazionale](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
 Lo spazio dei nomi <xref:System.Transactions> fornisce inoltre i tipi per implementare un gestore di risorse, ovvero un'applicazione che gestisce i dati permanenti o volatili utilizzati in una transazione e che collabora con la gestione transazioni per garantire atomicità e isolamento all'applicazione che utilizza tale transazione. La gestione transazioni fornita dall'infrastruttura <xref:System.Transactions> supporta le transazioni che coinvolgono più risorse volatili o una sola risorsa durevole. Per altre informazioni sull'implementazione di un gestore di risorse, vedere [implementazione di un gestore di risorse](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).  
  
 Inoltre, quando un gestore di risorse durevole aggiuntivo si integra in una transazione, la gestione transazioni collabora con una gestione transazioni basata su disco quale DTC allo scopo di eseguire in modo trasparente l'escalation delle transazioni da locali a distribuite. Di base l'infrastruttura <xref:System.Transactions> utilizza due meccanismi per ottimizzare le prestazioni:  
  
- Escalation dinamica, che garantisce che l'infrastruttura <xref:System.Transactions> ricorra al gestore MSDTC solo quando una transazione coinvolge più risorse distribuite. Per ulteriori informazioni sull'escalation dinamica, visualizzare [Escalation della gestione transazioni](../../../../docs/framework/data/transactions/transaction-management-escalation.md) argomento.  
  
- PSPE, che consente a una risorsa, ad esempio un database, di assumere la proprietà della transazione se è l'unica entità a parteciparvi. In seguito, se necessario, l'infrastruttura <xref:System.Transactions> può comunque eseguire l'escalation della gestione della transazione a MSDTC. Ciò consente di ridurre ulteriormente le probabilità di utilizzo del gestore MSDTC. Meccanismo PSPE è descritto in dettaglio nell'argomento[ottimizzazione mediante Commit monofase e notifica monofase promuovibile](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
 Lo spazio dei nomi <xref:System.Transactions> definisce tre livelli di attendibilità per restringere l'accesso ai tipi di risorse che espone: AllowPartiallyTrustedCallers, DistributedTransactionPermission e FullTrust. Per altre informazioni sui diversi livelli di attendibilità, vedere [livelli di attendibilità di sicurezza nell'accesso alle risorse](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
### <a name="writing-a-transactional-application"></a>Scrittura di un'applicazione transazionale  
 Lo spazio dei nomi <xref:System.Transactions> offre due modelli per creare le applicazioni di transazione. [Implementazione di una transazione implicita utilizzando l'ambito di transazione](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) descrive come il <xref:System.Transactions> dello spazio dei nomi supporta la creazione di transazioni implicite mediante la <xref:System.Transactions.TransactionScope> classe.  
  
 [Implementazione di una transazione esplicita utilizzando CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md) descrive come il <xref:System.Transactions> dello spazio dei nomi supporta la creazione di transazioni esplicite mediante il <xref:System.Transactions.CommittableTransaction> classe.  
  
 Per ulteriori informazioni sulla scrittura di un'applicazione transazionale, vedere [scrittura di un'applicazione transazionale](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
### <a name="implementing-a-resource-manager"></a>Implementazione di un gestore di risorse  
 Per implementare un gestore di risorse che può partecipare in una transazione, vedere [implementazione di un gestore di risorse](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md). Questa sezione descrive l'integrazione di una risorsa, il commit di una transazione, il ripristino in caso di errore e i metodi di ottimizzazione.
