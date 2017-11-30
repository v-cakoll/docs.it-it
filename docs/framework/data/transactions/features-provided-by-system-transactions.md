---
title: "Funzionalità offerte da System.Transactions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be3e2fec5d6859b38ae149e50fd1fe82838d8e08
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="features-provided-by-systemtransactions"></a>Funzionalità offerte da System.Transactions
Questa sezione descrive come utilizzare le funzionalità fornite dallo spazio dei nomi <xref:System.Transactions> per scrivere applicazioni transazionali e gestori di risorse personalizzati. In particolare, questa sezione descrive come creare una transazione (locale o distribuita) e come integrarvi una o più risorse.  
  
## <a name="overview-of-systemtransactions"></a>Panoramica su System.Transactions  
 Grazie al supporto delle transazioni create in SQL Server, ADO.NET, MSMQ e Microsoft Distributed Transaction Coordinator (MSDTC), l'infrastruttura fornita dalle classi dello spazio dei nomi <xref:System.Transactions> rende la programmazione transazionale semplice ed efficiente. Lo spazio dei nomi <xref:System.Transactions> fornisce sia un modello di programmazione esplicito basato sulla classe <xref:System.Transactions.Transaction> sia un modello di programmazione implicito che utilizza la classe <xref:System.Transactions.TransactionScope>, in cui le transazioni vengono gestite automaticamente dall'infrastruttura. Per ulteriori informazioni su come creare un'applicazione transazionale utilizzando i due modelli, vedere [la scrittura di un'applicazione transazionale](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
 Lo spazio dei nomi <xref:System.Transactions> fornisce inoltre i tipi per implementare un gestore di risorse, ovvero un'applicazione che gestisce i dati permanenti o volatili utilizzati in una transazione e che collabora con la gestione transazioni per garantire atomicità e isolamento all'applicazione che utilizza tale transazione. La gestione transazioni fornita dall'infrastruttura <xref:System.Transactions> supporta le transazioni che coinvolgono più risorse volatili o una sola risorsa durevole. Per ulteriori informazioni sull'implementazione di un gestore di risorse, vedere [Implementing a Resource Manager](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).  
  
 Inoltre, quando un gestore di risorse durevole aggiuntivo si integra in una transazione, la gestione transazioni collabora con una gestione transazioni basata su disco quale DTC allo scopo di eseguire in modo trasparente l'escalation delle transazioni da locali a distribuite. Di base l'infrastruttura <xref:System.Transactions> utilizza due meccanismi per ottimizzare le prestazioni:  
  
-   Escalation dinamica, che garantisce che l'infrastruttura <xref:System.Transactions> ricorra al gestore MSDTC solo quando una transazione coinvolge più risorse distribuite. Per ulteriori informazioni sull'escalation dinamica, vedere [escalation della gestione transazioni](../../../../docs/framework/data/transactions/transaction-management-escalation.md) argomento.  
  
-   PSPE, che consente a una risorsa, ad esempio un database, di assumere la proprietà della transazione se è l'unica entità a parteciparvi. In seguito, se necessario, l'infrastruttura <xref:System.Transactions> può comunque eseguire l'escalation della gestione della transazione a MSDTC. Ciò consente di ridurre ulteriormente le probabilità di utilizzo del gestore MSDTC. PSPE sono illustrati in dettaglio nell'argomento[ottimizzazione utilizzando il Commit a fase singola e Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
 Lo spazio dei nomi <xref:System.Transactions> definisce tre livelli di attendibilità per restringere l'accesso ai tipi di risorse che espone: AllowPartiallyTrustedCallers, DistributedTransactionPermission e FullTrust. Per ulteriori informazioni sui diversi livelli di attendibilità, vedere [dei livelli di attendibilità di sicurezza di accesso alle risorse](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md).  
  
## <a name="in-this-section"></a>In questa sezione  
  
### <a name="writing-a-transactional-application"></a>Scrittura di un'applicazione transazionale  
 Lo spazio dei nomi <xref:System.Transactions> offre due modelli per creare le applicazioni di transazione. [Implementazione di una transazione implicita con ambito di transazione](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) viene descritto come <xref:System.Transactions> dello spazio dei nomi supporta la creazione di transazioni implicite utilizzando la <xref:System.Transactions.TransactionScope> classe.  
  
 [Implementazione di una transazione esplicita utilizzando CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md) viene descritto come <xref:System.Transactions> dello spazio dei nomi supporta la creazione di transazioni esplicite utilizzando la <xref:System.Transactions.CommittableTransaction> classe.  
  
 Per argomenti aggiuntivi che illustrano la scrittura di un'applicazione transazionale, vedere [la scrittura di un'applicazione transazionale](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
### <a name="implementing-a-resource-manager"></a>Implementazione di un gestore di risorse  
 Per implementare un gestore delle risorse che può partecipare in una transazione, vedere [Implementing a Resource Manager](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md). Questa sezione descrive l'integrazione di una risorsa, il commit di una transazione, il ripristino in caso di errore e i metodi di ottimizzazione.
