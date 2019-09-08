---
title: Transazioni e concorrenza
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: 837fe6c42d64f7416dbd895e56a38d1a409e567a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791311"
---
# <a name="transactions-and-concurrency"></a>Transazioni e concorrenza
Una transazione è costituita da un singolo comando o da un gruppo di comandi che vengono eseguiti come un pacchetto. Le transazioni consentono di combinare più operazioni in un'unica unità di lavoro. Se si verifica un problema in un determinato punto della transazione, sarà possibile annullare tutti gli aggiornamenti ripristinando la condizione antecedente all'inizio della transazione.  
  
 Per poter garantire la coerenza dei dati, una transazione deve essere conforme alle proprietà ACID, ovvero atomicità, coerenza, isolamento e durabilità. La maggior parte dei sistemi di database relazionale, ad esempio Microsoft SQL Server, supporta le transazioni fornendo funzionalità di blocco, di registrazione e di gestione delle transazioni ogni volta che un'applicazione client esegue un'operazione di aggiornamento, inserimento o eliminazione.  
  
> [!NOTE]
> Le transazioni che implicano l'uso di più risorse possono abbassare la concorrenza se i blocchi vengono mantenuti troppo a lungo. Mantenere pertanto le transazioni per il minor tempo possibile.  
  
 Se una transazione implica l'uso di più tabelle nello stesso database o server, è spesso preferibile usare transazioni esplicite nelle stored procedure. È possibile creare transazioni in stored procedure SQL Server usando le istruzioni Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` e `ROLLBACK TRANSACTION`. Per altre informazioni, vedere la documentazione online di SQL Server.  
  
 Le transazioni che coinvolgono diversi gestori di risorse, ad esempio una transazione tra SQL Server e Oracle, richiedono una transazione distribuita.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Transazioni locali](local-transactions.md)  
 Viene illustrato come eseguire transazioni su un database.  
  
 [Transazioni distribuite](distributed-transactions.md)  
 Viene descritto come eseguire transazioni distribuite in ADO.NET.  
  
 [Integrazione di System.Transactions con SQL Server](system-transactions-integration-with-sql-server.md)  
 Viene <xref:System.Transactions> descritta l'integrazione con SQL Server per l'utilizzo di transazioni distribuite.  
  
 [Concorrenza ottimistica](optimistic-concurrency.md)  
 Vengono descritte la concorrenza ottimistica e la concorrenza pessimistica e come è possibile verificare le violazioni della concorrenza.  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sulle transazioni](../transactions/transaction-fundamentals.md)
- [Connessione a un'origine dati](connecting-to-a-data-source.md)
- [Comandi e parametri](commands-and-parameters.md)
- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [DbProviderFactories](dbproviderfactories.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
