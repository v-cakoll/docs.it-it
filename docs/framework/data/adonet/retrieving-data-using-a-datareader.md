---
title: Recupero di dati tramite un oggetto DataReader
description: Informazioni su come recuperare i dati usando un DataReader in ADO.NET con questo codice di esempio. DataReader fornisce un flusso di dati non memorizzato nel buffer.
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 6e5161cc325bf0379bb9241b99c473c539ad1081
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286598"
---
# <a name="retrieve-data-using-a-datareader"></a>Recuperare i dati usando un DataReader
Per recuperare i dati usando un **DataReader**, creare un'istanza dell'oggetto **Command** e quindi creare un **DataReader** chiamando **Command. ExecuteReader** per recuperare le righe da un'origine dati. **DataReader** fornisce un flusso di dati non memorizzato nel buffer che consente alla logica procedurale di elaborare in modo efficiente i risultati da un'origine dati. Il **DataReader** è una scelta ottimale quando si recuperano grandi quantità di dati perché i dati non vengono memorizzati nella cache.

Nell'esempio seguente viene illustrato l'utilizzo di un **DataReader**, dove `reader` rappresenta un DataReader valido e `command` rappresenta un oggetto comando valido.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Utilizzare il metodo **DataReader. Read** per ottenere una riga dai risultati della query. È possibile accedere a ogni colonna della riga restituita passando il nome o il numero ordinale della colonna a **DataReader**. Tuttavia, per ottenere prestazioni ottimali, **DataReader** fornisce una serie di metodi che consentono di accedere ai valori delle colonne nei tipi di dati nativi (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**e così via). Per un elenco di metodi tipizzati della funzione di accesso per i data **Reader**specifici del provider di dati, vedere <xref:System.Data.OleDb.OleDbDataReader> e <xref:System.Data.SqlClient.SqlDataReader> . Utilizzando i metodi tipizzati della funzione di accesso quando si conosce il tipo di dati sottostante, è possibile ridurre la quantità di conversione del tipo necessaria durante il recupero del valore della colonna.  
  
 Nell'esempio seguente viene eseguita l'iterazione di un oggetto **DataReader** e vengono restituite due colonne da ogni riga.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Chiusura dell'oggetto DataReader  
 Al termine dell'utilizzo dell'oggetto **DataReader** , chiamare sempre il metodo **Close** .  
  
 Se il **comando** contiene parametri di output o valori restituiti, tali valori non saranno disponibili fino alla chiusura del **DataReader** .  
  
 Mentre un **DataReader** è aperto, la **connessione** viene utilizzata esclusivamente da tale **DataReader**. Non è possibile eseguire alcun comando per la **connessione**, inclusa la creazione di un altro **DataReader**, fino alla chiusura del **DataReader** originale.  
  
> [!NOTE]
> Non chiamare **Close** o **Dispose** per una **connessione**, un **DataReader**o qualsiasi altro oggetto gestito nel metodo **Finalize** della classe. Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente. Se la classe non è proprietaria di risorse non gestite, non includere un metodo **Finalize** nella definizione della classe. Per altre informazioni, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Recupero di più set di risultati con NextResult  
 Se **DataReader** restituisce più set di risultati, chiamare il metodo **NextResult** per scorrere i set di risultati in modo sequenziale. Nell'esempio seguente viene illustrata l'elaborazione dei risultati di due dichiarazioni SELECT da parte del tipo <xref:System.Data.SqlClient.SqlDataReader> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Recupero delle informazioni sullo schema dal DataReader  
 Mentre un **DataReader** è aperto, è possibile recuperare le informazioni sullo schema relative al set di risultati corrente usando il metodo **GetSchemaTable** . **GetSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto popolato con righe e colonne che contengono le informazioni sullo schema per il set di risultati corrente. Il **DataTable** contiene una riga per ogni colonna del set di risultati. Ogni colonna della tabella dello schema è mappata a una proprietà delle colonne restituite nelle righe del set di risultati, dove **ColumnName** è il nome della proprietà e il valore della colonna è il valore della proprietà. Nell'esempio seguente vengono scritte le informazioni sullo schema per **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Uso dei capitoli OLE DB  
 I set di righe gerarchici, o capitoli (tipo OLE DB **DBTYPE_HCHAPTER**, tipo ADO **adChapter**), possono essere recuperati utilizzando <xref:System.Data.OleDb.OleDbDataReader> . Quando una query che include un capitolo viene restituita come **DataReader**, il capitolo viene restituito come una colonna nel **DataReader** e viene esposto come oggetto **DataReader** .  
  
 Il **set di dati** ADO.NET può essere utilizzato anche per rappresentare i set di righe gerarchici utilizzando le relazioni padre-figlio tra le tabelle. Per ulteriori informazioni, vedere [DataSet, DataTable e DataViews](./dataset-datatable-dataview/index.md).  
  
 Nell'esempio di codice seguente viene usato il provider MSDataShape per generare una colonna del capitolo contenente gli ordini per ogni cliente presente in un elenco di clienti.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Restituzione di risultati con CURSORi REF Oracle  
 Con il provider di dati .NET Framework per Oracle è possibile usare i REF CURSOR Oracle per la restituzione del risultato di una query. I REF CURSOR Oracle vengono restituiti come <xref:System.Data.OracleClient.OracleDataReader>.  
  
 È possibile recuperare un <xref:System.Data.OracleClient.OracleDataReader> oggetto che rappresenta un REF CURSOR Oracle utilizzando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> metodo. È inoltre possibile specificare un oggetto <xref:System.Data.OracleClient.OracleCommand> che restituisce uno o più REF CURSOR Oracle come **SelectCommand** per un oggetto <xref:System.Data.OracleClient.OracleDataAdapter> utilizzato per riempire un oggetto <xref:System.Data.DataSet> .  
  
 Per accedere a un cursore REF restituito da un'origine dati Oracle, creare un oggetto <xref:System.Data.OracleClient.OracleCommand> per la query e aggiungere un parametro di output che fa riferimento al cursore Ref alla <xref:System.Data.OracleClient.OracleCommand.Parameters> raccolta di <xref:System.Data.OracleClient.OracleCommand> . È necessario che il nome del parametro corrisponda al nome del parametro REF CURSOR della query. Impostare il tipo del parametro su <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> . Il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo di <xref:System.Data.OracleClient.OracleCommand> restituisce un oggetto <xref:System.Data.OracleClient.OracleDataReader> per il cursore Ref.  
  
 Se <xref:System.Data.OracleClient.OracleCommand> restituisce più cursori Ref, aggiungere più parametri di output. È possibile accedere ai diversi CURSORi REF chiamando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo. La chiamata a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> restituisce un oggetto che fa <xref:System.Data.OracleClient.OracleDataReader> riferimento al primo REF CURSOR. È quindi possibile chiamare il <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> metodo per accedere ai cursori Ref successivi. Sebbene i parametri nella <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> raccolta corrispondano ai parametri di output di REF CURSOR in base al nome, il <xref:System.Data.OracleClient.OracleDataReader> accede a tali parametri nell'ordine in cui sono stati aggiunti alla <xref:System.Data.OracleClient.OracleCommand.Parameters> raccolta.  
  
 Si considerino ad esempio il package e il corpo package Oracle seguenti.  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS
  TYPE T_CURSOR IS REF CURSOR;
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
    DEPTCURSOR OUT T_CURSOR);
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
    DEPTCURSOR OUT T_CURSOR)
  IS
  BEGIN
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;
  END OPEN_TWO_CURSORS;
END CURSPKG;
```  
  
 Il codice seguente crea un oggetto <xref:System.Data.OracleClient.OracleCommand> che restituisce i REF CURSOR dal pacchetto Oracle precedente aggiungendo due parametri di tipo <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> alla <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> raccolta.  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 Il codice seguente restituisce i risultati del comando precedente usando i <xref:System.Data.OracleClient.OracleDataReader.Read> metodi e <xref:System.Data.OracleClient.OracleDataReader.NextResult> dell'oggetto <xref:System.Data.OracleClient.OracleDataReader> . I parametri REF CURSOR vengono restituiti in ordine.  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 Nell'esempio seguente viene usato il comando precedente per popolare un oggetto <xref:System.Data.DataSet> con i risultati del pacchetto Oracle.  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```

> [!NOTE]
> Per evitare un **overflow**, è consigliabile gestire anche qualsiasi conversione dal tipo di numero Oracle a un tipo di .NET Framework valido prima di archiviare il valore in un oggetto <xref:System.Data.DataRow> . È possibile utilizzare l' <xref:System.Data.Common.DataAdapter.FillError> evento per determinare se si è verificato un **overflow** . Per ulteriori informazioni sull' <xref:System.Data.Common.DataAdapter.FillError> evento, vedere [gestione di eventi DataAdapter](handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Vedere anche

- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Comandi e parametri](commands-and-parameters.md)
- [Recupero di informazioni sullo schema del database](retrieving-database-schema-information.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
