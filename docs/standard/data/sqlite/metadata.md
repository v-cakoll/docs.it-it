---
title: Metadati
ms.date: 12/13/2019
description: Informazioni su come recuperare i metadati relativi al database.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447195"
---
# <a name="metadata"></a><span data-ttu-id="c053e-103">Metadati</span><span class="sxs-lookup"><span data-stu-id="c053e-103">Metadata</span></span>

<span data-ttu-id="c053e-104">Sono disponibili due API per il recupero dei metadati in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c053e-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="c053e-105">Uno Recupera i metadati relativi ai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="c053e-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="c053e-106">L'altro recupera i metadati relativi allo schema del database.</span><span class="sxs-lookup"><span data-stu-id="c053e-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="c053e-107">Metadati risultati query</span><span class="sxs-lookup"><span data-stu-id="c053e-107">Query result metadata</span></span>

<span data-ttu-id="c053e-108">È possibile recuperare i metadati relativi ai risultati di una query usando il metodo <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> su `SqliteDataReader`.</span><span class="sxs-lookup"><span data-stu-id="c053e-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="c053e-109">Il <xref:System.Data.DataTable> restituito contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="c053e-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="c053e-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="c053e-110">Column</span></span>             | <span data-ttu-id="c053e-111">Tipo di</span><span class="sxs-lookup"><span data-stu-id="c053e-111">Type</span></span>    | <span data-ttu-id="c053e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c053e-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="c053e-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="c053e-113">Boolean</span></span> | <span data-ttu-id="c053e-114">True se la colonna di origine può essere NULL.</span><span class="sxs-lookup"><span data-stu-id="c053e-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="c053e-115">Stringa</span><span class="sxs-lookup"><span data-stu-id="c053e-115">String</span></span>  | <span data-ttu-id="c053e-116">Nome del database della colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="c053e-116">The name of the origin column's database.</span></span> <span data-ttu-id="c053e-117">Sempre NULL per le espressioni.</span><span class="sxs-lookup"><span data-stu-id="c053e-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="c053e-118">Stringa</span><span class="sxs-lookup"><span data-stu-id="c053e-118">String</span></span>  | <span data-ttu-id="c053e-119">Nome senza alias della colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="c053e-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="c053e-120">Sempre NULL per le espressioni.</span><span class="sxs-lookup"><span data-stu-id="c053e-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="c053e-121">Stringa</span><span class="sxs-lookup"><span data-stu-id="c053e-121">String</span></span>  | <span data-ttu-id="c053e-122">Sempre NULL.</span><span class="sxs-lookup"><span data-stu-id="c053e-122">Always NULL.</span></span> <span data-ttu-id="c053e-123">SQLite non supporta gli schemi.</span><span class="sxs-lookup"><span data-stu-id="c053e-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="c053e-124">Stringa</span><span class="sxs-lookup"><span data-stu-id="c053e-124">String</span></span>  | <span data-ttu-id="c053e-125">Percorso del file di database specificato nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="c053e-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="c053e-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="c053e-126">String</span></span>  | <span data-ttu-id="c053e-127">Nome della tabella della colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="c053e-127">The name of the origin column's table.</span></span> <span data-ttu-id="c053e-128">Sempre NULL per le espressioni.</span><span class="sxs-lookup"><span data-stu-id="c053e-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="c053e-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="c053e-129">String</span></span>  | <span data-ttu-id="c053e-130">Nome o alias della colonna nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="c053e-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="c053e-131">Int32</span><span class="sxs-lookup"><span data-stu-id="c053e-131">Int32</span></span>   | <span data-ttu-id="c053e-132">Numero ordinale della colonna nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="c053e-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="c053e-133">Int32</span><span class="sxs-lookup"><span data-stu-id="c053e-133">Int32</span></span>   | <span data-ttu-id="c053e-134">Sempre-1.</span><span class="sxs-lookup"><span data-stu-id="c053e-134">Always -1.</span></span> <span data-ttu-id="c053e-135">Questo può cambiare nelle versioni future di `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="c053e-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="c053e-136">Tipo di</span><span class="sxs-lookup"><span data-stu-id="c053e-136">Type</span></span>    | <span data-ttu-id="c053e-137">Tipo di dati .NET predefinito della colonna.</span><span class="sxs-lookup"><span data-stu-id="c053e-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="c053e-138">Stringa</span><span class="sxs-lookup"><span data-stu-id="c053e-138">String</span></span>  | <span data-ttu-id="c053e-139">Tipo di dati SQLite della colonna.</span><span class="sxs-lookup"><span data-stu-id="c053e-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="c053e-140">Boolean</span><span class="sxs-lookup"><span data-stu-id="c053e-140">Boolean</span></span> | <span data-ttu-id="c053e-141">True se il nome della colonna è associato a un alias nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="c053e-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="c053e-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="c053e-142">Boolean</span></span> | <span data-ttu-id="c053e-143">True se la colonna Origin è stata creata con la parola chiave AutoIncrement.</span><span class="sxs-lookup"><span data-stu-id="c053e-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="c053e-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="c053e-144">Boolean</span></span> | <span data-ttu-id="c053e-145">True se la colonna ha origine da un'espressione nella query.</span><span class="sxs-lookup"><span data-stu-id="c053e-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="c053e-146">Boolean</span><span class="sxs-lookup"><span data-stu-id="c053e-146">Boolean</span></span> | <span data-ttu-id="c053e-147">True se la colonna di origine fa parte della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="c053e-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="c053e-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="c053e-148">Boolean</span></span> | <span data-ttu-id="c053e-149">True se la colonna di origine è UNIVOCa.</span><span class="sxs-lookup"><span data-stu-id="c053e-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="c053e-150">Int16</span><span class="sxs-lookup"><span data-stu-id="c053e-150">Int16</span></span>   | <span data-ttu-id="c053e-151">Sempre NULL.</span><span class="sxs-lookup"><span data-stu-id="c053e-151">Always NULL.</span></span> <span data-ttu-id="c053e-152">Questo può cambiare nelle versioni future di `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="c053e-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="c053e-153">Int16</span><span class="sxs-lookup"><span data-stu-id="c053e-153">Int16</span></span>   | <span data-ttu-id="c053e-154">Sempre NULL.</span><span class="sxs-lookup"><span data-stu-id="c053e-154">Always NULL.</span></span> <span data-ttu-id="c053e-155">Questo può cambiare nelle versioni future di `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="c053e-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="c053e-156">Nell'esempio seguente viene illustrato come utilizzare `GetSchemaTable` per creare una stringa di debug che mostra i metadati relativi a un risultato:</span><span class="sxs-lookup"><span data-stu-id="c053e-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="c053e-157">Questa query, ad esempio, produrrebbe la stringa di debug seguente:</span><span class="sxs-lookup"><span data-stu-id="c053e-157">For example, this query would produce the following debug string:</span></span>

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a><span data-ttu-id="c053e-158">Metadati dello schema</span><span class="sxs-lookup"><span data-stu-id="c053e-158">Schema metadata</span></span>

<span data-ttu-id="c053e-159">Microsoft. Data. SQLite non implementa il metodo GetSchema su DbConnection.</span><span class="sxs-lookup"><span data-stu-id="c053e-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="c053e-160">In alternativa, è possibile eseguire una query direttamente sulle informazioni dello schema usando le istruzioni [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Table e pragma, ad esempio [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) e [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span><span class="sxs-lookup"><span data-stu-id="c053e-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="c053e-161">Questa query, ad esempio, recupererà i metadati relativi a tutte le colonne del database.</span><span class="sxs-lookup"><span data-stu-id="c053e-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="c053e-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c053e-162">See also</span></span>

* [<span data-ttu-id="c053e-163">Archiviazione dello schema del database SQL</span><span class="sxs-lookup"><span data-stu-id="c053e-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="c053e-164">Istruzioni PRAGMA</span><span class="sxs-lookup"><span data-stu-id="c053e-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="c053e-165">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c053e-165">Data types</span></span>](types.md)
