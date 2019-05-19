---
title: Transazioni locali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
ms.openlocfilehash: f686c20a9afd981405e32854fcc594abac78c85c
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882034"
---
# <a name="local-transactions"></a>Transazioni locali
Le transazioni in ADO.NET vengono usate quando si desidera associare più attività in modo da poterle eseguire come una singola unità di lavoro. Ad esempio, si supponga che un'applicazione esegua due attività. Ovvero che prima aggiorni una tabella con le informazioni sull'ordine e che, successivamente, aggiorni una tabella contenente le informazioni d'inventario addebitando gli articoli ordinati. Se una delle attività non riesce, quindi entrambi gli aggiornamenti di rollback.  
  
## <a name="determining-the-transaction-type"></a>Determinazione del tipo di transazione  
 Una transazione viene considerata una transazione locale quando tratta di una transazione monofase e viene gestito direttamente dal database. Una transazione viene considerata una transazione distribuita quando è coordinata da un monitoraggio delle transazioni e utilizza meccanismi fail-safe (ad esempio, i commit in due fasi) per la risoluzione delle transazioni.  
  
 Ognuno dei provider di dati .NET Framework ha un proprio `Transaction` oggetto per l'esecuzione di transazioni locali. Per eseguire una transazione in un database di SQL Server, selezionare una transazione <xref:System.Data.SqlClient>. Per una transazione Oracle usare il provider <xref:System.Data.OracleClient>. Inoltre, è presente un <xref:System.Data.Common.DbTransaction> classe disponibile per la scrittura di codice indipendente dal provider che richiede transazioni.  
  
> [!NOTE]
> Le transazioni sono più efficienti quando vengono eseguite nel server. Se si usa un database SQL Server in cui sono ampiamente usate le transazioni esplicite, è consigliabile scrivere queste transazioni come stored procedure usando l'istruzione BEGIN TRANSACTION Transact-SQL.
  
## <a name="performing-a-transaction-using-a-single-connection"></a>Esecuzione di una transazione con una singola connessione  
 In ADO.NET è possibile controllare le transazioni con il `Connection` oggetto. È possibile avviare una transazione locale con il metodo `BeginTransaction`. Una volta iniziata una transazione, è possibile inserire un comando nell'elenco della transazione usando la proprietà `Transaction` di un oggetto `Command`. In seguito è possibile eseguire il commit o il rollback delle modifiche apportate nell'origine dati in base all'esito corretto o errato dei componenti della transazione.  
  
> [!NOTE]
>  Il metodo `EnlistDistributedTransaction` non deve essere usato per una transazione locale.  
  
 L'ambito della transazione si limita alla connessione. Nell'esempio seguente viene eseguita una transazione esplicita composta da due comandi separati nel blocco `try`. I comandi eseguono istruzioni INSERT sulla tabella Production. ScrapReason nel database di esempio AdventureWorks-SQL Server, viene eseguito il commit se non vengono generate eccezioni. Se, invece, viene generata un'eccezione, il codice del blocco `catch` esegue il rollback della transazione. Allo stesso modo, se la transazione viene interrotta oppure la connessione viene chiusa prima del completamento della transazione, viene eseguito automaticamente il rollback della transazione.  
  
## <a name="example"></a>Esempio  
 Per eseguire una transazione, usare la procedura seguente:  
  
1. Chiamare il metodo <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> dell'oggetto <xref:System.Data.SqlClient.SqlConnection> per contrassegnare l'inizio della transazione. Il metodo <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> restituisce un riferimento alla transazione. Questo riferimento viene assegnato agli oggetti <xref:System.Data.SqlClient.SqlCommand> contenuti nell'elenco della transazione.  
  
2. Assegnare l'oggetto `Transaction` alla proprietà <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> dell'oggetto <xref:System.Data.SqlClient.SqlCommand> da eseguire. Se un comando viene eseguito su una connessione con una transazione attiva e l'oggetto `Transaction` non è stato assegnato alla proprietà `Transaction` dell'oggetto `Command`, viene generata un'eccezione.  
  
3. Eseguire i comandi richiesti.  
  
4. Chiamare il metodo <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> dell'oggetto <xref:System.Data.SqlClient.SqlTransaction> per completare la transazione oppure il metodo <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> per interrompere la transazione. Se la connessione viene chiusa o eliminata prima che venga eseguito il metodo <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> o <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>, viene eseguito il rollback della transazione.  
  
 Esempio di codice seguente illustra la logica transazionale usando ADO.NET con Microsoft SQL Server.  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [Transazioni distribuite](../../../../docs/framework/data/adonet/distributed-transactions.md)
- [Integrazione di System.Transactions con SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
