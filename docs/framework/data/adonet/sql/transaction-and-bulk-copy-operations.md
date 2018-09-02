---
title: Transazioni e operazioni di copia bulk
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f6f0cbc9-f7bf-4d6e-875f-ad1ba0b4aa62
ms.openlocfilehash: 24657f541daf5bb098f8db3b59a3241ecf832d39
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398865"
---
# <a name="transaction-and-bulk-copy-operations"></a>Transazioni e operazioni di copia bulk
Le operazioni di copia bulk possono essere eseguite come operazioni isolate oppure come un singolo passaggio di una transazione a più passaggi. Quest'ultima opzione consente di eseguire più operazioni di copia di massa all'interno della stessa transazione, nonché di eseguire altre operazioni di database, ad esempio inserimenti, aggiornamenti ed eliminazioni, e di eseguire comunque il commit o il rollback dell'intera transazione.  
  
 Per impostazione predefinita, un'operazione di copia di massa viene eseguita come operazione isolata. L'operazione avviene infatti in modalità non transazionale, pertanto non è possibile eseguirne il rollback. Se è necessario eseguire il rollback tutto o parte della copia bulk quando si verifica un errore, è possibile usare una <xref:System.Data.SqlClient.SqlBulkCopy>-transazione gestita, eseguire l'operazione di copia bulk in una transazione esistente oppure inserirla nell'elenco un **System. Transactions** <xref:System.Transactions.Transaction>.  
  
## <a name="performing-a-non-transacted-bulk-copy-operation"></a>Esecuzione di un'operazione di copia di massa non transazionale  
 Nell'applicazione console seguente viene illustrato cosa si verifica se viene rilevato un errore durante un'operazione di copia di massa non transazionale.  
  
 Nell'esempio, ogni tabella di origine e tabella di destinazione includono un' `Identity` colonna denominata **ProductID**. Il codice innanzitutto prepara la tabella di destinazione eliminando tutte le righe e quindi inserendo una singola riga il cui **ProductID** è noto che esiste nella tabella di origine. Per impostazione predefinita, nella tabella di destinazione viene generato un nuovo valore della colonna `Identity` per ciascuna riga aggiunta. In questo esempio, invece, quando si apre la connessione viene impostata un'opzione che impone al processo di caricamento di massa l'uso dei valori `Identity` dalla tabella di origine.  
  
 Quando si esegue l'operazione di copia di massa, la proprietà <xref:System.Data.SqlClient.SqlBulkCopy.BatchSize%2A> è impostata su 10. Se viene rilevata una riga non valida, viene generata un'eccezione. Nel primo esempio, l'operazione di copia di massa è di tipo non transazionale. Viene eseguito il commit di tutti i batch copiati fino al rilevamento dell'errore, viene eseguito il rollback del batch contenente la chiave duplicata e l'operazione di copia di massa viene interrotta prima dell'elaborazione di altri batch.  
  
> [!NOTE]
>  In questo esempio non funzionerà a meno che non sono state create le tabelle di lavoro come descritto in [esempio di copia di massa](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Questo codice viene fornito per illustrare la sintassi per usare **SqlBulkCopy** solo. Se le tabelle di origine e destinazione si trovano nella stessa istanza di SQL Server, è più semplice e rapido usare un' [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` istruzione per copiare i dati.  
  
 [!code-csharp[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/VB/source.vb#1)]  
  
## <a name="performing-a-dedicated-bulk-copy-operation-in-a-transaction"></a>Esecuzione di un'operazione di copia bulk dedicata in una transazione  
 Per impostazione predefinita, un'operazione di copia di massa corrisponde alla relativa transazione. Per eseguire un'operazione di copia di massa dedicata, creare una nuova istanza del tipo <xref:System.Data.SqlClient.SqlBulkCopy> con una stringa di connessione oppure usare un oggetto <xref:System.Data.SqlClient.SqlConnection> esistente senza una transazione attiva. In ciascuno scenario, l'operazione di copia di massa consente di creare la transazione e quindi di eseguirne il commit o il rollback.  
  
 È possibile specificare in modo esplicito l'opzione <xref:System.Data.SqlClient.SqlBulkCopyOptions.UseInternalTransaction> nel costruttore della classe <xref:System.Data.SqlClient.SqlBulkCopy> per fare in modo un'operazione di copia di massa venga eseguita nella relativa transazione e che quindi ogni batch dell'operazione di copia di massa venga eseguita in una transazione distinta.  
  
> [!NOTE]
>  Dal momento che vengono eseguiti batch diversi all'interno di transazioni distinte, se si verifica un errore durante l'operazione di copia di massa, verrà eseguito il rollback di tutte le righe del batch corrente, ma quelle del batch precedente resteranno nel database.  
  
 La seguente applicazione console è analoga all'esempio precedente, con una sola eccezione: in questo esempio, l'operazione di copia di massa gestisce le relative transazioni. Viene eseguito il commit di tutti i batch copiati fino al rilevamento dell'errore, viene eseguito il rollback del batch contenente la chiave duplicata e l'operazione di copia di massa viene interrotta prima dell'elaborazione di altri batch.  
  
> [!IMPORTANT]
>  In questo esempio non funzionerà a meno che non sono state create le tabelle di lavoro come descritto in [esempio di copia di massa](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Questo codice viene fornito per illustrare la sintassi per usare **SqlBulkCopy** solo. Se le tabelle di origine e destinazione si trovano nella stessa istanza di SQL Server, è più semplice e rapido usare un' [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` istruzione per copiare i dati.  
  
 [!code-csharp[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/VB/source.vb#1)]  
  
## <a name="using-existing-transactions"></a>Uso di transazioni esistenti  
 È possibile specificare un oggetto <xref:System.Data.SqlClient.SqlTransaction> esistente come parametro in un costruttore <xref:System.Data.SqlClient.SqlBulkCopy>. In questa situazione l'operazione di copia di massa viene eseguita in una transazione esistente e non viene apportata alcuna modifica allo stato della transazione, ovvero non ne viene eseguito il commit o l'annullamento. Questo consente a un'applicazione di includere l'operazione di copia di massa in una transazione con altre operazioni di database. Tuttavia, se non viene specificato un oggetto <xref:System.Data.SqlClient.SqlTransaction>, se non viene passato un riferimento null e se nella connessione è presente una transazione attiva, verrà generata un'eccezione.  
  
 Se è necessario eseguire il rollback dell'intera operazione di copia di massa perché si verifica un errore oppure se è necessario eseguire tale copia come parte di un processo di dimensioni maggiori di cui si può eseguire il rollback, è possibile fornire un oggetto <xref:System.Data.SqlClient.SqlTransaction> al costruttore <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 La seguente applicazione console è analoga al primo esempio (non transazionale), con una sola eccezione: in questo esempio l'operazione di copia di massa è inclusa in una transazione esterna di dimensioni maggiori. Quando si verifica l'errore di violazione della chiave primaria, viene eseguito il rollback dell'intera transazione e non viene aggiunta alcuna riga alla tabella di destinazione.  
  
> [!IMPORTANT]
>  In questo esempio non funzionerà a meno che non sono state create le tabelle di lavoro come descritto in [esempio di copia di massa](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Questo codice viene fornito per illustrare la sintassi per usare **SqlBulkCopy** solo. Se le tabelle di origine e destinazione si trovano nella stessa istanza di SQL Server, è più semplice e rapido usare un' [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` istruzione per copiare i dati.  
  
 [!code-csharp[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operazioni di copia di massa in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
