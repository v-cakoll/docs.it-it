---
title: Modifica di dati con valori di grandi dimensioni (max)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: cb37fdb85d323d4f0816a3667a4624da8ec75e65
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979846"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="d1d65-102">Modifica di dati con valori elevati (massimi) in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d1d65-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="d1d65-103">I tipi di dati LOB (oggetti di grandi dimensioni) sono quelli che superano la dimensione massima di 8 kilobyte (KB) per le righe.</span><span class="sxs-lookup"><span data-stu-id="d1d65-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="d1d65-104">In SQL Server viene fornito un identificatore `max` per i tipi di dati `varchar`, `nvarchar` e `varbinary` per consentire l'archiviazione di valori di dimensioni pari a 2^32 byte.</span><span class="sxs-lookup"><span data-stu-id="d1d65-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="d1d65-105">Nelle colonne di tabelle e nelle variabili Transact-SQL possono essere specificati tipi di dati `varchar(max)`, `nvarchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="d1d65-106">In ADO.NET i tipi di dati `max` possono essere recuperati da un `DataReader` e possono inoltre essere specificati come parametri di input e di output senza richiedere una gestione speciale.</span><span class="sxs-lookup"><span data-stu-id="d1d65-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="d1d65-107">Per tipi di dati `varchar` di grandi dimensioni, è possibile recuperare e aggiornare i dati in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="d1d65-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="d1d65-108">I tipi di dati `max` possono essere usati per eseguire confronti, come le variabili Transact-SQL, e per eseguire concatenazioni.</span><span class="sxs-lookup"><span data-stu-id="d1d65-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="d1d65-109">È inoltre usarli nelle clausole DISTINCT, ORDER BY e GROUP BY di un'istruzione SELECT, nonché nelle aggregazioni, nelle unioni e nelle sottoquery.</span><span class="sxs-lookup"><span data-stu-id="d1d65-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="d1d65-110">La tabella seguente fornisce i collegamenti alla documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1d65-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="d1d65-111">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d1d65-111">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="d1d65-112">Utilizzo di tipi di dati con valori di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="d1d65-112">Using Large-Value Data Types</span></span>](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="d1d65-113">Restrizioni per i tipi di valori di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="d1d65-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="d1d65-114">Le seguenti restrizioni si applicano ai tipi di dati `max` e non ai tipi di dati di dimensioni minori:</span><span class="sxs-lookup"><span data-stu-id="d1d65-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="d1d65-115">Un tipo `sql_variant` non può contenere un tipo di dati `varchar` di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d1d65-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="d1d65-116">Le colonne `varchar` di grandi dimensioni non possono essere specificate come colonne di chiave primaria in un indice.</span><span class="sxs-lookup"><span data-stu-id="d1d65-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="d1d65-117">Sono consentite in una colonna inclusa in un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="d1d65-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="d1d65-118">Le colonne `varchar` di grandi dimensioni non possono essere usate come colonne chiave di partizionamento.</span><span class="sxs-lookup"><span data-stu-id="d1d65-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="d1d65-119">Uso di tipi di valori di grandi dimensioni in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1d65-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="d1d65-120">La funzione `OPENROWSET` di Transact-SQL è un metodo unico per eseguire la connessione e l'accesso ai dati remoti.</span><span class="sxs-lookup"><span data-stu-id="d1d65-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="d1d65-121">Include tutte le informazioni di connessione necessarie per l'accesso remoto ai dati da un'origine dati OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d1d65-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="d1d65-122">È possibile fare riferimento a `OPENROWSET` nella clausola FROM di una query come se fosse un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="d1d65-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="d1d65-123">È inoltre possibile farvi riferimento come tabella di destinazione di un'istruzione INSERT, UPDATE o DELETE, soggetta alle funzionalità del provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d1d65-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="d1d65-124">La funzione `OPENROWSET` include il provider di set di righe `BULK`, che consente di leggere i dati direttamente da un file senza caricare i dati in una tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d1d65-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="d1d65-125">Questo consente l'uso di `OPENROWSET` in una semplice istruzione INSERT SELECT.</span><span class="sxs-lookup"><span data-stu-id="d1d65-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="d1d65-126">Gli argomenti dell'opzione `OPENROWSET BULK` forniscono un controllo significativo sulla posizione in cui iniziare e terminare la lettura dei dati, su come gestire gli errori e su come vengono interpretati i dati.</span><span class="sxs-lookup"><span data-stu-id="d1d65-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="d1d65-127">È ad esempio possibile specificare che il file di dati venga letto come una singola riga o come un set di righe di una singola colonna di tipo `varbinary`, `varchar` o `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="d1d65-128">Per la sintassi e le opzioni complete, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1d65-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="d1d65-129">Nell'esempio seguente viene inserita una foto nella tabella ProductPhoto del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d1d65-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="d1d65-130">Quando si usa il provider di `BULK OPENROWSET`, è necessario fornire l'elenco di colonne denominato anche se non si inseriscono valori in ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="d1d65-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="d1d65-131">In questo caso, la chiave primaria è definita come colonna Identity e può essere omessa dall'elenco di colonne.</span><span class="sxs-lookup"><span data-stu-id="d1d65-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="d1d65-132">Notare che è necessario fornire anche un nome di correlazione alla fine dell'istruzione `OPENROWSET`, che in questo caso è ThumbnailPhoto.</span><span class="sxs-lookup"><span data-stu-id="d1d65-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="d1d65-133">Tale nome è correlato alla colonna della tabella `ProductPhoto` in cui viene caricato il file.</span><span class="sxs-lookup"><span data-stu-id="d1d65-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,   
    ThumbnailPhotoFilePath,   
    LargePhoto,   
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET   
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="d1d65-134">Aggiornamento di dati tramite UPDATE .WRITE</span><span class="sxs-lookup"><span data-stu-id="d1d65-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="d1d65-135">L'istruzione Transact-SQL UPDATE include una nuova sintassi WRITE per modificare il contenuto delle colonne `varchar(max)`, `nvarchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="d1d65-136">In tal modo è possibile eseguire aggiornamenti parziali dei dati.</span><span class="sxs-lookup"><span data-stu-id="d1d65-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="d1d65-137">La sintassi UPDATE .WRITE viene illustrata di seguito in formato abbreviato:</span><span class="sxs-lookup"><span data-stu-id="d1d65-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="d1d65-138">AGGIORNAMENTO</span><span class="sxs-lookup"><span data-stu-id="d1d65-138">UPDATE</span></span>  
  
 <span data-ttu-id="d1d65-139">{ *\<object>* }</span><span class="sxs-lookup"><span data-stu-id="d1d65-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="d1d65-140">SET</span><span class="sxs-lookup"><span data-stu-id="d1d65-140">SET</span></span>  
  
 <span data-ttu-id="d1d65-141">{ *column_name* = {. WRITE ( *espressione* , @Offset, @Length)}</span><span class="sxs-lookup"><span data-stu-id="d1d65-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="d1d65-142">Il metodo WRITE specifica che una sezione del valore del *column_name* verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="d1d65-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="d1d65-143">L'espressione è il valore che verrà copiato nel *column_name*, il `@Offset` è il punto iniziale in cui verrà scritta l'espressione e l'argomento `@Length` è la lunghezza della sezione nella colonna.</span><span class="sxs-lookup"><span data-stu-id="d1d65-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="d1d65-144">\* Se</span><span class="sxs-lookup"><span data-stu-id="d1d65-144">If</span></span>|<span data-ttu-id="d1d65-145">Quindi</span><span class="sxs-lookup"><span data-stu-id="d1d65-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="d1d65-146">L'espressione è impostata su NULL.</span><span class="sxs-lookup"><span data-stu-id="d1d65-146">The expression is set to NULL</span></span>|<span data-ttu-id="d1d65-147">`@Length` viene ignorato e il valore in *column_name* viene troncato in corrispondenza del `@Offset`specificato.</span><span class="sxs-lookup"><span data-stu-id="d1d65-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="d1d65-148">Il valore di `@Offset` è NULL.</span><span class="sxs-lookup"><span data-stu-id="d1d65-148">`@Offset` is NULL</span></span>|<span data-ttu-id="d1d65-149">L'operazione di aggiornamento aggiunge l'espressione alla fine del valore di *column_name* esistente e `@Length` viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="d1d65-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="d1d65-150">Il valore di `@Offset` è maggiore della lunghezza del valore di column_name.</span><span class="sxs-lookup"><span data-stu-id="d1d65-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="d1d65-151">SQL Server restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="d1d65-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="d1d65-152">Il valore di `@Length` è NULL.</span><span class="sxs-lookup"><span data-stu-id="d1d65-152">`@Length` is NULL</span></span>|<span data-ttu-id="d1d65-153">L'operazione di aggiornamento rimuove tutti i dati a partire da `@Offset` alla fine del valore di `column_name`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d1d65-154">Il valore di `@Offset` o di `@Length` non può essere un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="d1d65-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1d65-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1d65-155">Example</span></span>  
 <span data-ttu-id="d1d65-156">In questo esempio di Transact-SQL viene aggiornato un valore parziale di DocumentSummary, una colonna `nvarchar(max)` della tabella Document nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d1d65-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="d1d65-157">La parola "components" viene sostituita con la parola "features" specificando la parola di sostituzione, la posizione iniziale (offset) della parola da sostituire nei dati esistenti e il numero di caratteri da sostituire (lunghezza).</span><span class="sxs-lookup"><span data-stu-id="d1d65-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="d1d65-158">Per confrontare i risultati, nell'esempio sono incluse le istruzioni SELECT precedenti e successive all'istruzione UPDATE.</span><span class="sxs-lookup"><span data-stu-id="d1d65-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO   
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="d1d65-159">Uso di tipi di valori di grandi dimensioni in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d1d65-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="d1d65-160">È possibile utilizzare tipi di valore di grandi dimensioni in ADO.NET specificando tipi di valore di grandi dimensioni come <xref:System.Data.SqlClient.SqlParameter> oggetti in una <xref:System.Data.SqlClient.SqlDataReader> per restituire un set di risultati o utilizzando un <xref:System.Data.SqlClient.SqlDataAdapter> per riempire un /`DataSet``DataTable`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="d1d65-161">Non vi è differenza tra il modo di usare un tipo di valore di grandi dimensioni e il relativo tipo di dati del valore di dimensioni minori.</span><span class="sxs-lookup"><span data-stu-id="d1d65-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="d1d65-162">Uso di GetSqlBytes per il recupero di dati</span><span class="sxs-lookup"><span data-stu-id="d1d65-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="d1d65-163">È possibile usare il metodo `GetSqlBytes` del tipo <xref:System.Data.SqlClient.SqlDataReader> per recuperare il contenuto di una colonna `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="d1d65-164">Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlCommand> denominato `cmd` che consente di selezionare dati `varbinary(max)` da una tabella e un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati come tipo <xref:System.Data.SqlTypes.SqlBytes>.</span><span class="sxs-lookup"><span data-stu-id="d1d65-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="d1d65-165">Uso di GetSqlChars per il recupero di dati</span><span class="sxs-lookup"><span data-stu-id="d1d65-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="d1d65-166">È possibile usare il metodo `GetSqlChars` del tipo <xref:System.Data.SqlClient.SqlDataReader> per recuperare il contenuto di una colonna `varchar(max)` o `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="d1d65-167">Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlCommand> denominato `cmd` che consente di selezionare dati `nvarchar(max)` da una tabella e un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1d65-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="d1d65-168">Uso di GetSqlBinary per il recupero di dati</span><span class="sxs-lookup"><span data-stu-id="d1d65-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="d1d65-169">È possibile usare il metodo `GetSqlBinary` di un tipo <xref:System.Data.SqlClient.SqlDataReader> per recuperare il contenuto di una colonna `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="d1d65-170">Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlCommand> denominato `cmd` che consente di selezionare dati `varbinary(max)` da una tabella e un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati come flusso <xref:System.Data.SqlTypes.SqlBinary>.</span><span class="sxs-lookup"><span data-stu-id="d1d65-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="d1d65-171">Uso di GetBytes per il recupero di dati</span><span class="sxs-lookup"><span data-stu-id="d1d65-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="d1d65-172">Il metodo `GetBytes` di un tipo <xref:System.Data.SqlClient.SqlDataReader> consente di leggere un flusso di byte dall'offset della colonna specificata nella matrice di byte a partire dall'offset della matrice specificata.</span><span class="sxs-lookup"><span data-stu-id="d1d65-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="d1d65-173">Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare byte in una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="d1d65-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="d1d65-174">Notare che, a differenza di `GetSqlBytes`, con `GetBytes` è necessario specificare una dimensione per il buffer della matrice.</span><span class="sxs-lookup"><span data-stu-id="d1d65-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="d1d65-175">Uso di GetValue per il recupero di dati</span><span class="sxs-lookup"><span data-stu-id="d1d65-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="d1d65-176">Il metodo `GetValue` di un tipo <xref:System.Data.SqlClient.SqlDataReader> consente di leggere il valore dall'offset della colonna specificata in una matrice.</span><span class="sxs-lookup"><span data-stu-id="d1d65-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="d1d65-177">Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare dati binari dall'offset della prima colonna e dati di tipo stringa dall'offset della seconda colonna.</span><span class="sxs-lookup"><span data-stu-id="d1d65-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="d1d65-178">Conversione da tipi di valore di grandi dimensioni a tipi CLR</span><span class="sxs-lookup"><span data-stu-id="d1d65-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="d1d65-179">È possibile convertire il contenuto di una colonna `varchar(max)` o `nvarchar(max)` usando uno dei metodi disponibili per la conversione di stringhe, ad esempio `ToString`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="d1d65-180">Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1d65-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a><span data-ttu-id="d1d65-181">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1d65-181">Example</span></span>  
 <span data-ttu-id="d1d65-182">Il codice seguente consente di recuperare il nome e l'oggetto `LargePhoto` dalla tabella `ProductPhoto` del database `AdventureWorks` e di salvarlo in un file.</span><span class="sxs-lookup"><span data-stu-id="d1d65-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="d1d65-183">È necessario compilare l'assembly con un riferimento allo spazio dei nomi <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="d1d65-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="d1d65-184">Il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> del tipo <xref:System.Data.SqlClient.SqlDataReader> restituisce un oggetto <xref:System.Data.SqlTypes.SqlBytes> che espone una proprietà `Stream`.</span><span class="sxs-lookup"><span data-stu-id="d1d65-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="d1d65-185">Il codice lo usa per creare un nuovo oggetto `Bitmap`, quindi lo salva nel `ImageFormat`gif.</span><span class="sxs-lookup"><span data-stu-id="d1d65-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="d1d65-186">Utilizzo dei parametri di tipi di valore di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="d1d65-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="d1d65-187">I tipi di valore di grandi dimensioni possono essere usati negli oggetti <xref:System.Data.SqlClient.SqlParameter> nello stesso modo in cui si usano tipi di valore di dimensioni minori in oggetti <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="d1d65-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="d1d65-188">È possibile recuperare i tipi di valore di grandi dimensioni come <xref:System.Data.SqlClient.SqlParameter> valori, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d1d65-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="d1d65-189">Il codice presuppone l'esistenza della seguente stored procedure GetDocumentSummary nel database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d1d65-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="d1d65-190">Il stored procedure accetta un parametro di input denominato @DocumentID e restituisce il contenuto della colonna DocumentSummary nel parametro @DocumentSummary output.</span><span class="sxs-lookup"><span data-stu-id="d1d65-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
```sql
CREATE PROCEDURE GetDocumentSummary   
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a><span data-ttu-id="d1d65-191">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1d65-191">Example</span></span>  
 <span data-ttu-id="d1d65-192">Il codice di ADO.NET crea oggetti <xref:System.Data.SqlClient.SqlConnection> e <xref:System.Data.SqlClient.SqlCommand> per eseguire la stored procedure GetDocumentSummary e recuperare le informazioni di riepilogo del documento archiviate come tipo di valore di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d1d65-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="d1d65-193">Il codice passa un valore per il parametro di input @DocumentID e Visualizza i risultati restituiti nel parametro di output @DocumentSummary nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d1d65-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d1d65-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1d65-194">See also</span></span>

- [<span data-ttu-id="d1d65-195">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1d65-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="d1d65-196">Mapping dei tipi di dati SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1d65-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="d1d65-197">Operazioni sui dati SQL Server in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d1d65-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="d1d65-198">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d1d65-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
