---
title: Parametri
ms.date: 12/13/2019
description: Informazioni su come usare i parametri SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400456"
---
# <a name="parameters"></a>Parametri

I parametri vengono utilizzati per la protezione da attacchi SQL injection. Anziché concatenare l'input dell'utente con istruzioni SQL, usare i parametri per garantire che l'input venga considerato solo come valore letterale e non venga mai eseguito. In SQLite, i parametri sono in genere consentiti ovunque sia consentito un valore letterale nelle istruzioni SQL.

I parametri possono essere `:` `@`preceduti `$`dal prefisso , , o .

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Vedere [tipi di dati](types.md) per informazioni dettagliate su come i valori .NET vengono mappati ai valori SQLite.See Data types for details about how .NET values are mapped to SQLite values.

## <a name="truncation"></a>Troncamento

Utilizzare <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> la proprietà per troncare i valori TEXT e BLOB.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Tipi alternativi

A volte, è possibile utilizzare un tipo SQLite alternativo. A tale scopo, impostare la <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> proprietà.

È possibile utilizzare i seguenti mapping di tipi alternativi. Per i mapping predefiniti, vedere [Tipi di dati](types.md).

| valore          | SqliteType (TipoSqliteType) | Osservazioni          |
| -------------- | ---------- | ---------------- |
| Char           | Integer    | UTF-16           |
| Datetime       | Real       | Valore del giorno giuliano |
| DateTimeOffset | Real       | Valore del giorno giuliano |
| Guid           | BLOB       |                  |
| TimeSpan       | Real       | In giorni          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Parametri di output

SQLite non supporta i parametri di output. Restituisce invece i valori nei risultati della query.

## <a name="see-also"></a>Vedere anche

* [Tipi di dati](types.md)
