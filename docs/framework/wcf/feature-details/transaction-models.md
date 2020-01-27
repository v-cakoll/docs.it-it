---
title: Modelli di transazione
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: d6c78a5342bf19d19308352cddc241f436bfcb3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745330"
---
# <a name="transaction-models"></a>Modelli di transazione
In questo argomento viene descritta la relazione tra i modelli di programmazione della transazione e i componenti dell'infrastruttura forniti da Microsoft.  
  
 Quando si utilizzano le transazioni in Windows Communication Foundation (WCF), è importante comprendere che non si sta effettuando la selezione tra modelli transazionali diversi, ma si opera a livelli diversi di un modello integrato e coerente.  
  
 Nelle sezioni seguenti vengono descritti i tre componenti primari della transazione.  
  
## <a name="windows-communication-foundation-transactions"></a>Transazioni di Windows Communication Foundation  
 Il supporto delle transazioni in WCF consente di scrivere servizi transazionali. Inoltre, con il supporto per il protocollo WS-AtomicTransaction (WS-AT), le applicazioni possono fluire sulle transazioni ai servizi Web compilati utilizzando una tecnologia WCF o di terze parti.  
  
 In un'applicazione o un servizio WCF, le funzionalità delle transazioni WCF forniscono attributi e configurazione per specificare in modo dichiarativo come e quando l'infrastruttura deve creare, fluire e sincronizzare le transazioni.  
  
## <a name="systemtransactions-transactions"></a>Transazioni System.Transactions  
 Lo spazio dei nomi <xref:System.Transactions> fornisce sia un modello di programmazione esplicito basato sulla classe <xref:System.Transactions.Transaction> sia un modello di programmazione implicito che utilizza la classe <xref:System.Transactions.TransactionScope>, in cui le transazioni vengono gestite automaticamente dall'infrastruttura.  
  
 Per ulteriori informazioni su come creare un'applicazione transazionale utilizzando questi due modelli, vedere [scrittura di un'applicazione transazionale](https://go.microsoft.com/fwlink/?LinkId=94947).  
  
 In un'applicazione o un servizio WCF, <xref:System.Transactions> fornisce il modello di programmazione per la creazione di transazioni in un'applicazione client e per l'interazione esplicita con una transazione, quando necessario, all'interno di un servizio.  
  
## <a name="msdtc-transactions"></a>Transazioni MSDTC  
 MSDTC (Microsoft Distributed Transaction Coordinator) è un gestore transazioni che fornisce supporto per transazioni distribuite.  
  
 Per ulteriori informazioni, vedere il [riferimento per programmatori DTC](https://docs.microsoft.com/previous-versions/windows/desktop/ms686108(v=vs.85)).  
  
 In un'applicazione o un servizio WCF, MSDTC fornisce l'infrastruttura per il coordinamento delle transazioni create all'interno di un client o di un servizio.
