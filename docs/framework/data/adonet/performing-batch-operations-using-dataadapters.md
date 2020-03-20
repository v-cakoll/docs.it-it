---
title: Esecuzione di operazioni batch tramite oggetti DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e72ed5af-b24f-486c-8429-c8fd2208f844
ms.openlocfilehash: 62a61051e5b9d896f8a89ed3d2745859fc07a7ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149258"
---
# <a name="performing-batch-operations-using-dataadapters"></a><span data-ttu-id="d2b85-102">Esecuzione di operazioni batch tramite oggetti DataAdapter</span><span class="sxs-lookup"><span data-stu-id="d2b85-102">Performing Batch Operations Using DataAdapters</span></span>
<span data-ttu-id="d2b85-103">Il supporto batch in ADO.NET consente a un tipo <xref:System.Data.Common.DataAdapter> di raggruppare le operazioni INSERT, UPDATE e DELETE da un tipo <xref:System.Data.DataSet> o <xref:System.Data.DataTable> e di inviarle al server in batch, anziché inviare una singola operazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="d2b85-103">Batch support in ADO.NET allows a <xref:System.Data.Common.DataAdapter> to group INSERT, UPDATE, and DELETE operations from a <xref:System.Data.DataSet> or <xref:System.Data.DataTable> to the server, instead of sending one operation at a time.</span></span> <span data-ttu-id="d2b85-104">La riduzione nel numero di percorsi di andata e ritorno al server determina in genere un notevole miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d2b85-104">The reduction in the number of round trips to the server typically results in significant performance gains.</span></span> <span data-ttu-id="d2b85-105">Gli aggiornamenti batch sono supportati per i provider di dati .NET di SQL Server (<xref:System.Data.SqlClient>) e Oracle (<xref:System.Data.OracleClient>).</span><span class="sxs-lookup"><span data-stu-id="d2b85-105">Batch updates are supported for the .NET data providers for SQL Server (<xref:System.Data.SqlClient>) and Oracle (<xref:System.Data.OracleClient>).</span></span>  
  
 <span data-ttu-id="d2b85-106">Per l'aggiornamento di un database con modifiche provenienti da un <xref:System.Data.DataSet>, nelle versioni precedenti di ADO.NET il metodo `Update` di un `DataAdapter` eseguiva gli aggiornamenti del database una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="d2b85-106">When updating a database with changes from a <xref:System.Data.DataSet> in previous versions of ADO.NET, the `Update` method of a `DataAdapter` performed updates to the database one row at a time.</span></span> <span data-ttu-id="d2b85-107">Scorrendo le righe nella <xref:System.Data.DataTable> specificata, ciascuna riga <xref:System.Data.DataRow> veniva esaminata per rilevare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="d2b85-107">As it iterated through the rows in the specified <xref:System.Data.DataTable>, it examined each <xref:System.Data.DataRow> to see if it had been modified.</span></span> <span data-ttu-id="d2b85-108">Se la riga era stata modificata, veniva chiamato il comando appropriato `UpdateCommand`, `InsertCommand` o `DeleteCommand`, in base al valore della proprietà <xref:System.Data.DataRow.RowState%2A> per quella determinata riga.</span><span class="sxs-lookup"><span data-stu-id="d2b85-108">If the row had been modified, it called the appropriate `UpdateCommand`, `InsertCommand`, or `DeleteCommand`, depending on the value of the <xref:System.Data.DataRow.RowState%2A> property for that row.</span></span> <span data-ttu-id="d2b85-109">Ogni aggiornamento di riga comportava un percorso di andata e ritorno in rete al database.</span><span class="sxs-lookup"><span data-stu-id="d2b85-109">Every row update involved a network round-trip to the database.</span></span>  
  
 <span data-ttu-id="d2b85-110">A partire da ADO.NET 2.0, <xref:System.Data.Common.DbDataAdapter> espone una proprietà <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2b85-110">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbDataAdapter> exposes an <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A> property.</span></span> <span data-ttu-id="d2b85-111">Impostando `UpdateBatchSize` su un valore intero positivo, gli aggiornamenti vengono inviati al database come batch della dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="d2b85-111">Setting the `UpdateBatchSize` to a positive integer value causes updates to the database to be sent as batches of the specified size.</span></span> <span data-ttu-id="d2b85-112">Ad esempio, impostando `UpdateBatchSize` su 10, verranno raggruppate 10 istruzioni separate e inviate come singolo batch.</span><span class="sxs-lookup"><span data-stu-id="d2b85-112">For example, setting the `UpdateBatchSize` to 10 will group 10 separate statements and submit them as single batch.</span></span> <span data-ttu-id="d2b85-113">Impostando `UpdateBatchSize` su 0, il <xref:System.Data.Common.DataAdapter> utilizzerà la dimensione di batch massima che il server è in grado di gestire.</span><span class="sxs-lookup"><span data-stu-id="d2b85-113">Setting the `UpdateBatchSize` to 0 will cause the <xref:System.Data.Common.DataAdapter> to use the largest batch size that the server can handle.</span></span> <span data-ttu-id="d2b85-114">Se invece si imposta il valore su 1, gli aggiornamenti batch vengono disabilitati, in quanto le righe vengono inviate una alla volta.</span><span class="sxs-lookup"><span data-stu-id="d2b85-114">Setting it to 1 disables batch updates, as rows are sent one at a time.</span></span>  
  
 <span data-ttu-id="d2b85-115">Le prestazioni risulteranno ridotte se si esegue un batch di dimensioni molto elevate.</span><span class="sxs-lookup"><span data-stu-id="d2b85-115">Executing an extremely large batch could decrease performance.</span></span> <span data-ttu-id="d2b85-116">Pertanto, prima di implementare l'applicazione è consigliabile verificare quale sia la dimensione ottimale per i batch.</span><span class="sxs-lookup"><span data-stu-id="d2b85-116">Therefore, you should test for the optimum batch size setting before implementing your application.</span></span>  
  
## <a name="using-the-updatebatchsize-property"></a><span data-ttu-id="d2b85-117">Utilizzo della proprietà UpdateBatchSize</span><span class="sxs-lookup"><span data-stu-id="d2b85-117">Using the UpdateBatchSize Property</span></span>  
 <span data-ttu-id="d2b85-118">Quando gli aggiornamenti batch sono abilitati, il valore della proprietà <xref:System.Data.IDbCommand.UpdatedRowSource%2A> dei comandi `UpdateCommand`, `InsertCommand` e `DeleteCommand` di Data Adapter deve essere impostato su <xref:System.Data.UpdateRowSource.None> o su <xref:System.Data.UpdateRowSource.OutputParameters>.</span><span class="sxs-lookup"><span data-stu-id="d2b85-118">When batch updates are enabled, the <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of the DataAdapter's `UpdateCommand`, `InsertCommand`, and `DeleteCommand` should be set to <xref:System.Data.UpdateRowSource.None> or <xref:System.Data.UpdateRowSource.OutputParameters>.</span></span> <span data-ttu-id="d2b85-119">Quando si esegue un aggiornamento batch, il valore <xref:System.Data.IDbCommand.UpdatedRowSource%2A> o <xref:System.Data.UpdateRowSource.FirstReturnedRecord> della proprietà <xref:System.Data.UpdateRowSource.Both> del comando non è valido.</span><span class="sxs-lookup"><span data-stu-id="d2b85-119">When performing a batch update, the command's <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of <xref:System.Data.UpdateRowSource.FirstReturnedRecord> or <xref:System.Data.UpdateRowSource.Both> is invalid.</span></span>  
  
 <span data-ttu-id="d2b85-120">Nella procedura seguente viene illustrato l'uso della proprietà `UpdateBatchSize`.</span><span class="sxs-lookup"><span data-stu-id="d2b85-120">The following procedure demonstrates the use of the `UpdateBatchSize` property.</span></span> <span data-ttu-id="d2b85-121">La procedura accetta due <xref:System.Data.DataSet> argomenti, un oggetto con colonne che rappresentano i campi **ProductCategoryID** e **Name** nella tabella **Production.ProductCategory** e un numero intero che rappresenta la dimensione del batch (il numero di righe nel batch).</span><span class="sxs-lookup"><span data-stu-id="d2b85-121">The procedure takes two arguments, a <xref:System.Data.DataSet> object that has columns representing the **ProductCategoryID** and **Name** fields in the **Production.ProductCategory** table, and an integer representing the batch size (the number of rows in the batch).</span></span> <span data-ttu-id="d2b85-122">Il codice crea un nuovo oggetto <xref:System.Data.SqlClient.SqlDataAdapter>, impostandone le proprietà <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> e <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2b85-122">The code creates a new <xref:System.Data.SqlClient.SqlDataAdapter> object, setting its <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties.</span></span> <span data-ttu-id="d2b85-123">Nel codice si presuppone che l'oggetto <xref:System.Data.DataSet> contenga righe modificate.</span><span class="sxs-lookup"><span data-stu-id="d2b85-123">The code assumes that the <xref:System.Data.DataSet> object has modified rows.</span></span> <span data-ttu-id="d2b85-124">La proprietà `UpdateBatchSize` viene impostata e viene eseguito l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d2b85-124">It sets the `UpdateBatchSize` property and executes the update.</span></span>  
  
```vb  
Public Sub BatchUpdate( _  
  ByVal dataTable As DataTable, ByVal batchSize As Int32)  
    ' Assumes GetConnectionString() returns a valid connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    ' Connect to the AdventureWorks database.  
    Using connection As New SqlConnection(connectionString)  
        ' Create a SqlDataAdapter.  
        Dim adapter As New SqlDataAdapter()  
  
        'Set the UPDATE command and parameters.  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Production.ProductCategory SET " _  
          & "Name=@Name WHERE ProductCategoryID=@ProdCatID;", _  
          connection)  
        adapter.UpdateCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",  _  
          SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.UpdateCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the INSERT command and parameter.  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);", _  
  connection)  
        adapter.InsertCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.InsertCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the DELETE command and parameter.  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Production.ProductCategory " _  
          & "WHERE ProductCategoryID=@ProdCatID;", connection)  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID", _  
           SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None  
  
        ' Set the batch size.  
        adapter.UpdateBatchSize = batchSize  
  
        ' Execute the update.  
        adapter.Update(dataTable)  
    End Using  
End Sub  
```  
  
```csharp  
public static void BatchUpdate(DataTable dataTable,Int32 batchSize)  
{  
    // Assumes GetConnectionString() returns a valid connection string.  
    string connectionString = GetConnectionString();  
  
    // Connect to the AdventureWorks database.  
    using (SqlConnection connection = new
      SqlConnection(connectionString))  
    {  
  
        // Create a SqlDataAdapter.  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        // Set the UPDATE command and parameters.  
        adapter.UpdateCommand = new SqlCommand(  
            "UPDATE Production.ProductCategory SET "  
            + "Name=@Name WHERE ProductCategoryID=@ProdCatID;",
            connection);  
        adapter.UpdateCommand.Parameters.Add("@Name",
           SqlDbType.NVarChar, 50, "Name");  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",
           SqlDbType.Int, 4, "ProductCategoryID");  
         adapter.UpdateCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the INSERT command and parameter.  
        adapter.InsertCommand = new SqlCommand(  
            "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);",
            connection);  
        adapter.InsertCommand.Parameters.Add("@Name",
          SqlDbType.NVarChar, 50, "Name");  
        adapter.InsertCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the DELETE command and parameter.  
        adapter.DeleteCommand = new SqlCommand(  
            "DELETE FROM Production.ProductCategory "  
            + "WHERE ProductCategoryID=@ProdCatID;", connection);  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID",
          SqlDbType.Int, 4, "ProductCategoryID");  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the batch size.  
        adapter.UpdateBatchSize = batchSize;  
  
        // Execute the update.  
        adapter.Update(dataTable);  
    }  
}  
```  
  
## <a name="handling-batch-update-related-events-and-errors"></a><span data-ttu-id="d2b85-125">Gestione di eventi ed errori relativi all'aggiornamento batch</span><span class="sxs-lookup"><span data-stu-id="d2b85-125">Handling Batch Update-Related Events and Errors</span></span>  
 <span data-ttu-id="d2b85-126">Il **DataAdapter** dispone di due eventi correlati all'aggiornamento: **RowUpdating** e **RowUpdated**.</span><span class="sxs-lookup"><span data-stu-id="d2b85-126">The **DataAdapter** has two update-related events: **RowUpdating** and **RowUpdated**.</span></span> <span data-ttu-id="d2b85-127">In versioni precedenti di ADO.NET quando l'elaborazione batch è disabilitata, ciascuno di questi eventi viene generato una volta per ogni riga elaborata.</span><span class="sxs-lookup"><span data-stu-id="d2b85-127">In previous versions of ADO.NET, when batch processing is disabled, each of these events is generated once for each row processed.</span></span> <span data-ttu-id="d2b85-128">**RowUpdating** viene generato prima dell'aggiornamento e **RowUpdated** viene generato dopo il completamento dell'aggiornamento del database.</span><span class="sxs-lookup"><span data-stu-id="d2b85-128">**RowUpdating** is generated before the update occurs, and **RowUpdated** is generated after the database update has been completed.</span></span>  
  
### <a name="event-behavior-changes-with-batch-updates"></a><span data-ttu-id="d2b85-129">Modifiche al comportamento degli eventi con aggiornamenti batch</span><span class="sxs-lookup"><span data-stu-id="d2b85-129">Event Behavior Changes with Batch Updates</span></span>  
 <span data-ttu-id="d2b85-130">Quando l'elaborazione batch è abilitata, in un'unica operazione di database vengono aggiornate più righe.</span><span class="sxs-lookup"><span data-stu-id="d2b85-130">When batch processing is enabled, multiple rows are updated in a single database operation.</span></span> <span data-ttu-id="d2b85-131">Pertanto, si verifica un solo evento `RowUpdated` per ogni batch, mentre l'evento `RowUpdating` si verifica per ogni riga elaborata.</span><span class="sxs-lookup"><span data-stu-id="d2b85-131">Therefore, only one `RowUpdated` event occurs for each batch, whereas the `RowUpdating` event occurs for each row processed.</span></span> <span data-ttu-id="d2b85-132">Quando l'elaborazione batch è disabilitata, i due eventi vengono generati con interfoliazione uno-a-uno, dove un evento `RowUpdating` e un evento `RowUpdated` vengono generati per una riga e un evento `RowUpdating` e un evento `RowUpdated` per la riga successiva, fino all'elaborazione di tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="d2b85-132">When batch processing is disabled, the two events are fired with one-to-one interleaving, where one `RowUpdating` event and one `RowUpdated` event fire for a row, and then one `RowUpdating` and one `RowUpdated` event fire for the next row, until all of the rows are processed.</span></span>  
  
### <a name="accessing-updated-rows"></a><span data-ttu-id="d2b85-133">Accesso alle righe aggiornate</span><span class="sxs-lookup"><span data-stu-id="d2b85-133">Accessing Updated Rows</span></span>  
 <span data-ttu-id="d2b85-134">Quando l'elaborazione batch è disabilitata, è possibile accedere alla riga aggiornata mediante la proprietà <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> della classe <xref:System.Data.Common.RowUpdatedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d2b85-134">When batch processing is disabled, the row being updated can be accessed using the <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> property of the <xref:System.Data.Common.RowUpdatedEventArgs> class.</span></span>  
  
 <span data-ttu-id="d2b85-135">Quando l'elaborazione batch è abilitata, viene generato un unico evento `RowUpdated` per più righe.</span><span class="sxs-lookup"><span data-stu-id="d2b85-135">When batch processing is enabled, a single `RowUpdated` event is generated for multiple rows.</span></span> <span data-ttu-id="d2b85-136">Pertanto, il valore della proprietà `Row` per ciascuna riga è null.</span><span class="sxs-lookup"><span data-stu-id="d2b85-136">Therefore, the value of the `Row` property for each row is null.</span></span> <span data-ttu-id="d2b85-137">Gli eventi `RowUpdating` vengono comunque generati per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="d2b85-137">`RowUpdating` events are still generated for each row.</span></span> <span data-ttu-id="d2b85-138">Il metodo <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> della classe <xref:System.Data.Common.RowUpdatedEventArgs> consente di accedere alle righe elaborate mediante la copia dei riferimenti alle righe in una matrice.</span><span class="sxs-lookup"><span data-stu-id="d2b85-138">The <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method of the <xref:System.Data.Common.RowUpdatedEventArgs> class allows you to access the processed rows by copying references to the rows into an array.</span></span> <span data-ttu-id="d2b85-139">Se non viene elaborata nessuna riga, `CopyToRows` genera un'eccezione <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="d2b85-139">If no rows are being processed, `CopyToRows` throws an <xref:System.ArgumentNullException>.</span></span> <span data-ttu-id="d2b85-140">Usare la proprietà <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> per restituire il numero di righe elaborate prima di chiamare il metodo <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2b85-140">Use the <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> property to return the number of rows processed before calling the <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method.</span></span>  
  
### <a name="handling-data-errors"></a><span data-ttu-id="d2b85-141">Gestione degli errori di dati</span><span class="sxs-lookup"><span data-stu-id="d2b85-141">Handling Data Errors</span></span>  
 <span data-ttu-id="d2b85-142">I risultati dell'esecuzione batch sono identici a quelli ottenuti eseguendo le singole istruzioni una alla volta.</span><span class="sxs-lookup"><span data-stu-id="d2b85-142">Batch execution has the same effect as the execution of each individual statement.</span></span> <span data-ttu-id="d2b85-143">Le istruzioni vengono eseguite nell'ordine in base al quale sono state aggiunte al batch.</span><span class="sxs-lookup"><span data-stu-id="d2b85-143">Statements are executed in the order that the statements were added to the batch.</span></span> <span data-ttu-id="d2b85-144">La gestione degli errori è la stessa sia in modalità batch sia quando la modalità batch è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d2b85-144">Errors are handled the same way in batch mode as they are when batch mode is disabled.</span></span> <span data-ttu-id="d2b85-145">Ogni riga viene elaborata separatamente.</span><span class="sxs-lookup"><span data-stu-id="d2b85-145">Each row is processed separately.</span></span> <span data-ttu-id="d2b85-146">Solo le righe che sono state elaborate correttamente nel database verranno aggiornate nell'oggetto <xref:System.Data.DataRow> corrispondente all'interno di <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="d2b85-146">Only rows that have been successfully processed in the database will be updated in the corresponding <xref:System.Data.DataRow> within the <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="d2b85-147">Il provider di dati e il server database back-end determinano i costrutti SQL supportati per l'esecuzione batch.</span><span class="sxs-lookup"><span data-stu-id="d2b85-147">The data provider and the back-end database server determine which SQL constructs are supported for batch execution.</span></span> <span data-ttu-id="d2b85-148">Se per l'esecuzione viene inviata un'istruzione non supportata, è possibile che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d2b85-148">An exception may be thrown if a non-supported statement is submitted for execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b85-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b85-149">See also</span></span>

- [<span data-ttu-id="d2b85-150">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="d2b85-150">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="d2b85-151">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="d2b85-151">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="d2b85-152">Gestione di eventi DataAdapter</span><span class="sxs-lookup"><span data-stu-id="d2b85-152">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)
- [<span data-ttu-id="d2b85-153">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d2b85-153">ADO.NET Overview</span></span>](ado-net-overview.md)
