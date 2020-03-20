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
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="de4ac-102">Recuperare i dati usando un DataReaderRetrieve data using a DataReader</span><span class="sxs-lookup"><span data-stu-id="de4ac-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="de4ac-103">Per recuperare i dati utilizzando un **DataReader**, creare un'istanza dell'oggetto **Command,** quindi creare un **oggetto DataReader** chiamando **Command.ExecuteReader** per recuperare righe da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="de4ac-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="de4ac-104">Il **DataReader** fornisce un flusso di dati senza buffer che consente alla logica procedurale di elaborare in modo efficiente i risultati da un'origine dati in sequenza.</span><span class="sxs-lookup"><span data-stu-id="de4ac-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="de4ac-105">Il **DataReader** è una buona scelta quando si recuperano grandi quantità di dati perché i dati non sono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="de4ac-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="de4ac-106">Nell'esempio seguente viene illustrato l'utilizzo di un `command` **DataReader**, in cui `reader` rappresenta un DataReader valido e rappresenta un oggetto Command valido.</span><span class="sxs-lookup"><span data-stu-id="de4ac-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="de4ac-107">Utilizzare il metodo **DataReader.Read** per ottenere una riga dai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="de4ac-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="de4ac-108">È possibile accedere a ogni colonna della riga restituita passando il nome o il numero ordinale della colonna a **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="de4ac-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="de4ac-109">Tuttavia, per ottenere prestazioni ottimali, **DataReader** fornisce una serie di metodi che consentono di accedere ai valori delle colonne nei relativi tipi di dati nativi (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**e così via).</span><span class="sxs-lookup"><span data-stu-id="de4ac-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="de4ac-110">Per un elenco dei metodi delle opzioni di accesso <xref:System.Data.OleDb.OleDbDataReader> tipizzate per **DataReader**specifici del provider di dati, vedere e <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="de4ac-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="de4ac-111">L'utilizzo dei metodi della funzione di accesso tipizzato quando si conosce il tipo di dati sottostante riduce la quantità di conversione del tipo necessaria durante il recupero del valore della colonna.</span><span class="sxs-lookup"><span data-stu-id="de4ac-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="de4ac-112">L'esempio seguente scorre un oggetto **DataReader** e restituisce due colonne da ogni riga.</span><span class="sxs-lookup"><span data-stu-id="de4ac-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="de4ac-113">Chiusura dell'oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="de4ac-113">Closing the DataReader</span></span>  
 <span data-ttu-id="de4ac-114">Chiamare sempre il **Close** metodo dopo aver terminato di utilizzare il **DataReader** oggetto.</span><span class="sxs-lookup"><span data-stu-id="de4ac-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="de4ac-115">Se il **comando** contiene parametri di output o valori restituiti, tali valori non sono disponibili fino a quando il **DataReader** viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="de4ac-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="de4ac-116">Mentre un **DataReader** è aperto, il **Connection** è in uso esclusivamente da tale **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="de4ac-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="de4ac-117">Non è possibile eseguire comandi per **Connection**, inclusa la creazione di un altro **DataReader**, fino alla chiusura del **DataReader** originale.</span><span class="sxs-lookup"><span data-stu-id="de4ac-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de4ac-118">Non chiamare **Close** o **Dispose** su un **oggetto Connection**, un **DataReader**o qualsiasi altro oggetto gestito nel metodo **Finalize** della classe.</span><span class="sxs-lookup"><span data-stu-id="de4ac-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="de4ac-119">Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente.</span><span class="sxs-lookup"><span data-stu-id="de4ac-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="de4ac-120">Se la classe non possiede alcuna risorsa non gestita, non includere un metodo **Finalize** nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="de4ac-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="de4ac-121">Per ulteriori informazioni, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="de4ac-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="de4ac-122">Recupero di più set di risultati tramite NextResultRetrieving multiple result sets using NextResult</span><span class="sxs-lookup"><span data-stu-id="de4ac-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="de4ac-123">Se il **DataReader** restituisce più set di risultati, chiamare il **NextResult** metodo per scorrere i set di risultati in sequenza.</span><span class="sxs-lookup"><span data-stu-id="de4ac-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="de4ac-124">Nell'esempio seguente viene illustrata l'elaborazione dei risultati di due dichiarazioni SELECT da parte del tipo <xref:System.Data.SqlClient.SqlDataReader> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="de4ac-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="de4ac-125">Recupero di informazioni sullo schema da DataReaderGetting schema information from the DataReader</span><span class="sxs-lookup"><span data-stu-id="de4ac-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="de4ac-126">Mentre un **DataReader** è aperto, è possibile recuperare le informazioni sullo schema sul set di risultati corrente utilizzando il **GetSchemaTable** metodo.</span><span class="sxs-lookup"><span data-stu-id="de4ac-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="de4ac-127">**GetSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto popolato con righe e colonne che contengono le informazioni sullo schema per il set di risultati corrente.</span><span class="sxs-lookup"><span data-stu-id="de4ac-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="de4ac-128">Il **DataTable** contiene una riga per ogni colonna del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="de4ac-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="de4ac-129">Ogni colonna della tabella dello schema esegue il mapping a una proprietà delle colonne restituite nelle righe del set di risultati, dove **ColumnName** è il nome della proprietà e il valore della colonna è il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="de4ac-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="de4ac-130">Nell'esempio seguente vengono scrivete le informazioni sullo schema per **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="de4ac-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="de4ac-131">Utilizzo dei capitoli OLE DB</span><span class="sxs-lookup"><span data-stu-id="de4ac-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="de4ac-132">È possibile recuperare i set di righe gerarchici o i capitoli (tipo <xref:System.Data.OleDb.OleDbDataReader>OLE DB **DBTYPE_HCHAPTER**, tipo ADO **adChapter**), utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="de4ac-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="de4ac-133">Quando una query che include un capitolo viene restituita come **DataReader**, il capitolo viene restituito come colonna in tale **DataReader** e viene esposto come oggetto **DataReader** .</span><span class="sxs-lookup"><span data-stu-id="de4ac-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="de4ac-134">Il ADO.NET **DataSet** può essere utilizzato anche per rappresentare set di righe gerarchici utilizzando relazioni padre-figlio tra tabelle.</span><span class="sxs-lookup"><span data-stu-id="de4ac-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="de4ac-135">Per ulteriori informazioni, vedere [DataSets, DataTables e DataViews](./dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="de4ac-135">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="de4ac-136">Nell'esempio di codice seguente viene usato il provider MSDataShape per generare una colonna del capitolo contenente gli ordini per ogni cliente presente in un elenco di clienti.</span><span class="sxs-lookup"><span data-stu-id="de4ac-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="de4ac-137">Restituzione dei risultati con Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="de4ac-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="de4ac-138">Con il provider di dati .NET Framework per Oracle è possibile usare i REF CURSOR Oracle per la restituzione del risultato di una query.</span><span class="sxs-lookup"><span data-stu-id="de4ac-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="de4ac-139">I REF CURSOR Oracle vengono restituiti come <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="de4ac-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="de4ac-140">È possibile <xref:System.Data.OracleClient.OracleDataReader> recuperare un oggetto che rappresenta <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> un Oracle REF CURSOR utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="de4ac-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="de4ac-141">È inoltre possibile <xref:System.Data.OracleClient.OracleCommand> specificare un che restituisce uno o più <xref:System.Data.OracleClient.OracleDataAdapter> CHIAMAVA.R <xref:System.Data.DataSet>Oracle REF come **SelectCommand** per un oggetto utilizzato per riempire un oggetto .</span><span class="sxs-lookup"><span data-stu-id="de4ac-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="de4ac-142">Per accedere a un CURSOR REF restituito da <xref:System.Data.OracleClient.OracleCommand> un'origine dati Oracle, creare un oggetto <xref:System.Data.OracleClient.OracleCommand.Parameters> per <xref:System.Data.OracleClient.OracleCommand>la query e aggiungere un parametro di output che faccia riferimento a REF CURSOR alla raccolta dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="de4ac-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="de4ac-143">È necessario che il nome del parametro corrisponda al nome del parametro REF CURSOR della query.</span><span class="sxs-lookup"><span data-stu-id="de4ac-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="de4ac-144">Impostare il tipo <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>del parametro su .</span><span class="sxs-lookup"><span data-stu-id="de4ac-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de4ac-145">Il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo <xref:System.Data.OracleClient.OracleCommand> dell'utente restituisce un <xref:System.Data.OracleClient.OracleDataReader> per il CURSOR REF.</span><span class="sxs-lookup"><span data-stu-id="de4ac-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="de4ac-146">Se <xref:System.Data.OracleClient.OracleCommand> restituisce più REF CURSORS, aggiungere più parametri di output.</span><span class="sxs-lookup"><span data-stu-id="de4ac-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="de4ac-147">È possibile accedere ai diversi REF(ARIE) chiamando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo .</span><span class="sxs-lookup"><span data-stu-id="de4ac-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="de4ac-148">La chiamata <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> a <xref:System.Data.OracleClient.OracleDataReader> restituisce un riferimento al primo CURSOR REF.</span><span class="sxs-lookup"><span data-stu-id="de4ac-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="de4ac-149">È quindi possibile <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> chiamare il metodo per accedere ai REF SUCCESSIVI.</span><span class="sxs-lookup"><span data-stu-id="de4ac-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="de4ac-150">Anche se i <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> parametri nella raccolta corrispondono ai parametri di output REF CURSOR in base al nome, li <xref:System.Data.OracleClient.OracleDataReader> accede nell'ordine in cui sono stati aggiunti alla <xref:System.Data.OracleClient.OracleCommand.Parameters> raccolta.</span><span class="sxs-lookup"><span data-stu-id="de4ac-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="de4ac-151">Si considerino ad esempio il package e il corpo package Oracle seguenti.</span><span class="sxs-lookup"><span data-stu-id="de4ac-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="de4ac-152">Il codice seguente <xref:System.Data.OracleClient.OracleCommand> crea un oggetto che restituisce i REF CURSO <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> dal <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> pacchetto Oracle precedente aggiungendo due parametri di tipo alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="de4ac-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="de4ac-153">Il codice seguente restituisce i risultati <xref:System.Data.OracleClient.OracleDataReader.Read> <xref:System.Data.OracleClient.OracleDataReader.NextResult> del comando <xref:System.Data.OracleClient.OracleDataReader>precedente utilizzando i metodi e dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="de4ac-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="de4ac-154">I parametri REF CURSOR vengono restituiti in ordine.</span><span class="sxs-lookup"><span data-stu-id="de4ac-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="de4ac-155">Nell'esempio seguente viene utilizzato <xref:System.Data.DataSet> il comando precedente per popolare un con i risultati del pacchetto Oracle.</span><span class="sxs-lookup"><span data-stu-id="de4ac-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="de4ac-156">Per evitare **un'eccezione OverflowException**, è consigliabile gestire anche qualsiasi conversione dal tipo <xref:System.Data.DataRow>Oracle NUMBER a un tipo .NET Framework valido prima di archiviare il valore in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="de4ac-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="de4ac-157">È possibile <xref:System.Data.Common.DataAdapter.FillError> utilizzare l'evento per determinare se si è verificata **un'eccezione OverflowException.**</span><span class="sxs-lookup"><span data-stu-id="de4ac-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="de4ac-158">Per ulteriori informazioni <xref:System.Data.Common.DataAdapter.FillError> sull'evento, vedere [Gestione degli eventi DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="de4ac-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4ac-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de4ac-159">See also</span></span>

- [<span data-ttu-id="de4ac-160">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="de4ac-160">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="de4ac-161">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="de4ac-161">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="de4ac-162">Recupero di informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="de4ac-162">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="de4ac-163">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de4ac-163">ADO.NET Overview</span></span>](ado-net-overview.md)
