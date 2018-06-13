---
title: Singole operazioni di copia di massa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: 47f89feb90efbafb6c43bbad78f05292213a0c58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365865"
---
# <a name="single-bulk-copy-operations"></a>Singole operazioni di copia di massa
L'approccio più semplice per eseguire un'operazione di copia di massa in SQL Server consiste nell'eseguire una singola operazione in un database. Per impostazione predefinita, un'operazione di copia di massa viene eseguita come operazione isolata: l'operazione di copia avviene in modalità non transazionale, senza la possibilità di eseguirne il rollback.  
  
> [!NOTE]
>  Per eseguire il rollback di una parte o dell'intera copia di massa quando si verifica un errore, è possibile usare una transazione gestita di <xref:System.Data.SqlClient.SqlBulkCopy> oppure eseguire la copia di massa in una transazione esistente. **SqlBulkCopy** funzionerà anche con <xref:System.Transactions> se la connessione viene inserita, in modo implicito o esplicito, in un **System. Transactions** delle transazioni.  
>   
>  Per ulteriori informazioni, vedere [delle transazioni e operazioni di copia Bulk](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).  
  
 In generale, i passaggi per eseguire un'operazione di copia di massa sono i seguenti:  
  
1.  Connettersi al server di origine per recuperare i dati da copiare. I dati possono provenire anche da altre origini, se possono essere recuperati da un oggetto<xref:System.Data.IDataReader> o <xref:System.Data.DataTable>.  
  
2.  Connettersi al server di destinazione (a meno che non si desidera **SqlBulkCopy** per stabilire una connessione per l'utente).  
  
3.  Creare un oggetto <xref:System.Data.SqlClient.SqlBulkCopy>, impostando tutte le proprietà necessarie.  
  
4.  Impostare il **DestinationTableName** proprietà per indicare la tabella di destinazione per la maggior parte delle operazioni di inserimento.  
  
5.  Chiamare uno del **WriteToServer** metodi.  
  
6.  Facoltativamente, aggiornare le proprietà e chiamate **WriteToServer** nuovamente se necessario.  
  
7.  Chiamare <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A> o eseguire il wrapping delle operazioni di copia di massa all'interno di un'istruzione `Using`.  
  
> [!CAUTION]
>  È consigliabile assicurare che la corrispondenza tra i tipi di dati della colonna di origine e quelli di destinazione. Se i tipi di dati non corrispondono, **SqlBulkCopy** tenta di convertire ogni valore di origine al tipo di dati di destinazione, tramite le regole utilizzate da <xref:System.Data.SqlClient.SqlParameter.Value%2A>. Le conversioni possono influenzare le prestazioni e possono provocare errori imprevisti. Ad esempio, non è sempre possibile convertire un tipo di dati `Double` in `Decimal`.  
  
## <a name="example"></a>Esempio  
 Nell'applicazione console riportata di seguito viene illustrato come caricare i dati usando la classe <xref:System.Data.SqlClient.SqlBulkCopy>. In questo esempio, un <xref:System.Data.SqlClient.SqlDataReader> consente di copiare i dati di **Production. Product** tabella in SQL Server**AdventureWorks** database in una tabella simile dello stesso database.  
  
> [!IMPORTANT]
>  Questo esempio non verrà eseguito a meno che non state create le tabelle di lavoro come descritto in [l'installazione di esempio copia Bulk](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Questo codice viene fornito per illustrare la sintassi per l'utilizzo di **SqlBulkCopy** solo. Se la tabella di origine e quella di destinazione risiedono nella stessa istanza di SQL Server, per copiare i dati è più semplice e rapido usare un'istruzione `INSERT … SELECT` Transact-SQL.  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a>Esecuzione di un'operazione di copia di massa con Transact-SQL e la classe Command  
 Nell'esempio seguente viene illustrato come usare il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> per eseguire l'istruzione BULK INSERT.  
  
> [!NOTE]
>  Il percorso di file per l'origine dati è relativo al server. Per la corretta esecuzione dell'operazione di copia di massa, è necessario che il processo server abbia accesso a tale percorso.  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Operazioni di copia di massa in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
