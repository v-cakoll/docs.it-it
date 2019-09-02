---
title: Scrittura di un'applicazione transazionale
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 318771c83a5b7ebc0f3fb2bb8c59240269a2dea9
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205819"
---
# <a name="writing-a-transactional-application"></a>Scrittura di un'applicazione transazionale
I programmatori di applicazioni transazionali possono utilizzare i due modelli di programmazione forniti dallo spazio dei nomi <xref:System.Transactions> per creare una transazione. È possibile utilizzare il modello di programmazione esplicita utilizzando la <xref:System.Transactions.Transaction> classe o il modello di programmazione implicito in cui le transazioni vengono gestite automaticamente dall'infrastruttura, utilizzando la <xref:System.Transactions.TransactionScope> classe. Si consiglia di utilizzare il modello di transazione implicita per lo sviluppo. Per ulteriori informazioni sull'utilizzo di un ambito di transazione, vedere l'argomento [implementazione di una transazione implicita mediante ambito di transazione](implementing-an-implicit-transaction-using-transaction-scope.md) .  
  
 Entrambi i modelli supportano il commit delle transazioni quando il programma raggiunge uno stato coerente. Se il commit riesce, il sistema esegue il commit permanente della transazione. Se il commit non riesce, la transazione viene interrotta. Se risulta impossibile completare correttamente una transazione, il programma dell'applicazione tenta di interromperla e quindi di annullarne gli effetti.  
  
## <a name="in-this-section"></a>In questa sezione  
  
### <a name="creating-a-transaction"></a>Creazione di una transazione  
 Lo spazio dei nomi <xref:System.Transactions> offre due modelli per creare una transazione. Questi modelli vengono descritti negli argomenti seguenti.  
  
 [Implementazione di una transazione implicita utilizzando l'ambito di transazione](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Descrive il modo in cui lo spazio dei nomi <xref:System.Transactions> supporta la creazione di transazioni implicite mediante la classe <xref:System.Transactions.TransactionScope>.  
  
 [Implementazione di una transazione esplicita utilizzando CommittableTransaction](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Descrive il modo in cui lo spazio dei nomi <xref:System.Transactions> supporta la creazione di transazioni esplicite mediante la classe <xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Gestione dell'escalation delle transazioni  
 Quando una transazione deve accedere a una risorsa contenuta in un altro dominio applicazione oppure quando si desidera integrare le risorse in un altro gestore di risorse durevoli, il sistema esegue automaticamente l'escalation di tale transazione in modo che venga gestita dal gestore MSDTC. L'escalation delle transazioni è analizzata nell'argomento relativo all'escalation della [gestione delle transazioni](transaction-management-escalation.md) .  
  
### <a name="concurrency"></a>Concorrenza  
 L'argomento [gestione della concorrenza con DependentTransaction](managing-concurrency-with-dependenttransaction.md) dimostra come è possibile ottenere la concorrenza tra le attività asincrone usando la <xref:System.Transactions.DependentTransaction> classe.  
  
### <a name="com-interop"></a>Interoperabilità COM+  
 Nell'argomento [interoperabilità con le transazioni di Enterprise Services e com+](interoperability-with-enterprise-services-and-com-transactions.md) viene illustrato come è possibile fare in modo che le transazioni distribuite interagiscano con le transazioni com+.  
  
### <a name="diagnostics"></a>Diagnostica  
 [Tracce diagnostiche](diagnostic-traces.md) descrive come è possibile utilizzare i codici di traccia generati dall' <xref:System.Transactions> infrastruttura di per risolvere gli errori nelle applicazioni.  
  
### <a name="working-within-aspnet"></a>Utilizzo delle funzionalità all'interno di ASP.NET  
 L'argomento [using System. Transactions in ASP.NET](using-system-transactions-in-aspnet.md) descrive come è possibile <xref:System.Transactions> usare correttamente all'interno di un'applicazione ASP.NET.
