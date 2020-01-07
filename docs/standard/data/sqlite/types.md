---
title: Tipi di dati
ms.date: 12/13/2019
description: Vengono descritti i tipi di dati supportati e alcune delle relative limitazioni.
ms.openlocfilehash: ae70cb91a5a6d9cfed45a5a47dda25a70362871e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447181"
---
# <a name="data-types"></a>Tipi di dati

SQLite dispone solo di quattro tipi di dati primitivi: INTEGER, REAL, TEXT e BLOB. Le API che restituiscono valori di database come `object` restituiranno solo uno di questi quattro tipi. I tipi .NET aggiuntivi sono supportati da Microsoft. Data. SQLite, ma i valori vengono in definitiva assegnati tra questi tipi e uno dei quattro tipi primitivi.

| .NET           | SQLite  | Note                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` o `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | AAAA-MM-GG HH: mm: SS. FFFFFFF                                   |
| DateTimeOffset | TEXT    | AAAA-MM-GG HH: mm: SS. FFFFFFFzzz                                |
| Decimal        | TEXT    | formato `0.0###########################`. Il vero è la perdita di perdite. |
| Double         | REAL    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | REAL    |                                                               |
| Stringa         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d. hh: mm: SS. fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt64         | INTEGER | Overflow dei valori di grandi dimensioni                                         |

## <a name="alternative-types"></a>Tipi alternativi

Alcuni tipi .NET possono essere letti da tipi SQLite alternativi. I parametri possono inoltre essere configurati per l'utilizzo di questi tipi alternativi. Per altre informazioni, vedere [Parametri](parameters.md#alternative-types).

| .NET           | SQLite  | Note          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | REAL    | Valore di Julian Day |
| DateTimeOffset | REAL    | Valore di Julian Day |
| GUID           | BLOB    |                  |
| TimeSpan       | REAL    | In giorni          |

La query seguente, ad esempio, legge un valore TimeSpan da una colonna reale del set di risultati.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Tipi di colonna

SQLite usa un sistema di tipi dinamico in cui il tipo di un valore è associato al valore stesso e non alla colonna in cui è archiviato. È possibile usare il nome del tipo di colonna desiderato. Microsoft. Data. SQLite non applica alcuna semantica aggiuntiva a questi nomi.

Il nome del tipo di colonna ha un effetto sull' [affinità del tipo](https://www.sqlite.org/datatype3.html#type_affinity). Un problema comune è che l'uso di un tipo di colonna di stringa tenterà di convertire i valori in INTEGER o REAL, il che può causare risultati imprevisti. È consigliabile usare solo i quattro nomi di tipi SQLite primitivi: INTEGER, REAL, TEXT e BLOB.

SQLite consente di specificare i facet di tipo, ad esempio lunghezza, precisione e scala, ma non vengono applicati dal motore di database. L'applicazione è responsabile dell'applicazione di questi.

## <a name="see-also"></a>Vedere anche

- [Tipi di DataType in SQLite](https://www.sqlite.org/datatype3.html)
