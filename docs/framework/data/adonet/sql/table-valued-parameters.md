---
title: Parametri valutati a livello di tabella
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: ccef487eb27a5a170d197a6bc670ec4d2bcf8bdf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645790"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="c18e0-102">Parametri valutati a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="c18e0-102">Table-Valued Parameters</span></span>
<span data-ttu-id="c18e0-103">I parametri valutati a livello di tabella consentono di eseguire facilmente il marshaling di più righe di dati di un'applicazione client in SQL Server senza richiedere più round trip o logica speciale lato server per l'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="c18e0-103">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="c18e0-104">È possibile usare i parametri con valori di tabella per incapsulare le righe di dati in un'applicazione client e inviare i dati al server in un singolo comando con parametri.</span><span class="sxs-lookup"><span data-stu-id="c18e0-104">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="c18e0-105">Le righe di dati in arrivo vengono archiviate in una variabile di tabella che può quindi essere usata tramite [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c18e0-105">The incoming data rows are stored in a table variable that can then be operated on by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c18e0-106">I valori di colonna nei parametri con valori di tabella sono accessibili tramite istruzioni SELECT [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] standard.</span><span class="sxs-lookup"><span data-stu-id="c18e0-106">Column values in table-valued parameters can be accessed using standard [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] SELECT statements.</span></span> <span data-ttu-id="c18e0-107">I parametri con valori di tabella sono fortemente tipizzati e la loro struttura viene convalidata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c18e0-107">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="c18e0-108">La dimensione dei parametri valutati a livello di tabella è limitata solo dalla memoria del server.</span><span class="sxs-lookup"><span data-stu-id="c18e0-108">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c18e0-109">Non è possibile restituire dati in un parametro valutato a livello di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-109">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="c18e0-110">I parametri valutati a livello di tabella sono di solo input. La parola chiave OUTPUT non è supportata.</span><span class="sxs-lookup"><span data-stu-id="c18e0-110">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="c18e0-111">Per altre informazioni sui parametri con valori di tabella, vedere le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="c18e0-111">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="c18e0-112">Risorsa</span><span class="sxs-lookup"><span data-stu-id="c18e0-112">Resource</span></span>|<span data-ttu-id="c18e0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c18e0-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c18e0-114">[Parametri con valori di tabella (motore di Database)](https://go.microsoft.com/fwlink/?LinkId=98363) nella documentazione Online di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c18e0-114">[Table-Valued Parameters (Database Engine)](https://go.microsoft.com/fwlink/?LinkId=98363) in SQL Server Books Online</span></span>|<span data-ttu-id="c18e0-115">Viene descritto come creare e usare i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-115">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="c18e0-116">[Tipi di tabella definiti dall'utente](https://go.microsoft.com/fwlink/?LinkId=98364) nella documentazione Online di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c18e0-116">[User-Defined Table Types](https://go.microsoft.com/fwlink/?LinkId=98364) in SQL Server Books Online</span></span>|<span data-ttu-id="c18e0-117">Vengono descritti i tipi di tabella definiti dall'utente usati per dichiarare i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-117">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="c18e0-118">Passaggio di più righe nelle versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c18e0-118">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="c18e0-119">Prima di parametri con valori di tabella sono stati introdotti in SQL Server 2008, le opzioni per passare più righe di dati a una stored procedure o un comando SQL con parametri erano limitate.</span><span class="sxs-lookup"><span data-stu-id="c18e0-119">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="c18e0-120">Per passare più righe al server, uno sviluppatore poteva scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c18e0-120">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="c18e0-121">Usare una serie di parametri singoli per rappresentare i valori in più colonne e righe di dati.</span><span class="sxs-lookup"><span data-stu-id="c18e0-121">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="c18e0-122">La quantità di dati che è possibile passare tramite questo metodo è limitata dal numero di parametri consentiti.</span><span class="sxs-lookup"><span data-stu-id="c18e0-122">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="c18e0-123">Le routine di SQL Server possono includere al massimo 2100 parametri.</span><span class="sxs-lookup"><span data-stu-id="c18e0-123">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="c18e0-124">Per assemblare questi singoli valori in una variabile di tabella o in una tabella temporanea per l'elaborazione è necessaria la logica sul lato server.</span><span class="sxs-lookup"><span data-stu-id="c18e0-124">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="c18e0-125">Aggregare più valori di dati in stringhe delimitate o in documenti XML, quindi passare tali valori di testo a una routine o a un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c18e0-125">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="c18e0-126">A tale scopo, è necessario che la routine o l'istruzione includa la logica necessaria per la convalida delle strutture di dati e la separazione dei valori.</span><span class="sxs-lookup"><span data-stu-id="c18e0-126">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="c18e0-127">Creare una serie di istruzioni SQL singole per le modifiche ai dati che riguardano più righe, ad esempio quelle create chiamando il metodo `Update` di un oggetto <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-127">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="c18e0-128">Le modifiche possono essere inviate al server individualmente o raggruppate in batch.</span><span class="sxs-lookup"><span data-stu-id="c18e0-128">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="c18e0-129">Anche in caso di invio in batch che contengono più istruzioni, ogni istruzione viene tuttavia eseguita separatamente nel server.</span><span class="sxs-lookup"><span data-stu-id="c18e0-129">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="c18e0-130">Usare l'utilità `bcp` o l'oggetto <xref:System.Data.SqlClient.SqlBulkCopy> per caricare numerose righe di dati in una tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-130">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="c18e0-131">Sebbene questa tecnica sia molto efficace, non supporta l'elaborazione sul lato server, a meno che i dati non vengano caricati in una tabella temporanea o in una variabile di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-131">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="c18e0-132">Creazione di tipi di parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="c18e0-132">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="c18e0-133">I parametri con valori di tabella sono basati su strutture di tabella fortemente tipizzate definite tramite istruzioni CREATE TYPE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c18e0-133">Table-valued parameters are based on strongly-typed table structures that are defined by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] CREATE TYPE statements.</span></span> <span data-ttu-id="c18e0-134">Per poter utilizzare i parametri con valori di tabella nelle applicazioni client, è prima necessario creare un tipo di tabella e definire la struttura in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c18e0-134">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="c18e0-135">Per altre informazioni sulla creazione di tipi di tabella, vedere [tipi di tabella definiti dall'utente](https://go.microsoft.com/fwlink/?LinkID=98364) nella documentazione Online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c18e0-135">For more information about creating table types, see [User-Defined Table Types](https://go.microsoft.com/fwlink/?LinkID=98364) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="c18e0-136">L'istruzione seguente consente di creare un tipo di tabella denominato CategoryTableType, costituito dalle colonne CategoryID e CategoryName:</span><span class="sxs-lookup"><span data-stu-id="c18e0-136">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```  
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="c18e0-137">Dopo aver creato un tipo di tabella, è possibile dichiarare i parametri con valori di tabella basati su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="c18e0-137">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="c18e0-138">Nel frammento [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] seguente viene illustrato come dichiarare un parametro con valori di tabella in una definizione di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c18e0-138">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="c18e0-139">Si noti che, per dichiarare un parametro con valori di tabella, è necessaria la parola chiave READONLY.</span><span class="sxs-lookup"><span data-stu-id="c18e0-139">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```  
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="c18e0-140">Modifica di dati con i parametri con valori di tabella (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c18e0-140">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="c18e0-141">I parametri con valori di tabella possono essere usati nelle modifiche dei dati basate su set che riguardano più righe eseguendo un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="c18e0-141">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="c18e0-142">È ad esempio possibile selezionare tutte le righe in un parametro con valori di tabella e inserirle in una tabella di database oppure creare un'istruzione di aggiornamento tramite l'unione in join di un parametro con valori di tabella con la tabella che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="c18e0-142">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="c18e0-143">L'istruzione UPDATE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] seguente illustra come usare un parametro con valori di tabella tramite la sua unione in join con la tabella Categories.</span><span class="sxs-lookup"><span data-stu-id="c18e0-143">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="c18e0-144">Quando si usa un parametro con valori di tabella con un JOIN in una clausola FROM, è anche necessario usare un alias per il parametro, come illustrato di seguito, dove per il parametro con valori di tabella viene usato l'alias "ec":</span><span class="sxs-lookup"><span data-stu-id="c18e0-144">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```  
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="c18e0-145">In questo esempio [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] viene illustrato come selezionare le righe da un parametro con valori di tabella per eseguire un'istruzione INSERT in una singola operazione basata su set.</span><span class="sxs-lookup"><span data-stu-id="c18e0-145">This [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```  
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="c18e0-146">Limitazioni relative ai parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="c18e0-146">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="c18e0-147">Per i parametri con valori di tabella sono previste diverse limitazioni:</span><span class="sxs-lookup"><span data-stu-id="c18e0-147">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="c18e0-148">Non è possibile passare parametri con valori di tabella [funzioni definite dall'utente CLR](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span><span class="sxs-lookup"><span data-stu-id="c18e0-148">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="c18e0-149">I parametri con valori di tabella possono essere indicizzati solo per supportare vincoli UNIQUE o PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="c18e0-149">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="c18e0-150">In SQL Server non vengono gestite statistiche relative ai parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-150">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="c18e0-151">I parametri con valori di tabella sono di sola lettura nel codice [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c18e0-151">Table-valued parameters are read-only in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="c18e0-152">Non è possibile aggiornare i valori delle colonne nelle righe di un parametro con valori di tabella e non è possibile inserire o eliminare righe.</span><span class="sxs-lookup"><span data-stu-id="c18e0-152">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="c18e0-153">Per modificare i dati passati a una stored procedure o a un'istruzione con parametri in un parametro con valori di tabella, è necessario inserire i dati in una tabella temporanea o in una variabile di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-153">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="c18e0-154">Non è possibile usare istruzioni ALTER TABLE per modificare la struttura dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-154">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="c18e0-155">Configurazione di un esempio SqlParameter</span><span class="sxs-lookup"><span data-stu-id="c18e0-155">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="c18e0-156"><xref:System.Data.SqlClient> supporta il popolamento dei parametri con valori di tabella dal <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> oppure <xref:System.Collections.Generic.IEnumerable%601>  \  <xref:Microsoft.SqlServer.Server.SqlDataRecord> oggetti.</span><span class="sxs-lookup"><span data-stu-id="c18e0-156"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="c18e0-157">È necessario specificare un nome di tipo per il parametro con valori di tabella usando la proprietà <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> di un oggetto <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-157">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="c18e0-158">`TypeName` deve corrispondere al nome di un tipo compatibile creato in precedenza nel server.</span><span class="sxs-lookup"><span data-stu-id="c18e0-158">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="c18e0-159">Nel frammento di codice seguente viene illustrato come configurare <xref:System.Data.SqlClient.SqlParameter> per inserire dati.</span><span class="sxs-lookup"><span data-stu-id="c18e0-159">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  
 
<span data-ttu-id="c18e0-160">Nell'esempio seguente, il `addedCategories` variabile contiene un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-160">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c18e0-161">Per vedere come la variabile è popolata, vedere gli esempi nella sezione successiva [passando un parametro con valori di tabella a una Stored Procedure](#passing).</span><span class="sxs-lookup"><span data-stu-id="c18e0-161">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 <span data-ttu-id="c18e0-162">È anche possibile usare qualsiasi oggetto derivato da <xref:System.Data.Common.DbDataReader> per trasmettere flussi di righe di dati a un parametro con valori di tabella, come illustrato in questo frammento:</span><span class="sxs-lookup"><span data-stu-id="c18e0-162">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing"></a> <span data-ttu-id="c18e0-163">Passaggio di un parametro con valori di tabella a una Stored Procedure</span><span class="sxs-lookup"><span data-stu-id="c18e0-163">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="c18e0-164">In questo esempio viene illustrato come passare i dati di un parametro con valori di tabella a una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c18e0-164">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="c18e0-165">Il codice consente di estrarre le righe aggiunte in un nuovo oggetto <xref:System.Data.DataTable> tramite il metodo <xref:System.Data.DataTable.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-165">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="c18e0-166">Viene quindi definito un oggetto <xref:System.Data.SqlClient.SqlCommand>, impostando la proprietà <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> su <xref:System.Data.CommandType.StoredProcedure>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-166">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="c18e0-167">L'oggetto <xref:System.Data.SqlClient.SqlParameter> viene popolato usando il metodo <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> e la proprietà <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> viene impostata su `Structured`.</span><span class="sxs-lookup"><span data-stu-id="c18e0-167">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="c18e0-168">Viene quindi eseguito <xref:System.Data.SqlClient.SqlCommand> usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-168">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="c18e0-169">Passaggio di un parametro con valori di tabella a un'istruzione SQL con parametri</span><span class="sxs-lookup"><span data-stu-id="c18e0-169">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="c18e0-170">Nell'esempio seguente viene illustrato come inserire i dati nella tabella dbo.Categories tramite un'istruzione INSERT con una sottoquery SELECT che dispone di un parametro con valori di tabella come origine dati.</span><span class="sxs-lookup"><span data-stu-id="c18e0-170">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="c18e0-171">Quando si passa un parametro con valori di tabella a un'istruzione SQL con parametri, è necessario specificare un nome di tipo per il parametro con valori di tabella usando la nuova proprietà <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> di un oggetto <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-171">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="c18e0-172">`TypeName` deve corrispondere al nome di un tipo compatibile creato in precedenza nel server.</span><span class="sxs-lookup"><span data-stu-id="c18e0-172">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="c18e0-173">Nel codice di questo esempio viene usata la proprietà `TypeName` per fare riferimento alla struttura di tipi definita in dbo.CategoryTableType.</span><span class="sxs-lookup"><span data-stu-id="c18e0-173">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c18e0-174">Se si fornisce un valore per una colonna Identity in un parametro con valori di tabella, è necessario eseguire l'istruzione SET IDENTITY_INSERT per la sessione.</span><span class="sxs-lookup"><span data-stu-id="c18e0-174">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =   
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="c18e0-175">Trasmissione di flussi di righe con un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="c18e0-175">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="c18e0-176">È anche possibile usare qualsiasi oggetto derivato da <xref:System.Data.Common.DbDataReader> per trasmettere flussi di righe di dati a un parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-176">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="c18e0-177">Nel frammento di codice seguente viene illustrato il recupero di dati da un database Oracle tramite un oggetto <xref:System.Data.OracleClient.OracleCommand> e un oggetto <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="c18e0-177">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="c18e0-178">Nel codice viene quindi configurato un oggetto <xref:System.Data.SqlClient.SqlCommand> per richiamare una stored procedure con un singolo parametro di input.</span><span class="sxs-lookup"><span data-stu-id="c18e0-178">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="c18e0-179">La proprietà <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> di <xref:System.Data.SqlClient.SqlParameter> è impostata su `Structured`.</span><span class="sxs-lookup"><span data-stu-id="c18e0-179">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="c18e0-180"><xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passa il set di risultati di `OracleDataReader` alla stored procedure come parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c18e0-180">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a><span data-ttu-id="c18e0-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c18e0-181">See also</span></span>

- [<span data-ttu-id="c18e0-182">Configurazione di parametri e tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="c18e0-182">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="c18e0-183">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="c18e0-183">Commands and Parameters</span></span>](../../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="c18e0-184">Parametri DataAdapter</span><span class="sxs-lookup"><span data-stu-id="c18e0-184">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)
- [<span data-ttu-id="c18e0-185">Operazioni sui dati SQL Server in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c18e0-185">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)
- [<span data-ttu-id="c18e0-186">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c18e0-186">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
