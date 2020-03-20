---
title: Sequenze Oracle
ms.date: 03/30/2017
ms.assetid: 27cd371d-8252-414d-b5b2-5d31fa44b585
ms.openlocfilehash: d6e6bb51b8bd317c7161500b89993be689659fad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149414"
---
# <a name="oracle-sequences"></a>Sequenze Oracle
Il provider di dati .NET Framework per Oracle fornisce supporto per il recupero dei valori chiave delle sequenze di Oracle generati dal server dopo l'esecuzione di inserimenti tramite <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
 In SQL Server e Oracle è supportata la creazione di colonne a incremento automatico che è possibile impostare come chiavi primarie. Tali valori vengono generati dal server quando si aggiungono righe a una tabella. In SQL Server viene impostata la proprietà Identity di una colonna, mentre in Oracle viene creata una sequenza. Di seguito è illustrata la differenza tra colonne a incremento automatico di SQL Server e sequenze di Oracle:  
  
- In SQL Server, per una colonna contrassegnata come colonna a incremento automatico vengono automaticamente generati nuovi valori quando si inserisce una nuova riga.  
  
- In Oracle, per generare nuovi valori per una colonna di una tabella viene creata una sequenza, ma non esiste alcun collegamento diretto tra la sequenza e la tabella o la colonna. Una sequenza di Oracle è un oggetto, analogamente a una tabella o a una stored procedure.  
  
 Quando si crea una sequenza in un database Oracle, è possibile definirne il valore iniziale e l'incremento tra i valori. È anche possibile eseguire una query sulla sequenza per rilevare nuovi valori prima di inviare nuove righe. Il codice è quindi in grado di riconoscere i valori chiave per le nuove righe prima che vengano inserite nel database.  
  
 Per altre informazioni sulla creazione di colonne a incremento automatico tramite SQL Server e ADO.NET, vedere Recupero di [valori Identity o Autonumber](retrieving-identity-or-autonumber-values.md) e [Creazione di colonne autoIncrement.](./dataset-datatable-dataview/creating-autoincrement-columns.md)  
  
## <a name="example"></a>Esempio  
 Nell'esempio in C# seguente viene illustrato come recuperare nuovi valori di sequenza da un database Oracle. Alla sequenza viene fatto riferimento nella query INSERT INTO usata per inviare le nuove righe e viene quindi restituito il valore di sequenza generato tramite la clausola RETURNING introdotta in Oracle10g. Viene aggiunta una serie di nuove righe in sospeso in <xref:System.Data.DataTable> usando la funzionalità di incremento automatico di ADO.NET per generare valori di chiave primaria "segnaposto". Si noti che il valore dell'incremento generato per la nuova riga è soltanto un "segnaposto". Il database potrebbe quindi generare valori diversi da quelli generati da ADO.NET.  
  
 Prima dell'invio degli inserimenti in sospeso nel database, in questo esempio viene visualizzato il contenuto delle righe. Quindi, nel codice viene creato un nuovo oggetto <xref:System.Data.OracleClient.OracleDataAdapter> e vengono impostate le relative proprietà <xref:System.Data.OracleClient.OracleDataAdapter.InsertCommand%2A> e <xref:System.Data.OracleClient.OracleDataAdapter.UpdateBatchSize%2A>. Nell'esempio viene anche specificata la logica per restituire i valori generati dal server tramite parametri di output. Viene quindi eseguito l'aggiornamento per inviare le righe in sospeso e viene visualizzato il contenuto di <xref:System.Data.DataTable>.  
  
```csharp  
public void OracleSequence(String connectionString)  
{  
   String insertString =
      "INSERT INTO SequenceTest_Table (ID, OtherColumn)" +  
      "VALUES (SequenceTest_Sequence.NEXTVAL, :OtherColumn)" +  
      "RETURNING ID INTO :ID";  
  
   using (OracleConnection conn = new OracleConnection(connectionString))  
   {  
      //Open a connection.  
      conn.Open();  
      OracleCommand cmd = conn.CreateCommand();  
  
      // Prepare the database.  
      cmd.CommandText = "DROP SEQUENCE SequenceTest_Sequence";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "DROP TABLE SequenceTest_Table";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "CREATE TABLE SequenceTest_Table " +  
                     "(ID int PRIMARY KEY, OtherColumn varchar(255))";  
      cmd.ExecuteNonQuery();  
  
      cmd.CommandText = "CREATE SEQUENCE SequenceTest_Sequence " +  
                        "START WITH 100 INCREMENT BY 5";  
      cmd.ExecuteNonQuery();  
  
      DataTable testTable = new DataTable();  
      DataColumn column = testTable.Columns.Add("ID", typeof(int));  
      column.AutoIncrement = true;  
      column.AutoIncrementSeed = -1;  
      column.AutoIncrementStep = -1;  
      testTable.PrimaryKey = new DataColumn[] { column };  
      testTable.Columns.Add("OtherColumn", typeof(string));  
      for (int rowCounter = 1; rowCounter <= 15; rowCounter++)  
      {  
         testTable.Rows.Add(null, "Row #" + rowCounter.ToString());  
      }  
  
      Console.WriteLine("Before Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      Console.WriteLine();  
  
      cmd.CommandText =
        "SELECT ID, OtherColumn FROM SequenceTest_Table";  
      OracleDataAdapter da = new OracleDataAdapter(cmd);  
      da.InsertCommand = new OracleCommand(insertString, conn);  
      da.InsertCommand.Parameters.Add(":ID", OracleType.Int32, 0, "ID");  
      da.InsertCommand.Parameters[0].Direction = ParameterDirection.Output;  
      da.InsertCommand.Parameters.Add(":OtherColumn", OracleType.VarChar, 255, "OtherColumn");  
      da.InsertCommand.UpdatedRowSource = UpdateRowSource.OutputParameters;  
      da.UpdateBatchSize = 10;  
  
      da.Update(testTable);  
  
      Console.WriteLine("After Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      // Close the connection.  
      conn.Close();  
   }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](oracle-and-adonet.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
