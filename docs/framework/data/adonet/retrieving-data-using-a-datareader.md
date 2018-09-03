---
title: Recupero di dati tramite un oggetto DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 4370a7a700a01943548bf067827e6640245caf4e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482164"
---
# <a name="retrieving-data-using-a-datareader"></a>Recupero di dati tramite un oggetto DataReader
Recupero di dati usando un **DataReader** comporta la creazione di un'istanza del **comando** oggetto e quindi creando un **DataReader** chiamando  **Command. ExecuteReader** per recuperare righe da un'origine dati. Nell'esempio seguente viene illustrato l'utilizzo un **DataReader** in cui `reader` rappresenta un DataReader valido e `command` rappresenta un oggetto Command valido.  
  
```  
reader = command.ExecuteReader();  
```  
  
 Si utilizza il **lettura** metodo per il **DataReader** oggetto per ottenere una riga dai risultati della query. È possibile accedere a ogni colonna della riga restituita passando il nome o il riferimento ordinale della colonna per il **DataReader**. Tuttavia, per prestazioni ottimali, il **DataReader** fornisce una serie di metodi che consentono di accedere ai valori di colonna nei tipi di dati nativi (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**e così via). Per un elenco di metodi tipizzati della funzione di accesso per i dati specifici del provider **DataReaders**, vedere <xref:System.Data.OleDb.OleDbDataReader> e <xref:System.Data.SqlClient.SqlDataReader>. L'utilizzo di metodi di funzioni di accesso tipizzate, quando si conosce il tipo di dati sottostante, riduce il numero di conversioni dei tipi necessari al momento del recupero del valore della colonna.  
  
> [!NOTE]
>  La versione di Windows Server 2003 di .NET Framework include una proprietà aggiuntiva per i **DataReader**, **HasRows**, che consente di determinare se il **DataReader**ha restituito risultati prima di leggerli da quest'ultimo.  
  
 Esempio di codice seguente esegue l'iterazione attraverso un **DataReader** oggetto e restituisce due colonne di ogni riga.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 Il **DataReader** fornisce un flusso non memorizzato nel buffer di dati che consente una logica procedurale di elaborare sequenzialmente risultati da un'origine dati. Il **DataReader** è una scelta ottimale quando si recuperano grandi quantità di dati perché i dati non viene memorizzato nella cache in memoria.  
  
## <a name="closing-the-datareader"></a>Chiusura dell'oggetto DataReader  
 È necessario chiamare sempre il **Chiudi** metodo dopo aver utilizzando il **DataReader** oggetto.  
  
 Se il **comando** contiene output parametri o valori restituiti, non saranno disponibili finché il **DataReader** viene chiuso.  
  
 Si noti che, anche se un **DataReader** è aperto, il **connessione** è usato esclusivamente dal **DataReader**. Non è possibile eseguire alcun comando per il **connessione**, inclusa la creazione di un'altra **DataReader**, finché l'originale **DataReader** viene chiuso.  
  
> [!NOTE]
>  Non chiamare **Close** o **Dispose** in un **connessione**, un **DataReader**, o qualsiasi altro oggetto gestito nel **Finalize**  metodo della classe. Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente. Se la classe non è proprietario delle risorse non gestite, non includere un **Finalize** metodo nella definizione della classe. Per altre informazioni, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Recupero di più set di risultati tramite NextResult  
 Se vengono restituiti più set di risultati, il **DataReader** fornisce le **NextResult** Imposta metodo per scorrere il risultato in ordine. Nell'esempio seguente viene illustrata l'elaborazione dei risultati di due dichiarazioni SELECT da parte del tipo <xref:System.Data.SqlClient.SqlDataReader> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Recupero di informazioni sullo schema dall'oggetto DataReader  
 Mentre un **DataReader** è aperto, è possibile recuperare le informazioni sullo schema relative al risultato corrente impostato utilizzando il **GetSchemaTable** (metodo). **GetSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto compilato con righe e colonne che contengono le informazioni sullo schema per il set di risultati corrente. Il **DataTable** contiene una riga per ogni colonna del set di risultati. Ogni colonna della riga della tabella dello schema è mappata a una proprietà della colonna restituita nel set di risultati, in cui il **ColumnName** è il nome della proprietà e il valore della colonna è il valore della proprietà. L'esempio di codice seguente scrive le informazioni sullo schema per **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Utilizzo dei capitoli OLE DB  
 Set di righe gerarchici, o capitoli (tipo OLE DB **DBTYPE_HCHAPTER**, tipo ADO **adChapter**) può essere recuperato tramite il <xref:System.Data.OleDb.OleDbDataReader>. Quando una query che include un capitolo viene restituita come un **DataReader**, il capitolo viene restituito come una colonna in cui **DataReader** e viene esposto come un **DataReader** oggetto.  
  
 ADO.NET **set di dati** possono essere usati anche per rappresentare rowset gerarchici usando relazioni padre-figlio tra le tabelle. Per altre informazioni, vedere [DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 Nell'esempio di codice seguente viene usato il provider MSDataShape per generare una colonna del capitolo contenente gli ordini per ogni cliente presente in un elenco di clienti.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Restituzione di risultati con i REF CURSOR Oracle  
 Con il provider di dati .NET Framework per Oracle è possibile usare i REF CURSOR Oracle per la restituzione del risultato di una query. I REF CURSOR Oracle vengono restituiti come <xref:System.Data.OracleClient.OracleDataReader>.  
  
 È possibile recuperare un **OracleDataReader** oggetto, che rappresenta un REF CURSOR Oracle usando la <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> metodo ed è inoltre possibile specificare un <xref:System.Data.OracleClient.OracleCommand> che restituisce uno o più oggetti REF CURSOR Oracle come il  **SelectCommand** per un <xref:System.Data.OracleClient.OracleDataAdapter> utilizzato per riempire un <xref:System.Data.DataSet>.  
  
 Per accedere a un REF CURSOR restituito da un'origine dati Oracle, creare un **OracleCommand** per la query e aggiungere un parametro di output che fa riferimento al REF CURSOR alle **parametri** raccolta del  **OracleCommand**. È necessario che il nome del parametro corrisponda al nome del parametro REF CURSOR della query. Impostare il tipo del parametro da **OracleType. Cursor**. Il **ExecuteReader** metodo le **OracleCommand** restituirà un' **OracleDataReader** per il REF CURSOR.  
  
 Se il **OracleCommand** restituisce più REF CURSOR, aggiungere più parametri di output. È possibile accedere ai diversi REF CURSOR chiamando il **OracleCommand** (metodo). La chiamata a **ExecuteReader** restituisce un **OracleDataReader** che fa riferimento al primo REF CURSOR. È quindi possibile chiamare il **OracleDataReader. NextResult** metodo per accedere ai REF CURSOR successivi. Anche se i parametri in di **OracleCommand** raccolta corrispondono al REF CURSOR i parametri di output in base al nome, il **OracleDataReader** accede alle variabili nell'ordine in cui sono stati aggiunti per il  **Parametri** raccolta.  
  
 Si considerino ad esempio il package e il corpo package Oracle seguenti.  
  
```  
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
  
 Il codice seguente crea un **OracleCommand** che restituisce i REF CURSOR dal package Oracle precedente tramite l'aggiunta di due parametri di tipo **OracleType. Cursor** per il **parametri** collection.  
  
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
  
 Il codice seguente restituisce i risultati del comando precedente tramite il **Read** e **NextResult** metodi del **OracleDataReader**. I parametri REF CURSOR vengono restituiti in ordine.  
  
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
  
 L'esempio seguente usa il comando precedente per popolare una **set di dati** con i risultati del package Oracle.  
  
> [!NOTE]
>  Per evitare un' **OverflowException**, si consiglia di gestire le conversioni dal tipo NUMBER Oracle in un tipo .NET Framework valido prima di archiviare i valori in un **DataRow**. È possibile usare la **FillError** evento per determinare se un' **OverflowException** si è verificato. Per altre informazioni sul **FillError** eventi, vedere [gestione degli eventi DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di DataReader](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Recupero di informazioni sullo schema del database](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
