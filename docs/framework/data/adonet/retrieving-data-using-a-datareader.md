---
title: Recupero di dati tramite un oggetto DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 75d1dba6678be0bfa45be5f3e60e8e76f80a7e9e
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083847"
---
# <a name="retrieve-data-using-a-datareader"></a>Recuperare i dati tramite un oggetto DataReader
Per recuperare dati usando un **DataReader**, creare un'istanza del **comando** dell'oggetto e quindi creare un **DataReader** chiamando **Command. ExecuteReader**  per recuperare righe da un'origine dati. Il **DataReader** fornisce un flusso non memorizzato nel buffer di dati che consente una logica procedurale di elaborare sequenzialmente risultati da un'origine dati. Il **DataReader** è un'ottima scelta quando si recuperano grandi quantità di dati perché i dati non viene memorizzato nella cache in memoria.

Nell'esempio seguente viene illustrato l'utilizzo un **DataReader**, dove `reader` rappresenta un DataReader valido e `command` rappresenta un oggetto Command valido.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Usare la **DataReader. Read** metodo per ottenere una riga dai risultati della query. È possibile accedere a ogni colonna della riga restituita passando il nome o numero ordinale della colonna per il **DataReader**. Tuttavia, per prestazioni ottimali, il **DataReader** fornisce una serie di metodi che consentono di accedere ai valori di colonna nei tipi di dati nativi (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**e così via). Per un elenco di metodi tipizzati della funzione di accesso per i dati specifici del provider **DataReaders**, vedere <xref:System.Data.OleDb.OleDbDataReader> e <xref:System.Data.SqlClient.SqlDataReader>. Usando i metodi tipizzati della funzione di accesso quando si conoscono i dati sottostanti tipo riduce la quantità di conversione del tipo richiesto quando si recupera il valore della colonna.  
  
 L'esempio seguente scorrere una **DataReader** specificato e restituisce due colonne di ogni riga.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Chiusura dell'oggetto DataReader  
 Chiamare sempre il **Close** metodo dopo aver usando la **DataReader** oggetto.  
  
 Se il **comando** è contenuto l'output parametri o valori restituiti, questi valori non sono disponibili solo le **DataReader** viene chiuso.  
  
 Mentre un **DataReader** è aperto, il **connessione** è usato esclusivamente dal **DataReader**. Non è possibile eseguire alcun comando per il **connessione**, inclusa la creazione di un'altra **DataReader**, finché l'originale **DataReader** viene chiuso.  
  
> [!NOTE]
>  Non chiamare **Close** o **Dispose** in un **connessione**, un **DataReader**, o qualsiasi altro oggetto gestito nel **Finalize**  metodo della classe. Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente. Se la classe non è proprietario delle risorse non gestite, non includere un **Finalize** metodo nella definizione della classe. Per altre informazioni, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Il recupero di risultati multipli imposta tramite NextResult  
 Se il **DataReader** restituisce più set di risultati, chiamata il **NextResult** metodo per scorrere il risultato è imposta in modo sequenziale. Nell'esempio seguente viene illustrata l'elaborazione dei risultati di due dichiarazioni SELECT da parte del tipo <xref:System.Data.SqlClient.SqlDataReader> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Recupero di informazioni sullo schema da DataReader  
 Mentre un **DataReader** è aperto, è possibile recuperare le informazioni sullo schema relative al risultato corrente impostato utilizzando il **GetSchemaTable** (metodo). **GetSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto compilato con righe e colonne che contengono le informazioni sullo schema per il set di risultati corrente. Il **DataTable** contiene una riga per ogni colonna del set di risultati. Esegue il mapping di ogni colonna della tabella dello schema a una proprietà delle colonne restituite nel set di righe del risultato, in cui il **ColumnName** è il nome della proprietà e il valore della colonna è il valore della proprietà. L'esempio seguente scrive le informazioni sullo schema per **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Utilizzo con capitoli OLE DB  
 Set di righe gerarchici, o capitoli (tipo OLE DB **DBTYPE_HCHAPTER**, tipo ADO **adChapter**), può essere recuperato tramite il <xref:System.Data.OleDb.OleDbDataReader>. Quando una query che include un capitolo viene restituita come un **DataReader**, il capitolo viene restituito come una colonna in cui **DataReader** e viene esposto come un **DataReader** oggetto.  
  
 ADO.NET **set di dati** può anche essere utilizzato per rappresentare rowset gerarchici usando relazioni padre-figlio tra le tabelle. Per altre informazioni, vedere [DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Restituzione di risultati con i REF CURSOR Oracle  
 Con il provider di dati .NET Framework per Oracle è possibile usare i REF CURSOR Oracle per la restituzione del risultato di una query. I REF CURSOR Oracle vengono restituiti come <xref:System.Data.OracleClient.OracleDataReader>.  
  
 È possibile recuperare un <xref:System.Data.OracleClient.OracleDataReader> oggetto che rappresenta un REF CURSOR Oracle usando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> (metodo). È inoltre possibile specificare una <xref:System.Data.OracleClient.OracleCommand> che restituisce uno o più oggetti REF CURSOR Oracle come i **SelectCommand** per un' <xref:System.Data.OracleClient.OracleDataAdapter> usato per riempire un <xref:System.Data.DataSet>.  
  
 Per accedere a un REF CURSOR restituito da un'origine dati Oracle, creare un <xref:System.Data.OracleClient.OracleCommand> per la query e aggiungere un parametro di output che fa riferimento al REF CURSOR al <xref:System.Data.OracleClient.OracleCommand.Parameters> insieme del <xref:System.Data.OracleClient.OracleCommand>. È necessario che il nome del parametro corrisponda al nome del parametro REF CURSOR della query. Impostare il tipo del parametro da <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>. Il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo per il <xref:System.Data.OracleClient.OracleCommand> restituisce un <xref:System.Data.OracleClient.OracleDataReader> per il REF CURSOR.  
  
 Se il <xref:System.Data.OracleClient.OracleCommand> restituisce più REF CURSOR, aggiungere più parametri di output. È possibile accedere ai diversi REF CURSOR chiamando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> (metodo). La chiamata a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> restituisce un <xref:System.Data.OracleClient.OracleDataReader> che fa riferimento al primo REF CURSOR. È quindi possibile chiamare il <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> metodo per accedere ai REF CURSOR successivi. Anche se i parametri in di <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> raccolta corrispondono al REF CURSOR i parametri di output in base al nome, il <xref:System.Data.OracleClient.OracleDataReader> accede alle variabili nell'ordine in cui sono stati aggiunti al <xref:System.Data.OracleClient.OracleCommand.Parameters> raccolta.  
  
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
  
 Il codice seguente crea un <xref:System.Data.OracleClient.OracleCommand> che restituisce i REF CURSOR dal package Oracle precedente tramite l'aggiunta di due parametri di tipo <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> per il <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> raccolta.  
  
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
  
 Il codice seguente restituisce i risultati del comando precedente tramite il <xref:System.Data.OracleClient.OracleDataReader.Read> e <xref:System.Data.OracleClient.OracleDataReader.NextResult> metodi del <xref:System.Data.OracleClient.OracleDataReader>. I parametri REF CURSOR vengono restituiti in ordine.  
  
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
  
 L'esempio seguente usa il comando precedente per popolare un <xref:System.Data.DataSet> con i risultati del package Oracle.  
  
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
>  Per evitare un' **OverflowException**, si consiglia di gestire le conversioni dal tipo NUMBER Oracle in un tipo .NET Framework valido prima di archiviare i valori in un <xref:System.Data.DataRow>. È possibile usare la <xref:System.Data.Common.DataAdapter.FillError> evento per determinare se un' **OverflowException** si è verificato. Per altre informazioni sul <xref:System.Data.Common.DataAdapter.FillError> eventi, vedere [la gestione degli eventi DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Vedere anche
- [Utilizzo di DataReader](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)
- [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Recupero di informazioni sullo schema del database](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
