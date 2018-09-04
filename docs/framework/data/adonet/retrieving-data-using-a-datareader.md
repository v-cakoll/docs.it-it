---
title: Recupero di dati tramite un oggetto DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 4370a7a700a01943548bf067827e6640245caf4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516791"
---
# <a name="retrieving-data-using-a-datareader"></a><span data-ttu-id="c41e0-102">Recupero di dati tramite un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="c41e0-102">Retrieving Data Using a DataReader</span></span>
<span data-ttu-id="c41e0-103">Recupero di dati usando un **DataReader** comporta la creazione di un'istanza del **comando** oggetto e quindi creando un **DataReader** chiamando  **Command. ExecuteReader** per recuperare righe da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c41e0-103">Retrieving data using a **DataReader** involves creating an instance of the **Command** object and then creating a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="c41e0-104">Nell'esempio seguente viene illustrato l'utilizzo un **DataReader** in cui `reader` rappresenta un DataReader valido e `command` rappresenta un oggetto Command valido.</span><span class="sxs-lookup"><span data-stu-id="c41e0-104">The following example illustrates using a **DataReader** where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  
  
```  
reader = command.ExecuteReader();  
```  
  
 <span data-ttu-id="c41e0-105">Si utilizza il **lettura** metodo per il **DataReader** oggetto per ottenere una riga dai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="c41e0-105">You use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span> <span data-ttu-id="c41e0-106">È possibile accedere a ogni colonna della riga restituita passando il nome o il riferimento ordinale della colonna per il **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="c41e0-106">You can access each column of the returned row by passing the name or ordinal reference of the column to the **DataReader**.</span></span> <span data-ttu-id="c41e0-107">Tuttavia, per prestazioni ottimali, il **DataReader** fornisce una serie di metodi che consentono di accedere ai valori di colonna nei tipi di dati nativi (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**e così via).</span><span class="sxs-lookup"><span data-stu-id="c41e0-107">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="c41e0-108">Per un elenco di metodi tipizzati della funzione di accesso per i dati specifici del provider **DataReaders**, vedere <xref:System.Data.OleDb.OleDbDataReader> e <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="c41e0-108">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="c41e0-109">L'utilizzo di metodi di funzioni di accesso tipizzate, quando si conosce il tipo di dati sottostante, riduce il numero di conversioni dei tipi necessari al momento del recupero del valore della colonna.</span><span class="sxs-lookup"><span data-stu-id="c41e0-109">Using the typed accessor methods, assuming the underlying data type is known, reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c41e0-110">La versione di Windows Server 2003 di .NET Framework include una proprietà aggiuntiva per i **DataReader**, **HasRows**, che consente di determinare se il **DataReader**ha restituito risultati prima di leggerli da quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="c41e0-110">The Windows Server 2003 release of the .NET Framework includes an additional property for the **DataReader**, **HasRows**, which enables you to determine if the **DataReader** has returned any results before reading from it.</span></span>  
  
 <span data-ttu-id="c41e0-111">Esempio di codice seguente esegue l'iterazione attraverso un **DataReader** oggetto e restituisce due colonne di ogni riga.</span><span class="sxs-lookup"><span data-stu-id="c41e0-111">The following code example iterates through a **DataReader** object, and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 <span data-ttu-id="c41e0-112">Il **DataReader** fornisce un flusso non memorizzato nel buffer di dati che consente una logica procedurale di elaborare sequenzialmente risultati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c41e0-112">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="c41e0-113">Il **DataReader** è una scelta ottimale quando si recuperano grandi quantità di dati perché i dati non viene memorizzato nella cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="c41e0-113">The **DataReader** is a good choice when retrieving large amounts of data because the data is not cached in memory.</span></span>  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="c41e0-114">Chiusura dell'oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="c41e0-114">Closing the DataReader</span></span>  
 <span data-ttu-id="c41e0-115">È necessario chiamare sempre il **Chiudi** metodo dopo aver utilizzando il **DataReader** oggetto.</span><span class="sxs-lookup"><span data-stu-id="c41e0-115">You should always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="c41e0-116">Se il **comando** contiene output parametri o valori restituiti, non saranno disponibili finché il **DataReader** viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="c41e0-116">If your **Command** contains output parameters or return values, they will not be available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="c41e0-117">Si noti che, anche se un **DataReader** è aperto, il **connessione** è usato esclusivamente dal **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="c41e0-117">Note that while a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="c41e0-118">Non è possibile eseguire alcun comando per il **connessione**, inclusa la creazione di un'altra **DataReader**, finché l'originale **DataReader** viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="c41e0-118">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c41e0-119">Non chiamare **Close** o **Dispose** in un **connessione**, un **DataReader**, o qualsiasi altro oggetto gestito nel **Finalize**  metodo della classe.</span><span class="sxs-lookup"><span data-stu-id="c41e0-119">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="c41e0-120">Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente.</span><span class="sxs-lookup"><span data-stu-id="c41e0-120">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="c41e0-121">Se la classe non è proprietario delle risorse non gestite, non includere un **Finalize** metodo nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="c41e0-121">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="c41e0-122">Per altre informazioni, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="c41e0-122">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="c41e0-123">Recupero di più set di risultati tramite NextResult</span><span class="sxs-lookup"><span data-stu-id="c41e0-123">Retrieving Multiple Result Sets using NextResult</span></span>  
 <span data-ttu-id="c41e0-124">Se vengono restituiti più set di risultati, il **DataReader** fornisce le **NextResult** Imposta metodo per scorrere il risultato in ordine.</span><span class="sxs-lookup"><span data-stu-id="c41e0-124">If multiple result sets are returned, the **DataReader** provides the **NextResult** method to iterate through the result sets in order.</span></span> <span data-ttu-id="c41e0-125">Nell'esempio seguente viene illustrata l'elaborazione dei risultati di due dichiarazioni SELECT da parte del tipo <xref:System.Data.SqlClient.SqlDataReader> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="c41e0-125">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="c41e0-126">Recupero di informazioni sullo schema dall'oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="c41e0-126">Getting Schema Information from the DataReader</span></span>  
 <span data-ttu-id="c41e0-127">Mentre un **DataReader** è aperto, è possibile recuperare le informazioni sullo schema relative al risultato corrente impostato utilizzando il **GetSchemaTable** (metodo).</span><span class="sxs-lookup"><span data-stu-id="c41e0-127">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="c41e0-128">**GetSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto compilato con righe e colonne che contengono le informazioni sullo schema per il set di risultati corrente.</span><span class="sxs-lookup"><span data-stu-id="c41e0-128">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="c41e0-129">Il **DataTable** contiene una riga per ogni colonna del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="c41e0-129">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="c41e0-130">Ogni colonna della riga della tabella dello schema è mappata a una proprietà della colonna restituita nel set di risultati, in cui il **ColumnName** è il nome della proprietà e il valore della colonna è il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c41e0-130">Each column of the schema table row maps to a property of the column returned in the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="c41e0-131">L'esempio di codice seguente scrive le informazioni sullo schema per **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="c41e0-131">The following code example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="c41e0-132">Utilizzo dei capitoli OLE DB</span><span class="sxs-lookup"><span data-stu-id="c41e0-132">Working with OLE DB Chapters</span></span>  
 <span data-ttu-id="c41e0-133">Set di righe gerarchici, o capitoli (tipo OLE DB **DBTYPE_HCHAPTER**, tipo ADO **adChapter**) può essere recuperato tramite il <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="c41e0-133">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**) can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="c41e0-134">Quando una query che include un capitolo viene restituita come un **DataReader**, il capitolo viene restituito come una colonna in cui **DataReader** e viene esposto come un **DataReader** oggetto.</span><span class="sxs-lookup"><span data-stu-id="c41e0-134">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="c41e0-135">ADO.NET **set di dati** possono essere usati anche per rappresentare rowset gerarchici usando relazioni padre-figlio tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="c41e0-135">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets using parent-child relationships between tables.</span></span> <span data-ttu-id="c41e0-136">Per altre informazioni, vedere [DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="c41e0-136">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="c41e0-137">Nell'esempio di codice seguente viene usato il provider MSDataShape per generare una colonna del capitolo contenente gli ordini per ogni cliente presente in un elenco di clienti.</span><span class="sxs-lookup"><span data-stu-id="c41e0-137">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="c41e0-138">Restituzione di risultati con i REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="c41e0-138">Returning Results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="c41e0-139">Con il provider di dati .NET Framework per Oracle è possibile usare i REF CURSOR Oracle per la restituzione del risultato di una query.</span><span class="sxs-lookup"><span data-stu-id="c41e0-139">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="c41e0-140">I REF CURSOR Oracle vengono restituiti come <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="c41e0-140">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="c41e0-141">È possibile recuperare un **OracleDataReader** oggetto, che rappresenta un REF CURSOR Oracle usando la <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> metodo ed è inoltre possibile specificare un <xref:System.Data.OracleClient.OracleCommand> che restituisce uno o più oggetti REF CURSOR Oracle come il  **SelectCommand** per un <xref:System.Data.OracleClient.OracleDataAdapter> utilizzato per riempire un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c41e0-141">You can retrieve an **OracleDataReader** object, that represents an Oracle REF CURSOR using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method, and you can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="c41e0-142">Per accedere a un REF CURSOR restituito da un'origine dati Oracle, creare un **OracleCommand** per la query e aggiungere un parametro di output che fa riferimento al REF CURSOR alle **parametri** raccolta del  **OracleCommand**.</span><span class="sxs-lookup"><span data-stu-id="c41e0-142">To access a REF CURSOR returned from an Oracle data source, create an **OracleCommand** for your query and add an output parameter that references the REF CURSOR to the **Parameters** collection of your **OracleCommand**.</span></span> <span data-ttu-id="c41e0-143">È necessario che il nome del parametro corrisponda al nome del parametro REF CURSOR della query.</span><span class="sxs-lookup"><span data-stu-id="c41e0-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="c41e0-144">Impostare il tipo del parametro da **OracleType. Cursor**.</span><span class="sxs-lookup"><span data-stu-id="c41e0-144">Set the type of the parameter to **OracleType.Cursor**.</span></span> <span data-ttu-id="c41e0-145">Il **ExecuteReader** metodo le **OracleCommand** restituirà un' **OracleDataReader** per il REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="c41e0-145">The **ExecuteReader** method of your **OracleCommand** will return an **OracleDataReader** for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="c41e0-146">Se il **OracleCommand** restituisce più REF CURSOR, aggiungere più parametri di output.</span><span class="sxs-lookup"><span data-stu-id="c41e0-146">If your **OracleCommand** returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="c41e0-147">È possibile accedere ai diversi REF CURSOR chiamando il **OracleCommand** (metodo).</span><span class="sxs-lookup"><span data-stu-id="c41e0-147">You can access the different REF CURSORs by calling the **OracleCommand.ExecuteReader** method.</span></span> <span data-ttu-id="c41e0-148">La chiamata a **ExecuteReader** restituisce un **OracleDataReader** che fa riferimento al primo REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="c41e0-148">The call to **ExecuteReader** returns an **OracleDataReader** referencing the first REF CURSOR.</span></span> <span data-ttu-id="c41e0-149">È quindi possibile chiamare il **OracleDataReader. NextResult** metodo per accedere ai REF CURSOR successivi.</span><span class="sxs-lookup"><span data-stu-id="c41e0-149">You can then call the **OracleDataReader.NextResult** method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="c41e0-150">Anche se i parametri in di **OracleCommand** raccolta corrispondono al REF CURSOR i parametri di output in base al nome, il **OracleDataReader** accede alle variabili nell'ordine in cui sono stati aggiunti per il  **Parametri** raccolta.</span><span class="sxs-lookup"><span data-stu-id="c41e0-150">Although the parameters in your **OracleCommand.Parameters** collection match the REF CURSOR output parameters by name, the **OracleDataReader** accesses them in the order that they were added to the **Parameters** collection.</span></span>  
  
 <span data-ttu-id="c41e0-151">Si considerino ad esempio il package e il corpo package Oracle seguenti.</span><span class="sxs-lookup"><span data-stu-id="c41e0-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="c41e0-152">Il codice seguente crea un **OracleCommand** che restituisce i REF CURSOR dal package Oracle precedente tramite l'aggiunta di due parametri di tipo **OracleType. Cursor** per il **parametri** collection.</span><span class="sxs-lookup"><span data-stu-id="c41e0-152">The following code creates an **OracleCommand** that returns the REF CURSORs from the previous Oracle package by adding two parameters of type **OracleType.Cursor** to the **Parameters** collection.</span></span>  
  
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
  
 <span data-ttu-id="c41e0-153">Il codice seguente restituisce i risultati del comando precedente tramite il **Read** e **NextResult** metodi del **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="c41e0-153">The following code returns the results of the previous command using the **Read** and **NextResult** methods of the **OracleDataReader**.</span></span> <span data-ttu-id="c41e0-154">I parametri REF CURSOR vengono restituiti in ordine.</span><span class="sxs-lookup"><span data-stu-id="c41e0-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="c41e0-155">L'esempio seguente usa il comando precedente per popolare una **set di dati** con i risultati del package Oracle.</span><span class="sxs-lookup"><span data-stu-id="c41e0-155">The following example uses the previous command to populate a **DataSet** with the results of the Oracle package.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c41e0-156">Per evitare un' **OverflowException**, si consiglia di gestire le conversioni dal tipo NUMBER Oracle in un tipo .NET Framework valido prima di archiviare i valori in un **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="c41e0-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a **DataRow**.</span></span> <span data-ttu-id="c41e0-157">È possibile usare la **FillError** evento per determinare se un' **OverflowException** si è verificato.</span><span class="sxs-lookup"><span data-stu-id="c41e0-157">You can use the **FillError** event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="c41e0-158">Per altre informazioni sul **FillError** eventi, vedere [gestione degli eventi DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="c41e0-158">For more information on the **FillError** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c41e0-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c41e0-159">See Also</span></span>  
 [<span data-ttu-id="c41e0-160">Utilizzo di DataReader</span><span class="sxs-lookup"><span data-stu-id="c41e0-160">Working with DataReaders</span></span>](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="c41e0-161">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="c41e0-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="c41e0-162">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="c41e0-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="c41e0-163">Recupero di informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="c41e0-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="c41e0-164">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c41e0-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
