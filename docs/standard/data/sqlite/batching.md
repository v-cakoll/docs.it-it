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
# <a name="batching"></a><span data-ttu-id="73a15-103">Batch</span><span class="sxs-lookup"><span data-stu-id="73a15-103">Batching</span></span>

<span data-ttu-id="73a15-104">SQLite non supporta in modo nativo l'invio in batch di istruzioni SQL in un unico comando.</span><span class="sxs-lookup"><span data-stu-id="73a15-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="73a15-105">Tuttavia, poiché non è presente alcuna rete, non sarebbe in realtà utile per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="73a15-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="73a15-106">Microsoft. Data. SQLite, tuttavia, implementa la suddivisione in batch delle istruzioni per facilitare il comportamento in modo più simile ad altri provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="73a15-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="73a15-107">Quando si <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>chiama, le istruzioni vengono eseguite fino alla prima che restituisce i risultati.</span><span class="sxs-lookup"><span data-stu-id="73a15-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="73a15-108">La <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> chiamata continua a eseguire le istruzioni fino a quella successiva che restituisce i risultati o fino a quando non raggiunge la fine del batch.</span><span class="sxs-lookup"><span data-stu-id="73a15-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="73a15-109">Chiama <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> o <xref:System.Data.Common.DbDataReader.Close%2A> esegue tutte le istruzioni rimanenti che non sono state `NextResult()`utilizzate da.</span><span class="sxs-lookup"><span data-stu-id="73a15-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="73a15-110">Se non si elimina un lettore dati, il finalizzatore tenta di eseguire le istruzioni rimanenti, ma gli eventuali errori incontrati vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="73a15-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="73a15-111">Per questo motivo, è importante eliminare `DbDataReader` gli oggetti quando si usano i batch.</span><span class="sxs-lookup"><span data-stu-id="73a15-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="73a15-112">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="73a15-112">See also</span></span>

* [<span data-ttu-id="73a15-113">Inserimento bulk</span><span class="sxs-lookup"><span data-stu-id="73a15-113">Bulk Insert</span></span>](bulk-insert.md)
