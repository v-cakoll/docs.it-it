---
title: Parametri
ms.date: 12/13/2019
description: Informazioni su come usare i parametri SQL.
ms.openlocfilehash: b24610a5cb65e2b24171452acef9bf55b4995431
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768950"
---
# <a name="parameters"></a>Parametri

I parametri vengono usati per la protezione da attacchi SQL injection. Anziché concatenare l'input dell'utente con istruzioni SQL, usare i parametri per garantire che l'input venga trattato solo come valore letterale e mai eseguito. In SQLite i parametri sono in genere consentiti ovunque sia consentito un valore letterale nelle istruzioni SQL.

Il prefisso dei parametri può essere `:` , `@` o `$` .

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Per informazioni dettagliate su come viene eseguito il mapping dei valori .NET ai valori SQLite, vedere [tipi di dati](types.md) .

## <a name="truncation"></a>Troncamento

Utilizzare la <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> proprietà per troncare i valori di testo e BLOB.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Size = 30;
```

## <a name="alternative-types"></a>Tipi alternativi

In alcuni casi può essere utile usare un tipo SQLite alternativo. A tale scopo, impostare la <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> Proprietà.

È possibile utilizzare i mapping di tipi alternativi seguenti. Per i mapping predefiniti, vedere [tipi di dati](types.md).

| Valore          | SqliteType | Osservazioni          |
| -------------- | ---------- | ---------------- |
| Char           | Integer    | UTF-16           |
| Datetime       | Real       | Valore di Julian Day |
| DateTimeOffset | Real       | Valore di Julian Day |
| Guid           | BLOB       |                  |
| TimeSpan       | Real       | In giorni          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Parametri di output

SQLite non supporta i parametri di output. Restituire invece i valori nei risultati della query.

## <a name="see-also"></a>Vedere anche

* [Tipi di dati](types.md)
