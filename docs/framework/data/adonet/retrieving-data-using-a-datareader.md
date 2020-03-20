---
title: Recupero di dati tramite un oggetto DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149024"
---
# <a name="retrieve-data-using-a-datareader"></a>Recuperare i dati usando un DataReaderRetrieve data using a DataReader
Per recuperare i dati utilizzando un **DataReader**, creare un'istanza dell'oggetto **Command,** quindi creare un **oggetto DataReader** chiamando **Command.ExecuteReader** per recuperare righe da un'origine dati. Il **DataReader** fornisce un flusso di dati senza buffer che consente alla logica procedurale di elaborare in modo efficiente i risultati da un'origine dati in sequenza. Il **DataReader** è una buona scelta quando si recuperano grandi quantità di dati perché i dati non sono memorizzati nella cache.

Nell'esempio seguente viene illustrato l'utilizzo di un `command` **DataReader**, in cui `reader` rappresenta un DataReader valido e rappresenta un oggetto Command valido.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Utilizzare il metodo **DataReader.Read** per ottenere una riga dai risultati della query. È possibile accedere a ogni colonna della riga restituita passando il nome o il numero ordinale della colonna a **DataReader**. Tuttavia, per ottenere prestazioni ottimali, **DataReader** fornisce una serie di metodi che consentono di accedere ai valori delle colonne nei relativi tipi di dati nativi (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**e così via). Per un elenco dei metodi delle opzioni di accesso <xref:System.Data.OleDb.OleDbDataReader> tipizzate per **DataReader**specifici del provider di dati, vedere e <xref:System.Data.SqlClient.SqlDataReader>. L'utilizzo dei metodi della funzione di accesso tipizzato quando si conosce il tipo di dati sottostante riduce la quantità di conversione del tipo necessaria durante il recupero del valore della colonna.  
  
 L'esempio seguente scorre un oggetto **DataReader** e restituisce due colonne da ogni riga.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Chiusura dell'oggetto DataReader  
 Chiamare sempre il **Close** metodo dopo aver terminato di utilizzare il **DataReader** oggetto.  
  
 Se il **comando** contiene parametri di output o valori restituiti, tali valori non sono disponibili fino a quando il **DataReader** viene chiuso.  
  
 Mentre un **DataReader** è aperto, il **Connection** è in uso esclusivamente da tale **DataReader**. Non è possibile eseguire comandi per **Connection**, inclusa la creazione di un altro **DataReader**, fino alla chiusura del **DataReader** originale.  
  
> [!NOTE]
> Non chiamare **Close** o **Dispose** su un **oggetto Connection**, un **DataReader**o qualsiasi altro oggetto gestito nel metodo **Finalize** della classe. Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente. Se la classe non possiede alcuna risorsa non gestita, non includere un metodo **Finalize** nella definizione della classe. Per ulteriori informazioni, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Recupero di più set di risultati tramite NextResultRetrieving multiple result sets using NextResult  
 Se il **DataReader** restituisce più set di risultati, chiamare il **NextResult** metodo per scorrere i set di risultati in sequenza. Nell'esempio seguente viene illustrata l'elaborazione dei risultati di due dichiarazioni SELECT da parte del tipo <xref:System.Data.SqlClient.SqlDataReader> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Recupero di informazioni sullo schema da DataReaderGetting schema information from the DataReader  
 Mentre un **DataReader** è aperto, è possibile recuperare le informazioni sullo schema sul set di risultati corrente utilizzando il **GetSchemaTable** metodo. **GetSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto popolato con righe e colonne che contengono le informazioni sullo schema per il set di risultati corrente. Il **DataTable** contiene una riga per ogni colonna del set di risultati. Ogni colonna della tabella dello schema esegue il mapping a una proprietà delle colonne restituite nelle righe del set di risultati, dove **ColumnName** è il nome della proprietà e il valore della colonna è il valore della proprietà. Nell'esempio seguente vengono scrivete le informazioni sullo schema per **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Utilizzo dei capitoli OLE DB  
 È possibile recuperare i set di righe gerarchici o i capitoli (tipo <xref:System.Data.OleDb.OleDbDataReader>OLE DB **DBTYPE_HCHAPTER**, tipo ADO **adChapter**), utilizzando il metodo . Quando una query che include un capitolo viene restituita come **DataReader**, il capitolo viene restituito come colonna in tale **DataReader** e viene esposto come oggetto **DataReader** .  
  
 Il ADO.NET **DataSet** può essere utilizzato anche per rappresentare set di righe gerarchici utilizzando relazioni padre-figlio tra tabelle. Per ulteriori informazioni, vedere [DataSets, DataTables e DataViews](./dataset-datatable-dataview/index.md).  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Restituzione dei risultati con Oracle REF CURSOR  
 Con il provider di dati .NET Framework per Oracle è possibile usare i REF CURSOR Oracle per la restituzione del risultato di una query. I REF CURSOR Oracle vengono restituiti come <xref:System.Data.OracleClient.OracleDataReader>.  
  
 È possibile <xref:System.Data.OracleClient.OracleDataReader> recuperare un oggetto che rappresenta <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> un Oracle REF CURSOR utilizzando il metodo . È inoltre possibile <xref:System.Data.OracleClient.OracleCommand> specificare un che restituisce uno o più <xref:System.Data.OracleClient.OracleDataAdapter> CHIAMAVA.R <xref:System.Data.DataSet>Oracle REF come **SelectCommand** per un oggetto utilizzato per riempire un oggetto .  
  
 Per accedere a un CURSOR REF restituito da <xref:System.Data.OracleClient.OracleCommand> un'origine dati Oracle, creare un oggetto <xref:System.Data.OracleClient.OracleCommand.Parameters> per <xref:System.Data.OracleClient.OracleCommand>la query e aggiungere un parametro di output che faccia riferimento a REF CURSOR alla raccolta dell'oggetto . È necessario che il nome del parametro corrisponda al nome del parametro REF CURSOR della query. Impostare il tipo <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>del parametro su . Il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo <xref:System.Data.OracleClient.OracleCommand> dell'utente restituisce un <xref:System.Data.OracleClient.OracleDataReader> per il CURSOR REF.  
  
 Se <xref:System.Data.OracleClient.OracleCommand> restituisce più REF CURSORS, aggiungere più parametri di output. È possibile accedere ai diversi REF(ARIE) chiamando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo . La chiamata <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> a <xref:System.Data.OracleClient.OracleDataReader> restituisce un riferimento al primo CURSOR REF. È quindi possibile <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> chiamare il metodo per accedere ai REF SUCCESSIVI. Anche se i <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> parametri nella raccolta corrispondono ai parametri di output REF CURSOR in base al nome, li <xref:System.Data.OracleClient.OracleDataReader> accede nell'ordine in cui sono stati aggiunti alla <xref:System.Data.OracleClient.OracleCommand.Parameters> raccolta.  
  
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
  
 Il codice seguente <xref:System.Data.OracleClient.OracleCommand> crea un oggetto che restituisce i REF CURSO <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> dal <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> pacchetto Oracle precedente aggiungendo due parametri di tipo alla raccolta.  
  
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
  
 Il codice seguente restituisce i risultati <xref:System.Data.OracleClient.OracleDataReader.Read> <xref:System.Data.OracleClient.OracleDataReader.NextResult> del comando <xref:System.Data.OracleClient.OracleDataReader>precedente utilizzando i metodi e dell'oggetto . I parametri REF CURSOR vengono restituiti in ordine.  
  
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
  
 Nell'esempio seguente viene utilizzato <xref:System.Data.DataSet> il comando precedente per popolare un con i risultati del pacchetto Oracle.  
  
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
> Per evitare **un'eccezione OverflowException**, è consigliabile gestire anche qualsiasi conversione dal tipo <xref:System.Data.DataRow>Oracle NUMBER a un tipo .NET Framework valido prima di archiviare il valore in un oggetto . È possibile <xref:System.Data.Common.DataAdapter.FillError> utilizzare l'evento per determinare se si è verificata **un'eccezione OverflowException.** Per ulteriori informazioni <xref:System.Data.Common.DataAdapter.FillError> sull'evento, vedere [Gestione degli eventi DataAdapter](handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Vedere anche

- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Comandi e parametri](commands-and-parameters.md)
- [Recupero di informazioni sullo schema del database](retrieving-database-schema-information.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
