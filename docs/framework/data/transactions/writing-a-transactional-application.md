---
title: Scrittura di un'applicazione transazionale
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 048df434ff0ada2ab5f8c7473913f6c34c05d1a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793491"
---
# <a name="writing-a-transactional-application"></a>Scrittura di un'applicazione transazionale
I programmatori di applicazioni transazionali possono utilizzare i due modelli di programmazione forniti dallo spazio dei nomi <xref:System.Transactions> per creare una transazione. È possibile usare il modello di programmazione esplicito tramite il <xref:System.Transactions.Transaction> classe o il modello di programmazione implicito in cui le transazioni vengono gestite automaticamente dall'infrastruttura, usando il <xref:System.Transactions.TransactionScope> classe. È consigliabile usare il modello di esecuzione implicita delle transazioni per lo sviluppo. È possibile trovare altre informazioni su come usare un ambito di transazione nel [implementazione di una transazione implicita utilizzando l'ambito di transazione](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) argomento.  
  
 Entrambi i modelli supportano il commit delle transazioni quando il programma raggiunge uno stato coerente. Se il commit riesce, il sistema esegue il commit permanente della transazione. Se il commit non riesce, la transazione viene interrotta. Se risulta impossibile completare correttamente una transazione, il programma dell'applicazione tenta di interromperla e quindi di annullarne gli effetti.  
  
## <a name="in-this-section"></a>In questa sezione  
  
### <a name="creating-a-transaction"></a>Creazione di una transazione  
 Lo spazio dei nomi <xref:System.Transactions> offre due modelli per creare una transazione. Questi modelli vengono descritti negli argomenti seguenti.  
  
 [Implementazione di una transazione implicita utilizzando l'ambito di transazione](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Descrive il modo in cui lo spazio dei nomi <xref:System.Transactions> supporta la creazione di transazioni implicite mediante la classe <xref:System.Transactions.TransactionScope>.  
  
 [Implementazione di una transazione esplicita utilizzando CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Descrive il modo in cui lo spazio dei nomi <xref:System.Transactions> supporta la creazione di transazioni esplicite mediante la classe <xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Gestione dell'escalation delle transazioni  
 Quando una transazione deve accedere a una risorsa contenuta in un altro dominio applicazione oppure quando si desidera integrare le risorse in un altro gestore di risorse durevoli, il sistema esegue automaticamente l'escalation di tale transazione in modo che venga gestita dal gestore MSDTC. Escalation delle transazioni viene trattato nel [Escalation della gestione transazioni](../../../../docs/framework/data/transactions/transaction-management-escalation.md) argomento.  
  
### <a name="concurrency"></a>Concorrenza  
 L'argomento [gestione della concorrenza con DependentTransaction](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) illustra come è possibile ottenere la concorrenza fra attività asincrone usando il <xref:System.Transactions.DependentTransaction> classe.  
  
### <a name="com-interop"></a>Interoperabilità COM+  
 L'argomento [interoperabilità con transazioni COM+ ed Enterprise Services](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) viene illustrato come è possibile apportare le transazioni distribuite interagiscono con transazioni COM+.  
  
### <a name="diagnostics"></a>Diagnostica  
 [Le tracce diagnostiche](../../../../docs/framework/data/transactions/diagnostic-traces.md) descrive come è possibile usare i codici di traccia generati dal <xref:System.Transactions> infrastruttura per risolvere gli errori nelle applicazioni.  
  
### <a name="working-within-aspnet"></a>Utilizzo delle funzionalità all'interno di ASP.NET  
 Il [utilizzando System. Transactions in ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) argomento viene descritto come è possibile utilizzare correttamente <xref:System.Transactions> all'interno di un'applicazione ASP.NET.
