---
title: Modelli di transazione
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9efe8c6994cc80957b707bbae0885a3c5896f70a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-models"></a>Modelli di transazione
In questo argomento viene descritta la relazione tra i modelli di programmazione della transazione e i componenti dell'infrastruttura forniti da Microsoft.  
  
 Quando si utilizzano transazioni in Windows Communication Foundation (WCF), è importante comprendere che sta non selezionando tra modelli transazionali differenti ma piuttosto operando a livelli differenti di un modello integrato e coerenza.  
  
 Nelle sezioni seguenti vengono descritti i tre componenti primari della transazione.  
  
## <a name="windows-communication-foundation-transactions"></a>Transazioni di Windows Communication Foundation  
 Il supporto delle transazioni in WCF consente di che scrivere servizi transazionali. Inoltre, con il supporto per il protocollo WS-AtomicTransaction (WS-AT), le applicazioni possono propagare transazioni a servizi Web generati tramite WCF o tecnologia di terze parti.  
  
 In un servizio WCF o un'applicazione, le funzionalità delle transazioni WCF forniscono gli attributi e configurazione per specificare in modo dichiarativo come e quando l'infrastruttura deve creare, flusso e sincronizzare transazioni.  
  
## <a name="systemtransactions-transactions"></a>Transazioni System.Transactions  
 Lo spazio dei nomi <xref:System.Transactions> fornisce sia un modello di programmazione esplicito basato sulla classe <xref:System.Transactions.Transaction> sia un modello di programmazione implicito che utilizza la classe <xref:System.Transactions.TransactionScope>, in cui le transazioni vengono gestite automaticamente dall'infrastruttura.  
  
 Per ulteriori informazioni su come creare un'applicazione transazionale usando questi due modelli, vedere [scrittura di un'applicazione transazionale](http://go.microsoft.com/fwlink/?LinkId=94947).  
  
 In un servizio WCF o un'applicazione, <xref:System.Transactions> fornisce il modello di programmazione per la creazione di transazioni all'interno di un'applicazione client e per l'interazione esplicita con una transazione, se necessario, all'interno di un servizio.  
  
## <a name="msdtc-transactions"></a>Transazioni MSDTC  
 MSDTC (Microsoft Distributed Transaction Coordinator) è un gestore transazioni che fornisce supporto per transazioni distribuite.  
  
 Per altre informazioni, vedere la [di riferimento per programmatori di DTC](http://go.microsoft.com/fwlink/?LinkId=94948).  
  
 In un servizio WCF o un'applicazione, MSDTC fornisce l'infrastruttura per il coordinamento di transazioni create all'interno di un client o un servizio.
