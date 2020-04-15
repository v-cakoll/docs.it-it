---
title: Tipi di dati
ms.date: 12/13/2019
description: Vengono descritti i tipi di dati supportati e alcune delle limitazioni che li circondano.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389047"
---
# <a name="data-types"></a>Tipi di dati

SQLite dispone solo di quattro tipi di dati primitivi: INTEGER, REAL, TEXT e BLOB. Le API che restituiscono `object` valori di database come un restituiranno solo uno di questi quattro tipi. Tipi .NET aggiuntivi sono supportati da Microsoft.Data.Sqlite, ma i valori vengono infine raggruppati tra questi tipi e uno dei quattro tipi primitivi.

| .NET           | SQLite  | Osservazioni                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` o `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| Datetime       | TEXT    | aaaa-MM-gg HH:mm:ss. FFFFFFF                                   |
| DateTimeOffset | TEXT    | aaaa-MM-gg HH:mm:ss. FFFFFFFzzz                                |
| Decimal        | TEXT    | `0.0###########################`Formato. REALE sarebbe lossy. |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| string         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh:mm:ss.fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | Overflow di valori elevati                                         |

## <a name="alternative-types"></a>Tipi alternativi

Alcuni tipi .NET possono essere letti da tipi SQLite alternativi. I parametri possono anche essere configurati per utilizzare questi tipi alternativi. Per altre informazioni, vedere [Parametri](parameters.md#alternative-types).

| .NET           | SQLite  | Osservazioni          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| Datetime       | real    | Valore del giorno giuliano |
| DateTimeOffset | real    | Valore del giorno giuliano |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | In giorni          |

Ad esempio, la query seguente legge un valore TimeSpan da una colonna REAL nel set di risultati.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Tipi di colonna

SQLite utilizza un sistema di tipi dinamici in cui il tipo di un valore è associato al valore stesso e non alla colonna in cui è archiviato. È possibile utilizzare qualsiasi nome di tipo di colonna desiderato. Microsoft.Data.Sqlite non applichererà alcuna semantica aggiuntiva a questi nomi.

Il nome del tipo di colonna ha un impatto [sull'affinità](https://www.sqlite.org/datatype3.html#type_affinity)dei tipi . Un gotcha comune è che l'utilizzo di un tipo di colonna di STRING tenterà di convertire i valori in INTEGER o REAL, il che può portare a risultati imprevisti. È consigliabile utilizzare solo i quattro nomi di tipo SQLite primitivi: INTEGER, REAL, TEXT e BLOB.

SQLite consente di specificare facet di tipo come lunghezza, precisione e scala, ma non vengono applicati dal motore di database. L'app è responsabile dell'applicazione di questi elementi.

## <a name="see-also"></a>Vedere anche

- [Tipi di dati in SQLiteDatatypes In SQLite](https://www.sqlite.org/datatype3.html)
