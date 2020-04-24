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
# <a name="metadata"></a>Metadati

Sono disponibili due API per il recupero dei metadati in ADO.NET. Uno Recupera i metadati relativi ai risultati della query. L'altro recupera i metadati relativi allo schema del database.

## <a name="query-result-metadata"></a>Metadati risultati query

È possibile recuperare i metadati relativi ai risultati di una query usando <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> il metodo `SqliteDataReader`in. L'oggetto <xref:System.Data.DataTable> restituito contiene le colonne seguenti:

| Colonna             | Type    | Description                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Boolean | True se la colonna di origine può essere NULL.                                    |
| `BaseCatalogName`  | string  | Nome del database della colonna di origine. Sempre NULL per le espressioni.    |
| `BaseColumnName`   | string  | Nome senza alias della colonna di origine. Sempre NULL per le espressioni.    |
| `BaseSchemaName`   | string  | Sempre NULL. SQLite non supporta gli schemi.                              |
| `BaseServerName`   | string  | Percorso del file di database specificato nella stringa di connessione.         |
| `BaseTableName`    | string  | Nome della tabella della colonna di origine. Sempre NULL per le espressioni.       |
| `ColumnName`       | string  | Nome o alias della colonna nel set di risultati.                        |
| `ColumnOrdinal`    | Int32   | Numero ordinale della colonna nel set di risultati.                              |
| `ColumnSize`       | Int32   | Sempre-1. Questo può cambiare nelle versioni future di `Microsoft.Data.Sqlite`.   |
| `DataType`         | Type    | Tipo di dati .NET predefinito della colonna.                                 |
| `DataTypeName`     | string  | Tipo di dati SQLite della colonna.                                       |
| `IsAliased`        | Boolean | True se il nome della colonna è associato a un alias nel set di risultati.                     |
| `IsAutoIncrement`  | Boolean | True se la colonna Origin è stata creata con la parola chiave AutoIncrement.     |
| `IsExpression`     | Boolean | True se la colonna ha origine da un'espressione nella query.            |
| `IsKey`            | Boolean | True se la colonna di origine fa parte della chiave primaria.                     |
| `IsUnique`         | Boolean | True se la colonna di origine è UNIVOCa.                                      |
| `NumericPrecision` | Int16   | Sempre NULL. Questo può cambiare nelle versioni future di `Microsoft.Data.Sqlite`. |
| `NumericScale`     | Int16   | Sempre NULL. Questo può cambiare nelle versioni future di `Microsoft.Data.Sqlite`. |

Nell'esempio seguente viene illustrato come utilizzare `GetSchemaTable` per creare una stringa di debug che mostra i metadati relativi a un risultato:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

Questa query, ad esempio, produrrebbe la stringa di debug seguente:

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

## <a name="schema-metadata"></a>Metadati dello schema

Microsoft. Data. SQLite non implementa il metodo GetSchema su DbConnection. In alternativa, è possibile eseguire una query direttamente sulle informazioni dello schema usando le istruzioni [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Table e pragma, ad esempio [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) e [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).

Questa query, ad esempio, recupererà i metadati relativi a tutte le colonne del database.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>Vedi anche

* [Archiviazione dello schema del database SQL](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [Istruzioni PRAGMA](https://www.sqlite.org/pragma.html)
* [Tipi di dati](types.md)
