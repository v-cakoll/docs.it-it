---
title: Transazioni e concorrenza
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 80db92f94f8cb523c3b8f9d0d08bbcb6b33c2fbe
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="transactions-and-concurrency"></a>Transazioni e concorrenza
Una transazione è costituita da un singolo comando o da un gruppo di comandi che vengono eseguiti come un pacchetto. Le transazioni consentono di combinare più operazioni in un'unica unità di lavoro. Se si verifica un problema in un determinato punto della transazione, sarà possibile annullare tutti gli aggiornamenti ripristinando la condizione antecedente all'inizio della transazione.  
  
 Per poter garantire la coerenza dei dati, una transazione deve essere conforme alle proprietà ACID, ovvero atomicità, coerenza, isolamento e durabilità. La maggioranza dei sistemi di database relazionale, ad esempio Microsoft SQL Server, supportano le transazioni fornendo funzionalità di blocco, di registrazione e di gestione delle transazioni volta che un'applicazione client esegue un'operazione di aggiornamento, inserimento o eliminazione.  
  
> [!NOTE]
>  Le transazioni che implicano l'uso di più risorse possono abbassare la concorrenza se i blocchi vengono mantenuti troppo a lungo. Mantenere pertanto le transazioni per il minor tempo possibile.  
  
 Se una transazione implica l'uso di più tabelle nello stesso database o server, è spesso preferibile usare transazioni esplicite nelle stored procedure. È possibile creare transazioni in stored procedure SQL Server usando le istruzioni Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` e `ROLLBACK TRANSACTION`. Per altre informazioni, vedere la documentazione online di SQL Server.  
  
 Le transazioni che interessano i gestori di risorse diversi, ad esempio una transazione tra SQL Server e Oracle, è necessaria una transazione distribuita.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Transazioni locali](../../../../docs/framework/data/adonet/local-transactions.md)  
 Viene illustrato come eseguire transazioni su un database.  
  
 [Transazioni distribuite](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 Viene descritto come eseguire transazioni distribuite in ADO.NET.  
  
 [Integrazione di System.Transactions con SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 Viene descritto <xref:System.Transactions> integrazione con SQL Server per l'utilizzo di transazioni distribuite.  
  
 [Concorrenza ottimistica](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 Vengono descritte la concorrenza ottimistica e la concorrenza pessimistica e come è possibile verificare le violazioni della concorrenza.  
  
## <a name="see-also"></a>Vedere anche  
 [Nozioni fondamentali sulle transazioni](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [Connessione a un'origine dati](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
