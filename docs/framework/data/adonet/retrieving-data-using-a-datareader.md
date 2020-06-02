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
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="eba7b-104">Recuperare i dati usando un DataReader</span><span class="sxs-lookup"><span data-stu-id="eba7b-104">Retrieve data using a DataReader</span></span>
<span data-ttu-id="eba7b-105">Per recuperare i dati usando un **DataReader**, creare un'istanza dell'oggetto **Command** e quindi creare un **DataReader** chiamando **Command. ExecuteReader** per recuperare le righe da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="eba7b-105">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="eba7b-106">**DataReader** fornisce un flusso di dati non memorizzato nel buffer che consente alla logica procedurale di elaborare in modo efficiente i risultati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="eba7b-106">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="eba7b-107">Il **DataReader** è una scelta ottimale quando si recuperano grandi quantità di dati perché i dati non vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="eba7b-107">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="eba7b-108">Nell'esempio seguente viene illustrato l'utilizzo di un **DataReader**, dove `reader` rappresenta un DataReader valido e `command` rappresenta un oggetto comando valido.</span><span class="sxs-lookup"><span data-stu-id="eba7b-108">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="eba7b-109">Utilizzare il metodo **DataReader. Read** per ottenere una riga dai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="eba7b-109">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="eba7b-110">È possibile accedere a ogni colonna della riga restituita passando il nome o il numero ordinale della colonna a **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="eba7b-110">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="eba7b-111">Tuttavia, per ottenere prestazioni ottimali, **DataReader** fornisce una serie di metodi che consentono di accedere ai valori delle colonne nei tipi di dati nativi (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**e così via).</span><span class="sxs-lookup"><span data-stu-id="eba7b-111">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="eba7b-112">Per un elenco di metodi tipizzati della funzione di accesso per i data **Reader**specifici del provider di dati, vedere <xref:System.Data.OleDb.OleDbDataReader> e <xref:System.Data.SqlClient.SqlDataReader> .</span><span class="sxs-lookup"><span data-stu-id="eba7b-112">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="eba7b-113">Utilizzando i metodi tipizzati della funzione di accesso quando si conosce il tipo di dati sottostante, è possibile ridurre la quantità di conversione del tipo necessaria durante il recupero del valore della colonna.</span><span class="sxs-lookup"><span data-stu-id="eba7b-113">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="eba7b-114">Nell'esempio seguente viene eseguita l'iterazione di un oggetto **DataReader** e vengono restituite due colonne da ogni riga.</span><span class="sxs-lookup"><span data-stu-id="eba7b-114">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="eba7b-115">Chiusura dell'oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="eba7b-115">Closing the DataReader</span></span>  
 <span data-ttu-id="eba7b-116">Al termine dell'utilizzo dell'oggetto **DataReader** , chiamare sempre il metodo **Close** .</span><span class="sxs-lookup"><span data-stu-id="eba7b-116">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="eba7b-117">Se il **comando** contiene parametri di output o valori restituiti, tali valori non saranno disponibili fino alla chiusura del **DataReader** .</span><span class="sxs-lookup"><span data-stu-id="eba7b-117">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="eba7b-118">Mentre un **DataReader** è aperto, la **connessione** viene utilizzata esclusivamente da tale **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="eba7b-118">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="eba7b-119">Non è possibile eseguire alcun comando per la **connessione**, inclusa la creazione di un altro **DataReader**, fino alla chiusura del **DataReader** originale.</span><span class="sxs-lookup"><span data-stu-id="eba7b-119">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eba7b-120">Non chiamare **Close** o **Dispose** per una **connessione**, un **DataReader**o qualsiasi altro oggetto gestito nel metodo **Finalize** della classe.</span><span class="sxs-lookup"><span data-stu-id="eba7b-120">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="eba7b-121">Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente.</span><span class="sxs-lookup"><span data-stu-id="eba7b-121">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="eba7b-122">Se la classe non è proprietaria di risorse non gestite, non includere un metodo **Finalize** nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="eba7b-122">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="eba7b-123">Per altre informazioni, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="eba7b-123">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="eba7b-124">Recupero di più set di risultati con NextResult</span><span class="sxs-lookup"><span data-stu-id="eba7b-124">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="eba7b-125">Se **DataReader** restituisce più set di risultati, chiamare il metodo **NextResult** per scorrere i set di risultati in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="eba7b-125">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="eba7b-126">Nell'esempio seguente viene illustrata l'elaborazione dei risultati di due dichiarazioni SELECT da parte del tipo <xref:System.Data.SqlClient.SqlDataReader> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="eba7b-126">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="eba7b-127">Recupero delle informazioni sullo schema dal DataReader</span><span class="sxs-lookup"><span data-stu-id="eba7b-127">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="eba7b-128">Mentre un **DataReader** è aperto, è possibile recuperare le informazioni sullo schema relative al set di risultati corrente usando il metodo **GetSchemaTable** .</span><span class="sxs-lookup"><span data-stu-id="eba7b-128">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="eba7b-129">**GetSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto popolato con righe e colonne che contengono le informazioni sullo schema per il set di risultati corrente.</span><span class="sxs-lookup"><span data-stu-id="eba7b-129">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="eba7b-130">Il **DataTable** contiene una riga per ogni colonna del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="eba7b-130">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="eba7b-131">Ogni colonna della tabella dello schema è mappata a una proprietà delle colonne restituite nelle righe del set di risultati, dove **ColumnName** è il nome della proprietà e il valore della colonna è il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="eba7b-131">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="eba7b-132">Nell'esempio seguente vengono scritte le informazioni sullo schema per **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="eba7b-132">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="eba7b-133">Uso dei capitoli OLE DB</span><span class="sxs-lookup"><span data-stu-id="eba7b-133">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="eba7b-134">I set di righe gerarchici, o capitoli (tipo OLE DB **DBTYPE_HCHAPTER**, tipo ADO **adChapter**), possono essere recuperati utilizzando <xref:System.Data.OleDb.OleDbDataReader> .</span><span class="sxs-lookup"><span data-stu-id="eba7b-134">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="eba7b-135">Quando una query che include un capitolo viene restituita come **DataReader**, il capitolo viene restituito come una colonna nel **DataReader** e viene esposto come oggetto **DataReader** .</span><span class="sxs-lookup"><span data-stu-id="eba7b-135">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="eba7b-136">Il **set di dati** ADO.NET può essere utilizzato anche per rappresentare i set di righe gerarchici utilizzando le relazioni padre-figlio tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="eba7b-136">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="eba7b-137">Per ulteriori informazioni, vedere [DataSet, DataTable e DataViews](./dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="eba7b-137">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="eba7b-138">Nell'esempio di codice seguente viene usato il provider MSDataShape per generare una colonna del capitolo contenente gli ordini per ogni cliente presente in un elenco di clienti.</span><span class="sxs-lookup"><span data-stu-id="eba7b-138">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="eba7b-139">Restituzione di risultati con CURSORi REF Oracle</span><span class="sxs-lookup"><span data-stu-id="eba7b-139">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="eba7b-140">Con il provider di dati .NET Framework per Oracle è possibile usare i REF CURSOR Oracle per la restituzione del risultato di una query.</span><span class="sxs-lookup"><span data-stu-id="eba7b-140">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="eba7b-141">I REF CURSOR Oracle vengono restituiti come <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="eba7b-141">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="eba7b-142">È possibile recuperare un <xref:System.Data.OracleClient.OracleDataReader> oggetto che rappresenta un REF CURSOR Oracle utilizzando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="eba7b-142">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="eba7b-143">È inoltre possibile specificare un oggetto <xref:System.Data.OracleClient.OracleCommand> che restituisce uno o più REF CURSOR Oracle come **SelectCommand** per un oggetto <xref:System.Data.OracleClient.OracleDataAdapter> utilizzato per riempire un oggetto <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="eba7b-143">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="eba7b-144">Per accedere a un cursore REF restituito da un'origine dati Oracle, creare un oggetto <xref:System.Data.OracleClient.OracleCommand> per la query e aggiungere un parametro di output che fa riferimento al cursore Ref alla <xref:System.Data.OracleClient.OracleCommand.Parameters> raccolta di <xref:System.Data.OracleClient.OracleCommand> .</span><span class="sxs-lookup"><span data-stu-id="eba7b-144">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="eba7b-145">È necessario che il nome del parametro corrisponda al nome del parametro REF CURSOR della query.</span><span class="sxs-lookup"><span data-stu-id="eba7b-145">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="eba7b-146">Impostare il tipo del parametro su <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="eba7b-146">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eba7b-147">Il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo di <xref:System.Data.OracleClient.OracleCommand> restituisce un oggetto <xref:System.Data.OracleClient.OracleDataReader> per il cursore Ref.</span><span class="sxs-lookup"><span data-stu-id="eba7b-147">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="eba7b-148">Se <xref:System.Data.OracleClient.OracleCommand> restituisce più cursori Ref, aggiungere più parametri di output.</span><span class="sxs-lookup"><span data-stu-id="eba7b-148">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="eba7b-149">È possibile accedere ai diversi CURSORi REF chiamando il <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="eba7b-149">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="eba7b-150">La chiamata a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> restituisce un oggetto che fa <xref:System.Data.OracleClient.OracleDataReader> riferimento al primo REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="eba7b-150">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="eba7b-151">È quindi possibile chiamare il <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> metodo per accedere ai cursori Ref successivi.</span><span class="sxs-lookup"><span data-stu-id="eba7b-151">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="eba7b-152">Sebbene i parametri nella <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> raccolta corrispondano ai parametri di output di REF CURSOR in base al nome, il <xref:System.Data.OracleClient.OracleDataReader> accede a tali parametri nell'ordine in cui sono stati aggiunti alla <xref:System.Data.OracleClient.OracleCommand.Parameters> raccolta.</span><span class="sxs-lookup"><span data-stu-id="eba7b-152">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="eba7b-153">Si considerino ad esempio il package e il corpo package Oracle seguenti.</span><span class="sxs-lookup"><span data-stu-id="eba7b-153">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="eba7b-154">Il codice seguente crea un oggetto <xref:System.Data.OracleClient.OracleCommand> che restituisce i REF CURSOR dal pacchetto Oracle precedente aggiungendo due parametri di tipo <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> alla <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> raccolta.</span><span class="sxs-lookup"><span data-stu-id="eba7b-154">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="eba7b-155">Il codice seguente restituisce i risultati del comando precedente usando i <xref:System.Data.OracleClient.OracleDataReader.Read> metodi e <xref:System.Data.OracleClient.OracleDataReader.NextResult> dell'oggetto <xref:System.Data.OracleClient.OracleDataReader> .</span><span class="sxs-lookup"><span data-stu-id="eba7b-155">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="eba7b-156">I parametri REF CURSOR vengono restituiti in ordine.</span><span class="sxs-lookup"><span data-stu-id="eba7b-156">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="eba7b-157">Nell'esempio seguente viene usato il comando precedente per popolare un oggetto <xref:System.Data.DataSet> con i risultati del pacchetto Oracle.</span><span class="sxs-lookup"><span data-stu-id="eba7b-157">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="eba7b-158">Per evitare un **overflow**, è consigliabile gestire anche qualsiasi conversione dal tipo di numero Oracle a un tipo di .NET Framework valido prima di archiviare il valore in un oggetto <xref:System.Data.DataRow> .</span><span class="sxs-lookup"><span data-stu-id="eba7b-158">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="eba7b-159">È possibile utilizzare l' <xref:System.Data.Common.DataAdapter.FillError> evento per determinare se si è verificato un **overflow** .</span><span class="sxs-lookup"><span data-stu-id="eba7b-159">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="eba7b-160">Per ulteriori informazioni sull' <xref:System.Data.Common.DataAdapter.FillError> evento, vedere [gestione di eventi DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="eba7b-160">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba7b-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eba7b-161">See also</span></span>

- [<span data-ttu-id="eba7b-162">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="eba7b-162">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="eba7b-163">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="eba7b-163">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="eba7b-164">Recupero di informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="eba7b-164">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="eba7b-165">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eba7b-165">ADO.NET Overview</span></span>](ado-net-overview.md)
