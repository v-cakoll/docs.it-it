---
title: Limitazioni di ADO.NET
ms.date: 12/13/2019
description: Descrive alcune delle limitazioni di ADO.NET che possono verificarsi.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901256"
---
# <a name="adonet-limitations"></a>Limitazioni di ADO.NET

Microsoft. Data. SQLite fornisce le implementazioni di molte delle astrazioni ADO.NET, ma esistono alcune limitazioni.

## <a name="database-schema-information"></a>Informazioni sullo schema del database

I metadati relativi ai risultati della query sono <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> disponibili tramite il metodo.

`DbConnection.GetSchema()`non è implementato. Questa API non è ben definita, quindi è consigliabile recuperare i metadati del database direttamente usando le API SQLite standard come la tabella [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) e il [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) pragma.

Per ulteriori informazioni, vedere [metadati](metadata.md).

## <a name="systemtransactions"></a>System.Transactions

Microsoft. Data. SQLite non supporta ancora System. Transactions. Usare invece le transazioni ADO.NET. Per altre informazioni, vedere [Transazioni](transactions.md).

Inviare commenti e suggerimenti sulla mancanza di supporto per System. Transactions sul problema [#13825](https://github.com/dotnet/efcore/issues/13825).

## <a name="data-adapters"></a>Adattatori dati

`DbDataAdapter`non è ancora implementato da Microsoft. Data. sqlite. Ciò significa che è possibile usare solo `DataSet` ADO.NET `DataTable` e caricare i dati e non aggiornarli.

Usare [#13838](https://github.com/dotnet/efcore/issues/13838) di problema per fornire commenti e `DbDataAdapter`suggerimenti sull'implementazione di.

## <a name="output-parameters"></a>Parametri di output

SQLite non supporta i parametri di output.

## <a name="positional-parameters"></a>Parametri posizionali

Microsoft. Data. SQLite supporta solo i [parametri](parameters.md)denominati. I parametri posizionali non sono supportati.

## <a name="stored-procedures"></a>Stored procedure

SQLite non supporta le stored procedure.

## <a name="isolation-levels"></a>Livelli di isolamento

I `Chaos` livelli `Snapshot` di isolamento e non sono supportati nelle transazioni SQLite.

## <a name="see-also"></a>Vedi anche

* [Limitazioni asincrone](async.md)
* [Tipi di dati](types.md)
* [Transazioni](transactions.md)
