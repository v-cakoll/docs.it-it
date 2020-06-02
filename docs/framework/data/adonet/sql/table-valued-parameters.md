---
title: Parametri con valori di tabella
description: Informazioni su come effettuare il marshalling di più righe di dati da un'applicazione client a SQL Server utilizzando parametri con valori di tabella.
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: 7b1f0a6c416f660f06cea099197ba136f84407f9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286197"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="8314f-103">Parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="8314f-103">Table-Valued Parameters</span></span>
<span data-ttu-id="8314f-104">I parametri con valori di tabella offrono un modo semplice per effettuare il marshalling di più righe di dati da un'applicazione client di SQL Server senza richiedere più round trip o una logica speciale sul lato server per l'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="8314f-104">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="8314f-105">I parametri con valori di tabella possono essere usati per incapsulare le righe di dati in un'applicazione client e inviare i dati al server in un singolo comando con parametri.</span><span class="sxs-lookup"><span data-stu-id="8314f-105">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="8314f-106">Le righe di dati in ingresso vengono archiviate in una variabile di tabella su cui è possibile operare tramite Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8314f-106">The incoming data rows are stored in a table variable that can then be operated on by using Transact-SQL.</span></span>  
  
 <span data-ttu-id="8314f-107">I valori di colonna nei parametri con valori di tabella sono accessibili tramite istruzioni Transact-SQL SELECT standard.</span><span class="sxs-lookup"><span data-stu-id="8314f-107">Column values in table-valued parameters can be accessed using standard Transact-SQL SELECT statements.</span></span> <span data-ttu-id="8314f-108">I parametri con valori di tabella sono fortemente tipizzati e la convalida della relativa struttura è automatica.</span><span class="sxs-lookup"><span data-stu-id="8314f-108">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="8314f-109">La dimensione dei parametri con valori di tabella è limitata solo dalla memoria del server.</span><span class="sxs-lookup"><span data-stu-id="8314f-109">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8314f-110">Non è possibile restituire dati in un parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-110">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="8314f-111">I parametri con valori di tabella sono di solo input; la parola chiave OUTPUT non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8314f-111">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="8314f-112">Per altre informazioni sui parametri con valori di tabella, vedere le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="8314f-112">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="8314f-113">Risorsa</span><span class="sxs-lookup"><span data-stu-id="8314f-113">Resource</span></span>|<span data-ttu-id="8314f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8314f-114">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="8314f-115">Utilizzare parametri con valori di tabella (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="8314f-115">Use Table-Valued Parameters (Database Engine)</span></span>](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|<span data-ttu-id="8314f-116">Viene descritto come creare e usare parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-116">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="8314f-117">[Tipi di tabella definiti dall'utente](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="8314f-117">[User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span></span>|<span data-ttu-id="8314f-118">Vengono descritti i tipi di tabella definiti dall'utente usati per dichiarare parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-118">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="8314f-119">Passaggio di più righe nelle versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8314f-119">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="8314f-120">Prima dell'introduzione dei parametri con valori di tabella in SQL Server 2008, le opzioni per passare più righe di dati a una stored procedure o a un comando SQL con parametri erano limitate.</span><span class="sxs-lookup"><span data-stu-id="8314f-120">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="8314f-121">Uno sviluppatore può scegliere tra le opzioni seguenti per passare più righe al server:</span><span class="sxs-lookup"><span data-stu-id="8314f-121">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="8314f-122">usare una serie di parametri singoli per rappresentare i valori in più colonne e righe di dati.</span><span class="sxs-lookup"><span data-stu-id="8314f-122">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="8314f-123">La quantità di dati che è possibile passare usando questo metodo è limitata dal numero di parametri consentiti.</span><span class="sxs-lookup"><span data-stu-id="8314f-123">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="8314f-124">Le stored procedure di SQL Server possono includere al massimo 2100 parametri.</span><span class="sxs-lookup"><span data-stu-id="8314f-124">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="8314f-125">La logica lato server è necessaria per assemblare questi singoli valori in una variabile di tabella o in una tabella temporanea per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="8314f-125">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="8314f-126">Aggregare più valori di dati in stringhe delimitate o in documenti XML, quindi passare i valori di testo a una procedura o a un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8314f-126">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="8314f-127">Questa operazione richiede che la routine o l'istruzione includa la logica necessaria per convalidare le strutture dei dati e disaggregare i valori.</span><span class="sxs-lookup"><span data-stu-id="8314f-127">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="8314f-128">Creare una serie di singole istruzioni SQL per le modifiche ai dati che interessano più righe, ad esempio quelle create chiamando il metodo `Update` di un <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="8314f-128">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="8314f-129">È possibile inviare le modifiche al server singolarmente o in batch in gruppi.</span><span class="sxs-lookup"><span data-stu-id="8314f-129">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="8314f-130">Tuttavia, anche in caso di invio in batch contenenti più istruzioni, ogni istruzione viene eseguita separatamente sul server.</span><span class="sxs-lookup"><span data-stu-id="8314f-130">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="8314f-131">Usare il programma di utilità `bcp` o l'oggetto <xref:System.Data.SqlClient.SqlBulkCopy> per caricare molte righe di dati in una tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-131">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="8314f-132">Sebbene questa tecnica sia molto efficiente, non supporta l'elaborazione sul lato server, a meno che i dati non vengano caricati in una tabella temporanea o in una variabile di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-132">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="8314f-133">Creazione di tipi di parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="8314f-133">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="8314f-134">I parametri con valori di tabella sono basati su strutture di tabella fortemente tipizzate definite tramite istruzioni CREATE TYPE Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8314f-134">Table-valued parameters are based on strongly typed table structures that are defined by using Transact-SQL CREATE TYPE statements.</span></span> <span data-ttu-id="8314f-135">Per poter usare i parametri con valori di tabella nelle applicazioni client, è prima necessario creare un tipo di tabella e definire la struttura in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8314f-135">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="8314f-136">Per ulteriori informazioni sulla creazione di tipi di tabella, vedere [tipi di tabella definiti dall'utente](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span><span class="sxs-lookup"><span data-stu-id="8314f-136">For more information about creating table types, see [User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span></span>  
  
 <span data-ttu-id="8314f-137">Nell'istruzione seguente viene creato un tipo di tabella denominato CategoryTableType costituito da colonne CategoryID e CategoryName:</span><span class="sxs-lookup"><span data-stu-id="8314f-137">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="8314f-138">Dopo aver creato un tipo di tabella, è possibile dichiarare i parametri con valori di tabella in base a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="8314f-138">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="8314f-139">Nel frammento Transact-SQL seguente viene illustrato come dichiarare un parametro con valori di tabella in una definizione di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8314f-139">The following Transact-SQL fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="8314f-140">Si noti che la parola chiave READONLY è obbligatoria per dichiarare un parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-140">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```sql
CREATE PROCEDURE usp_UpdateCategories
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="8314f-141">Modifica di dati con i parametri con valori di tabella (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8314f-141">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="8314f-142">I parametri con valori di tabella possono essere usati nelle modifiche ai dati basate su set che interessano più righe eseguendo un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="8314f-142">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="8314f-143">È possibile, ad esempio, selezionare tutte le righe in un parametro con valori di tabella e inserirle in una tabella di database oppure creare un'istruzione di aggiornamento tramite l'aggiunta di un parametro con valori di tabella alla tabella che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="8314f-143">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="8314f-144">L'istruzione UPDATE Transact-SQL seguente illustra come usare un parametro con valori di tabella tramite la sua unione in join con la tabella Categories.</span><span class="sxs-lookup"><span data-stu-id="8314f-144">The following Transact-SQL UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="8314f-145">Quando si usa un parametro con valori di tabella con un JOIN in una clausola FROM, è anche necessario usare un alias per il parametro, come illustrato di seguito, dove per il parametro con valori di tabella viene usato l'alias "ec":</span><span class="sxs-lookup"><span data-stu-id="8314f-145">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="8314f-146">In questo esempio Transact-SQL viene illustrato come selezionare le righe da un parametro con valori di tabella per eseguire un'istruzione INSERT in una singola operazione basata su set.</span><span class="sxs-lookup"><span data-stu-id="8314f-146">This Transact-SQL example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="8314f-147">Limitazioni relative ai parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="8314f-147">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="8314f-148">Esistono diverse limitazioni per i parametri con valori di tabella:</span><span class="sxs-lookup"><span data-stu-id="8314f-148">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="8314f-149">Non è possibile passare parametri con valori di tabella a [funzioni CLR definite dall'utente](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span><span class="sxs-lookup"><span data-stu-id="8314f-149">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="8314f-150">I parametri con valori di tabella possono essere indicizzati solo per supportare vincoli UNIQUE o PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="8314f-150">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="8314f-151">SQL Server non gestisce statistiche su parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-151">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="8314f-152">I parametri con valori di tabella sono di sola lettura nel codice Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8314f-152">Table-valued parameters are read-only in Transact-SQL code.</span></span> <span data-ttu-id="8314f-153">Non è possibile aggiornare i valori delle colonne nelle righe di un parametro con valori di tabella e non è possibile inserire o eliminare righe.</span><span class="sxs-lookup"><span data-stu-id="8314f-153">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="8314f-154">Per modificare i dati trasferiti a un'istruzione stored procedure o parametrizzata in un parametro con valori di tabella, è necessario inserire i dati in una tabella temporanea o in una variabile di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-154">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="8314f-155">Non è possibile usare le istruzioni ALTER TABLE per modificare la progettazione dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-155">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="8314f-156">Configurazione di un esempio SqlParameter</span><span class="sxs-lookup"><span data-stu-id="8314f-156">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="8314f-157"><xref:System.Data.SqlClient> supporta il popolamento di parametri con valori di tabella da oggetti <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> o <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>.</span><span class="sxs-lookup"><span data-stu-id="8314f-157"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="8314f-158">È necessario specificare un nome di tipo per il parametro con valori di tabella usando la proprietà <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> di <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="8314f-158">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="8314f-159">Il `TypeName` deve corrispondere al nome di un tipo compatibile creato in precedenza nel server.</span><span class="sxs-lookup"><span data-stu-id="8314f-159">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="8314f-160">Il frammento di codice seguente illustra come configurare <xref:System.Data.SqlClient.SqlParameter> per inserire dati.</span><span class="sxs-lookup"><span data-stu-id="8314f-160">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  

<span data-ttu-id="8314f-161">Nell'esempio seguente la variabile `addedCategories` contiene un oggetto <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="8314f-161">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="8314f-162">Per vedere come viene popolata la variabile, vedere gli esempi nella sezione successiva [Passaggio di un parametro con valori di tabella a una stored procedure](#passing).</span><span class="sxs-lookup"><span data-stu-id="8314f-162">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

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
  
 <span data-ttu-id="8314f-163">È anche possibile usare qualsiasi oggetto derivato da <xref:System.Data.Common.DbDataReader> per trasmettere righe di dati a un parametro con valori di tabella, come illustrato in questo frammento:</span><span class="sxs-lookup"><span data-stu-id="8314f-163">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
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
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><a name="passing"></a><span data-ttu-id="8314f-164">Passaggio di un parametro con valori di tabella a una stored procedure</span><span class="sxs-lookup"><span data-stu-id="8314f-164">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="8314f-165">In questo esempio viene illustrato come trasferire i dati dei parametri con valori di tabella a una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8314f-165">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="8314f-166">Il codice estrae le righe aggiunte in una nuova <xref:System.Data.DataTable> usando il metodo <xref:System.Data.DataTable.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="8314f-166">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="8314f-167">Il codice definisce quindi un <xref:System.Data.SqlClient.SqlCommand>, impostando la proprietà <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> su <xref:System.Data.CommandType.StoredProcedure>.</span><span class="sxs-lookup"><span data-stu-id="8314f-167">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="8314f-168">Il <xref:System.Data.SqlClient.SqlParameter> viene popolato usando il metodo <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> e <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> viene impostato su `Structured`.</span><span class="sxs-lookup"><span data-stu-id="8314f-168">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="8314f-169"><xref:System.Data.SqlClient.SqlCommand> viene eseguito quindi usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.</span><span class="sxs-lookup"><span data-stu-id="8314f-169">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
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
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="8314f-170">Passaggio di un parametro con valori di tabella a un'istruzione SQL con parametri</span><span class="sxs-lookup"><span data-stu-id="8314f-170">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="8314f-171">Nell'esempio seguente viene illustrato come inserire dati nella tabella dbo.Categories tramite un'istruzione INSERT con una sottoquery SELECT che dispone di un parametro con valori di tabella come origine dati.</span><span class="sxs-lookup"><span data-stu-id="8314f-171">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="8314f-172">Quando si trasferisce un parametro con valori di tabella a un'istruzione SQL con parametri, è necessario specificare un nome di tipo per il parametro con valori di tabella tramite la nuova proprietà <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> di un <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="8314f-172">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="8314f-173">Questo `TypeName` deve corrispondere al nome di un tipo compatibile creato in precedenza nel server.</span><span class="sxs-lookup"><span data-stu-id="8314f-173">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="8314f-174">Il codice in questo esempio usa la proprietà `TypeName` per fare riferimento alla struttura del tipo definita in dbo.CategoryTableType.</span><span class="sxs-lookup"><span data-stu-id="8314f-174">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8314f-175">Se si fornisce un valore per una colonna Identity in un parametro con valori di tabella, è necessario eseguire l'istruzione SET IDENTITY_INSERT per la sessione.</span><span class="sxs-lookup"><span data-stu-id="8314f-175">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
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
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="8314f-176">Trasmissione di flussi di righe con un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="8314f-176">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="8314f-177">È anche possibile usare qualsiasi oggetto derivato da <xref:System.Data.Common.DbDataReader> per trasmettere righe di dati a un parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-177">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="8314f-178">Nel frammento di codice seguente viene illustrato il recupero di dati da un database Oracle tramite un <xref:System.Data.OracleClient.OracleCommand> e un <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="8314f-178">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="8314f-179">Il codice configura quindi un <xref:System.Data.SqlClient.SqlCommand> per richiamare una stored procedure con un singolo parametro di input.</span><span class="sxs-lookup"><span data-stu-id="8314f-179">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="8314f-180">La proprietà <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> del <xref:System.Data.SqlClient.SqlParameter> è impostata su `Structured`.</span><span class="sxs-lookup"><span data-stu-id="8314f-180">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="8314f-181"><xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> trasferisce il set di risultati `OracleDataReader` alla stored procedure come parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8314f-181">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8314f-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8314f-182">See also</span></span>

- [<span data-ttu-id="8314f-183">Configurazione di parametri e tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="8314f-183">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="8314f-184">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="8314f-184">Commands and Parameters</span></span>](../commands-and-parameters.md)
- [<span data-ttu-id="8314f-185">Parametri DataAdapter</span><span class="sxs-lookup"><span data-stu-id="8314f-185">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- [<span data-ttu-id="8314f-186">SQL Server operazioni sui dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8314f-186">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="8314f-187">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8314f-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
