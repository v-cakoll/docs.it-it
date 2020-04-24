---
title: Tipi di dati
ms.date: 12/13/2019
description: Vengono descritti i tipi di dati supportati e alcune delle relative limitazioni.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389047"
---
# <a name="data-types"></a>Tipi di dati

SQLite dispone solo di quattro tipi di dati primitivi: INTEGER, REAL, TEXT e BLOB. Le API che restituiscono i valori `object` del database come restituiranno sempre uno di questi quattro tipi. I tipi .NET aggiuntivi sono supportati da Microsoft. Data. SQLite, ma i valori vengono in definitiva assegnati tra questi tipi e uno dei quattro tipi primitivi.

| .NET           | SQLite  | Osservazioni                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` o `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| Datetime       | TEXT    | AAAA-MM-GG HH: mm: SS. FFFFFFF                                   |
| DateTimeOffset | TEXT    | AAAA-MM-GG HH: mm: SS. FFFFFFFzzz                                |
| Decimal        | TEXT    | `0.0###########################`formato. Il vero è la perdita di perdite. |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| string         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d. hh: mm: SS. fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | Overflow dei valori di grandi dimensioni                                         |

## <a name="alternative-types"></a>Tipi alternativi

Alcuni tipi .NET possono essere letti da tipi SQLite alternativi. I parametri possono inoltre essere configurati per l'utilizzo di questi tipi alternativi. Per altre informazioni, vedere [Parametri](parameters.md#alternative-types).

| .NET           | SQLite  | Osservazioni          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| Datetime       | real    | Valore di Julian Day |
| DateTimeOffset | real    | Valore di Julian Day |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | In giorni          |

La query seguente, ad esempio, legge un valore TimeSpan da una colonna reale del set di risultati.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Tipi di colonna

SQLite usa un sistema di tipi dinamico in cui il tipo di un valore è associato al valore stesso e non alla colonna in cui è archiviato. È possibile usare il nome del tipo di colonna desiderato. Microsoft. Data. SQLite non applica alcuna semantica aggiuntiva a questi nomi.

Il nome del tipo di colonna ha un effetto sull' [affinità del tipo](https://www.sqlite.org/datatype3.html#type_affinity). Un problema comune è che l'uso di un tipo di colonna di stringa tenterà di convertire i valori in INTEGER o REAL, il che può causare risultati imprevisti. È consigliabile usare solo i quattro nomi di tipi SQLite primitivi: INTEGER, REAL, TEXT e BLOB.

SQLite consente di specificare i facet di tipo, ad esempio lunghezza, precisione e scala, ma non vengono applicati dal motore di database. L'applicazione è responsabile dell'applicazione di questi.

## <a name="see-also"></a>Vedi anche

- [Tipi di DataType in SQLite](https://www.sqlite.org/datatype3.html)
