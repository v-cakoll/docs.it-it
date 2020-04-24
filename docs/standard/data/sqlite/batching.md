---
title: Batch
ms.date: 12/13/2019
description: Informazioni su come eseguire un batch di istruzioni SQL in un unico comando.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447055"
---
# <a name="batching"></a>Batch

SQLite non supporta in modo nativo l'invio in batch di istruzioni SQL in un unico comando. Tuttavia, poiché non è presente alcuna rete, non sarebbe in realtà utile per le prestazioni. Microsoft. Data. SQLite, tuttavia, implementa la suddivisione in batch delle istruzioni per facilitare il comportamento in modo più simile ad altri provider ADO.NET.

Quando si <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>chiama, le istruzioni vengono eseguite fino alla prima che restituisce i risultati. La <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> chiamata continua a eseguire le istruzioni fino a quella successiva che restituisce i risultati o fino a quando non raggiunge la fine del batch. Chiama <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> o <xref:System.Data.Common.DbDataReader.Close%2A> esegue tutte le istruzioni rimanenti che non sono state `NextResult()`utilizzate da. Se non si elimina un lettore dati, il finalizzatore tenta di eseguire le istruzioni rimanenti, ma gli eventuali errori incontrati vengono ignorati. Per questo motivo, è importante eliminare `DbDataReader` gli oggetti quando si usano i batch.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>Vedi anche

* [Inserimento bulk](bulk-insert.md)
